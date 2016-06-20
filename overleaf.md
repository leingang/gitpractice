#github + Overleaf Tutorial

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
