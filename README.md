# Stage 1 - Create Your Own Merge Conflict

In this stage, you will simulate creating a merge conflict with another contributor.

## What Happened?

Imagine the following:

* You have a master branch (`stage-1-master`) and you create a topic branch (`stage-1-topic-branch`).
* On the master branch is text that is wrong. You decide to correct it.
* In the meantime, someone else has submitted a merge request and merged it before you did, changing the original text that was wrong.
* You change the original text as well. Now, git does not know which version is correct since you did not know about the changed text yet you changed it as well. This creates a merge conflict.

This means you introduce a conflict by changing a text that has already been changed on the master by someone else.

## How Do I Resolve the Conflict?

Fear not! Execute, in this order:

1. Fork this repository into your own repository.
2. Change into `stage-1-topic-branch`:

```
$ git checkout stage-1-topic-branch
```

3. Change the clearly wrong text on your topic branch, commit, and push the changes.
4. (_Optional_) You can create a pull request, that is github's merge request, against your master branch (`stage-1-master`) to see that there indeed are merge conflicts.
5. Rebase your branch against the master branch so that your branch contains all the changes from the master branch:

```
$ git rebase stage-1-master
```

6. Open the `important-doc.adoc` file and notice the `<<<<<<` and `>>>>>>` delimiters, with `=====` in the middle. These inform you of the old version and the new version (old is above, new is below the equal signs).

7. Delete the old version of the text and keep your awesome new version.
8. Add the changed file to the index of your working tree:

```
$ git add important-doc.adoc
```

9. Continue rebasing:
```
$ git rebase --continue
```

10. Push your changes.

Now, you have resolved your merge conflict.


## Further Resources

You can read up on Git merge conflicts here:

* [YT Video Resource](https://www.youtube.com/watch?v=g8BRcB9NLp4) <-- Not affiliated with me in any manner.
* [Gui Git Conflict Tools](https://stackoverflow.com/questions/161813/how-to-resolve-merge-conflicts-in-git) - You can, and should (with more complex conflicts), use a gui tool to merge conflicts.
