# Wordpress templates

We can create different templates for our pages. 
Note, that comment with template name is required: `/* Template Name: Full Width Template */`

**page-full.php**

```php
<?php

/* Template Name: Full Width Template */

?>

<?php get_header(); ?>

<div class="row">

  <div class="col-md-12">
    <?php if (have_posts()): ?>

      <?php while (have_posts()): the_post(); ?>

          <article class="article">
            <h1><?php the_title(); ?></h1>

            <h6>Posted on <?php the_time('F jS, Y') ?></h6>

            <p><?php the_content(__('(more...)')); ?></p>
          </article>
      
      <?php endwhile; ?>

    <?php else: ?>
        <p><?php _e('Sorry, no posts matched your criteria.'); ?></p>
    <?php endif; ?>
  </div>
</div>

<?php get_footer(); ?>
```

**page-with-sidebar.php**

```php
<?php

/* Template Name: Template with sidebar menu */

?>

<?php get_header(); ?>

<div class="row">

  <div class="col-md-8">
    <?php if (have_posts()): ?>

      <?php while (have_posts()): the_post(); ?>

          <article class="article">
            <h1><?php the_title(); ?></h1>

            <h6>Posted on <?php the_time('F jS, Y') ?></h6>

            <p><?php the_content(__('(more...)')); ?></p>
          </article>
      
      <?php endwhile; ?>

    <?php else: ?>
        <p><?php _e('Sorry, no posts matched your criteria.'); ?></p>
    <?php endif; ?>
  </div>

  <div class="col-md-4">
    <?php
      wp_nav_menu([
        'theme_location' => 'sidebar-menu', 
      ]);
    ?>
  </div>
  
</div>

<?php get_footer(); ?>
```
