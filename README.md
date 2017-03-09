# wp_foundation_navwalker

Cara Penggunaan
```php
require_once( trailingslashit( get_template_directory() ) . 'libs/wp_foundation_navwalker.php' );
```

Jangan lupa register menu nya
```php
    register_nav_menu('primary', __('Primary Menu', TEXTDOMAIN));
```
Kemudian di header bisa anda buat seperti ini
```php
 <div class="top-bar-left">
            <?php
            $args = array(
                'theme_location' => 'primary',
                'echo' => true,
                'depth' => 3,
                'container' => false,
                'items_wrap'     => '<ul id="%1$s" class="%2$s desktop-menu" data-dropdown-menu>%3$s</ul>',
                'menu_class' => 'menu dropdown',
                'fallback_cb'       => 'wp_foundation_navwalker::fallback',
                'walker'            => new wp_foundation_navwalker()
            );
            wp_nav_menu( $args);?>

        </div>
```
