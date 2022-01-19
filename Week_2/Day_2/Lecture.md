[What the heck is the event loop anyway? | Philip Roberts | JSConf EU](https://www.youtube.com/watch?v=8aGhZQkoFbQ&t=2s)

[Lecture](https://us02web.zoom.us/rec/share/8XOWGtM9b3dem9WOSaRKhZk-G28fsjeL10iyHhC27VYekxJLypKIycw6kQ_oPtgy.eYvaIXWZpYsjIzs2)
j6AL==iB

## Teacher notes

Hey all,

Today we had three main objectives:

* Review callbacks
* Figure out how setTimeout works
* Figure out how setInterval works.

We did that, and learned lots of extra stuff along the way:
* "Asynchronous" kind of means the same thing as "concurrent" (I still can't think of a difference 🤷‍♀️)
* "Parallel" is different, and we mostly don't worry about parallel
* "Non-blocking" means "doesn't stop other code from running," e.g. "doesn't cause the browser to freeze up while it runs"
* "Blocking" means "the whole world (for some definition of "world") stops while this thing finishes"
* Javascript was designed for adding interactivity to web pages, so it's natural that it supports concurrency by default
* Ruby has sleep, Python has sleep, your terminal has sleep... Javascript doesn't have sleep????
* It has setTimeout instead, which is like an asynchronous version of sleep
* (But we can implement sleep in Javascript just by doing a while loop)
* setTimeout schedules a task (a function) to run later
* setInterval does the same, but repeats the task until you tell it to stop
* clearInterval (or clearTimeout) let you clear your intervals/timeouts