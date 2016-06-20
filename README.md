# AIM Textbook Workshop Sandbox

A practice `git` repository for the AIM Open Textbook Workshop, April 25-29, 2016.

Based on the LaTeX version of [The Geometric Theta Correspondence for Hilbert Modular Surfaces](http://arxiv.org/abs/1108.5305), by Jens Funke, John Millson.

Run pdflatex on `funke-millson-master.tex`

Forked by MPL 2016-06-13 to use as `git` practice with coworkers.

Vocabulary
----------

* **git** is software for managing a base of code that changes frequently.  
  Such applications are called *version control systems* or *revision control
  systems*.  `git` is the RCS *du jour* having taken over from others such as
  subversion (`svn`), `cvs`, and `rcs`.  It's open source, brought to you by
  Linus Torvalds of linux et al.

* **github** is a website/social network of people who use git.  
  It hosts user profiles and repositories.

* a **repository** is a base of code.  Usually about one "project" worth

* a **commit** is a change to a repository.  In git each commit has a unique
  address or *hash*.  Changes have to be added (or staged) first with the
  command `git add`.   Then whatever changes that have been staged must be
  commited with `git commit`.  Commit messages are required and become part of
  the commit log; write good ones for your own sake.

* a **branch** is a path of a repository's development.  If you must know, a
  git repository is a data structure known as a
  [directed acyclic graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph)
  or *DAG*.  Experimental changes can be committed to their own branch, preserving
  the master branch in its working state.  The command to create a branch is `git branch`

* to **clone** a git repository is to make a copy of it.  The repository's
  entire history is copied as the same time.  Repositories can be cloned from
  one machine to another, or from github to a local machine.  The command is
  `git clone <repository>`, where the repository might be identified by a URL.

* to **fork** a repository is a github action rather than a git one.
  It means to clone from one person's or organization's github account to your
  own.

* to **check out** a branch is to switch to that branch in your working repository.
  The command is `git checkout <branch name>`

* to **merge** branches of a repository is to synchronize them.  To merge the
  changes from branch `foo` into branch `master` (this is usually what you're doing),
  the sequence of commands is

      $ git checkout foo
      $ <do stuff>
      $ git add <changed files>
      $ git commit
      $ git checkout master
      $ git merge foo

 * a **pull** is a merger of one branch of a remote clone of a repository to a local one.
   In github, a user will often make changes on their own fork, then submit a
   *pull request* that their changes be merged into the global master repository.
   When working in a local clone, pulling “down” from a remote master merges in
   changes that have occurred since the clone.

 * a **push** is a merger of a local repository with a remote one.  In the typical
   github workflow, a user will make changes on their local clone, then push the
   changes to their remote (but still personal) fork.


First steps
-----------

1. Poke around this repository on github and see what you can see.

2. Fork this repository to your own github account.

3. Clone your fork to your local machine.  Usually you can do this by clicking
   the little clipboard icon, switching to a command line, typing "`git clone `",
   then pasting the repository's URL to the command line.

4. Create a branch.  Call it whatever you want.

5. Check out that branch!

6. There should be a file in the repository with your name on it.
   Rob introduced some undesirable LaTeX into all of these files.
   Although this is not a workshop on LaTeX best practices, see if you can find
   some things to change, and make the changes.

7. Run `git status` to see what files in the local directory are “dirty.”

8. Run `git diff` to see what's been changed.  You'll get a printout of which
   files have changed, which lines of those files have changed, and the line-by-line
   before-and-after versions of those changes.

9. Run `git add <filename>` to stage the changes of any files you want to commit.
   (In practice, you can stage many files for the same commit, which is one good reason
   that these are separate commands.)

10. Run `git commit -m "<message>"` to commit your changes.  One style of commit
    message is just to use sentence predicates, starting with an imperative verb.
    For example, “delete unnecessary linebreaks”.  You'll see your commit has
    been given a shiny new hash.

11. Run `git push --all` to push your development branch up to your github fork.
    (Without the `--all` option, only the `master` branch will get pushed.)
    You'll need to submit your github username and password.
    Switch to github and you will see this activity noted.

12. Submit a pull request against my master.

Next steps
----------

You noticed that your local `git` command “knew” that your local repository came
from github.  Type `git remote -v` to see what it knows about any other remote
repositories.

Well, nothing else.  But we can add one now.  Run

    $ git remote add upstream https://github.com/leingang/gitpractice.git

This lets your local repository know about another repository called *upstream*.
Run `git remote -v` again and see what you get.

Once pull requests have been made, run this command:

    $ git pull upstream master

You will see that all changes I made to the “upstream” repository (on the
`master` branch) got merged into your working branch.  Your branch is now
up-to-date with the main repository.

See also this [Github help page about adding a remote](https://help.github.com/articles/configuring-a-remote-for-a-fork/)

More github features
--------------------

An *organization* on github is like a group.  An organization can have repositories.
This is useful for the situation when administration of the repository may change
hands.  I created an organization for us.

*Issues* are simple discussion threads attached to a repository.  Good for pointing out bugs or
requests for enhancement.

You can *follow* other github users to see what they're up to.

You can *star* a repository if you want to get notifications on its development.

References
----------

Git takes a long time to grok.  For more, consult one of these.

* [Git for Authors](http://mathbook.pugetsound.edu/gfa/html/git-for-authors.html) by Rob Beezer et al.  By a mathematician, focused on code bases that are documents rather than software.
* [The Git “red book”](https://git-scm.com/book/en/v2) The definitive guide.


##github + Overleaf Tutorial

[Overleaf](https://www.overleaf.com/) is an online platform for latex collaboration.  With a free account, one can collaborate with any number of other users on a latex document, observing changes in real time.  This would be another option to collaborate on latex documents.  (Sharelatex is another one similar to Overleaf.)

It includes a feature that links Overleaf and Git.  You can clone any Overleaf project, and you can also push any project you have to Overleaf.

####Overleaf to local git repository to github

First, make a (free) Overleaf account if you don't have one yet.  I've made a "toy" project in Overleaf that we can use to try this out. We'll clone this project to our local directory, and then sync this to a github remote repository.

1. Click [this link](https://www.overleaf.com/4551529zqsdhy) to open the Overleaf project.

2. Click "Share" (on top menu bar) to see to find the address of the git repository of this project on Overleaf.  

   (Spoiler alert: the address is  just https://git.overleaf.com/4551529zqsdhy; replacing "www" with "git" in the Overleaf project link.)

3. Clone to your local directory:

   `git clone https://git.overleaf.com/2029559gkypzx`

   You now have the Overleaf project on your local directory.
   
   You can now work on the latex project offline, then commit and push it back to overleaf.

4. Next, suppose that we also want to have this project on github. Create a blank repository on github, then specify this as an additional remote repository:

   `git remote add githubrepo <address of your github repository>`

   _(What comes after `add` is whatever name you pick; here I picked "githubrepo".)_

   _If you type `git remote -v`, you'll see that there are now two remote repositories associated with this local repository: origin (the Overleaf one) and githubrepo (the github one)._

5. Push to github

   `git push githubrepo master`

####GitHub to local git to Overleaf

Now for the reverse action.  Our goal will be to get the latex project in this githubpractice repository to Overleaf.  First, make sure that the local directory is up-to-date.

1. Go to your Overleaf account and create a new project.

  In your new project, you have to have at least one latex file; this could be just a blank file.  (This "dummy" tex file will eventually get deleted anyway.)

2. In your local git directory, add Overleaf as the second remote git repository: 

   `git remote add overleaf <address of your overleaf project (git instead of www)>`
   
   _(What comes after `add` is whatever name you pick; here I picked "overleaf".)_
   
   _If you type `git remote -v`, you'll see that there are now two remote repositories associated with this local repository: origin (the github one) and overleaf (the Overleaf one)._

3. Pull the latest content from Overleaf and merge to your current branch:

   `git checkout <branch>`
   `git pull overleaf master`
   
   _(Note: we can work with whatever branch locally/on github, but on Overleaf, we can only work with the master branch.)_

4. The Overleaf website says you need to do this

   `git revert --mainline 1 HEAD`

   to revert the merge to get rid of the files in the existing Overleaf project.
   
5. Push to Overleaf:

   `git push overleaf master`

[More info here](https://www.overleaf.com/help/230-how-do-i-push-a-new-project-to-overleaf-via-git#.V2HExPkrLb0)
