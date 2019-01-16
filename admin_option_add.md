# Add option to Wordpress Admin page

1. Create file `wp-contant/themes/mytheme/options.php`:

```php
<?php

// Custom setting
/* Admin init */
add_action( 'admin_init', 'my_settings_init' );
 
/* Settings Init */
function my_settings_init(){
 
    /* Register Settings */
    register_setting(
        'reading', // Options group
        'feedback_active', // Option name/database
        'boolean_sanitize' // sanitize callback function
    );
 
    /* Create settings section */
    add_settings_section(
        'my-section-id', // Section ID
        'Additional settings', // Section title
        'custom_settings_section_description', // Section callback function
        'reading' // Settings page slug
    );
 
    /* Create settings field */
    add_settings_field(
        'my-settings-field-id',       // Field ID
        'Форма обратной связи',       // Field title 
        'my_settings_field_callback', // Field callback function
        'reading',                    // Settings page slug
        'my-section-id'               // Section ID
    );
}
 
/* Sanitize Callback Function */
function boolean_sanitize($input)
{
    return isset($input) ? true : false;
}
 
/* Setting Section Description */
function custom_settings_section_description(){
    echo wpautop('This section contains custom settings');
}
 
/* Settings Field Callback */
function my_settings_field_callback(){
    ?>
    <label>
        <input type="checkbox" value="1" 
               name="feedback_active" <?php checked( get_option( 'feedback_active', true ) ); ?>> 
      Show feedback form
    </label>
    <?php
}
```

2. Include this file in `wp-contant/themes/mytheme/functions.php`:

```php
include 'options.php';
```

3. Visit admin page `/wp-admin/options-reading.php` to see your new option.

## Useful info

### Get option value

```php
echo get_option('feedback_active', 'Some default value');
```

### Settings table

Wordpress settings stored at `wp_options` table.
