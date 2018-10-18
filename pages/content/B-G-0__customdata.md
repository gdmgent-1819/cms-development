---
title: Custom Data
title_long: Custom Data & Fields
permalink: wordpress/custom-fields/
---

## Custom Data

Met de titel, editor, samenvatting, uitgelichte afbeelding en publicatiedatum komen we vaak niet toe om data op een gestructureerde manier te beheren.

Als we een website zouden maken voor de mediatheek, is een custom post type "book" wel toepasselijk. Dit kunnen we gebruiken om alle boeken op te laden die beschikbaar zijn.   Echter, het zou dan ook meteen handig zijn als er extra invulvelden voor die boeken voorhanden zijn. Denk maar aan isbn-nummer, aantal bladzijdes, auteur, ...  
Als we dergelijke informatie voor alle boeken in de editor zouden steken, is de kans groot dat het niet bij elk boek exact hetzelfde wordt weergegeven. Het is ook beter om die informatie apart te bewaren, zodat we het op verschillende manieren kunnen weergeven.

Juist om die reden is custom data en custom fields van groot belang. Gelukkig heeft Wordpress hier een oplossing voor door een ingebouwde Custom Fields optie.

Deze extra velden worden als **meta-informatie** in de database bewaard, in de tabel wp_postmeta

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/wp_postmeta.png" alt="WP Postmeta Table" caption="De tabel wp_posmeta" %}


## Custom Fields (aangepaste velden)

Wordpress biedt standaard reeds de mogelijkheid aan om extra infomatie in te vullen via Custom Fields (Aangepaste Velden) in het Nederlands. Je ziet dit meestal standaard niet staan omdat die **meta-box** niet ingeschakeld staat (zoals op de screenshot hieronder).

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/bericht-bewerken.png" alt="Bericht Bewerken" caption="Aangepaste velden is niet zichtbaar op het edit-screen" %}

### Custom Fields inschakelen voor CPT

Indien je de aangepaste velden ook niet ziet bij je Custom Post Type, na het openklappen, wil dat zeggen dat dit moet toegevoegd worden bij de registratie van dat post type (onder supports).

{% highlight php %}
...,
'supports' => array('title','editor','thumbnail','custom-fields')
...;
{% endhighlight %}

### Aangepaste velden inschakelen

Je kan dit echter wel inschakelen, via het verborgen menu onder **Scherminstellingen** (knop bovenaan). Daarbinnen heb je een optie "Aangepaste Velden" die je kan aanvinken. Eens je dat gedaan hebt, zal je een **meta-box** zien openklappen onder de editor. 

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/scherminstellingen.png" alt="Scherminstellingen" caption="Scherminstellingen is opengeklapt" %}

Hierin kan je op basis van een key &amp; value extra informatie (a.k.a. meta-informatie) plaatsen.

 {% include shared/figure.html src="https://s.cmsdevelopment.be/wp/aangepaste-velden.png" alt="Aangepaste Velden" caption="Aangepaste velden is  zichtbaar op het edit-screen" %}

Die key's kan je hergebruiken over de verschillende (custom) posts heen. Zo kunnen we in bovenstaand voorbeeld, voor alle posts de isbn en pagina's opgeven.

## Aangepaste velden weergeven

### Alle velden weergeven

Om alle meta-data te tonen in een template file, kan je `the_meta()` gebruiken, binnen **The Loop**.

{% highlight php %}
<?php the_meta(); ?>
{% endhighlight %}

Het resultaat in de broncode zou dan het volgende kunnen zijn:

{% highlight html %}
<ul class='post-meta'>
    <li><span class='post-meta-key'>isbn:</span> 9789002244025</li>
    <li><span class='post-meta-key'>pages:</span> 175</li>
</ul>
{% endhighlight %}

### Een enkel veld weergeven

Wil je slechts één van de metafields weergeven, kan je volgende functie gebruiken:

{% highlight php %}
get_post_meta($post_id, $key, $single);
{% endhighlight %}

> References
> ---
> - [Codex: Custom Fields](https://codex.wordpress.org/Custom_Fields)
> - [Code Ref: get_post_meta()](https://codex.wordpress.org/Custom_Fields)
> - [Code Ref: the_meta()](https://codex.wordpress.org/Template_Tags/the_meta)
{:.card.card-source}