## Understanding How It Works
![alt text](img/ss1.png)

In this experiment, i added a println! statement immediately after calling spawner.spawn() to better observe execution order. When i ran the program, the output printed "kevins's Komputer: hey hey" first, even though it appeared after the spawn call in the code. This happens because spawn only schedules the task to run asynchronously — it does not block or wait for it to complete. Therefore, the main thread continues immediately to the next line and prints "hey hey" before the async task starts. The actual async task begins later, prints "howdy!", waits for 2 seconds using TimerFuture, and then prints "done!". This shows the asynchronous behavior of Rust futures, where tasks are scheduled and executed independently of the main thread flow.

