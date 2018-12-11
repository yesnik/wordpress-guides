# Wordpress Architecture

WordPress uses template files to generate the final page "look" and content. 
For example, when viewing the front page of your WordPress site, you are actually viewing several template files:

- index.php
- header.php
- sidebar.php
- footer.php

## Default Theme

```
<body>
  <div id="page">
  <div id="header"></div>
  <div id="content" class="narrowcolumn"></div>
  <div id="sidebar"></div>
  <div id="footer"></div>
  </div><!-- end page -->
</body>
```

Some themes may add a second, third, or even fourth sidebar, creating a column effect. 
However, in all cases, the basic core structure essentially remains the same.

## Template files

WordPress themes divide the core structure into individual blocks called *template files*:

- Header - *header.php*
- Sidebar/Menu - *sidebar.php*
- Content - *index.php, single.php, page.php, category.php, author.php, search.php, etc.*
- Footer - *footer.php*

When viewing a web page that uses a particular WordPress theme, the specific template files generated are dependent upon the user's request. If a user clicks on a category tag, the *category template* will be used. If the user views a page, the *page template* will be used.

When these core template files are loaded in combination with the *WordPress Loop* and *queries*, a variety of templates can be generated.

