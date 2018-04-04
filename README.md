git2know
========

Git dashboard to supply information about all local git repositories.  

Getting started
---------------

The current version finds all local git repositories and prints out a list of the respective status of each repository, differentiating between uncommited, unpushed and up-to-date.

1. Install python3.6.
1. Install python dependencies.
    ```
    sudo pip3 install -r requirements.txt
    ```
1. Copy `git2know` to a directory contained in `$PATH`.
    ```
    sudo cp git2know /usr/local/bin/
    ```
1. Run git2know.
    ```
    git2know
    * (1/2) Creating index database
    * (2/2) Searching for git repositores
    :: Checking status
    * (1/5) ⇡ /home/moenka/Forge/@moenka/git2know/.git
    * (2/5) ⤊ /home/moenka/Forge/@moenka/proving_ground/.git
    * (3/5) ⇡ /home/moenka/Forge/@moenka/rc/.git
    * (4/5) ⇡ /home/moenka/Forge/@moenka/setup/.git
    * (5/5) ✓ /home/moenka/Forge/@moenka/tilesylum/.git
    => Key:
    => ✓  up-to-date
    => ⤊  unpushed changes
    => ⇡  uncommited changes
    => ⤋  changes on remote (not yet implemented)
    ```
1. Profit!

How it works
------------

git2know uses

* **mlocate** to create a list of all git repositories on the local machine
* **websocketd** to provide a dashboard with information about those repositories

The first and most useful idea of git2know was born since I am using multiple computers for my work. I don't like to carry around computers commuting between my home and my office so I have a computer in both locations. Since I am always working with git to track and document my projects I sometimes blocked my own work by forgetting to push changes to the git server. git2know helps by showing which repositories have unpushed changes on the local machine so I never again have to cope with this problem. As it can be a time consuming and tedious work to firstly find and secondly commit and push all my local changes by hand, I came up with the idea of git2know to do the work for me.

### mlocate

The application creates an mlocate database in your default cache directory (`$HOME/.cache/mlocate.db`). This database is updated on every run. The way mlocate works only changes will be comitted to the database on each run so the first run of the application might take some seconds or minutes depending on the size of your home directory. The mlocate database is not limited to this application and only stores an index of all files contained in your home directory. You are free to use this database with other applications relying on mlocate.

Goals
-----

* find all git repositories on the local machine with unpushed changes
* automatically push all changes to a special (new) branch on shutdown (like hooking into the procedure)
* automatically fetch or notify me about such branches on all local git repositories on startup so I know where I left working

License
-------

Usually MIT, but may also be AGPLv3 - need some time to read about the new license - it will be of course open source, and free for private usage.

