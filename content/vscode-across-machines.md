Title: Three reasons to use VS Code's integrated terminal
Date: 2019-10-16 10:20
Category: timesavers
Tags: Bash, VSCode, timesavers, IDE
Slug: vscode-across-machines
Authors: PK
Summary: Preserve your terminal history across machines, document your work while you're doing it, create runnable documentation - with VS Code

---------------------------
![Sheep]({static}/images/sheep.jpg)
> “Everyday, all day I have to be productive. And when I ain't productive, I get concerned.” - Young Jeezy
---------------------------

I'm an IDE sheep. I admit it. I've followed [Clint Edwards](https://clintjedwards.com/) to [Atom](https://atom.io/) and then to [Visual Studio Code](https://code.visualstudio.com/). I've been pleasantly surprised this, and generally [Microsoft's recent forays into the Open Source world](https://opensource.microsoft.com/) (including TypeScript & Go to Kubernetes). 

Many of the parts please me (Docker integration, plugins, polyglot progamming support, and debugging especially stand out) - but the killer 
feature for me is the [Integrated Terminal](https://code.visualstudio.com/docs/editor/integrated-terminal). You can set it up to operate just 
pretty much like your normal terminal (I use ZSH and thus .zshrc). More importantly, I've rigged it up such that pressing "ctrl-b" will run 
the line (or selected lines) in the terminal below where I'm editing. I demonstrate both here: 
<hr>
<figure class="large">
    <div class="myvideo">
       <video  style="display:block; width:100%; height:100%;" autoplay controls>
           <source src="{static}/images/ctrlb-vscode.mp4" type="video/mp4" />
       </video>
    </div>
<figcaption><i>(enlarge it to see the details!)</i></figcaption>
</figure>
<hr>

Cute, right? 
**Here are three reasons why VS Code's integrated terminal is not just cute, it's awesome.** 

## Document your work, while you work

When I'm trying to troubleshoot a problem, or just working with a new project on Github, I find myself trying a ton of things out on the
command line. I used to copy my history into a bug ticket or a note taking program like Evernote, or use [the IPython facility to 
copy work from a session](https://stackoverflow.com/questions/41070403/how-to-copy-from-ipython-session-without-terminal-prompts)

I realized that I could do this even more effectively by creating a directory of my notes, then opening it into VS Code. You can name the 
notes by the ticket identifer or try what's worked for me: [the superfolder system](https://github.com/galfarragem/superfolder). 

Anyway, because I can run the text that I'm typing into my notes, I get a nice REPL-y experience without compromising my ability to save 
what I've done for review later. 

<hr>
<figure class="large">
    <div class="myvideo">
       <video  style="display:block; width:100%; height:100%;" autoplay controls>
           <source src="{static}/images/pelican-example.mp4" type="video/mp4" />
       </video>
    </div>
<figcaption><i>(enlarge it to see the details!)</i></figcaption>
</figure>
<hr>

## Create runnable documentation

I've found that a lot of documentation or blog posts that I'm trying to use will contain commands that I try to run on my own machine.
My workflow for playing with something new - let's say, [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way/blob/master/docs/02-client-tools.md) - used to look like this:

<hr>
<figure class="large">
    <div class="myvideo">
       <video  style="display:block; width:100%; height:100%;" autoplay controls>
           <source src="{static}/images/kthw-hard.mp4" type="video/mp4" />
       </video>
    </div>
<figcaption><i>(enlarge it to see the details!)</i></figcaption>
</figure>
<hr>

It really sucks when things don't work the way you expected them to, or you need to add additional comments/notes for your future self to 
not hate life. Hell - it'd be nice to share an annotated version with my colleagues and friends!

So now - my "best self" copies the commands into my notes, and run them from there using the integrated terminal (as described above).
Let's take a look at how this goes with the same setup I did before: 

<hr>
<figure class="large">
    <div class="myvideo">
       <video  style="display:block; width:100%; height:100%;" autoplay controls>
           <source src="{static}/images/kthw-runbook.mp4" type="video/mp4" />
       </video>
    </div>
<figcaption><i>(enlarge it to see the details!)</i></figcaption>
</figure>
<hr>

You can see that I've annotated and commented a lot more. This isn't a great example of what actually happens, but imagine if people gave
you a runbook file like THIS when you started a new project, instead of some markdown or screenshots that you've got to copy/paste. 

---

![Runbook for MITM]({static}/images/proxy-runbook.png)

---

That's a realistic example of me trying something new and failing miserably is this file I used for [transparent proxy setup with MITMProxy](https://docs.mitmproxy.org/stable/concepts-modes/#transparent-proxy).


## Preserve your terminal history across machines

Perhaps my favourite use of the integrated terminal is related to runnable documentation - and that's the fact that you no longer have to 
rely only on the history you've got on the variety of machines to which you SSH. 

So in the normal course of a day on DevOps, I'd ssh into double digits of machines. Let's say I wanted to run similar commands on 4 VMs -
let's pick something trivial like finding all the java processes running there. I can just ctrl+b the following lines:

```sh
ssh machine-one.domain.com
ps -ef | grep java | grep -v grep | awk '{ print $1" "$2}' #find all java processes
```

and be on my merry way. I get to use the IDE functionality of VS Code as well, for example, to copy and paste in the names of all the hosts
that I need to get to - or use find/replace on a multi-line set of commands I'd saved for use elsewhere. 

There's also the fact that I can further annotate these commands for easy discovery later... more on this in another post.


## My Next Steps - aka other related things that I'll post for you in the future
- automatically extract out the silly prompt symbols (e.g. $, >, #) from project documentation
- more hotkeys for use with the integrated terminal! 
- storing your savedhistory in version control, and making it easier to search
- intelligent documentation / runbooks, using Jupyter notebooks 


# Extras
Did you like this? Want to discuss it? 
More ways to play are coming soon. But for now, email paulATirregularengineering.com 
to start a conversation (and get into our Slack community)

[Post History](https://github.com/irregularengineering/blogirreng/commits/master/content/vscode-across-machines.md)