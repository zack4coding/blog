
Not recommended using module 'Threading' instead of 'Thread'.
Because when module 'Thread' exit, it will kill all subthread immediately.
And module 'Threading' can wait important subthread finished its work.

GIL ( global interpreter lock) 
Interpreter Main Loop execute only one thread at same time。
And GIL control this。

But before a thread invokes an I/O job, it will release the GIL.

So multi-I/O jobs may appropriate for multithreading environment
