# Git-Visualizing
A guide to thinking in graphs, not just commands.

This article assumes you have a basic understanding of Git! I'll show you how to transform from someone who just types Git commands into someone who truly understands them by learning to visualize the commit graph that forms the heart of every Git repository.

<img width="1250" height="455" alt="image" src="https://github.com/user-attachments/assets/9ea85d68-df09-4091-9808-122cda688a44" />

Have you ever done a git rebase and watched your code vanish? Or stared at a git log output, trying to decipher the story of your project?

If so, you're not alone. Many people treat Git like a magic memorizing commands like git push--force without understanding what they actually do then pray to the god that nothing breaks. The problem is that we're thinking of Git as a collection of commands, when we should be learning it as a visual story. Your repository isn't just a folder with files! It's a living, branching timeline of your project's evolution. And once you learn to see this timeline in your mind's eye, everything changes.

# The Commit Graph
At its heart, a Git repository is not a folder of files, it is a timeline of snapshots. But unlike a linear timeline, this timeline can branch, merge ect, forming a living history of your project's development.

(a snapshot)  (other-snapshots)
    |        /      |       |
    A  <--  B  <--  C  <--  D (main) <- HEAD

Each snapshot stores a complete snapshot of every file in your repository at that moment AKA: a Commit, which consists of a Hash, a Parent Pointer and a Commit Message. The Commit Message tells your teammates and your future self why the change was made where the Parent Pointer is a link to the past commit (that's what builds the timeline) and lastly the Hash is a 40-character hexadecimal string (a1b2c3d4e5…)

# Core Concepts
When working with Git, you should definitely use its logging, some commands to remember and there you are.

<img width="1122" height="444" alt="image" src="https://github.com/user-attachments/assets/42a36362-3e4e-4d46-9412-598688f65175" />


The picture shows a Git repository's graph on the command line that was initialized with the commit 'blah', switched or checked-out another branch (feature) before the second commit, merged after one commit 'blah1' made from master branch and one other 'blah2' from feature then other changes made from master (change 1 <- 4). If we were to interpret that we would take a look at the following!

--oneline option provides less lines of information from the default log command, that's why you're seeing the hash shortened (a hash of 7 chars).

Switching or checking out in Git is the process of moving from one branch or commit to another. When you run git switch or git checkout, you're essentially telling Git to update your working directory and staging area to match the snapshot of the branch or commit you're switching to.

- - -

<img width="514" height="484" alt="image" src="https://github.com/user-attachments/assets/ec8ddd5c-35c2-4afe-9fa8-945293bf574b" />


Im using a Visualizing helper! So, you could notice different hashes but the Graph remains the same as the logs above.

If you wonder what's the HEAD mark below master, that is a special pointer that points to the tip of a branch, simply tells you which version or part of the project you're at.

The branches now merged after they decided to split up on the way but feature was left behind since master has advanced in changes and feature does not keep track anymore! Suppose master made 4 other commits (like we saw in previous example), feature wouldn't have them if he doesn't keep track and here is where the miss begins. We have two scenarios:
1. either master branch is yours and you're just using too many branches for some cause (working localy):
- In this case for example you only need to keep track of what you have done and do what is needed (git merge master or git rebase master).
2. or it's some public/collaborative or else repositories that you're into:
- In this case you would always need to fetch with origin (git fetch origin) to get latest changes, merge/rebase and then work from there, if not, you will end up working on outdated code, merge conflicts will accumulate and of course integration would be painful! (Forget about git push--forcehh)


https://github.com/user-attachments/assets/a2fb6b90-7f1d-4abd-aae0-c36d67dfb3a9

- - -

When Git logging used along with VS-Code Graph they provide a perfect Vision of the project which transforms how you understand and navigate your codebase.

<img width="1313" height="368" alt="image" src="https://github.com/user-attachments/assets/95973508-7d0d-4033-b12f-6d913a9c648a" />

Notice above that we are now looking at feature branch, it is outdated (it only has till 'change3' where main is already at 'change4'), Git graph didn't mention anything of that but we're seeing that the VS-Code's Graph has a commit colored in orange which means that main has this commit and this branch not. Beautiful isn't it?
