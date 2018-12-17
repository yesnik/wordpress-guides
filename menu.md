# Wordpress Menu

## Menu areas

Define menu areas at `functions.php`:

```php
function register_my_menus() {
  register_nav_menus([
    'main-menu' => __('Main Menu'),
    'sidebar-menu' => __('Sidebar Menu'),
    'footer-menu' => __('Footer Menu')
  ]);
}
add_action( 'init', 'register_my_menus' );
```

It template (e.g `header.php`) output menu like this:

```php
<h1>Header</h1>

<div>
  <?php
    wp_nav_menu([
      'theme_location' => 'main-menu', 
    ]);
  ?>
</div>
```
