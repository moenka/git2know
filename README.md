git2know
========

Git dashboard to supply information about all local git repositories.  

How it works
------------

git2know uses

* **mlocate** to create a list of all git repositories on the local machine
* **websocketd** to provide a dashboard with information about those repositories

The first and most useful idea of git2know was born since I am using multiple computers for my work. I don't like to carry around computers commuting between my home and my office so I have a computer in both locations. Since I am always working with git to track and document my projects I sometimes blocked my own work by forgetting to push changes to the git server. git2know helps by showing which repositories have unpushed changes on the local machine so I never again have to cope with this problem. As it can be a time consuming and tedious work to firstly find and secondly commit and push all my local changes by hand, I came up with the idea of git2know to do the work for me.

Goals
-----

* find all git repositories on the local machine with unpushed changes
* automatically push all changes to a special (new) branch on shutdown (like hooking into the procedure)
* automatically fetch or notify me about such branches on all local git repositories on startup so I know where I left working

License
-------

Usually MIT, but may also be AGPLv3 - need some time to read about the new license - it will be of course open source, and free for private usage.

