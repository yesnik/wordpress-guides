# Theme structure

## Header

The header is the structure that traditionally sits at the top of a web page. 
It contains the title of the website. Template file: *header.php*

## Content

This container holds the *WordPress Loop*, that processes each post that will be displayed on the current page. 
These posts are then formatted according to how they match specific criteria within the *Loop tags*.

## Comments

Comments may be featured in the single post view (using the `comments.php` template file) or in a popup window (using the `comments-popup.php` template file). 

## Sidebar

As you saw with the Default Theme, the sidebar can be visible or not, depending upon the template file in use. The sidebar, in general, can be simple or complex. WordPress Themes often feature information within the sidebar in *nested lists*.

## Categories, Archives, and Meta

The other sidebar section titles, categories, archives, meta, and others, 
do not use template tags which generate their own titles. 
These are set inside of PHP statements which "print" the text on the page. 
While these could be put inside of heading tags, WordPress uses the `_e()` function to display or `echo` the text titles while also marking the text as a possible target for language translation.

## Footer

The footer is found within the `footer.php` template file.
