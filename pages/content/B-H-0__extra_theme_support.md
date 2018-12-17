---
title: Extra Theme support
title_long: Extra Theme support
permalink: wordpress/extrathemesupport
---

Sidebar
-------

Met widgets kan je extra content (tekst, plugins, ...) toevoegen aan je WordPress theme.
Meestal worden deze toegevoegd in onze sidebar. Hoewel we de overal in de theme kunnen definiëren.
Net zoals bij menus dienen we hiervoor locaties aan te maken in de `functions.php` en op te roepen in onze theme.

{% highlight php linenos %}
<?php
# …
function register_sidebar_locations() {
    /* Register the 'primary' sidebar. */
    register_sidebar(
        array(
            'id'            => 'primary-sidebar',
            'name'          => __( 'Primary Sidebar' ),
            'description'   => __( 'A short description of the sidebar.' ),
            'before_widget' => '<div id="%1$s" class="widget %2$s">',
            'after_widget'  => '</div>',
            'before_title'  => '<h3 class="widget-title">',
            'after_title'   => '</h3>',
        )
    );
    /* Repeat register_sidebar() code for additional sidebars. */
}
add_action( 'widgets_init', 'register_sidebar_locations' );
{% endhighlight %}{:data-file="functions.php"}

Net zoals bij menus moeten we deze nu nog ophalen in onze theme.
Doe dit in de sidebar.php file.

{% highlight php %}
<aside>
<?php dynamic_sidebar( 'primary-sidebar' ); ?>
</aside>
{% endhighlight %}{:data-file="sidebar.php"}

Je kan uiteraard in deze sidebar.php nog meer eigen html toevoegen.

Daarna moeten we deze sidebar inladen in elke template waar deze mag of moet staan.
Dit doe je net zoals bij header en footer aan de hand van een functie binnen WordPress. Voeg dus `<?php get_sidebar(); ?>` toe aan één of meerdere templates. 

Wil je nog een extra sidebar (of eerder widget zone) in je website dan kan je in de functie `register_sidebar_locations` de code nogmaals herhalen. Hierbij is het belangrijk dat je een nieuwe id maakt. Deze moet uniek zijn en gebruik je om de widget zone op te halen.

Voeg een nieuwe widget zone toe ('footer-sidebar') en haal deze dan op in je footer.php aan de hand van `<?php dynamic_sidebar( 'footer-sidebar' ); ?>`

> References
> ---
> - [Wordpress Theme: Sidebar](https://developer.wordpress.org/themes/functionality/sidebars/)
{:.card.card-source}

Custom Logo Support
-------------------

Uiteraard is het meest voor de hand liggende de mogelijkheid om een logo op te laden als administrator. Voeg deze toe in jullie thema.

{% highlight php linenos %}
add_theme_support( 'custom-logo' );
{% endhighlight %}{:data-file="functions.php"}

{% highlight php linenos %}
<?php
if ( has_custom_logo() ) {
        the_custom_logo();
} else {
        echo '<h1>'. get_bloginfo( 'name' ) .'</h1>';
}
?>
{% endhighlight %}{:data-file="header.php"}

> References
> ---
> - [Wordpress Theme: Custom Logo](https://developer.wordpress.org/themes/functionality/custom-logo/)
{:.card.card-source}


Custom Header Support
---------------------

Veel websites starten met een grote header afbeelding. Op alle pagina's of bijvoorbeeld enkel op de startpagina. Ook deze kunnen jullie toevoegen aan jullie thema.

> References
> ---
> - [Wordpress Theme: Custom Headers](https://developer.wordpress.org/themes/functionality/custom-headers/)
{:.card.card-source}

Post thumbnails (Feature images)
-------------------------------

Momenteel kan je afbeeldingen toevoegen aan de inhoud van je blog post.
Echter is het in de meeste gevallen nodig om een afbeelding apart te hebben. In je overzicht van je blog posts kan je dan naast je titel, een korte omschrijving dan ook deze afbeelding plaatsen.


{% highlight php linenos %}
add_theme_support( 'post-thumbnails' );
{% endhighlight %}{:data-file="functions.php"}

Daarna kan je in 'the loop' (bv bij single.php of home.php) de afbeelding oproepen aan de hand van een van de onderstaande codes.

{% highlight php linenos %}
<?php
the_post_thumbnail(); // Without parameter ->; Thumbnail
the_post_thumbnail( 'thumbnail' ); // Thumbnail (default 150px x 150px max)
the_post_thumbnail( 'medium' ); // Medium resolution (default 300px x 300px max)
the_post_thumbnail( 'medium_large' ); // Medium-large resolution (default 768px x no height limit max)
the_post_thumbnail( 'large' ); // Large resolution (default 1024px x 1024px max)
the_post_thumbnail( 'full' ); // Original image resolution (unmodified)
the_post_thumbnail( array( 100, 100 ) ); // Other resolutions (height, width)

?>
{% endhighlight %}{:data-file="home.php single.php ..."}


> References
> ---
> - [Lees verder over Post thumbnails](https://developer.wordpress.org/themes/functionality/featured-images-post-thumbnails/)
{:.card.card-source}