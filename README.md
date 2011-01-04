clojure-tools
=============

This is just a small repo for me to keep track of my Clojure-related tools;
scripts, JAR files, etc. I split this out of my
[dotfiles](https://github.com/rjray/dotfiles) repo since it really didn't fit
the "dotfiles" label any longer.

Contents
--------

Aside from having copies of clojure.jar, clojure-contrib.jar and any others
that I regularly use, the main contents of this repo are a pair of executable
scripts:

### clojure

This is a generalized launcher script for Clojure, written in Perl. It requires
Perl 5.10.0, but uses no external modules, only core Perl. It could be
back-ported to Perl 5.8.0 without too much difficulty. I wrote it because I had
been using a bash script (Jocho's *clojure* script in his
[clojure-extra](https://github.com/jochu/clojure-extra) repository), but found
that I wanted more flexibility in specifying JAR files to the class path, as
well as other options. So I set out to write something only a little more
complex than the original bash script, and ended up with this.

It's ended up being actually quite a bit more complex than the bash script.

But that happens, sometimes.

### swank-clojure

This is a less-general script, probably of less interest to others than the
**clojure** script itself. It is a bash script that uses the **clojure** script
to launch a Swank server using my local copy of
[swank-clojure](https://github.com/jochu/swank-clojure). The body of the script
(the eval-code, etc.) hails from the *swank-clojure* script that the leinengen
tool installs when you have it download/install swank-clojure through maven. I
just adapted it to my needs, is all. This is the script I use to start a Swank
server to use with emacs/SLIME. You're welcome to use it, too, but it has some
hard-coded paths that don't have command-line alternates, unlike the
**clojure** script itself.

General Use
-----------

These are mostly for my own edification, but if others find them useful and
have some helpful suggestions, I'm glad to hear them. For example, **clojure**
is very *nix-centric in how it looks up files and paths, because I generally
don't use Windows platforms. I can fix that, if others really want it, but for
now I have no need to.
