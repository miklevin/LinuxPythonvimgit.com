---
description: Learn Linux, Python, vim & git To Obsolescence-Proof Your Future
permalink: /journal/
---
<!--
 _     _                  ____        _   _                      _                 _ _                        
| |   (_)_ __  _   ___  _|  _ \ _   _| |_| |__   ___  _ ____   _(_)_ __ ___   __ _(_) |_   ___ ___  _ __ ___  
| |   | | '_ \| | | \ \/ / |_) | | | | __| '_ \ / _ \| '_ \ \ / / | '_ ` _ \ / _` | | __| / __/ _ \| '_ ` _ \ 
| |___| | | | | |_| |>  <|  __/| |_| | |_| | | | (_) | | | \ V /| | | | | | | (_| | | |_ | (_| (_) | | | | | |
|_____|_|_| |_|\__,_/_/\_\_|    \__, |\__|_| |_|\___/|_| |_|\_/ |_|_| |_| |_|\__, |_|\__(_)___\___/|_| |_| |_|
                                |___/                                        |___/-->
## Beginning of Journal

--------------------------------------------------------------------------------
## Sat May 21, 2022
### Github Pages, Day 2

We're starting a lesson and will begin with a review of yesterday, but not
everything from yesterday, because we covered so much. We will hit the
essentials. Those essentials are:

1. We are using Linux through Windows Terminal.
2. From Windows Terminal, a.k.a. command-line or shell or CLI, which we know by
   the $ prompt, we can use such programs as:
   - vim
   - git
   - less
   - echo
   - ls
   - cd
   - pwd
3. For web publishing, git is the one we're using right now.
   - There is a publishing system built into Github called Github Pages.
   - Github Pages uses another system called Jekyll
   - Jekyll takes markdown files and turns them into pretty HTML files
   - Those HTML files are accessible from URLs such as:
   - https://natlevin.github.io/publishme/
4. We learned quite a bit about git
   - We learned some of it's history, that it was written by Linus Torvalds
   - We learned that a folder (a.k.a. directory) can get turned into a git
     repo (a.k.a. repository)
   - We learned that these git repos can also be kept on Github
   - We learned how to use git (a little bit)
5. These are the git commands we learned:
   - Start by going to the Terminal
   - cd to where we want to make a new directory from
   - mkdir newlocation
   - cd newlocation
   - echo 

So what is echo? Echo as a command, a.k.a. program that works like "print" from
other systems such as kornshell and Python. 

The trick with echo is that it's normal use is this:

    echo "Hello World"

But you can also use it like this:

    echo "# Hello World" > index.md

...which actually creates the file by "redirecting" the output of echo into a
file. This is similar to the "piping" trick we learned yesterday, but instead
of the pipe | symbol to a program, it's the greater-than > symbol to a file.
Using >> will make it create or append instead of create or replace.

Once the file exists, you can go into it with vim:

    vim index.md

Once you're in vim, you can practice markdown and macros.

Macros start by navigating to where you want it to begin.

This is often the beginning of a line for "easier control" reasons.

Hit the "q" key, and then one of the keys "a" through "z". I usually choose "a"
because of never having to think about it. I record a macro, it goes in a. But
this is a choice. These are "registers". They are the same registers you would
use the double-quote (") to copy into.

So macros go into registers.
Normal copy/paste can go into the same registers.
This may seem like a conflict, but it's really cool for pasting recorded macros
into your .vimrc.

If your .vimrc is already loaded, pasting a macro for permanent future use is
as simple as pasting it into the .vimrc and "wrapping" it in:

    let @x = '[paste recorded macro here]'

And from that point on whenever you run vim, you can play back that macro by
typing:

    @x

Once you've played back a macro, say to insert an html line-break, you don't
have to keep typing @x which is a little tedious. You can keep your finger on
the shift-key and tap @@ which will replay the last macro.

In such a way, you can run the macro on each line in a list, so long as going
back to the beginning of the line and down 1 line is at the end of the recorded
macro.

I do this particular macro so much that I actually haven't put it in my .vimrc
so that I keep reminding myself how to record macros and that it's a good idea.

foo bar<br/>
foo bar<br/>
foo bar<br/>
foo bar<br/>
foo bar<br/>

This has led me to such macros as turning...

    some-keyworded-image.jpg

...into:

    ```markdown
    ![Some Keyworded Image](some-keyworded-image.jpg)
    ```
Okay, so we have done some practice markdown. Next step, publish!

Save and exit.

Turn folder into github repository by typing:

    git init

Next, we add index.md to the new git repository by typing:

    git add index.md

Next, we commit the changes by typing:

    git commit -am "something"

The next step is on Github. We make a new repo using the + in the upper-right,
give it a name that matches the folder on your machine.

It's going to give the commands.

The 2nd to last line is wrong. It gives https where it should give
git@github.com.

To fix this, click "SSH" before copying the last 3 lines to execute. You should
see something like:

    git remote add origin git@github.com:miklevin/experiment.git



















--------------------------------------------------------------------------------
## Sat May 21, 2022
### Escape The Little Mouse

> I am okay.<br/>
> This is good.<br/>
> I'm getting a handle on this.<br/>
> I can see I leave myself in insert mode.<br/>
> I can see hitting esc is not good right now.<br/>
> While I'm relaxing I can stay in insert mode.<br/>
> Yeah. I got it. That's something I never noticed before.<br/>
> Escape is very much a mode change... a transition. Habit.<br/>
> But I don't need to keep hitting Esc... even though that is my habit.<br/>
> I can stay in insert mode and capture a thing or two about my...<br/>
> <br/>
> What that?<br/>
> What is that makes this different?<br/>
> I think it has something to do with the flow.<br/>
> Yeah. No mouse is a good start. But the Esc key is like the little
> mouse.<br/>
> But I control that little mouse like I control my state.<br/>
><br/>
> <cite>&nbsp;Mike Levin, 2022</cite><br/>
























--------------------------------------------------------------------------------
## Fri May 20, 2022
### I'm a git, you're a git, everyone's a git, git

This is one for the history books. I have taught my wife enough Linux to load
vim and enough vim to write Python. 

But what about git? Hmmm. I used to think that one should take up Python first
through Jupyter Notebooks, then put off Linux, vim & git for as long as
necessary until the time is right. Then Microsoft fixed the WSL install on
Windows 11 to merely just be:

    wsl --install

Then I realized the age of easy-install Linux was upon us. It can be done under
a still-working version of Windows, so you have all your drivers, device
support, game compatibility and whatnot. There's no searching around, making
decisions, choosing Linux versions. About the only decision is whether you type
that command from a DOS Command window (COM) or a Windows Powershell. Either
will do the trick perfectly well. But after the command finishes, you'll have
Ubuntu 20.04 (as of the time of this writing) installed and running right in
the window you ran the command from.

So, things are different. It is no longer necessary to defer the Linux and vim
part of the experience. Quite the contrary, the vim part of the experience is
so very challenging, central and pivotal to making the transition to... what?
Another kind of human being in the same way engineers, musicians and athletes
are other kinds of human beings, that the sooner you begin this transformation,
the better. The only reason I deferred this transformation in the past is
because of how hard it was to get an everyday Linux system. Before Windows 11,
the wsl --install step still had a few show-stopping steps that followed,
namely turning on the hypervisor and doing a few reboots. It was too difficult
for the mainstream. It is not anymore.

vim is too difficult for the mainstream, you say? Yeah, Microsoft'll have you
believe that. They bought Github, built-in Linux and hired the creator of
Python. But what are they going to do about vim? Crush it with VSCode, of
course! You will use VSCode. You can depend on that. Microsoft needs you to
depend on that, for if you learn vim, you will have a viable path to
platform-independence, and that can not be allowed.

So get your ass to vim! Do it now! It's already installed on your machine. Run,
Forrest, run! Use vim and don't ever look back!

{% include youtubePlayer.html id="zKr3dhdZMFo" %}

Once you're on vim through WSL, you're already on Linux. Use vim to make a
file:

    vim hello.py

From inside the file, learn enough vim to write and save:

    print("Hello World!")

The keystrokes by the way are:

    i
    print("Hello World!")
    [Esc]
    :wq
    [Enter]

Okay, now from the command-line that you've returned to, type:

    python hello.py

Hit Enter, of course. It shouldn't need to be said, but after venturing into
vim for maybe the first time, I guess it does have to be said. A lot of assumed
keystrokes in everyday instructions have to become considerably more precise
when discussing vim.

And you'll see the output of your Hello World program. Okay, so now you know
Linux, Python and vim.

But what about git?

Honestly, git's the hardest of my recommended set of tools now. Sure, Linux,
Python and vim have so very, very, very, very, very much more to explore and
learn. But look, you can be functional with all three in just a single sitting.

    wsl --install
    echo "print('Hello World!') > hello.py
    python hello.py
    vimtutor

Okay, so now you know Linux, Python and vim. The rest is details.

But there's nothing like this for git. git eludes. git is still mysterious.

git builds upon assumed Linux knowledge that one might not have.

git requires initialization.

git requires initiation.

Put off git until the time is right.

Nervousness, tap, tap, tap... all that code not backed up. No undo. No ability
to flow it onto other computers. A laptop crash would be devastating... tap,
tap, tap... still, no git?

But when will the time be right?

What's that Nat? You want to web-publish like I do? 

Well, I guess the time has come the Walrus said to speak of that great and
awesome git's other main contribution to the free and open source world. This
massive git of git's first and largest contribution of course being Linux
itself. Linus Torvalds wrote git. Linus named it after himself.

This is appropriate given Linus' awesome creativity inventing the product from
scratch, as Ken Thompson, the creator of Unix, will tell you about Linus and
Linux and Bitkeeper's creator Larry McVoy will tell you about git. I am quite
sure Larry called Linus a git before Linus named git git.

At least Linus knows himself well. However, this wants me want to bang my:

    git reset --hard HEAD^^^^^^^^

But I get ahead of myself. Let's keep the geek jokes to a minimum. They only
infuriate those sincerely trying to learn.

Nat asks to web publish like me. Okay, so it's time to teach her...

Github Pages!!!

Okay, take a deep breath. You thought Linux, Python and vim were challenging.
Okay, let's just start with Github Pages. Why? Because:

- It lets you publish markdown as web pages (no HTML-knowledge necessary)
- Creating a markdown is quick and easy in vim.
- It forces us to learn enough git to make a local "repository"
- It forces us to get that repository up on Github
- Then your website is just a few Github / Settings away.

Okay, assume being in a Linux terminal but with little Linux experience, either
on operation or terminology. It can all be rather intimidating and
overwhelming, so break it down Barney-style.

- First is explaining what a git "repository: is.
- Next is explaining what the git program itself is.
- Then we have to explain what using a command-line program in a terminal is.

Okay, here we go:

- git is a command-line program (probably already on your machine)
- We have to check if it actually is on your machine. 
  - It usually is on recent versions of Linux (which you are on)
- To check if we have git:
  - Open a Terminal, which is also known as:
    - A shell
    - The command-line interface
    - CLI
  - As an aside, the Window versions which are similar but not Linux, are:
    - COM (the command window)
    - Powershell
  - None of this will work from the Windows versions
  - You can tell the difference between them based on their prompt
    - Both COM and Powershell use the greater-than ">" as their prompt
    - Linux uses the dollar-sign "$" as its prompt

Aside from very few special cases, I am never talking about COM or Powershell.
These have very little use except to install Windows software. We used COM to
install Linux with the wsl --install command. That's the last we should ever
have to use COM or Powershell as far as I'm concerned.

But we now have the Linux command-line. The preferred way to get to the Linux
command-line (a.k.a. Terminal, Shell or CLI) is through the new Windows
Terminal program, available through the Microsoft Store.

I am about to show you how to use the git program from the Linux command-line.

So we have a Linux command-line open and ready to use. We have it by running
Microsoft Terminal. Our default is set to Ubuntu 20.04. If it's not, change the
default to Ubuntu 20.04. That way whenever we want a Linux terminal, we open
Microsoft Terminal and it's instantly there.

Go to your Linux command-line.

The next step is to show you how to read the git --help without needing to
scroll-up. We have turned off the ability to scroll-up in a Linux command-line
so that vim doesn't get messed up with the scroll-wheel. This is a good thing
and we should keep it that way.

To show git help, we type:

    git --help | less

Now we are displaying the output of git --help, but we are "piping" it through
the program called "less".

The above command should be read as: show git's help, but pipe its output to
the program called less.

Piping is sending the output of one program into the input of another program.
This allows us to read all the help easily, even if it's taller than the
screen.

What would normally "scroll past" us and be lost off the top of the screen is
now all sent into a program that lets you navigate the text with the same keys
vim uses, including the q key to get exit the "less" program.

Okay, a word about how git "fits into" the overall picture.

The tools I use are really just 4 (plus Jupyter), so 5, really. But Jupyter is
for learning. The first 4 I expect I'll be using till the day I die.

- Linux
- Python
- vim
- git

git is important because your files must be:

- In more than one place
- Optionally very, very secret. To your satisfaction... enough for a journal.
  Why?
  - Because Microsoft bought Github
  - Github is the most popular place for git repos
  - Microsoft has their reputation and stock value on the line
  - A leak of private info that is their fault will be on the front page of the
    newspapers the next day and make their stock value plummet, lose customers,
    lose faith, and begin an inevitable downfall of the company.
  - Microsoft will not intentionally let private repos leak.
  - Much more than a person's private journal is at stake. Proprietary code
    worth millions or billions is kept this way, too.
  - It is easier these days for your local machine to be hacked than for
    Microsoft to screw up with this.

What is a git repo, or "repository"?

It is a folder (a.k.a. directory). Those words are interchangeable.

The Linux command to make a folder (a.k.a. directory) is mkdir

When you run mkdir, it makes the directory in the location where you are in the
command-line.

So you want to look at where you are to make sure it's where you want the
folder to be made, and you can do that with:

    pwd

pwd means path of working directory.

The first step is to find out where the Operating System compels you to be.
It's always easy to start there. 

From that location, I create a github folder.

- After starting up your computer, it is a "blank slate". Nothing is running.
- When you run a Terminal (a.k.a. command-line, shell or CLI), you are "home"
- When you run pwd, you will see that home is /home/ubuntu/
  - This is where the (Linux) OS "compels" you to be... home.
  - It is from here, you mkdir... but with good nicknames.
  - The most important nickname in my mind is github.

So open a terminal and type:

    mkdir github

This is already done.

Now we can:

    cd github

To make ourselves "inside" the github folder.

- From inside the github folder, we can make new directories. 
- The names are important because those are about to be "repos". 
- Repos start out as ONLY git repos on your own (local) computer.
- Even when it's on Github, it can STILL be kept private (but not published as
  a website if you're using free Github)
  - Github lets you keep a few private repos
  - But you cannot share other people into them
  - And you cannot turn them into Github Pages websites
- For our purposes, we will need a public repo.

So we cd into github

Then we mkdir on a name that will soon be a public repo.

    mkdir publishme
    cd publishme
    git init
    ls
    ls -a

You can see that there is a "hidden" .git folder made as a result of git init.

    vim index.md

This is the preferred file-name for a homepage under the Github Pages
publishing system. Write some markdown.

    git status
    git add index.md
 
There is now a .git folder in this location. In the next step, we:

 - Go to github.com
 - We select the + in the upper-right and select "New repository"
 - We put our cursor in the Repository name box and type the exact same name as
   the folder we're working from on our local computer.
 - We scroll down and we hit "Create repository"

We go back to the command-line and type:

    git commit -am "My first commit"
    git config --global user.email "youremail@somewhere.com"
    git config --global user.name "Your Name"

In the above instructions the git config commands only have to be done once per
computer.

We're almost there.

    git branch -M main
    git remote add origin git@github.com:gitusername/publishme.git

This reaches a point where some special public/private key (file) generation
must be done. Usernames and passwords don't work anymore on a git push.

Of the work we've done so far, there's definitely 2 separate parts:

- That which is 1-time startup stuff
- That which is recurring every time stuff

It is time to figure out how to get rid of passwords on git.

    cd ~/.ssh

If it doesn't exist, make it.

    mkdir ~/.ssh
    cd ~/.ssh

From inside ~/.ssh:

    ssh-keygen -t rsa -C "email@address.com"

Hit Enter to keep the answers blank, which is fine.

Check git origin with:

    git remote -v

Set the remote origin to have the username in it. All git repos on your
computer (local) in preparation for going onto a website like Github (remote as
in elsewhere) need to have that elsewhere-location set. The below example is an
actual real-world example. It's nuts, but it really is
git@github.com:[username]. The username being embedded tells it from which
Github user it should look for a public key. Therefore we are going to have to
generate a public key and put it on Github.

    git remote set-url origin git@gihub.com:miklevin/pipulate.git

Conceptually, we got to the end in our earlier session. This last step of
pushing shows that "authentication" (like username/password) is so often the
most difficult part of an entire process.

Because Microsoft is fighting against hacking, they locked down the security on
Github. Using a username and password is no longer possible on things like:

    git push

For the same reason sites are insisting on 2-factor authentication these days,
Github is insisting on better security. Using a username and password is
actually less secure than alternatives that involve public/private key files.
These keys live in a very standard location on Linux. That location is:

    ~/.ssh

This is the same as:

    /home/ubuntu/.ssh

The dot before the folder-name makes the folder "invisible" just like a .vimrc
file. It's not supposed to show up in a normal:

    ls

...listing of a folder's contents. But it will show if you use:

    ls -a

...because the "-a" forces Linux to show "all" files, including those starting
with a period "."

So, then we have to actually generate those keys. The get created with a
command-line program called ssh-keygen. Like "git", ssh-keygen was already on
your Linux. This is because these tasks are so so common these days that most
modern Linux like Ubuntu 20.04 which you're using have it pre-installed. So you
don't have get it. 

The command we used is:

    ssh-keygen -t rsa -C "email@address.com"

Of course replace the email with the one you use for Github.

This command prompts you 3-times for things. None of them are important. You
don't need that level of security. So by just hitting Enter to each of the
questions, you will end up with 2 keys in that folder:

- id_rsa
- id_rsa.pub

The first one is the secret part of the key. It does not get given out. It
stays on your machine. It's no big loss if you really lose it one day, because
you can regenerate a new public/private-key pair. That's what these are. And
you would just put the new public key where it goes, Github, for example.

So the CONTENTS of the public key named id_rsa.pub is going to go onto Github.

Once it's there, this command will work, although you will have one more "yes"
to answer if everything is done correctly. After that yes, you will be able to
just "git push" whenever you like. The first git push has to be this (after
you've added the public key to Github).

    git push -u origin main

When a folder is turned into a git repo with the git init command, many things
are not set yet.

If it's the first time using git on that machine, some of these settings are
"global", meaning not for the repo in particular, but for your whole Linux
system.

When first we tried anything that actually tried connecting to Github, we
started getting challenged to meet its requirements, including setting our
email and name. Those commands it made us do were:

    git config --global user.email "email@gmail.com"
    git config --global user.name "Your Name"

Of course, replace with your own.

Now the "global" in these commands meant (as I NOW know) a .gitconfig file was
created in home, a.k.a. ~/.gitconfig a.k.a. /home/ubuntu/.gitconfig, and as
such can be edited with:

    vim ~/.gitconfig

...which contains:

    [user]
        email = email@gmail.com
        name = Your Name

That is just an FYI, little bonus. It was the first challenge of connecting to
Github. The 2nd challenge was much bigger because it first demanded a username
and password, and then told us that was not good enough, starting August of
2021. 

To get the public key onto Github:

    cd ~/.ssh
    less id_rsa.pub

Use your mouse pointer to click-drag from the beginning to the end (including
your email address). This requires Windows Terminal to be set up for
click-dragging to copy into the Windows OS copy/paste buffer. This is a very
good idea. Do it.

Next, you go to Github / settings / SSH and GPG keys

Click New SSH Key.

Give it a title like "My Key"

Paste the public key text into the Key field

Click Save SSH Key

Now the command:

    git push -u origin main

...will work. Almost there! Remember to answer "yes" to the question that pops
up. It will add github to a "known_hosts" file in ~/.ssh. You can go look at it
with vim because it's sometimes necessary to delete lines out of there.

Last (after a successful push):

- Go to Github / Repository you want to publish as a website
- Go to Github / Settings (for the Repo) / Pages
- Select Source Branch: main
- Hit Save

Your site is punished. It will give you the link.

From here on out:

- Edit index.md
- git commit -am "Something"
- git push

Git pushing will go smooth from here on out.

New files can be added, but you must also git add and commit them as well.

Refer to Jekyll documentation, especially regarding "Front Matter" to control
details like title tags and URL it gets published on.


--------------------------------------------------------------------------------
## Mon May 02, 2022
### Cure Anxiety Through Telepathic Control Of Text

Too many things in life lean towards aspirational in nature. That sucks. In one
of my favorite book series, The Chronicles of Thomas Covenant, the Elohim are a
race of infinitely powerful beings who endlessly create without limit, but with
to no real effect on the world. It's the other extreme personified where
nothing is aspirational because everything is easy and instant. They become
island-gods within their own minds. That sucks too. We live somewhere
in-between, starting ineffectual at birth unable to even lift our heads and
backsliding to ineffectual as the rigors of age seize us, until at last we
cannot lift our heads again. 

Life is lived in the vibrating edge. We are only here because of highly
improbable and only temporarily stable orbits. Forces existing at all
inevitably cause such effects as oscillation, rotation, heartbeats and such.
Around such temporary but still quite long-term oscillations forms life. The
life that arises is in just the same state of temporary orbit and oscillation,
until it isn't anymore. Any fool can put a fatalistic twist on this saying
“than nothing matters”. This is patently untrue. We have no idea how deep the
rabbit hole goes during the time we're here during “our turn”. It's a greater
epidemic of our time than the pandemic that children are not taught better ways
to think. 

I've got the cure. Information has something to do with it. Labels are stupid,
but the grab-bag of things the label “information” encompasses includes such
things as meaning and purpose in life, as well as the framework for some plans
by which someone can achieve that state you might call “effective” or
“satisfied” or what have you. Again, labels fail. But it's a combination of
things going on in your head, how it manifests or becomes realized in what we
call the objective or real-world, and how the results of that interaction
absorb back into you through your senses. So many people get stuck here falling
into the trap of what's called solipsism (so only I exist) and nihilism (then
nothing really matters). 

The only thing objectively real in this picture is information. Everything else
can be explained away as potentially an illusion or a trick of our senses. This
is called the problem of induction. Since everything you know comes to you
through your senses, and senses can be tricked, there's no way to know that
anything is 100% real. Certainly the fact that we dream alone tells us this.
And we live on the same basis as the legal system in that only because of a
preponderance of evidence and compelling consistency makes us accept that we
are interacting with others in some sort of common objective reality.  To not
believe this is to die sooner. I'll take my turn to play, thank you very much.
Accepting that there others much like us yet entirely different also in the
game is a critical step. That leads to the "correct" golden rule of "Do not do
unto others as you would not have them do unto you" among other game-theory
equilibriums.

Play? Game? But life is suffering and on the whole not worth it, right? Wrong!
Many aspects of life are indeed that way but because so much of what's
important is what's going on in your head, you can decide to live well. Make
the best of a horrid situation. Change your mind enough to subdue the
horridness into the new normal but plug your course to a better place. Endure
but forge on with purpose and vision. Don't regress to being a more basic
pre-meta-cognition animal whose only choice is to go into shock and die, or
live in sad paranoid fear of every shadow around the corner until you die from
a slower, more heartbreaking form of shock: giving up. 

Your brain re-wires based on the neuro-chemicals it's awash in. If you're
negative all the time, your brain molds negative. If you're up-and-at-‘em all
the time, your brain molds resilient. We make ourselves who we are once our
brain passed through the uncanny divide of being able to understand spoken
language. We become meta-creatures more so than our more base-animal brethren,
though they too have some bits of rudimentary meta-cognition. If you drop into
fight or flight at every snapped twig, you'll be addicted to norepinephrine,
always anxious and die at sixty. From the moment you think therefore you are,
you can start thinking yourself into being who you are. Before that, it seems
greatly luck-of-the-draw chance. 

So what's this cure I propose? How can you take control of your mind, then your
immediate situation, then your life? How can you move further from the reactive
base-animal side of the spectrum more towards the Elohim? Honestly the only
difference between the Elohim with god-like powers constantly materializing
things into this world fully-formed only to evaporate and swirl into the next
thing is that their stuff actually manifests momentarily into this world.
Otherwise, it's all thought. The only difference is that I guess they could
manifest some food, clothing and shelter if they really needed to to get their
basic needs met, and you and I have to work-for or inherit the goods.

These Elohim have what appears to be telepathic and instant control over energy
and matter. They are endlessly inventive and Every Little Thing becomes real,
no matter how momentarily. What I propose for you is a similar process. Ever
want to write and not be sure how? What to write in, a paper journal or
something electronic. If paper, what about your privacy, handwriting and
writing speed? If electronic, what about your privacy and typing speed? And
what about all that uncertainly of whether you're ever going to re-read it and
do anything with it? It can all be crippling and on the whole I suspect is a
show stopper for most people.

Well what I'm telling you is that this is a skill like anything else, but for a
few nuances and subtleties that make all the difference, which you really must
get down if you are to start improving your life. The first few subtleties are
in your mind, and the last few subtleties are about the writing tools. So first
you must realize that you never really need to re-read anything. Just the act
of writing has manifested the idea into a form of reality. That form of reality
is interoperable idea-encoding. You have ***encoded*** your thoughts into
manifest reality. Language is imperfect and full of lies. Gödel's
incompleteness theorems prove that no language is perfect. Live with it. This
does not invalidate the tool. No tool is perfect. Just accommodate. Wrap the
imperfections of the tools you choose into your "new normal" and if it really
bothers you, draw a little too. Study the language's blind-spots. Whatever.
Just don't give up on the idea of language and writing because there's issues.

Okay, so those are the things in your head you must get over if you want to let
idea-manifesting become an everyday skill and no big deal. That's a cornerstone
of every-little-thing-gets-done or ELTgd as I'm now accronymizing it. But what
about the tool things you must know. Every piece of word-processing software
you ever encounter will will let you down, but vim, emacs and their clones.
There is no lifetime commitment by anything other than vi(m) and emacs to be
with you for life. They are tied to companies, profits and the idiosyncratic
user interfaces and platforms of the times they were born. Not with vi(m) and
not with emacs. They are both the pee-in-the-pool of tech. They're in and
they're not coming out. You can rely on them to never let you down. 

What I'm telling you is that with vi(m) or emacs, you can always type and write
as if you were born with the skill if your writing-tool is either vi(m) or
emacs. First you lift your head. Then you crawl. Then you walk. Then you talk
and ride a bike. Then you drive a car. Then you type in vim. That
non-thinkingness that makes walking, talking and driving so second-hand applies
to to typing and manifesting ideas. It's not so right now in this world for
most people because of the tyranny of tools, the profit-incentive of companies,
the constantly shifting and changing shape of technology devices and their
software we collectively call "platforms". It's all moving targets that works
against your mastering writing, and thus your own mind and life.

That's a fact. I could go into the reasons, but that will be for another time.
You're going to have to trust me on this, that nearly telepathic control over
text that will last a lifetime and be possible on any computer is yours for the
taking. The only hitch is mobile that doesn't accommodate a full-size typing
keyboard quite necessary for the sort of fluidity and going into the zone in
vim and emacs that we seek. We deal with the mobile problem by copy/pasting
from the mobile writing app of your choice into vim or emacs at your first
convenient moment. Okay, so 2-devices in your life: one in your pocket (without
the magic editors) and one on your keyboard-equipped device such as a laptop
that does have a magic editor.

The sooner you can have nearly telepathic control over text the better. That's
just the modern world. Pushing text around and transforming it in various ways
for various purposes, is power in today's world. And barring anything but
Armageddon where hunting and looting skills are the only thing that will
displace it, it's going to stay that way for the foreseeable future. Why does
nearly telepathic control of text cure anxiety? Because it gives you something
do to when the fight-or-flight reaction kicks in. Instead of scanning,
scanning, scanning for the danger and the next thing to be angry at and blame
for your problems, you can fire up vim and start typing and face your fears.
Start peeling away the layers of what's really going on. Always have a
psychologist on-hand in the form of your own self. You are your best
sounding-wall. You are your best therapist. You can listen to yourself forever
while you type, tapping many of the same resources you would paying for a
therapist to listen, but you won't run out of time or have the additional
anxiety about whether to be 100% truthful with another human being over shame
or whatnot.

Tools, tools, tools. It'll take you a long time to get there. But it gives you
a solid, concrete thing to work on. As you master vim through journaling, you
can start to do other things like blogging (publishing the bits you want to
share), coding (using vim but with language-syntax rules), writing your resume
or whatever. Being able to type well and write well is an eternal timeless
skill. It is an asset inside of you that can't be taken away. And so long as
your editor is vim or emacs, even the software can't be taken away through
user-interface evolution, upgrades, platform-shift, expiring licenses, and all
the other reasons no other text-editor or word processor will be with you for
your entire life. Only vim and emacs "internalize" into your body as
forever-skills. One day you can write their source code and binaries into your
DNA because their licensing allows it. Try doing that with Microsoft Word or
Google Docs!

Get Linux. You don't have to run a Linux desktop or even make Linux the main
operating system you boot into. If you're on a Mac, it's based on Unix which is
close enough. It'll run emacs or vim. If you're on Windows, get Linux (probably
Ubuntu) from the Microsoft Store. It'll install. There's some tricks to it
still today, and you don't necessarily want a Linux desktop running
side-by-side with a Windows desktop. That's just confusing. Avoid ziggurats of
this-contains-that-contains-that. Just get text-base Linux and run it in a
terminal. Oh, also get Windows Terminal. That is how you will access Linux.

Once you have Linux, run it through Windows Terminal. vim is already installed.
That's one of the things about vim. It's ubiquitous. And unlike emacs which
requires lots of customization to "settle in" and make it familiar and usable,
pretty much every copy of vi, vim, neovim or all the other clones out there are
the same. You can be functional right away wherever and whenever (100 years in
the future for sure) you sit down. At most you need to drop 1 configuration
file in location (your .vimrc) to make it even more comfortable and familiar.
But anyone adept at vim doesn't really need their personal .vimrc
configurations to be in business right away. They can't take that away from
you! 

Now type vim in the terminal. To quit vim, type:

```bash
:q[Enter]
```

There, now you're initiated into vim. To learn what the heck is going on and to
start down that path of nearly telepathic control over text that I'm promising
you, type in the command-line of Windows Terminal from the command-prompt
(after you quit vim):

```bash
vimtutor
```

Follow the tutorial. Learn how to move the cursor around with h, j, k & l.
Learn that even arrow-keys are unnecessary. Absolute key-press commands that do
things ROCKS! Your muscle-memory will sing for joy, and the same strange
mechanism about human beings that makes the complexity of driving second-nature
and not even something you think about will start to happen with text and
typing. You'll learn to do such things as choose your text-width, allow "hard
returns" to wrap your text, and to reformat it with a magical [Esc]vipgq[Enter]
command. You'll curse the [Esc] key but understand that no tool is perfect, and
that's the price of vim. You can rebind the Esc key to something more
convenient and understand that you're coding a .vimrc configuration file
dependency, but that might be okay because you can recreate it from scratch in
moments on a new machine on which you're using vim.

Start out with just a personal journal. You won't have that much pressure on
yourself to code or whatever. In the process of journaling to cure your anxiety
you will be mastering a skill that will serve you for life, and I promise you,
put you in another class than other people. I don't mean to be classist or
anything, but honestly vim (vi, neovim, whatever) will put you in a class above
all other information workers in the high tech economy. And emacs will put you
in a class above vi\* users, but that'll be the subject of another article.
Even if you use vim and want to move onto emacs, one of the most popular emacs
tricks is to emulate vim.

No project should be your one big project. Too much emotional investment in any
one material product or undertaking sets yoy up for excessive disappointment.
Failure happens. There will be failure over and over. Honestly, this is one of
the big tenants of what life is about. I've got 99 failures but giving up isn't
one. That being said, try to make one text-file (journal.txt perhaps) that will
be your one personal journal for life. You can edit other files, but this one
is special. You can start it today. Make it safe by signing up for Github and
use a private repo to keep your journal there. Sure, there's risks, but use
good "digital hygiene". Use a good password and 2-factor authentication.
Microsoft owns Github and they don't want your private stuff leaking any more
than you do, so it's a pretty good solution for a place to keep a private
journal these days.

As far as privacy on your own machine, keep your journal on the Linux side of
your Windows machine. Let's see a snooper find it there where only the
command-line provides easy-access to the file-locations, hahaha! Yeah, there's
lots of ways to go about addressing the privacy and security when journaling,
but learning vim and keeping it in Linux is best, I assure you. There's further
measures you can take, but that just causes artificial inertial resistance. You
need to do everything you can to build motivation and momentum at this point.

And so that's it. Once you can control text nearly telepathically, and thus
exercise your mind, administer self-therapy and develop self-discipline
(journaling daily), you will have in-roads into countless other things. Put
"proficient in vim" on your resume. I assure you it'll be a
conversation-starter 'cause it really does differentiate people. Learn how to
code-up a FizzBuzz example and you'll be more qualified for entry-level
programming jobs than most people coming out of school who haven't mastered
vim. Honestly, vim is an professional and personal self-journey and education
that may be more valuable than college. It'll certainly be the one practical
skill that will be with you for life no matter what else happens, short of
Armageddon. And vim'll probably help you during Armageddon too.

Don't give up. You will be discouraged getting started. There is a deep
learning curve. To give up is to hand over the reins of your life to some other
person or agency. So often it's moving back in with your parents rewarding some
narcissistic need in them, ironically for them failing at their job to get you
ready for life on your own. Come back home little bird because I never taught
you to fly right. Now go fetch me some worms so I can go full-circle and turn
child into parent-like provider. I'm helping you learn vim so that your
dependency on other people for lack of skills just won't happen.

There's something to be said for interdependence and “it takes a village”. The
thing to be said is that if you want that but you find yourself not in that
situation, you've got to start finding your village or tribe, petition for
membership, and lacking any clear valuable contributions you can start making
immediately, start at the bottom-rung clique or cast-wise. Yup, there's cliques
and casts in tribes and villages. Everyone knows everyone and are all up in
each other's business. It's what drive adventurous males out of those cesspools
to make it on their own and perchance return in a better position. 

Every idea has been had so no idea you have matters, right? Wrong! No idea has
been expressed in precisely the way you do. Your interpretation, nuances,
delivery, timing and indeed audience will be different. You can see that in how
I wrote this article. It's all been said many times before by many other
people. Likely someone working in emacs has said it far more beautifully with
far less keystrokes in an operating environment of their invention. But that's
a story for another time. There are may sort of wizards in this world and at
the top of the wizard hierarchy are emacs users. I'm teaching you simple
carpentry here with vim. Hammer and nail stuff. Learn vim and everything looks
like a nail.

Nailed it.

--------------------------------------------------------------------------------
## Sun May 01, 2022
### Let Me Introduce You To LPvg & ELTgd To Save The World

Hello May! Come what may. This is month 1 of the 2 months I've got left at this
comfortable little mountain cottage in the Poconos in the same neighborhood
where I skied with my family growing up. I was a Philadelphian all my life,
then I was a New Yorker for 15 years. Covid struck and I made like a shepherd
and got the flock out of there.

Now my lease is up and it's time for a change again. I honestly don't know
whether I'm going to be in the mountains for another 2 years or back on Staten
Island where my kid is homeschooled. But either way, I've got an itch that's
been with me for the better part of my life, and it's time to scratch it.
You're here for the scratching.

So let's launch this site properly, with my seminal article on a topic of
passion. I've got 2 new little acronyms for you that will change your life:
LPvg and ELTgd. Of course LPvg stands for Linux, Python, vim & git as is the
domain name of the site you're on. 

ELTgd stands for something whose reality is confirmed by the fact you're here
reading this. For you see, I'm an SEO (search engine optimizer) and getting you
here is what I do. Making connections invisible-handedly is what I do. So, hi.
Nice to meet you. You'll be seeing me again because whatever you searched on or
whatever link you followed, you will again because you did ones. So stop reading
if you will, but I'll see you soon. 

Every Little Thing Gets Done. Or, ELTgd. That's my new mantra now, Instead of
ELPGD for Every Little Thing Gets Done which resonates ***Help God***, which
I've been toying with lately. I'm improving it to ELTgd which resonates ***Felt
Good***. Yup. When every little thing gets done, it feels good. Recently, I've
started dispensing with a number of those little “makes all the difference”
projects. 

LPvg stand for Linux, Python, vim & git as anyone who follows me even a little
bit probably know by now. The v and the g are lowercase because vim and git are
always presented in the format of the UNIX/Linux commands they represent. Linux
and Python are more commonly presented as proper nouns. I lowercase the g and
the d in ELTgd just to make the acronyms pair well as a set—a strong mental
model, one leading into the other, making the connection between the two and
downplaying the actual effort that goes into the “getting done” part once
you've mastered LPvg. 

I'm a Jew and I'll write God freely, but each time I do I feel it in my gut.
Thing is I'd feel it if I wrote G_d or ה' or what have you. All the same.
Invoking the name of something beyond comprehension of us limited beings inside
the system. It's not blasphemy but if there is God or some super-being outside
the system looking it, it may very well be grepping references to itself,
curious about our striving to divinity ourselves. A lot in the Bible rings
true, not on a dogmatic belief sense, but in a good, solid SciFi sense. There's
a lot of likely scenarios in there and solid channeling of human nature
truisms. 

So do I believe? Okay, here's my religion. We exist. We exist in such a way
that we can ask and struggle with these questions. We arrive for meaning and
purpose, or at least enough reason to stay engaged in a game that seems like a
whole lot of unnecessary suffering. And so I believe that the nature of life
and existence is somehow tied to that very fact. Life is tragic and horrible
and there is much that can crush the soul, blah, blah, shut up! Shut up and
calculate. Yup, Douglas Adams probably states my worldview and religion best.
We're some kind of computer here to answer exactly the sort of questions that
have always plagued humanity. And we're mortal and we die and there's suffering
because it's required… at least for awhile. 

The unanswered question is whether that thing we sense and value as a sense of
self is merely an emergent property of cohesive blobs of autonomous matter or
whether, probably at the moment of conception where the 22 genes are spun like
the bullets in a game of Russian Roulette, we act as a sort of antenna tuning
in and becoming automated my what turns out to be the essence of who we our.
Our “vibe” such as it were. 

People deliberate whether there's fundamental particles smaller than quarks.
How could there not be if e=mc^2? Does that not mean that the smallest
wavelength of light/energy is the universes' pixels? And within one quanta is
it not reasonable to assume there's still some infinitely variable component
that keeps popping up as a string or a vibe or a loop or whatever? It seems to
me we intellectually have the whole picture and the grand unified theory of
everything is just a formality. 

So time is if the essence. Real or not, it's at least a derivative commodity of
great value we're issued a bitcoin hash on the blockchain. Who cares if we're a
hologram on the surface of infinitely nested black holes and virtual realities.
The fact we so fiercely feel we exist validates our very existence and makes us
at least of interest to other beings possessing that quality we call
consciousness. But again who cares? If such creatures don't exist as
non-terrestrial beings, it seems quite certain we'll make them here on Earth,
and we're going to have to throw our hat in the ring with some real badasses,
in a Darwinian sense. We need not be paper clips if we raise our machine
children like responsible and living parents. 

So RBI's and more we'll see in our lifetimes. To the nattering nabobs of
negativism who keep proclaiming the end of the world and are currently jumping
on the Gorey 2050 deadline, I give two simple counter-arguments. One: we're
still here. If your level of pessimism were correct, we'd have wiped ourselves
out with atomics a lifetime ago. We didn't. Almost coulda woulda shoulda won't
even win you a tiny stuffed animal at the carnival. Nope. We won. Pessimists
are wrong. Optimists have a firmer grip on reality in their faith in human
nature. Glad pessimists don't have their finger on the button or they would be
right and you wouldn't be reading this. 

The second argument is free energy around the corner. In just the next 30 years
relying cycle is done. Big oil and Detroit can no longer stem the tide. A
thousand points of light will be collecting a functionally infinite amount of
light. Solar getting more efficient is not 30 years away. It's a steady tic tok
of incremental progress. Actual trees and plants that do it naturally are being
recruited to the cause. 

Tech progresses exponentially and some of it is irrepressible. What pays it's
for it? The sun! Just 3D-print more solar panels and zap the power around with
forever improving batteries and superconducting material. A crossover will
occur where hydroponic like tech will outpace deforestation and killer drones
will cut down those who illegally cut down the irreplaceable resources of
nations. In time, the Sahara Desert could be green again, such is the
exponential power of tech once you plug in the functionally free energy. 

Carbon in the atmosphere? No problem. Turn it back into trees in a thousand
creative and world healing ways. It won't be so hard once high schoolers can
tackle the problem and at the same time earn themselves a vocation, a calling,
and obsolescence-proof skills for a lifetime. The only thing keeping
atmosphere-bound carbon bound is energy. Life uses energy to collect carbon.
Burning once-living matter (mostly ancient gooified scale-trees) releases that
carbon. Sounds like the perfect problem for humans to tackle, and we can
badmouth our predecessors all we want if you really need something to bitch and
gripe about. 

So how does a humble single individual help move the world towards this vision?
By example, of course! Have some impact as an individual, no matter how small
and seemingly indirectly connected to the solution. For my part, I'm going to
teach people how to have the knowing and doing of things in a way that requires
no college diploma, is completely compatible with pursuing one anyway, and will
give you the decisive advantage over those who only have the diploma.  

I will teach you Linux, Python, vim & git. I will tackle and get done every
little project. Whenever a little thing comes up that I think will improve my
life and the lives of others, I will do it. I will get it done. You will know
it because I am a search engine optimizer and you found me once, so you will
find me again. That will be part of the effect of me getting every little thing
done.


--------------------------------------------------------------------------------
## Thu Apr 21, 2022
### Accelerate Your Life With vim Macros

Look for the little accelerators. It's the little things in life that make all
the difference, like being able to record and play back macros with ease. vim
macros in particular are an accelerating force that once you start using, you
can get better at them for the rest of your life with no real major setbacks
via the giant reset-button of text-editor disruption. 

## Yet Another Macro System?

I have memorized, practiced and committed to muscle-memory the macro-system of
at least 3 different editors over the years, each time with my world being
rocked when the editor stopped being supported or whatnot. I plan on the vim
macro edit/playback system to be pretty much the last one I will ever learn. If
you want to do any better than this, you should switch to emacs which is
fundamentally based on the concept of macros (eMACS). But if you're a vimmer
like me, there's a few simple tricks you need to learn.

## Buffers a through z

First, you need to understand that vim has 26 buffers that are used for "named"
copy/paste in combination with the double-quote (") character. So you have to
use the Shift+' to get a double-quote which makes all named-buffer operations a
tiny bit more complex than if it were just a single-quote. But so be it. Get
into the habit of doing operations like:

    "add

...to copy the entire current line (including line-break) into the buffer named
"a". When you want to paste from that buffer, you reverse the process with:

    "ap

The way to visualize this is that any of the copy or yank operations that are
commonplace in vim can be preceded by:

    "a
    "b
    "c
    "d
    ...and so on

## And Yet Still It Eludes Me

I've been using vim for 10 years. I still haven't committed this to
muscle-memory. I use macros plenty. I copy/paste plenty. But I don't use the
named buffers without struggling every time. That stops today. It's difficult,
but first you need the basic realizations and strong mental models.

The strong mental model is that nothing you to today (if you already copy/paste
in vim) really changes all that much except that you have an "addressing
system" before any of your current operations. That addressing system uses the
double-quote and ONLY the double-quote. Because single and double quotes have
different meanings under different contexts (or sometimes the same meaning),
I've had trouble with this. This is one of those instances where it's only and
forever the double-quote, and it's only before the characters a through z.

## The Fonz & Edgar Allan Poe Help Me Remember

A cute little mental game you can use is like Poe's Quoth the Raven "Nevermore"

Quoth the "ayy

Would that be like Poe or Fonzie? Well, all the more reason to remember it.
Ridiculous juxtaposed associations help memory, and in this case it's both
Edgar Allan Poe and The Fonz who help me remember that to yank the entire
current line that your cursor's on into a buffer...

    Quoth The Fonz "ayy

Okay, that'll do. I think I'll be able to remember named buffers now.

## Macros Use vim Key-Buffers Just Like Yank/Delete

Now that you know that you can drop text into named-buffers a through z, you
should also know that when you record a macro you are putting into these exact
same buffers. This is important because you can paste from out of a buffer, and
you can paste recorded macros into your vim configuration file (~/.vimrc) the
same way you would paste any other text. This is a major convenience because
there are many special characters you will encounter that are quite difficult
to type properly, such as symbols that show as ^M, <80> and ^[. These represent
the Enter key, Backspace key and Escape key respectively, but you can't just
type them with the caret symbol plus displayed symbol as it would seem.

## Typing vim Control Characters Without Recording

You CAN type these special control characters in vim by going into insert mode
(hitting the "i" key) and then pressing Ctrl+v followed immediately by the
special key like Esc or Enter. In this way you can actually construct macros
without recording them. Or you have a bit more control when editing a pasted
macro, if even only to know what the heck you're looking at. But for the most
part, after you've recorded a macro you simply paste it from the buffer that
you recorded into, surround it in single-quotes (') and set it equal to a macro
key-combo, which are always the "@" symbol plus a character from a through z.

## Recording A Macro In vim

One of the biggest annoyances in vim can be turned into one of the biggest
improvements in your life. Too often new vimmers hit the "q" key by accident
when they're not in Insert-mode. Hitting q starts the macro-recording process.

When recording a macro, the "q" key works much like the quote-key (") when
preparing to yank/delete text into a buffer. So if you wanted to record a macro
into buffer "a", you would:

    qa[type whatever you want to record]Esc+q

## A Tale Of Two Q's

And whatever you recorded is now in buffer "a". The reason I put the Esc key
before hitting "q" to end macro-recording is because very often you are in
Insert-mode in vim, so hitting q in Insert-mode would just type a "q". In all
cases an Esc will be hit SOMETIME before hitting q to stop the recording. It's
really annoying to edit a macro after recording it, so it's good to get into
the habit of recording it well. So get in the habit of making sure you're not
in Insert-mode before hitting "q" for the second time to stop recording the
macro.

## Walk The ATAT Through Your File

Now that your macro is in buffer "a" you can play it back with @a. If you
recorded the macro into buffer "b", you would play it with @b. And because one
of the most common things to do with macros is to play the same one over and
over (to process each line in a list for example), vim gives you the delightful
shortcut "@@", leading to one of my favorite jokes: Just walk the ATAT through
the file. Star Wars fans might get it.

It's important to note that even though I put quotes around "@@" when talking
about it, I really mean just:

    qaifoobar[Esc]q
    @a
    @@
    @@
    @@

Will output:

    foobar
    foobar
    foobar
    foobar
    foobar

## Enter Your .vimrc vim Configuration File

Okay, so once you have a macro in a key-buffer, the trick is to paste it into
your .vimrc file. You may or may not actually have a .vimrc file when you start
out. It's a file that you make and curate over time with your settings and
preferences. It's a good decision to make a git repo and put a copy of your
.vimrc file in it and update it whenever you make a change to the one that's
actually in location on your system. 

## You Have Your .vimrc In A Git Repo, Right?

In case you're wondering, you can't make your live-.vimrc as part of a repo
because its location is not suitable as a git repo, being your actual
/home/[username] location (a.k.a.  "~/") or some other location which you can
mostly ignore because it's rarely used.

## Use Helper-Scripts Sparingly

I used to keep a script to automatically copy my .vimrc file into a vim git
repo, commit and push it up to Github. Over the years I found that to be silly
and have just gotten into the habit of whenever I changed my .vimrc (which
isn't that often) to simply:

    cp ~/.vimrc ~/github/vim/
    cd ~/github/vim
    git commit -am "Latest updates"
    git commit
    git push

Doing a little series of commands like this instead of a script-file gets you
into a good mindset. While helper-scripts are nice, it's like making up words
for things you say all the time that only you will ever understand and which
go away when switching machines. Avoid helper scripts when they cut into your
natural literate expressiveness.

## Editing Your .vimrc With Another File Loaded

It's natural to want to edit your .vimrc with another file opened. You're
probably going to be recording that macro in some file. The good news is that
those key-buffers a-z are in common to all files you have loaded during that
vim session. In other words, you can have whatever file you're editing loaded
along with your .vimrc, and that is how you can paste the contents of your
macro into your .vimrc. And THIS is the million-dollar trick to improve your
effectiveness over time.

You create and edit your .vimrc file as you would any other file in vim. And so
you can actually use vim document buffers to load your .vimrc at the same time
as any other file you're editing:

    :badd ~/.vimrc
    :bn

## Navigating vim Document Buffers

Document buffers are not like key-buffers in that they're not bound to keys a
through z. You simply cycle through through them with :bn for next-buffer, :bp
for previous-buffer or :b1 for the first buffer (it's not zero-based) or :blast
for the last buffer and so on.

In this way it is very easy to have just two documents loaded in vim because
:bn basically cycles between them.

It's also worth noting that as you research editing multiple documents in vim,
you will also encounter a more visually oriented "tab" system. In other words,
vim has tabbed editing modes that simulate a windowing environment where you
can switch between documents by selecting different tabs. This is not the way
to go in vim. It will only slow you down. Learn the document buffer system with
such hits as:

    :ls (lists all your buffers)
    :e (Shows name of file you're editing)
    :e [filename] (Jump to buffer containing that file)
    :b [filename] (Jump to buffer containing that file / better command-line completion)    

So it's really quite easy to navigate around tab-less buffers in vim and you
will get faster and faster over time without being hobbled by the more
graphical user interface conventions that have infiltrated vim.

## Displaying vim a Through z Registers

To show everything you've copied into your a through z registers in vim,
including whatever macros you've recorded, just type:

    :reg

Or:

    :registers

Many things in vim are this way. There's a shorter version that everyone uses
which works. But then there's the longer verbatim version.

## Pasting Your vim Macro Into Your .vimrc File

So once you have both the file you're developing your macro in and your .vimrc
loaded and you're happy with your macro and you've viewed it with the ":reg"
command, you can switch to your .vimrc file with :bn and paste the macro in.
You'll want to steer your cursor to where you want it to go, insert an empty
line, and paste it from your buffer:

    jjjjjj (to position)
    Shift+O (insert blank line)
    let @x = '[Esc] (Start command that will bind macro to key-combo)
    "ap (paste from the "a" buffer) 
    Shift+a' (Go back into insert mode via-append and close string with single-quote)
    [Esc]:w[Enter] (Get out of insert-mode and save file)

You may not understand everything that you pasted. There's a lot of
control-characters in there which make vim macros uniquely hard to edit.
Additionally, there are various macro-building techniques that achieve effects
similar to parameters and arguments for a macro (involving relative-to-cursor
copy/paste tricks) that I'd love to talk about here which are outside the scope
of this article.

## Quit & Load vim To Activate Revised .vimrc

Errors will occur. If you make an error editing your .vimrc file, vim will tell
you when you load it. Once you edit your .vimrc file you have to quit and load
vim to have the new .vimrc active. That's when it will tell you if an error
occurred. The most common thing is not closing your strings (single-quotes
around the macro).

--------------------------------------------------------------------------------
## Wed Apr 20, 2022
### Become Obsolescence-proof & Disruption-resistant

Learn Python, vim & git and become obsolescence-proof and disruption-resistant
in tech and life. I'm not talking about Linux desktops. Desktops don't matter.
I mean old-school Linux, Python, vim & get which you get to through the
Unix-like type-in terminals built into Macs and easily installable as the
Windows Terminal through the Microsoft store. It doesn't matter what platform
you're on: Windows, Mac or Linux. You can get started on your journey to
obsolescence-resistance and disruption-proofing today. I'm not in this for the
money. I'm one of those unicorns on the net, sincerely here to help.

It's going to take some discipline.

{% include youtubePlayer.html id="njDLNt-1ugM" %}


