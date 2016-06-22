# lecture-2016-06-22

Thanks to Dylan V. for volunteering to demonstrate all the things.

Transcript:

```
login as: pconrad
pconrad@butthead.cs.ucsb.edu's password:
Last login: Thu Apr 14 00:08:45 2016 from 128.111.64.136
-bash-4.3$ ssh dvanmali@butthead.cs.ucsb.edu
dvanmali@butthead.cs.ucsb.edu's password:
[dvanmali@butthead ~]$ who
pconrad  pts/0        2016-06-22 09:36 (128.111.54.61)
dvanmali pts/1        2016-06-22 09:44 (128.111.43.56)
[dvanmali@butthead ~]$ ls
cs16  cs32     Documents  Music     Public     Videos
cs24  Desktop  Downloads  Pictures  Templates
[dvanmali@butthead ~]$ mkdir cs56
[dvanmali@butthead ~]$ cd cs56
[dvanmali@butthead cs56]$ git clone https://github.com/UCSB-CS56-M16/lab00_dvali.git
Cloning into 'lab00_dvanmali'...

(gnome-ssh-askpass:9030): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh-aass'
Username for 'https://github.com': dvanmali

(gnome-ssh-askpass:9031): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh-aass'
Password for 'https://dvanmali@github.com':
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
Checking connectivity... done.
[dvanmali@butthead cs56]$ ls
lab00_dvanmali
[dvanmali@butthead cs56]$ ls
lab00_dvanmali
[dvanmali@butthead cs56]$ pwd
/cs/student/dvanmali/cs56
[dvanmali@butthead cs56]$ git clone https://github.com/dvanmali/cs56-rationalample.git
Cloning into 'cs56-rational-example'...
remote: Counting objects: 292, done.
remote: Total 292 (delta 0), reused 0 (delta 0), pack-reused 292
Receiving objects: 100% (292/292), 280.14 KiB | 349.00 KiB/s, done.
Resolving deltas: 100% (200/200), done.
Checking connectivity... done.
[dvanmali@butthead cs56]$ ls
cs56-rational-example  lab00_dvanmali
[dvanmali@butthead cs56]$ cd cs56-rational-example
[dvanmali@butthead cs56-rational-example]$ ls
ex01  ex02  ex03  ex04  ex05  ex06  ex07  ex08  index.html  LICENSE  README.m
[dvanmali@butthead cs56-rational-example]$ cat README.md
# cs56-rational-example

This is a set of tutorial examples of a class for Rational Numbers.  Illustra various concepts/techinques of Java Coding (a list of these appears below.)

These examples are intended as support for a course in which there are also ring assignments and lectures; this repo is not intended to be a stand-alone ciculum for learning Java.

Having said that, if you follow the code examples in order, and look up the cepts that are new to you at each step, that will probably go a long way towarlearning some important basic concepts of Java programming.

Link to javadocs: <http://ucsb-cs56-m16.github.io/cs56-rational-example>

# Guide to this set of Examples

* Top level directory contains
    * this `README.md` file
    * subdirectories `ex01`, `ex02`, etc. one per example
    * support files for continuous integration (.travis.yml)

* To follow these examples, consult each README.md in each subdirectory (ex01ADME.md) etc. in order, for further information.

# Basic description of the Rational class

The Rational class provides an abstraction for a rational number, that is oneat has an integer numerator, and a non-zero integer
denominator.  For a more formal definition, consult the [Wikipedia article ontional Numbers](https://en.wikipedia.org/wiki/Rational_number).

This tutorial will not try to motivate *why* we need a class for rational nums.   We will assume that there is some need to represent these in a program. e'll assume that once some Java code has gotten input from somewhere for the erator and denominator of two rational numbers, it needs to:
* Constructor objects that represent these two rational numbers
* Compute new rational numbers representing their sum, difference, and produc
* Output those rational numbers in some way to the user.

We'll assume that instances of the class are immutable, i.e. we provide a way construct objects, and getters for numerator and denominator, but no settersr numerator and denominator.

We'll assume that when instances of Rational are constructed, that if there aany common factors between the numerator and denominator, they are factored o  That is, the rational is represented internally in reduced form, and the gers for numerator and denominator reflect this.  Example:
* Suppose we create a Rational with `Rational r=new Rational(2,4);`
* Then, `r.toString()` will return `"1/2"`
* The getters for numerator and denominator will return `1` and `2`, respectiy.

We'll assume the following rules for negative numbers:
* The negative sign is attached to the numerator, and the denominator is alwapositive.
* Thus getNumerator() can return either a positive, zero, or negative integerhile getDenominator() always returns a strictly positive integer.

We'll also assume that, as a straightforward way of "outputting" rational nums, a toString() method suffices, with these formatting rules:
* The representation is simply `numerator/demoninator`, e.g. `3/4`, `-6/7`.
* We'll also assume that when the denominator is 1, that it should be omitted.g. `2`, and `0`, not `2/1` and `0/1'
* We'll assume that the negative sign, when present, always appears in the nuator

We'll leave the "quotient" of two rational numbers as a very straightforward gramming exercise.

In the first few examples, not all of these rules may yet be in place.  We'lld those incrementally.  Also, as we proceed through the examples, we may makeditional assumptions, set additional goals, and/or place additional restricti.  Those will be noted in the README.md for each example.

# Java Language Concepts

This is a work in progress; not all may be covered yet.  Will update this lisith reference to the first example where each concept is introduced as work ohis repo progresses.

1. private data members  (ex01)
1. public constructors (ex01)
1. toString method (ex02)
1. public getters (ex02)
1. JUnit testing (ex03)
1. immutable objects (throughout, but discussed in ex04)
1. static methods (class level) (ex05)
1. exceptions (IllegalArgumentException) (ex07)
1. proper way to override equals and hashcode (ex09 and beyond)
1. equals vs. == (ex09 and beyond)
1. comparable interface (ex09 and beyond)
1. creating an arraylist of rationals (ex09 and beyond)
1. sorting an arraylist of rationals (ex09 and beyond)

Java Language Toolset Skills

1. Compiling/Running by hand with `javac` and `java` (ex01)
1. Ant (ex02)
1. Running from a jar file (ex03)
1. JUnit jars (ex03)
1. Javadoc (ex04)
1. Adding line numbers to stack traces (ex05)
1. Adding links to Java Standard Libraries in our javdoc (ex06)
1. Packages (ex09 and beyond)
1. Maven (ex09 and beyond)

[dvanmali@butthead cs56-rational-example]$ pwd
/cs/student/dvanmali/cs56/cs56-rational-example
[dvanmali@butthead cs56-rational-example]$ cd ex01
[dvanmali@butthead ex01]$ ls
Main.java  Rational.java  README.md
[dvanmali@butthead ex01]$ javac Main.java
[dvanmali@butthead ex01]$ ls
Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex01]$ more Main.java
public class Main { // implicit: public class Main extends object

    public static void main (String [] args) {

        String usageMessage =
            "Usage: java Main int denom\n" +
            "  int and denom should be integers; denom may not be zero.";

        if (args.length != 2) {
            System.err.println(usageMessage);
            System.exit(1);
        }

        int num=1, denom=1; // must initialize to avoid "might not..." error
        try {
            num = Integer.parseInt(args[0]);
            denom = Integer.parseInt(args[1]);
        } catch (NumberFormatException e) {
            System.err.println(usageMessage);
            System.exit(2);
        }

[dvanmali@butthead ex01]$ ls
Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex01]$ more Main.class
▒▒▒▒









--More--(6%)
SourceFile
[dvanmali@butthead ex01]$ ls
Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex01]$ java Main
Usage: java Main int denom
  int and denom should be integers; denom may not be zero.
[dvanmali@butthead ex01]$ java Main 3 4
r1 = Rational@2a139a55
r2 = Rational@15db9742
[dvanmali@butthead ex01]$ pwd
/cs/student/dvanmali/cs56/cs56-rational-example/ex01
[dvanmali@butthead ex01]$ cd ../ex02
[dvanmali@butthead ex02]$ pwd
/cs/student/dvanmali/cs56/cs56-rational-example/ex02
[dvanmali@butthead ex02]$ ls
build.xml  Main.java  Rational.java  README.md
[dvanmali@butthead ex02]$ javac *.java
[dvanmali@butthead ex02]$ ls
build.xml  Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex02]$ java Main
Usage: java Main int denom
  int and denom should be integers; denom may not be zero.
[dvanmali@butthead ex02]$ java Main 3 4
r1 = 1/1
r2 = 3/4
[dvanmali@butthead ex02]$ java Main 13 42
r1 = 1/1
r2 = 13/42
[dvanmali@butthead ex02]$ ls
build.xml  Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex02]$ ant clean
Buildfile: /cs/student/dvanmali/cs56/cs56-rational-example/ex02/build.xml

clean:

BUILD SUCCESSFUL
Total time: 0 seconds
[dvanmali@butthead ex02]$ ls
build.xml  Main.java  Rational.java  README.md
[dvanmali@butthead ex02]$ ant compile
Buildfile: /cs/student/dvanmali/cs56/cs56-rational-example/ex02/build.xml

compile:
    [javac] Compiling 2 source files to /cs/student/dvanmali/cs56/cs56-rationexample/ex02

BUILD SUCCESSFUL
Total time: 0 seconds
[dvanmali@butthead ex02]$ ls
build.xml  Main.class  Main.java  Rational.class  Rational.java  README.md
[dvanmali@butthead ex02]$ ant run
Buildfile: /cs/student/dvanmali/cs56/cs56-rational-example/ex02/build.xml

run:
     [java] r.getNumerator()=5
     [java] r.getDenominator()=7

BUILD SUCCESSFUL
Total time: 0 seconds
[dvanmali@butthead ex02]$ cd ../..
[dvanmali@butthead cs56]$ ls
cs56-rational-example  lab00_dvanmali
[dvanmali@butthead cs56]$ cd lab00_dvanmali
[dvanmali@butthead lab00_dvanmali]$ ls
README.md
[dvanmali@butthead lab00_dvanmali]$ ls -al
total 20
drwx------ 3 dvanmali ugrad 4096 Jun 22 09:47 .
drwx------ 4 dvanmali ugrad 4096 Jun 22 09:51 ..
drwx------ 8 dvanmali ugrad 4096 Jun 22 09:47 .git
-rw------- 1 dvanmali ugrad  189 Jun 22 09:47 .gitignore
-rw------- 1 dvanmali ugrad   49 Jun 22 09:47 README.md
[dvanmali@butthead lab00_dvanmali]$ ls -a
.  ..  .git  .gitignore  README.md
[dvanmali@butthead lab00_dvanmali]$ more .gitignore
*.class

# Mobile Tools for Java (J2ME)
.mtj.tmp/

# Package Files #
*.jar
*.war
*.ear

# virtual machine crash logs, see http://www.java.com/en/download/help/error_
spot.xml
hs_err_pid*
[dvanmali@butthead lab00_dvanmali]$ emacs .gitignore
[dvanmali@butthead lab00_dvanmali]$ ls -al
total 20
drwx------ 3 dvanmali ugrad 4096 Jun 22 10:30 .
drwx------ 4 dvanmali ugrad 4096 Jun 22 09:51 ..
drwx------ 8 dvanmali ugrad 4096 Jun 22 09:47 .git
-rw------- 1 dvanmali ugrad  192 Jun 22 10:30 .gitignore
-rw------- 1 dvanmali ugrad   49 Jun 22 09:47 README.md
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   .gitignore

no changes added to commit (use "git add" and/or "git commit -a")
[dvanmali@butthead lab00_dvanmali]$ git add .gitignore
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   .gitignore

[dvanmali@butthead lab00_dvanmali]$ git commit -m "emacs Backup Files"
[master 184375f] emacs Backup Files
 1 file changed, 1 insertion(+)
[dvanmali@butthead lab00_dvanmali]$ git push origin master

(gnome-ssh-askpass:10447): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh-aass'
Username for 'https://github.com': dvanmali

(gnome-ssh-askpass:10452): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh-aass'
Password for 'https://dvanmali@github.com':
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 322 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To https://github.com/UCSB-CS56-M16/lab00_dvanmali.git
   d01e4d6..184375f  master -> master
[dvanmali@butthead lab00_dvanmali]$ ls
README.md
[dvanmali@butthead lab00_dvanmali]$ get status
bash: get: command not found...
Similar commands are::
'git'
'GET'
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
[dvanmali@butthead lab00_dvanmali]$ ls
README.md
[dvanmali@butthead lab00_dvanmali]$ ls ..
cs56-rational-example  lab00_dvanmali
[dvanmali@butthead lab00_dvanmali]$ ls ../cs56
ls: cannot access ../cs56: No such file or directory
[dvanmali@butthead lab00_dvanmali]$ ls ../cs56-rational-example/
ex01  ex02  ex03  ex04  ex05  ex06  ex07  ex08  index.html  LICENSE  README.m
[dvanmali@butthead lab00_dvanmali]$ ls ../cs56-rational-example/ex08
build.xml  javadoc  README.md  src
[dvanmali@butthead lab00_dvanmali]$ cp ../cs56-rational-example/ex08 .
cp: omitting directory ‘../cs56-rational-example/ex08’
[dvanmali@butthead lab00_dvanmali]$ cp -r ../cs56-rational-example/ex08 .
[dvanmali@butthead lab00_dvanmali]$ ls
ex08  README.md
[dvanmali@butthead lab00_dvanmali]$ mv ex08/* .
[dvanmali@butthead lab00_dvanmali]$ ls
build.xml  ex08  javadoc  README.md  src
[dvanmali@butthead lab00_dvanmali]$ rmdir ex08
[dvanmali@butthead lab00_dvanmali]$ ls
build.xml  javadoc  README.md  src
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        build.xml
        javadoc/
        src/

no changes added to commit (use "git add" and/or "git commit -a")
[dvanmali@butthead lab00_dvanmali]$ git add .
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   README.md
        new file:   build.xml
        new file:   javadoc/Main.html
        new file:   javadoc/Rational.html
        new file:   javadoc/RationalTest.html
        new file:   javadoc/allclasses-frame.html
        new file:   javadoc/allclasses-noframe.html
        new file:   javadoc/constant-values.html
        new file:   javadoc/deprecated-list.html
        new file:   javadoc/help-doc.html
        new file:   javadoc/index-all.html
        new file:   javadoc/index.html
        new file:   javadoc/overview-tree.html
        new file:   javadoc/package-frame.html
        new file:   javadoc/package-list
        new file:   javadoc/package-summary.html
        new file:   javadoc/package-tree.html
        new file:   javadoc/script.js
        new file:   javadoc/stylesheet.css
        new file:   src/Main.java
        new file:   src/Rational.java
        new file:   src/RationalTest.java

[dvanmali@butthead lab00_dvanmali]$ git commit
[master 14514ba] starting point ex08
 22 files changed, 3654 insertions(+), 2 deletions(-)
 rewrite README.md (100%)
 create mode 100644 build.xml
 create mode 100644 javadoc/Main.html
 create mode 100644 javadoc/Rational.html
 create mode 100644 javadoc/RationalTest.html
 create mode 100644 javadoc/allclasses-frame.html
 create mode 100644 javadoc/allclasses-noframe.html
 create mode 100644 javadoc/constant-values.html
 create mode 100644 javadoc/deprecated-list.html
 create mode 100644 javadoc/help-doc.html
 create mode 100644 javadoc/index-all.html
 create mode 100644 javadoc/index.html
 create mode 100644 javadoc/overview-tree.html
 create mode 100644 javadoc/package-frame.html
 create mode 100644 javadoc/package-list
 create mode 100644 javadoc/package-summary.html
 create mode 100644 javadoc/package-tree.html
 create mode 100644 javadoc/script.js
 create mode 100644 javadoc/stylesheet.css
 create mode 100644 src/Main.java
 create mode 100644 src/Rational.java
 create mode 100644 src/RationalTest.java
[dvanmali@butthead lab00_dvanmali]$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
[dvanmali@butthead lab00_dvanmali]$ git push origin master

(gnome-ssh-askpass:10566): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh- askpass'
Username for 'https://github.com': dvanmali

(gnome-ssh-askpass:10571): Gtk-WARNING **: cannot open display:
error: unable to read askpass response from '/usr/libexec/openssh/gnome-ssh- askpass'
Password for 'https://dvanmali@github.com':
Counting objects: 26, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (25/25), done.
Writing objects: 100% (26/26), 20.60 KiB | 0 bytes/s, done.
Total 26 (delta 10), reused 0 (delta 0)
To https://github.com/UCSB-CS56-M16/lab00_dvanmali.git
   184375f..14514ba  master -> master
[dvanmali@butthead lab00_dvanmali]$

```
