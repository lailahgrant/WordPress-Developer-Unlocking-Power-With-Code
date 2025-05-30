# Interior `page.php` template
- Making a dynamic pages
- Make dummy pages of `about us` in the WP admin, `privacy policy` page (publish `privacy Policy` page from the drafts)
- Go to `C:\Users\LAILAH\Local Sites\fictional-university\app\public\wp-content\themes\fictional-university-theme\interior-page.html` in a text editor.
- - Copy the `<div class="page-section ...>"` and paste in the `page.php`.
- - Replace the static HTML with dynamic `WP PHP functions`
- example `page.php`
```php
...
<h1 class="page-banner__title"><?php echo the_title(); ?></h1>
...
<div class="generic-content">
    <?php the_content(); ?>
</div>
```

- > We'll learn how to setup `Custom Fields` so that each page can have its own unique subtitle.

- Add an image dynamically using `<div class="page-banner__bg-image" style="background-image: url(<?php echo get_theme_file_uri('/images/ocean.jpg') ?>);"></div>`
```php
<div class="page-banner__bg-image" style="background-image: url(<?php echo get_theme_file_uri('/images/ocean.jpg') ?>);"></div>
```

- MAke unique page titles to the pages
- - Go to `functions.php` to `**tell**` PHP to do something.
- - We `**tell** PHP to do something by creating an **action**`
```php
<?php
...
// This function is used to create title names of the pages uniquely to that page
function university_features(){
    //to enable a feature in WordPress, we use add_theme_support
    add_theme_support('title-tag'); // This tells WordPress to manage the title tag automatically
}

// This action is for unique page titles | Tell PHP to automatically generate an appropriate title tag for each page
add_action('after_setup_theme', 'university_features');
```

- We'll create dynamic links later
- - But now, we create **manual dynamic nav links** as follows;
```php
...
<li><a href="<?php echo site_url('/about-us') ?>">About Us</a></li>
...
```
- - MAke logo link to homepage
> Not passing `anything` in the `**<?php echo site_url() ?>**` leads to navigating to the `home page.`
```php
<h1 class="school-logo-text float-left"> 
<a href="<?php echo site_url() ?>"><strong>Fictional</strong> University</a>
</h1>
```


