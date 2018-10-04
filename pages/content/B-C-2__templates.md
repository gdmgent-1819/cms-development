---
title: Template Files
title_long: Template Files
permalink: thema/template-files/
---

## Begrip

- **Template files** zitten binnen een thema en bevatten de markup hoe je site getoond wordt
- **Page templates** zijn **enkel** van toepassing op pagina's om hun look en feel te veranderen. Een pagina-template kan toegepast worden op een single page, een pagina-onderdeel of een reeks pagina's.
- **Template Tags** zijn ingebouwde WP-functies die je binnen een template kan gebruiken om data op te halen zoals de titel en content (vb `the_title()` of `the_content()`)
- **[Template Hierarchy](https://wphierarchy.com)** is de logica, gebruikt door Wordpress, welke templates te gebuiken in welke situatie.

## Template Files

Wordpress thema's zijn opgebouwd uit template files. Dit zijn php-files (let op de *.php-extensie!), die bestaan uit een mix van html, **template tags** en php-code.

Als je een thema bouwt, zal je de template files gebruiken om de lay-out en design van onderdelen van je website op te maken. Bijvoorbeeld, **header.php** zal gebruikt worden om een header te bouwen, terwijl **comments.php** zal gerbuikt worden voor de commentaar.

Als er iemand je website bezoekt, zal Wordpress een template laden, gebaseerd op de *request*. Het soort content dat verschijnt wordt bepaald door de **Post Type** en is geassocieerd met een specifieke template.

De **Template Hierarchy** beschrijft welk template file Wordpress moet gebruiken, op basis van de request. Het is dus van alle belang bij het bouwen van je thema dat je deze hierarchie goed begrijpt en op basis van de boomstructuur kan anticiperen welk template je moet ontwikkelen, in specifieke situaties.

De belangrijkste template file is **index.php**, aangezien dit de *catch-all*-template is. Dit is in theorie ook de enige template file die verplicht moet aanwezig zijn in jouw thema, hoewel het er in realiteit naar alle waarschijnlijkheid veel meer zullen zijn.

## Template Partials

Een partiële template is een stukje van een template dat onderdeel is van een andere template, zoals een header. Deze **partials** kunnen geëmbed worden in meerdere templates, waardoor je code kan hergebruikt worden.

- header.php for generating the site’s header
- footer.php for generating the footer
- sidebar.php for generating the sidebar

Je kan er zelf nog veel meer maken.

## Algemene WP Templates

Hieronder een oplijsting van enkele basic theme templates die herkend worden door Wordpress

Bron: https://developer.wordpress.org/themes/basics/template-files/

- **index.php**
    - The main template file. It is required in all themes.
- **style.css**
    The main stylesheet. It is required in all themes and contains the information header for your theme.
- **rtl.css**
    - The right-to-left stylesheet is included automatically if the website language’s text direction is right-to-left.
- **comments.php**
    - The comments template.
- **front-page.php**
    - The front page template is always used as the site front page if it exists, regardless of what settings on Admin > Settings > Reading.
- **home.php**
    - The home page template is the front page by default. If you do not set WordPress to use a static front page, this template is used to show latest posts.
- **header.php**
    - The header template file usually contains your site’s document type, meta information, links to stylesheets and scripts, and other data.
- **singular.php**
    -     - The singular template is used for posts when single.php is not found, or for pages when page.php are not found. If singular.php is not found, index.php is used.
- **single.php**
    - The single post template is used when a visitor requests a single post.
- **single-{post-type}.php**
    - The single post template used when a visitor requests a single post from a custom post type. For example, single-book.php would be used for displaying single posts from a custom post type named book. The index.php is used if a specific query template for the custom post type is not present.
- **archive-{post-type}.php**
    - The archive post type template is used when visitors request a custom post type archive. For example, archive-books.php would be used for displaying an archive of posts from the custom post type named books. The archive.php template file is used if the archive-- {post-type}.php is not present.
- **page.php**
    - The page template is used when visitors request individual pages, which are a built-in template.
- **page-{slug}.php**
    - The page slug template is used when visitors request a specific page, for example one with the “about” slug (page-about.php).
- **category.php**
    - The category template is used when visitors request posts by category.
- **tag.php**
    - The tag template is used when visitors request posts by tag.
- **taxonomy.php**
    - The taxonomy term template is used when a visitor requests a term in a custom taxonomy.
- **author.php**
    - The author page template is used whenever a visitor loads an author page.
- **date.php**
    - The date/time template is used when posts are requested by date or time. For example, the pages generated with these slugs:
    - http://example.com/blog/2014/
    - http://example.com/blog/2014/05/
    - http://example.com/blog/2014/05/26/
- **archive.php**
    - The archive template is used when visitors request posts by category, author, or date. Note: this template will be overridden if more specific templates are present like category.php, author.php, and date.php.
- **search.php**
    - The search results template is used to display a visitor’s search results.
- **attachment.php**
    - The attachment template is used when viewing a single attachment like an image, pdf, or other media file.
- **image.php**
    - The image attachment template is a more specific version of attachment.php and is used when viewing a single image attachment. If not present, WordPress will use attachment.php instead.
- **404.php**
    - The 404 template is used when WordPress cannot find a post, page, or other content that matches the visitor’s request.

## Template Tags

Binnen de template files kan je gebruik maken van Template Tags om informatie weer te geven, andere template files (partials) te includen of je website te customizen.

Je zou bijvoorbeeld in de template **index.php** andere bestanden kunnen includen:

- To include the header, use get_header()
- To include the sidebar, use get_sidebar()
- To include the footer, use get_footer()
- To include the search form, use get_search_form()
- To include custom theme files, use get_template_part()

{% highlight html %}
<body>
    <?php get_sidebar(); ?>
    <?php get_template_part( 'featured-content' ); ?>
</body>
{% endhighlight %}