# Async-Await-and-Actors
1 ] Async Await

2 ] Dates App - MVVM

3 ] News App


1 ] Async Await
<img width="982" alt="Screenshot 2024-09-03 at 1 56 24 PM" src="https://github.com/user-attachments/assets/c7dfadab-478e-4e9f-870f-1ed7630a1c9e">

link:- https://www.viget.com/articles/concurrency-multithreading-in-ios/
1) https://www.viget.com/articles/concurrency-multithreading-in-ios/

2) https://ali-akhtar.medium.com/concurrency-in-swift-grand-central-dispatch-part-1-945ff05e8863

3) https://www.swiftbysundell.com/articles/task-based-concurrency-in-swift/

4) https://cocoacasts.com/swift-and-cocoa-fundamentals-threads-queues-and-concurrency

GCD :
Let's talk a little bit about Grand Central Dispatch, also known as GCD.
We already learned that all the stuff that happens on our user interface is part of the main thread.
This is also known as the UI thread.
This thread is a serial queue.
That means that when the event comes in that order, it is processed.
You can also think of it as first in, first out.
The first event that comes to the queue gets processed first.
You have to make sure that your thread is nice and clean and there is no crazy downloading going on
of resources on your main thread or it will freeze the entire application as you have experienced in
the last lecture.
The other kind of cue that you can create is a global cue which can run concurrently.
Global, you can have different priority settings like user interactive.
This is a quality of service for user interactive, which means such as animations, event handling,
or updating your app's user interface.
It can also be user initiated.
This means that this kind of a quality of service for tasks prevent the user from actively using your
app.
The default is preferred, which means the quality of service class is default, which means that it's
going to take a decision on your behalf in selecting the default or whatever kind of quality of service
for the priority.
The utility quality of service or priority is for tasks that the user does not track actively.
The background is for maintenance tasks.
You if you want to do something in the background, meaning you might be updating something in the background
and clean up kind of a task.
An unspecified, which means there is no quality of service or priority setting that you have defined.
Now creating a serial queue using swift language is actually pretty straightforward.
You simply create a dispatch queue.
You provide a custom label, which in this case is serial queue.
And you execute the task using queue async.
The task that is the first one in line gets executed first.
And when that task finishes, then the second task is executed.
On the other hand, if you are creating a concurrent queue, you must specify in the attributes of the
dispatch queue that you are creating a concurrent queue.
In a concurrent queue, the queue async.
The first task is executed first, but there is no guarantee that which task will come back in the result
first.
It can be the second one.
It can be the third one.
It can be the first one.
So although the task will start in that order that they are added, but they can finish in any order,
hence concurrent.
Whenever we are working with a background queue, it can be used to download images and resources that
we don't really want to do on the main thread on the UI thread.
Because if we do it on the main thread it will block and freeze the user interface.
But one of the main problems with the code that you are looking at is we are currently in the main thread.
We download the image, we're currently in the background thread and we download the image, but we
are still in the background thread when we are trying to refresh the user interface.
This is not a good idea.
If you want to refresh the user interface or do anything with the user interface, you have to make
sure that you are in the main thread.
This means that you can download the image in the global background thread, but if you want to update
your user interface, you need to make sure that you're switching to the main thread or the UI thread.
This is done by dispatchqueue dot main dot async.
And this is going to make sure that your UI is fast.
And the thing that you're trying to update on the UI is being updated from the main thread and not the
global background thread.
So that is a crash course on GCD.
This course is mostly about async and await and actors and the new features of the swift language.
So let's go ahead and start using the new features now.

A] Async Await:-



















