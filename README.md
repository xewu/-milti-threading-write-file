# -milti-threading-write-file
#### (* this repo documents my own study on different ways that multiple threads write to a single json file.)

####  1. Have a thread in charge of writing. Maintain a queue, all other thread put data into this queue. Writing thread pull data outside of queue, and write into file.
####  2. Every thread write a file, Merge them together.
####  3. Lock：
```
ReadWriteLock rwlock = new ReentrantReadWriteLock();
rwlock.readLock().lock();
```
