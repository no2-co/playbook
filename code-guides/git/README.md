## Shopify

A guide for programming within version control.

## Maintain a Repo

- Avoid including files in source control that are specific to your
  development machine or process.
- Delete local and remote feature branches after merging.
- Perform work in a feature branch.
- Rebase frequently to incorporate upstream changes.
- Use a pull request for code reviews.

## Write a Feature

Create a local feature branch based off master.

    git checkout master
    git pull
    git checkout -b <branch-name>

Rebase frequently to incorporate upstream changes.

    git fetch origin
    git rebase origin/master

Resolve conflicts. When feature is complete, stage the changes.

    git add --all

When you've staged the changes, commit them.

    git status
    git commit -m <meaningful-commit-message>

Write a [good commit message]. Example format:

    Present-tense summary
    Under 50 characters
    Mentions specific features or bugs

If you've created more than one commit,
[use `git rebase` interactively](https://help.github.com/articles/about-git-rebase/)
to squash them into cohesive commits with good messages:

    git rebase -i origin/master

Share your branch.

    git push origin <branch-name>

Submit a [GitHub pull request].

Ask for a code review in the project's chat room.

[good commit message]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[GitHub pull request]: https://help.github.com/articles/using-pull-requests/

## Review Code

A team member other than the author reviews the pull request. 

They make comments and ask questions directly on lines of code in the GitHub or Bitbucket
web interface or in the project's chat room.

For changes which they can make themselves, they check out the branch.

    git checkout <branch-name>
    ./bin/setup
    git diff staging/master..HEAD

They make small changes right in the branch, test the feature on their machine,
run tests, commit, and push.

When satisfied, they Merge the pull request and delete the remote branch from the repo.