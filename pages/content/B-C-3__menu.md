---
title: Menu
title_long: Theme Menu
permalink: wordpress/thema/menu/
---


### Registreren en ophalen van menus in onze theme

Onze theme dient aan wordpress te vertellen welke locaties er voorzien zijn om menu items te plaatsen.
Wij gaan in dit voorbeeld 2 menus registreren in onze `functions.php`

{% highlight php linenos %}
<?php
  # …
  function register_menu_locations() {
    register_nav_menus(
      array(
        'primary-menu' => __( 'Primary Menu' ),
        'footer-menu' => __( 'Footer Menu' )
      )
    );
  }
  add_action( 'init', 'register_menu_locations' );
{% endhighlight %}{:data-file="functions.php"}

Nu kunnen we in de backoffice van WordPress een menu koppelen aan deze locatie.
Daarna moeten we dit menu nog oproepen binnen onze theme.
De primary-menu voegen we toe in onze header.php en de footer-menu in footer.php

{% highlight php %}
<?php wp_nav_menu( array( 'theme_location' => 'primary-menu' ) ); ?>
{% endhighlight %}

Na deze stap kan je je theme activeren en je website bekijken.


> References
> ---
> - [Theme Developer handboek](https://developer.wordpress.org/themes/functionality/navigation-menus/)
{:.card.card-source}
