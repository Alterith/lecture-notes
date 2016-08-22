# Introduction to thread coordination

- Sometimes multiple threads need to cooperate with each other to
  accomplish a job; in this case, we say that we need to coordinate
  the activity of the threads.
  
- The easiest way to coordiate threads is through accessing the memory
  all the treads share -- static memory and heap.

- The exact mechanism to achieve thread coordination is not trivial.

- In the lecture, we looked at the problems of thread coordination by
  writing various versions of the program in which two threads -- a
  producer thread and a consumer thread -- need to coordinate
  according to the following protocol:
  - producer is putting lines of text into a shared buffer;
  - consumer takes lines of text out of the shared buffer;
  - each line produced by the producer has to be consumed exactly once
    by the consumer.

The code is
[here](https://github.com/WITS-COMS2001/lecture-code/tree/master/thread-coordination). Take
a look at it, compile it, and see what happens when you run it.
- In `procon1.c`, there is no coordination between the producer and the
  consumer.
- In `procon2.c`, we try to achieve some coordination by using calls
  to `shed_yield()`.
- In `procon_flag.c`, we try achieve coordination by using a flag as
  part of the shared data structure.

The question we left open for the next lecture is whether the last
solution (`procon_flag.c`) works. **Try to answer this question for
yourself before the next lecture.**
