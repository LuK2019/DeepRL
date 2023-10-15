You can achieve this by using Git's capability to handle multiple remote repositories for a single local repository. Here's a step-by-step guide on how you can do this:

Clone the Original Repository:

If you haven't already, clone the original repository (upstream) to your local machine.

bash
Copy code
git clone https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
Add Your Personal GitHub Repository as a Remote:

Navigate to the directory of the cloned repository:

bash
Copy code
cd ORIGINAL_REPOSITORY
Add your personal GitHub repository as a new remote, traditionally named origin (since typically, origin points to your personal fork, and upstream points to the source repository you forked from):

bash
Copy code
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
If you have already set origin to the original repository, you can rename it to upstream using:

bash
Copy code
git remote rename origin upstream
And then add your personal repo as origin.

Push Your Local Changes to Your Personal GitHub Repository:

bash
Copy code
git push origin main  # or replace 'main' with your branch name
This will push your local changes to your personal GitHub repository.

Syncing with Upstream:

To fetch updates from the original repository (upstream) and merge them into your local branch, do the following:

bash
Copy code
git fetch upstream
git merge upstream/main  # or replace 'main' with the branch name you want to merge
Alternatively, you can rebase instead of merge:

bash
Copy code
git rebase upstream/main
Push the Updates to Your Personal GitHub Repository:

If you've merged (or rebased) changes from the upstream repository, you might want to push those updates to your personal GitHub repository:

bash
Copy code
git push origin main
Regularly Update From Upstream:

Whenever you want updates from the original repository, simply fetch and merge (or rebase) from the upstream remote, then push those updates to your personal origin remote:

bash
Copy code
git fetch upstream
git merge upstream/main
git push origin main