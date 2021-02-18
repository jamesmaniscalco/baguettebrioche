# baguettebrioche
The Baguette &amp; Brioche website

# README Contents
* [Initial setup](#initial-setup)
* [Build and view site](#build-and-view-site)
* [Creating a new post](#creating-a-new-post)

# Initial setup

You should only have to do most of this once.

Install the macOS command line tools, if you haven't already:

    xcode-select --install

Install Homebrew, if you haven't already:

    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Install Ruby via `rbenv`:

    brew install rbenv

Then initialize `rbenv`:

    rbenv init

You might also need these in your `~/.bash_profile.rc`:

    export RBENV_ROOT=/usr/local/var/rbenv
    export PATH="$RBENV_ROOT:$PATH"
    if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi

The `RBENV_ROOT` might be different on your machine. Run `rbenv prefix` to get where the shims are stored, then remove the '`/shims`' from the path name to get the correct `RBENV_ROOT`.

Restart your terminal app before proceeding.

You need to have the most up-to-date Ruby version. As of this writing it's version `2.7.2`.

    rbenv install 2.7.2

Clone or download this repository onto your computer.

In the directory where you have downloaded this repo, set the local Ruby version:

    rbenv local 2.7.2

You need to have bundler installed too:

    gem install --user-install bundler jekyll

Finally, install the required plugin gems:

    bundle install

That's it.


# Build and view site

Build the site with:

    jekyll build

The generated site files will be in the `_site/` directory.

Alernatively, build and view the site with:

    jekyll serve

If you don't want to use the command line, the `_build-site` executable will also build and serve the site.

The generated site will be visible at http://localhost:4000 (check command line output to be sure).

Stop the server with `ctrl-C`.



# Creating a new post

To create a new (recipe) post, you should just need to make the post files - everything else should get handled automagically.

Let's start with the `en` version. Copy an existing post in the `/_i18n/en/posts/` directory. Rename it with a relevant date and title, in the format `YYYY-MM-DD-post-title.md`. In the front matter, update the `title`, `categories`, etc. tags to the relevant values.

You will need to add the recipe picture file to the `/images/` directory and link it with the `image` tag in the post file.

Modify the text of the post (ingredients, instructions, etc.) as needed.

Now to make the French file: copy the file you have into the `/_i18n/fr/posts/` directory **with the same title**. Modify the language-specific content in the front matter and the text, but make sure to leave the `image` tag as-is. 

