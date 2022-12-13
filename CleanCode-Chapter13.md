# Chapter 13 - Concurrency

## Why Concurrency?

Concurrency is a decoupling strategy. It helps us decouple what gets done from when it gets done.

Decoupling what from when can dramatically improve both the throughput and structures of an application.

But structure is not the only motive for adopting concurrency. Some systems have response time and throughput constraints that require hand-coded concurrent solutions.

## Myths and Misconceptions

- Concurrency always improves performance.

Concurrency can sometimes improve performance, but only when there is a lot of wait time that can be shared between multiple threads or multiple processors.

- Design does not change when writing concurrent programs.

In fact, the design of a concurrent algorithm can be remarkably different from the design of a single-threaded system. The decoupling of what from when usually has a huge effect on the structure of the system.

- Understanding concurrency issues is not important when working with a container such as a Web or EJB containers.

In fact, you’d better know just what your container is doing and how to guard against the issues of concurrent update and deadlock described later in this chapter.

- Concurrency incurs some overhead, both in performance as well as writing additional code.
- Correct concurrency is complex, even for simple problems.
- Concurrency bug aren’t usually repeatable, so they are often ignored as one-offs instead of the true defects they are.
- Concurrency often requires a fundamental change in design strategy.

## Concurrency Defense Principles

### Single Responsibility Principle
Unfortunately, it is all too common for concurrency implementation details to be embedded directly into other production code. Here are a few things to consider:

- Concurrency-related code has its own life cycle of development, change, and tuning.
- Concurrency-related code has its own challenges, which are different from and often more difficult than nonconcurrency-related code.
- The number of ways in which miswritten concurrency-based code can fail makes it challenging enough without the added burden of surrounding application code.

**Recommendation:** Keep your ocncurrency-related code separate from other code.

## Corollary: Limit the Scope of Data
The more places shared data can get updated, the more likely:

- You will gorget to protect one or more of those places — effectively breaking all code that modifies that shared data.
- There will be duplication of effort required to make sure everything is effectively guarded(violation of DRY)
- It will be difficult to determine the source of failures, which are already hard enough to find.

**Recommendation:** Take data encapsulation to heart; severely limit the access of any data that may be shared.

## Corollary: Use Copies of Data
A good way to avoid shared data is to avoid sharing the data in the first place. In some situations it is possible to copy objects and treat them as read-only. In other cases it might be possible to copy objects, collect results from multiple threads in these copies and then merge the results in a single thread.

If there is an easy way to avoid sharing objects, the resulting code will be far less likely to cause problem. However, if using coppies of objects allows the code to avoid synchronizing, the savings in avoiding the intrinsic lock will likely make up for the additional creation and garbage collection overhead.

## Corollary: Threads Should Be as Independent as Possible
Consider writing your threaded code such that each thread exists in its own world, sharing no data with any other thread. each thread processes one client request, with all of its required data coming from an unshared source and stored as local variables. This makes each of those threads behave as if it were the only thread in the world and there were no synchronization requirements.

**Recommendation:** Attempt to partition data into independent subsets that can be operated on by independent threads, possibly in different processors.

## Know Your Library

### Thread-Safe Collections

**Recommendation:** Review the classes available to you and become familiar with them.

### Know Your Execution Models

<table>
  <tr>
    <th>Name</th>
    <th>Definition</th>
  </tr>
  <tr>
    <td>Bound Resources</td>
    <td>Resources of a fixed size or number used in a concurrent environment. Examples include database connections and fixed-size read/write buffers.</td>
  </tr>
  <tr>
    <td>Mutual Exclusion</td>
    <td>Only one thread can access shared data or a shared resource at a time.</td>
  </tr>
  <tr>
    <td>Starvation</td>
    <td>One thread or a group of threads is prohibited from proceeding for an excessively long time or forever. For example, always letting fast-running threads through first could starve out longer running threads if there is no end to the fast-running threads.</td>
  </tr>
  <tr>
    <td>Deadlock</td>
    <td>Two or more threads waiting for each other to finish, Each thread has a reousrce that the other thread requires and neither can finish until it gets the other resource.</td>
  </tr>
  <tr>
    <td>Livelock</td>
    <td>Threads in lockstep, each trying to do work but finding another in the way. Due to resonance, threads continue trying to make progress but are unable to for an excessively long time--or forever.</td>
  </tr>
</table>

## Producer-Consumer
One or more producer threads create some work and place it in a buffer or queue. One or more consumer threads acquire that work from the queue and complete it. The queue between the producers and consumers is a bound resource. Coordination between the producers and consumers via the queue involves producers and consumers signaling each other. Both potentially wait to be notified when they can continue.

## Readers-Writers
When you have a shared resource that primarily serves as a source of information for readers, but which is occasionally updated by writers, throughput is an issue. Emphasizing throughput can cause starvation and the accumulation of stale information.

The challenge is to balance the needs of both readers and writers to satisfy correct operation, provide reasonable throughput and avoiding starvation.

## Dining Philosophers
Replace philosophers with threads and forks with resources and this problem is similar to many enterprise applications in which processes compete for resources. Unless carefully designed, systems that compete in this way can experience deadlock, lovelock, throughput, and efficiency degradation.

**Recommendation:** Learn these basic algorithms and understand their solutions.

## Beware Dependencies Between Synchronized Methods
Dependencies between synchronized methods cause subtle bugs in concurrent code. However, if there is more than one synchronized method on the same shared class, then your system may be written incorrectly.

**Recommendation:** Avoid using more than one method on a shared object.

- **Client-Based Locking** — Have the client lock the server before calling the first method and make sure the lock’s extent includes code calling the last method.
- **Server-Based Locking** — Within the server create a method that locks the server, calls all the methods, and then unlocks. Have the client call the new method.
- **Adapted server** — create an intermediary that performs the locking. This is an example of server-based locking, where the original server cannot be changed.

## Keep Synchronized Sections Small
All sections of code guarded by the same lock are guaranteed to have only one thread executing through them at any given time. Locks are expensive because they create delays and add overhead.

**Recommendation:** Keep your synchronized sections as small as possible.

## Writing Correct Shut-Down Code Is Hard
Recommendation: Think about shut-down early and get it working early. It’s going to take longer than you expect. Review existing algorithms because this is probably harder thank you think.

## Testing Threaded Code
Testing does not guarantee correctness. However, good testing can minimize risk.

**Recommendation:** White tests that have the potential to expose problems and then run them frequently, with different programmatic configurations and system configurations and load. If tests ever fail, track down the failure. Don’t ignore a failure just because the tests pass on a subsequent run.

- Treat spurious failures as candidate threading issues.
- Get your nonthreaded code working first.
- Make your threaded code pluggable.
- Make your threaded code tunable.
- Run with more threads than processors.
- Run on different platforms.
- Insutrment your code to try and force failures.

## Treat Spurious Failures as Candidate Threading Issues
**Recommendation:** Do not ignore system failures as one-offs.

## Get Your Nonthreaded Code Working First
**Recommendation:** Don't try to chase down nonthreading bugs and threading bugs at the same time. Make sure your code works outside of threads.

## Make Your Threaded Code Pluggable
- One thread, several threads, varies as it executes.
- Threaded code interacts with something that can be both real or a test double.
- Execute with tests doubles that run quickly, slowly, variable.
- Configure tests so they can run for a number of iterations.

**Recommendation:** Make your thread-based code especially pulggable so that you can run it in various configurations.

## Make Your Threaded Code Tunable
Early on, find ways to time the performance of your system under different configurations. Allow the number of threads to be easily tuned. Consider allowing it to change while the system is running. Consider allowing self-tuning based on throughput and system utilization.

## Run with More Threads Than Processors
To encourage task swapping, run with more threads than processors or cores. The more frequently your tasks swap, the more likely you’ll encounter code that is missing a critical section or causes deadlock.

## Run on Different Platforms
This just reinforced the fact that different operating systems have different threading policies, each of which impacts the code’s execution.

**Recommendation:** Run your threaded code on all target platforms early and often.

## Instrument Your Code to Try and Force Failures
The reason that threading bugs can be infrequent, sporadic, and hard to repeat, is that only a very few pathways out of the many thousands of possible pathways through a vulnerable section actually fail.

You can instrument your code and force it to run in different orderings by adding calls to methods.

There are two options for code instrumentation:
- Hard-Coded
- Automated

## Hand-Coded
There are many problems with this approach:

- You have to manually find appropriate places to do this.
- How do you know where to put the call and what kind of call to use?
- Leaving such code in a production environment unnecessarily slows the code down.
- It’s shotgun approach. You may or may not find flaws. Indeed, the odds aren’t with you.

## Automated
You could use tools like an Aspect-Oriented Framework, CGLIB or ASM to programmatically instrument your code.

The point is to jiggle the code so the threads run in different orderings at different times, The combination of well-written tests and jiggling can dramatically increase the chance finding errors.

**Recommendation:** Use jiggling strategies to ferret out errors.

## Conclusion
First and foremost, follow the Single Responsibility Principle.

Avoid calling one locked section from another. Keep the amount of shared objects and the scope of the sharing as narrow as possible.
