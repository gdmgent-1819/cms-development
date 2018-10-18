---
title: Advanced Custom Fields
title_long: Plugin - Advanced Custom Fields
permalink: wordpress/custom-fields/advanced-custom-fields
---
 
## Plugin

Advanced Custom Fields is een open-source plugin die het een pak eenvoudiger en gebruiksvriendelijker maakt. Met deze plugin kan je velden groeperen, in een meta-box steken, ...

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/acf.jpg" alt="Advanced Custom Fields" caption="Bron: https://www.advancedcustomfields.com" %}

Er is een brede waaier aan velden die je kan toewijzen, je kan eveneens kiezen voor welke post type of specifieke post/pagina je de velden wil doen verschijnen.

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/acf-backend.jpg" alt="Advanced Custom Fields" %}

Het ophalen van de velden is ook straightforward.

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/acf-theme.jpg" alt="Advanced Custom Fields" caption="Bron: https://www.advancedcustomfields.com" %}

## Basic Documentation

Onderstaande functies kan je gebruiken in je thema templates binnen **the loop**.

**Bijvoorbeeld:**  
{% highlight php %}
<h4><?php echo get_field('my_subtitle'); ?></h4>
<article>
    <?php the_field('intro'); ?>
</article>
{% endhighlight %}

- `get_field()`	
    - Returns the value of a specific field.
- `the_field()`	
    - Displays the value of a specific field.
- `get_field_object()`
    -  Returns the settings (array) of a specific field
- `get_fields()`
    -  Returns an array of values (name => value) for a specific post
- `get_field_objects()`	
    - Returns an array of field settings (name => field) for a specific post

> References
> ---
> - [Bron: Advanced Custom Fields](https://www.advancedcustomfields.com)
> - [Plugin: Advanced Custom Fields](https://codex.wordpress.org/Custom_Fields)
> - [Documentatie](https://www.advancedcustomfields.com/resources/)
{:.card.card-source}
