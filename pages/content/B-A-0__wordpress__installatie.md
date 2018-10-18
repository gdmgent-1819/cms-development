---
title: Installatie
title_long: WordPress Installatie
permalink: wordpress/installatie/
---

Ontwikkelomgeving
-----------------

### MAMP 

Download en installeer de AMP stack voor uw OS via [mamp.info](https://www.mamp.info)

Broncode
--------

### Via de website

Je kan de broncode (van de Nederlandstalige versie) downloaden van [nl.wordpress.org](https://nl.wordpress.org/download/) en het bestand decomprimeren in de map `wordpress`.

In het voorbeeld maken we een wp-installatie voor een GDM-website.

Open de bijhorende folder van de `MAMP`-installatie en lokaliseer de folder `htdocs`.  
Maak in de folder `htdocs` een nieuwe project map aan met de naam `gdm`.  
Kopieer de inhoud van de gedownloade folder `wordpress` naar de folder `htdocs`>`gdm`. 

{% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/folder_mamp_installatie.png" alt="Folder structuur MAMP" caption="Folder structuur MAMP" %}


DB aanmaken via phpMyAdmin
-------------------------

Nadat de broncode gedownload is, moet er een database worden aangemaakt.  
Ga via de applicatie van MAMP naar `Open WebStart page` - de MAMP-startpagina naar phpMyAdmin. `Tools` > `phpMyAdmin`.  

Maak een nieuwe db aan onder `database` > `create database` met de db-naam: `dbwp_gdm`.  

{% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/create_db.png" alt="Create DB" caption="Create database" %}


Installatie
------------

Je kan surfen naar je lokale map en de configuratieprocedure doorlopen.  
Installatie pagina: http://localhost:8888/gdm/    
Doorloop de installatie procedure.  


 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_1.png" alt="Installatie WP" caption="Installatie WP" %}

|                        Veld | Waarde            |
|----------------------------:|-------------------|
|            **Databasenaam** | `dbwp_gdm`       |
| **Database-gebruikersnaam** | `root`     |
|     **Database-wachtwoord** | `root` |
|           **Database-host** | `localhost`       |
|             **Tabelprefix** | `dbwp_`             |
{:.table .table-striped}

 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_2.png" alt="Installatie WP" caption="Installatie WP" %}

|               Veld | Waarde                  |
|-------------------:|-------------------------|
|   **Websitetitel** | `GDM` |
| **Gebruikersnaam** | `gdm_gebruiker`         |
|     **Wachtwoord** | `gdm_pass`        |
|    **E-mailadres** | `eigen emailadres artevelde`    |
{:.table .table-striped}

 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_3.png" alt="Installatie WP" caption="Installatie WP" %}


Inloggen
--------

Na de installatie ziet de **frontoffice** (wat bezoekers te zien krijgen) website er zo uit:

 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_4.png" alt="Inloggen WP" caption="Inloggen WP" %}

We kunnen inloggen op de **backoffice** (wat beheerders te zien krijgen) met de WP-gebruikersgegevens.

|               Veld | Waarde           |
|-------------------:|------------------|
| **Gebruikersnaam** | `gdm_gebruiker`  |
|     **Wachtwoord** | `gdm_pass` |
{:.table .table-striped}

 {% include shared/figure.html src="https://www.arteveldehogeschool.be/campusGDM/gdmgent/cms/wp/installatie_5.png" alt="Inloggen WP" caption="Inloggen WP" %}