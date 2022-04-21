# Linux, Python, vim & git 

# Beginning of Journal

--------------------------------------------------------------------------------
## Thu Apr 21, 2022

# Accelerate Your Life With vim Macros

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
















