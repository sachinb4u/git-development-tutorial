### Prerequisites
- `git-demo` repository is forked
- Forked repository is setup and configured as per the previous instructions

## Developer Workflow
1. Developer identifies a feature or defect to be developed.
    - __feature-345__ is the feature to be developed which requires home page to be developed

2. Get latest changes from upstream branch
    ```
    git checkout master
    # Get the changes from upstream `master` branch and merge into local master branch
    git pull upstream master
    ```
3. Create a branch for the feature
    ```
    # go to master branch and create a new branch
    git checkout master

    # Create and checkout the branch
    git checkout -b feature/345-add-homepage
    Switched to a new branch 'feature/345-add-homepage'
    ```
### Prerequisites
- `git-demo` repository is forked

## GitHub Review Process
As of GitHub 2.8 GitHub comes with its own built-in review process. In the following this is explained.

### Starting a Review
To start a review on a pull request...

1. Open the Files changes tab in GitHub,
2. Leave comments on the code,
3. Select Start a review when finished. You can continue to leave multiple comments on the code.

Once finished you can Review changes, select an option, and finally Submit review. Your options are as follows:

* **Comment** - Comments do not require a review!
* **Approve** - Approves the pull request, equivalent to a Gerrit +1
* **Request** changes - Indicates that something needs to be resolved before merging to a Gerrit -1