# baguettebrioche
The Baguette &amp; Brioche website

## README Contents
* [Creating a new monthly theme](#creating-a-new-monthly-theme)
    * [Theme header](#theme-header)
    * [Theme page](#theme-page)
    * [Translation files](#translation-files)
    * [Updating other pages](#updating-other-pages)
* [Creating a new post](#creating-a-new-post)



## Creating a new monthly theme

To create a new month, you've got to do a few things: create a theme header file, create a theme page, update the translation directories, and update the main index and theme index.

### Theme header

First, you will need to make the theme header. To do so, copy one of the files in the `_includes/theme_headers/` directory to a new file, probably titled with the relevant month, for example `2017-01.html`.

In this file, there is a line where you `assign theme_header`. Change the argument to the name of this file, excluding the file extension `.html`. Make the same changes in the link `href` and the theme translation tags below.

Next, put a photo for the month into the `images` directory, and link it at the top of this file. Choose a `background-color` and a text `color` to go with the image and put them at the top of this page too.

### Theme page

For the monthly theme page, copy one of the pages in the `m` directory. Rename it to the appropriate month, for example `2017-01.html`. Set the `cat` and `theme_header` variables in the front matter appropriately. Next change the argument of the `tf` tag below to reflect the month name too; in this example it's `2017-01.md`. This is a markdown file that you'll now make two copies of: one in French and one in English.

In the `_i18n/en/m/` directory, copy an existing month file and modify it as you need. Make sure to save the file to the name you put into the `.html` file. Now do the same for the French version in the `_i18n/fr/m/` directory.

### Translation files

Next, edit the `_i18n/en.yml` and `_i18n/fr.yml` files to include the new translations for this month. Make sure to be consistent with theme naming. You need to add `theme.my_theme.name` and `theme.my_theme.month` tags.

### Updating other pages

Finally you need to update the main index page and the theme index page.

For the main index, go to `/index.html` and set the `{% include %}` line up top to have the new month's theme header (if you indeed want to put the new month as the current month on the site).

For the theme index, go to `/m/index.html` and add the new theme header to the list. These are sorted chronologically, newest fist, but you have to do the sorting manually!


## Creating a new post

To create a new (recipe) post, you should just need to make the post files - everything else should get handled automagically.

Let's start with the `en` version. Copy an existing post in the `/_i18n/en/posts/` directory. Rename it with a relevant date and title. In the front matter, update the `title`, `categories`, etc. tags to the relevant values.

You will need to add the recipe picture file to the `/images/` directory and link it with the `image` tag in the post file.

Modify the text of the post (ingredients, instructions, etc.) as needed.

Make sure that the relevant theme/month is in the categories! This is necessary for the theme page to include the right posts.

Now to make the French file: copy the file you have into the `/_i18n/fr/posts/` directory **with the same title**. Modify the language-specific content in the front matter and the text, but make sure to leave the `image` tag as-is. 

