---
layout: page
title: Branching and Merging
---

> Branch operation allows creating another line of development. We can use this operation to fork off the development process into two different directions.

&nbsp;

## ✰ Create Branch

***

* Creates a new branch using the `git branch <branch name>` command.

* We can create a new branch from an existing one. We can use a specific commit or tag as the starting point.

  * You can create the `branch` via a hash:

    ```sh
        git branch branch-name <sha1-of-commit>
    ```

  * Or by using a `symbolic` reference:

    ```sh
        git branch branch-name HEAD~3
    ```

* If any specific commit ID is not provided, then the branch will be created with HEAD as its starting point.

    ![after_create_branch](https://github.com/SGKutty/git-concepts/blob/master/images/feature_branch.png?raw=true)

&nbsp;

## ✰ Switch between Branches

***

* We can perform switching between branches using `git checkout` command.

&nbsp;

## ✰ Shortcut to Create and Switch Branch

***

* We have used two commands to create and switch branches, respectively.

* Git provides `–b` option with the `checkout` command, this operation creates a new branch and immediately switches to the new branch.

&nbsp;

## ✰ Delete a Branch

***

* __Delete Local Branch__

  * To delete the local branch use one of the following:

    ```sh
        git branch -d branch_name
        git branch -D branch_name
    ```

  * The `-d` option is an alias for `--delete`, which only deletes the branch if it has already been fully merged in its upstream branch.

  * You could also use `-D`, which is an alias for `--delete --force`, which deletes the branch irrespective of its merged status.

  * For more information `man git-branch`.

* __Delete Remote Branch__

  * You can delete a remote branch using

    ```sh
        git push <remote_name> --delete <branch_name>
    ```

  * Which was added in [Git v1.5.0](https://github.com/gitster/git/blob/master/Documentation/RelNotes/1.5.0.txt) to delete a remote `branch` or a `tag`.

  * Starting from [Git v2.8.0](https://github.com/git/git/blob/master/Documentation/RelNotes/2.8.0.txt) you can also use git push with the `-d` option as an alias for `--delete`.

&nbsp;

## ✰ Rename a Branch

***

* move locally (--move):

* We can change branch name by using `–m` option with `git branch` command followed by the `old-branch` and the `new-branch`.

* `push` new branch to remote(--set-upstream, optional):

    ```sh
        git push origin [-u] <new_name>
    ```

* `delete` old remote branch(--delete):

    ```sh
        git push origin -d <old_name>
    ```

&nbsp;

## ✰ Merge Two Branches

***

* After committing the changes done, the new branch will appear as follows:

    ![after_commit_in_new_branch](https://github.com/SGKutty/git-concepts/blob/master/images/feature_branch_commit.png?raw=true)

* Checkout to `master` branch and perform merge using following commands `git merge <feature branch>`.

* After the merge operation, the master branch will appear as follows:

    ![after_branch_merge](https://github.com/SGKutty/git-concepts/blob/master/images/merge.png?raw=true)