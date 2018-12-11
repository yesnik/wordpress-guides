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

