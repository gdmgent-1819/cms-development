---
title: Installatie
title_long: WordPress Installatie
permalink: wordpress_installatie/
---

Ontwikkelomgeving
-----------------

### MAMP 

Download en installeer de AMP stack voor uw OS via [mamp.info](https://www.mamp.info)

Broncode
--------

### Via de website

Je kan de broncode (van de Nederlandstalige versie) downloaden van [Wordpress download](https://nl.wordpress.org/download/) en het bestand decomprimeren in de map `wordpress`.

In het voorbeeld maken we een wp-installatie voor een GDM-website.

Open de bijhorende folder van de `MAMP`-installatie en lokaliseer de folder `htdocs`. Maak in de folder `htdocs` een nieuwe project map aan met de naam `gdm`. Kopieer de inhoud van de gedownloade folder `wordpress` naar de folder `htdocs`>`gdm`. 

{% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/folder_mamp_installatie.png" alt="Folder structuur MAMP" caption="Folder structuur MAMP" %}


Configuratie phpMyAdmin
---------------------

Nadat de broncode gedownload is, moet er een database worden aangemaakt.
Ga via MAMP naar PhpMyAdmin ( mogelijks: [http://localhost:8888/phpMyAdmin/?lang=en](http://localhost:8888/phpMyAdmin) )
Maak een nieuwe db aan met de naam: `dbwp_gdm`.

{% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/create_db.png" alt="Create DB" caption="Create database" %}


### Via de browser

De configuratie kan je ook via WP-CLI doen,   
Of je kan gewoon surfen naar je lokale map en de configuratieprocedure doorlopen.

 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_1.png" alt="Installatie WP" caption="Installatie WP" %}


Installatie
------------

Nadat de configuratie voltooid is, kan de installatie beginnen.

|               Veld | Waarde                  |
|-------------------:|-------------------------|
|   **Websitetitel** | `GDM` |
| **Gebruikersnaam** | `gdm_gebruiker`         |
|     **Wachtwoord** | `gdm_pass`        |
|    **E-mailadres** | `eigen emailadres artevelde`    |

|                        Veld | Waarde            |
|----------------------------:|-------------------|
|            **Databasenaam** | `dbwp_gdm`       |
| **Database-gebruikersnaam** | `root`     |
|     **Database-wachtwoord** | `root` |
|           **Database-host** | `localhost`       |
|             **Tabelprefix** | `dbwp_`             |

{:.table .table-striped}
{:.table .table-striped}

### Manier 1 (via browser)

![Installatieproces in de browser 00]({{ site.baseurl }}/images/installatie/installatieproces.00.png "Installatieproces in de browser"){:.screenshot}

![Installatieproces in de browser 01]({{ site.baseurl }}/images/installatie/installatieproces.01.png "Installatieproces in de browser"){:.screenshot}

![Installatieproces in de browser 02]({{ site.baseurl }}/images/installatie/installatieproces.02.png "Installatieproces in de browser"){:.screenshot}



Inloggen
--------

Na de installatie ziet de **frontoffice** (wat bezoekers te zien krijgen) website er zo uit:

![Website]({{ site.baseurl }}/images/installatie/website.png "Website"){:.screenshot}

We kunnen inloggen op de **backoffice** (wat beheerders te zien krijgen) met de WP-gebruikersgegevens.

|               Veld | Waarde           |
|-------------------:|------------------|
| **Gebruikersnaam** | `gdm_gebruiker`  |
|     **Wachtwoord** | `gdm_pass` |
{:.table .table-striped}


![Inlogformulier]({{ site.baseurl }}/images/installatie/inloggen.00.png "Inlogformulier"){:.screenshot}

![WordPress Dashboard]({{ site.baseurl }}/images/installatie/inloggen.01.png "WordPress Dashboard"){:.screenshot}

