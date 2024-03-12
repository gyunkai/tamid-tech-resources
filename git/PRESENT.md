---
marp: true
theme: gaia
class: invert
---

<!-- _class: lead -->

# Git - Getting Started

```sh
> mkdir test
> cd test
> git init

Initialized empty Git repository in test/.git/
```

---

At this point you may notice a new, hidden directory created
in the current folder. Let's take a look.

```sh
> ls -F .git

HEAD
branches/
config
description
hooks/
info/
objects/
refs/
```

Hopefully by the end of this guide some of those files
won't seem so cryptic, and you will know what they do.

---

## Terminology

- The `.git` folder is referred to as the "repository" or
  **"local repository"**
- The directory above the `.git` folder, where you edit your
  actual files, is called the "working directory" or **"workspace"**

---

## Summary of commands

```sh
mkdir -p test; cd test;
git init; ls -F .git;
```

---

## Warning

For the purposes of this guide we will be poking
around in this folder from time to time. Given that we just
created this repository, and we're not using it for anything
real, it's completely safe.
In fact, it's even _encouraged_ - there's no better way to
learn how Git works.

That said, in general it is _highly_ recommended not to
touch anything in this folder normally, as it may result in
data loss or corruption.

---

<!-- _class: lead -->

## Next

Let's learn about commits.

---

## Create a commit

This is something you're going to do. A lot.

```sh
# Create a file with some text, the value doesn't matter
> echo "hello" >> file.txt

# Add the new file to git
> git add .

> git commit -m "Initial commit"

master  406bb3b Initial commit
 1 file changed, 1 insertion
  create mode 100644 file.txt
```

---

Already from running this one command we can see two very important
bits of information.

- The "branch", which is indicated by `master`.
- By default, `master` is the first/initial branch that is created,
  but after that there's _nothing_ special about it.
  We'll get to master soon
- A hash, which is indicated as `406bb3b` in this example.
  When you run this on your machine it _will_ be something different.

This section is only interested in commits, we'll have plenty of time
to talk about branches.

---

## Commit

So what just happened?

Imagine taking a copy/backup of a file or directory of files.
A very common approach will be to take a copy and rename the new
version to something like "test-1".

That's basically what we just did. Think of a commit as
that directory of files, preserved forever, but without it
necessarily cluttering up your desktop.

---

Let's do it again, just for fun.

```sh
# Update the file
> echo "hello again" >> file.txt

# Add the new contents
> git add .

> git commit -m "Second commit"

master 672e562 Second commit
 1 file changed, 1 insertion
```

> What happens if you try commiting without changing the file?

Again we see `master`, and now a different hash `672e562`.
Maybe we should stop to talk about what a hash is.

---

## Hash

You will probably see the hash referred to by a number of names
in various places, both here and elsewhere. Such as:

- sha1
- sha
- hash
- commit ID

They're all the same thing I promise.
But what the hell is that exactly?!?

---

The hash is a unique address/reference/pointer to that commit.
In the example of taking copies of a file/directory the hash
could be thought of the filename.
Such as "test-1", "test-2", etc.

After a while those filenames would all blur together,
how would we know what each one contained?
The commit hash is very big and is guaranteed to be unique,
so you don't have to keep coming up with new names.
If you're wondering why the hash isn't just a number,
that's a little harder to explain .

---

## Log

Let's take a look at those two commits. How do we do that?

```sh
> git log 672e562

commit 672e562c008009ec391e11a1fa3574af39428ae1
Author: Charles OFarrell <charleso@charleso.org>
Date:   Sun Apr 17 10:56:55 2016 +1000

    Second commit

commit 406bb3bffbd02113ad5e2fecb4da364c01b20bb3
Author: Charles OFarrell <charleso@charleso.org>
Date:   Sun Apr 17 10:35:29 2016 +1000

    Initial commit
```

---

The first thing to note is that `672e562` is only
the first 7 characters of a much longer hash
`672e562c008009ec391e11a1fa3574af39428ae1`.

> What other forms of the hash does Git accept?
> Can it be shorter?

> What happens when you use log to view the first commit?
> What was missing?

---

Secondly you can see the commit "message" that we supplied
to the `commit -m` command. That's handy, we can
see more information about that commit.
That's better than having `really-long-filename-3` to indicate
what a particular backup was for.

We can also see who created that commit, which isn't all
that interesting when we're working by ourselves, but
in larger projects that might be very important.
Who broke the program - oh it was Charles!!!

---

> Create a few more commits and then look at them with log

> Advanced The full hash is stored as a file under `.git` somewhere,
> can you find it?

---

<!-- _class: lead -->

## Next

Next up we're going to look at what `master` is.

---

<!-- _class: invert lead -->

# Git - Master

This guide is intended as a primer for understanding
what `Master` is. You should have previously
read about commits.

---

## Master

So far we've create a few commits. Let create another.

```sh
> echo "goodbye" >> file.txt

# Add the new contents
> git add .

> git commit -m "Third commit"

master 41ce7fa Third commit
 1 file changed, 1 insertion
```

---

<!-- _class: lead invert -->

So what is this `master` exactly?
You probably already know that it's a branch,
but what is that?

Let's take a detour.

---

## Graph

Git has a very "rich" command line.
In general I want to avoid throwing around 10 different versions
of a command, that is probably going to be confusing at this stage.
`log` alone has about 30 options, many of which can be very useful.
The ones I want to show now look like this:

```sh
> git log --graph --oneline --decorate 41ce7fa

* 41ce7fa  Third commit
* 672e562 Second commit
* 406bb3b Initial commit
```

---

> What does each of those options do?
> Can you use different combinations of them?

## So this contains one extra bit of Git terminology we haven't seen before. `HEAD`

Understanding `HEAD` is critical to understanding how Git _really_ works,
so let's take a second to dig a little deeper.

Way back in the beginning we looked at the contents of the `.git` directory.
Let's do that again:

---

```sh
> ls -F .git

COMMIT_EDITMSG
HEAD
branches/
config
description
hooks/
index
info/
logs/
objects/
refs/
```

Interesting, there's a file called `HEAD`. Let's take a look.

---

```sh
# The `cat` command prints the contents of a file on the terminal
> cat .git/HEAD

ref: refs/heads/master
```

So we should recognize the `master` part, but what is `refs/heads/`?

Let's keep digging.

---

## Refs

You'll also notice there is a `refs/` directory in `.git`.

```sh
> ls -F .git/refs

heads/
tags/
```

Ignore `tags`, let's focus on `heads`.

```sh
> ls -F .git/refs/heads

master
```

---

And at the end of the rabbit hole?

```sh
> cat .git/refs/heads/master

41ce7faa5b8b2cf480d44c3b12f0545fed9683c3
```

That's the most recent commit!
So `HEAD` is just a reference to `refs/heads/master`,
which in turn is just a reference to a specific commit,
which captures a collection of files.

Something like this:

```
HEAD -> refs/heads/master -> 41ce7fa -> file.txt
```

---

Actually that looks a _little_ like our `log --graph` command.

```
> git log --graph --oneline --decorate 41ce7fa

* 41ce7fa  Third commit
* 672e562 Second commit
* 406bb3b Initial commit
```

It would appear that `refs/heads/master` is just the long winded way
of saying `master`. They're the _same_ thing.

---

Perhaps a slightly more obscure point is that a branch is just a "head" ref.
Said another way - everything under `refs/heads` is a branch.
We look at some other types of refs later on, but for now we
might just focus on heads.

> Can you use `HEAD`, `master` or even `refs/heads/master` in the `log` command?

> What happens if you don't supply `log` a commit/ref, what does it default to?

> If you make another commit what changes? Is it `HEAD` or the ref?

---

<!-- _class: lead -->

## Next

Ok, that's probably enough for this section.
Next we'll see what happens when we start creating
multiple branches.
