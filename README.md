# Git-Visualizing
A guide to thinking in graphs, not just commands.

(a git log here)

Have you ever done a git rebase and watched your code vanish? Or stared at a git log output, trying to decipher the story of your project?

If so, you're not alone. Many people treat Git like a magic memorizing commands like git push - force-with-lease without understanding what they actually do then pray to the gods that nothing breaks.

The problem is that we're thinking of Git as a collection of commands, when we should be learning it as a visual story. Your repository isn't just a folder with files! It's a living, branching timeline of your project's evolution. And once you learn to see this timeline in your mind's eye, everything changes.

In this article, I'll show you how to transform from someone who just types Git commands into someone who truly understands them by learning to visualize the commit graph that forms the heart of every Git repository.

# The Commit Graph
At its heart, a Git repository is not a folder of files, it is a timeline of snapshots. But unlike a linear timeline, this timeline can branch, merge ect, forming a living history of your project's development.

(a snapshot)  (other-snapshots)
    |        /      |       |
    A  <--  B  <--  C  <--  D (main) <- HEAD

Each snapshot stores a complete snapshot of every file in your repository at that moment AKA: a Commit, which consists of a Hash, a Parent Pointer and a Commit Message. The Commit Message tells your teammates and your future self why the change was made where the Parent Pointer is a link to the past commit (that's what builds the timeline) and lastly the Hash is a 40-character hexadecimal string (a1b2c3d4e5…)

# Visualizing Core Concept
So far, we understand that Git is a graph of commits, each commit is a node, a frozen moment in time that can never be changed.

(a picture that shows what is below)

The picture shows a Git repository's graph that I initialized, i switched or checked-out another branch (feature) on the second commit made two other changes and got behind by one commit. You will notice a HEAD mark above the new branche's name, that is a special pointer that points to the tip of a branch, simply tells you which version or part of the project you're at.

if you run git status on the command line
