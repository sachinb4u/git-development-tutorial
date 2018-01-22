## Git Development Best Practices

Every developer should follow below best practices while working on Git projects

* Always perform work in a branch. Do not make any changes on `master` branch
    >This way all work is done in isolation on a dedicated branch rather than the main branch. It allows you to submit multiple pull requests without confusion. You can iterate without polluting the master branch with potentially unstable, unfinished code. 

* Create a branch from base branch on which you will develop a feature/defect
    >This way, you can make sure that code in master will almost always build without problems, and can be mostly used directly for releases

* Never push into `master` branch. Make a Pull Request. `Push` rights on all repository are revoked and only `Pull Request` are allowed
    > It notifies team members that they have completed a feature. It also enables easy peer-review of the code and dedicates forum for discussing the proposed feature.

* Update your local `master` branch and do an interactive rebase before pushing your feature and making a Pull Request.
    > Rebasing will merge in the requested branch (`master`) and apply the commits that you have made locally to the top of the history without creating a merge commit (assuming there were no conflicts). Resulting in a nice and clean history. [read more ...](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

* Resolve potential conflicts while rebasing and before making a Pull Request.

* Delete local and remote feature branches after merging your `Pull Request`.
    > It will clutter up your list of branches with dead branches. It insures you only ever merge the branch back into (`master`) once. Feature branches should only exist while the work is still in progress.

* Before making a Pull Request, make sure your feature branch builds successfully and passes all tests (including code style checks).
    > You are about to add your code to a stable branch. If your feature-branch tests fail, there is a high chance that your destination branch build will fail too. Additionally, you need to apply code style check before making a Pull Request. It aids readability and reduces the chance of formatting fixes being mingled in with actual changes.

* Use `.gitignore` file.
    > It already has a list of system files that should not be sent with your code into a remote repository. In addition, it excludes setting folders and files for most used editors, as well as most common dependency folders.

* Write good commit messages
    * Having a good guideline for creating commits and sticking to it makes working with Git and collaborating with others a lot easier. Here are some rules of thumb ([source](https://chris.beams.io/posts/git-commit/#seven-rules)):
    * Separate the subject from the body with a newline between the two.
        > Git is smart enough to distinguish the first line of your commit message as your summary. In fact, if you try git shortlog, instead of git log, you will see a long list of commit messages, consisting of the id of the commit, and the summary only.
    * Limit the subject line to 50 characters and Wrap the body at 72 characters.
        > Commits should be as fine-grained and focused as possible, it is not the place to be verbose. [read more...](https://medium.com/@preslavrachev/what-s-with-the-50-72-rule-8a906f61f09c)
    * Capitalize the subject line.
    * Do not end the subject line with a period.
    * Use [imperative mood](https://en.wikipedia.org/wiki/Imperative_mood) in the subject line.
        > Rather than writing messages that say what a committer has done. It's better to consider these messages as the instructions for what is going to be done after the commit is applied on the repository. 
    * Use the body to explain **what** and **why** as opposed to **how**.