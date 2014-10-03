Getting Started With Jekyll
===========================

Making a webpage is easy. Making a _website_, with a standard layout made of consistent 
headers, footers, and all that shiny gets harder with each page you add to the site. To
make it all look like you know what you're doing (and you _do_ know what you're doing, 
right?) it all has to look the same. And what happens when you get bored with it and 
want to redesign it? You have to do it all over again by hand.

Or not. Half the fun of being a dev is that you can use tools (or write them yourself)
to deal with all the tedious stuff so you can get to the fun bits. One really great 
tool for building websites and blogs is called Jekyll. It's a command line tool for
creating websites that handles all the repetitive stuff for you.

Today, we're going to go over 
    * Installing Jekyll in your c9 workspace
    * Creating a new website
    * Writing a blog post
    * Hosting it on GitHub for free
    
Installation
============

Jekyll depends on a program called Ruby. Ruby is a bit like NodeJs in that it
it runs programs written in a specific language (Ruby) and has a package manager
called Gem that can be used to install programs written in Ruby, like Node's Npm
program. Normally, you'd have to install Ruby yourself, but the good news is that
Ruby comes pre-installed in every Cloud9 workspace. To install Jekyll

```
gem install jekyll
```

Creating a New GitHub Repo For Your Site
========================================

Go ahead an open a tab with GitHub (login if you're not already) and a tab with 
whatever Cloud9 workspace you're going to use. If you don't have a workspace set 
up, a simple HTML5 one will do.

Github will host a website for each user and organization for free. Using this 
feature is actually really easy. If you create a repository on Github and name it
in the pattern yoursusername.github.io, GitHub will host the files of that repo 
at that URL, provided that repo contains a website. Even better, GitHub supports 
Jekyll projects out of the box, so our Jekyll projects will automatically be built 
into websites.

Let's start

    1.) Switch to your GitHub tab. In the upper-right corner, click +, and then 
        click New repository.
    2.) Give it the name [whatever your github username is].github.io - Make sure your
        username is spelled correctly (I screwed this up once and it took me all 
        night to figure out that was what I'd done wrong *facepalm*)
    3.) Check the "Initialize this repository with a README" box
    4.) click the "Add .gitignore" button, type in jekyll and select "Jekyll" from
        the dropdown.
    5.) Click "Create Repository"
    
Now that you should be at the main page for your newly created repository. On the
right-hand column, towards the bottom, there should be a widget to copy the SSH 
clone URL. Click on the clipboard to copy that link. Now let's switch to your c9
workspace tab. Your bash command line should be at the bottom of your screen.
Type:

```
git clone [hit Ctrl+V to past the SSH URL here]
```

and then hit Enter. The prompt may give you a gibberish warning, just type "yes"
and hit enter again if it does. Git will create a new directory for your repository
with a brand spanking new empty README.md file ready to go. Now we can use Jekyll
to create a new projet in our repo directory. 

PROTIP: When you're using the command line, if you hit Tab, bash will autocomplete
a lot of stuff for you like directory and filenames, command names, all kinds of 
stuff. For instance, you're about to feed the Jekyll "new" command the directory for 
your website repo. That's probably really long and you may not feel like typing it
all. So just type the first few (like 3) letters, hit Tab, and let the command line
complete it for you. 

To fill our repo directory with all the stuff Jekyll needs to do its magic, we type

```
jekyll new [whatever your repo directory is] -- force
```

We need the "--force" switch at the end, because otherwise Jekyll will whine and cry
because the directory you're giving it already exists and has stuff in it.

Hit enter on that magic spell and watch a shiny new blog all your own appear out 
of nowhere. Your repo directory is now filled with a bunch of new files and folders
and even has a couple example pages in there to show you how it all works. In 
addition to having commands for creating and building projects, Jekyll comes with 
a simple HTTP server command we can use to view our sites as we work on them. Lets 
actually take a minute to fire our sites up right now and take a look at what 
Jekyll has given us to work with.

In bash, navigate to your repo directory and type:

```
jekyll serve --host $IP -- port $PORT
```

The "--host" and "--port" switches are needed in our c9 workspaces in order to point
the "serve" sub-command to a place where we can see what it's serving us. The site is 
actually viewable to the entire Web right now and here's how to see it.

[your workspace name]-c9-[your Cloud9 username].c9.io

for instance I have workspace named "sparkclub" and my c9 handle is "themooserooster"
so when I serve a Jekyll site in my workspace, I can see it at the address

sparkclub-c9-themooserooster.c9.io

So I would open a new tab, enter that url (no autocomplete here kids, sorry) and I
should see my blog staring back at me.