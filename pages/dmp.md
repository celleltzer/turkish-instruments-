---
title: Data Managment Plan
layout: about
permalink: /dmp.html
---


# Data Management Plan

# Section 1: Project Overview

Our project is a website that hosts a collection of Turkish instruments; where they are from, what they look like, when they were made, what category of instrument it is (wind, brass, string). We are using Collection Builder, GitHub, and Google sheets to display and host our instruments collection. Collection Builder is used as the website frontend—which is hosted using GitHub Pages—and the collection index/metadata is hosted headlessly using Google Sheets. This approach to index management enables greater extensibility, allowing the data to be re-used within diverse platforms and access mediums. 

This is an important collection because music is a part of culture… Being able to find instruments related to a location and culture makes it easier to appreciate the way songs were made and how people played music. People who are studying instruments will find this website useful—along with anyone researching Turkish culture in general—given that music is a reflection of culture. 

# Section 2: Roles & Responsibilities

**Serene**

Serene introduced the topic of the collection and researched various resources pertaining to Turkish instruments. In addition, they aided in the formatting and data input of collection data displayed in the final Collection Builder website. 

**Celleltzer:** 

Celleltzer created the repository of which they both collaborated on, they added information into the collection, section 1 of this, source institution chart. Did creative changes to the theme of the Collection Builder.


# Section 3: Data Inventory & Provenance

## Source objects

| Source Institution  | \# objects | How accessed  | rights |
| :---- | :---- | :---- | :---- |
| Organology | 22 | Website  | Educational fair use |
| Wikipedia  | 1 | Website | Creative Commons |
| The MET Museum  | 1 | Website | Public domain |

**Organology**

In Copyright \- [http://rightsstatements.org/vocab/InC/1.0/](https://rightsstatements.org/vocab/InC/1.0/) 

Images sourced from Organology used under educational fair use, Organology uses copyrighted images under educational free use. 

**Wikipedia**

Attribution-ShareAlike 4.0 International \- [https://creativecommons.org/licenses/by-sa/4.0/deed.en](https://creativecommons.org/licenses/by-sa/4.0/deed.en)  

Wikipedia does not include conditions

**The MET Museum**

Attribution 4.0 International \- [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/) 

The MET lists the image used as public domain, available for any use. 

## File inventory

| File Type | Description | Number | Approximate total Volume |
| :---- | :---- | :---- | :---- |
| jpeg | Lossy image file with less efficient compression and no support for alpha band (older, universal adoption) | 2 | \~0.08 mb |
| webp | Lossy image file with support for alpha band (newer but widespread adaption on web) | 22 | \~0.44 mb |
| csv | Comma separated spreadsheet file | 1 | \~0.01 mb |
| md | Text file with basic formatting capabilities | 15 | \~0.02 mb |

## Tools and access

Someone will need a csv editor in order to interact with the primary data directory. Because the csv is hosted through Google Drive’s API, they may be able to use GET requests to download the csv. 

If they wanted to reproduce our project’s functionality, it would be very easy to create a GitHub account and clone the repository. If they did not want to use a GitHub account they could simply clone the repository using https to work on a local Git repository or on another Git enabled web service provider such as CloudFlare. 

Collection Builder’s functionality is self contained and relies on universal web file formats such as csv, js, html, yaml, etc… If someone were to clone the repository they would clone Collection Builder with it. It is fairly likely that a functional website could be made available without using GitHub pages and instead using another web hosting service. 

# Section 4: Storage & Stewardship

## During the project

During project development, data starts in Serene’s Google Drive, which hosts our collection csv (which automatically updates the GitHub Pages frontend), in addition to source files for all image files and other auxiliary files used in the collection. Celleltzer’s GitHub repository is treated as a public, final destination for the data which is drafted in Google Drive. During this process, auxiliary files are not directly transferred from Google Drive to the GitHub repository, instead each member downloads each file to their personal computer and manually uploads new files to GitHub. Under this methodology, the auxiliary files exist in 3 places: 2 in remote servers, and 1 on the contributor’s personal computer (although personal storage is highly temporary). 

The public can look at our GitHub repository but cannot directly edit it. Because GitHub only allows the person who made the repository to access its settings, only one of us can change settings. GitHub repositories may also be duplicated, allowing third parties to interpret the collection. Third parties do not have access to the entirety of the Google Drive directory this project sources data from. 

## After the project

Once the term is over, the data will enter an un-maintained / un-disturbed state. While the project contributors do not plan to continue maintenance of the website, all of the data and functionality of the website will not be actively deprecated. Because the website relies on various highly popular dependencies and frameworks it is likely that in this state the website will remain functional for the foreseeable future. If accessibility is impacted, each dependency is large enough to garner community preservation efforts which could bring the website back to functionality. In addition, the community has the resources to directly access and clone the repository, if there is ever interest in preserving the website in the long-term. 

# Section 5: Access, Reuse & Rights

In our current implementation of the website, there are no functional restrictions to access, reuse, or rights. The website is publicly accessible, its repository is open-source, but rights are a bit more murky. Images in this website are not guaranteed to be free of copyright from their original providers, which may impact official viable interpretation rights for the website. 

## Our license

We chose the MIT license because we are using a template that used this license and figured it also fit what we were looking for in a license, which lets people use it free of charge to anyone and people can copy it and use it freely and modify it without us having any repercussions.

## Rights implications of our sources

For the objects with more restrictive terms we are using the argument of educational fair use since this website is made for educational purposes. Because these objects are copyrighted others who use our collection will need to think and be aware of that for their uses. 

## Ethical considerations

The instruments and materials of this collection date back centuries. While the original creators of these instruments are no longer alive, their cultural relevance and usage is still part of our consideration. This collection aims to focus on instruments which are used in Turkish music, although they may have a much broader cultural origin and usage. Descriptions in the metadata focus on each instrument’s relation to Turkish music history, as opposed to the instrument’s broader history. 

# Appendix: Data Dictionary

| Field Name | Definition | Example Value | Notes on Use |
| :---- | :---- | :---- | :---- |
| **objectid** | The name(s) of the instrument  | “zurna”, “Ney”, “doumbek- darbuka” | The objectid field is used to name the item in Collection Builder’s item system. All letters are kept lowercase, forward slashes are converted to dashes, and any tone characters are replaced with their non-tone variant.  |
| **title** | The name(s) of the instrument  | “Zurna”, “Ney”, “Doumbek / Darbuka” | The name of the instrument with capitalization, forward slashes to denote alternate titles, and original accent marking. |
| **filename** | The name of the image saved to our google drive | “kemenche.webp”, “turkish-ney.jpg” | This follows the same minimal naming conventions as objectid but includes the file extension suffix for each image.  |
| **format** | Format of the object’s representation file | “image/webp”, “image/jpg” | The format of the image. Collection Builder denotes format hierarchy… so to denote that the object uses an image stored as webp, “image/webp” is used. |
| **source** | Url of the source of object information | “[https://organology.net/instrument/zurna/](https://organology.net/instrument/zurna/)” | The url of the object source—where the imagery and reference information was found for the object. |
| **rightsstatement** | Rights statement of the given object | “[http://rightsstatements.org/vocab/UND/1.0/](https://rightsstatements.org/vocab/UND/1.0/)” | The rights statement associated with the object’s image. |
| **description-source** | Description of the object given from item’s source | “The Turkish ney is an end-blown flute made of reed, known for its mystical and evocative sound. It is a crucial instrument in Turkish classical music and plays a significant role in the spiritual music of the Mevlevi Sufi rites (semâ). The ney is one of the oldest musical instruments still in use, with its origins often traced back to Ancient Egypt around the 3rd millennium BCE. It is regarded as a symbol of spirituality, often played by Sufis to evoke a sense of deep meditation and connection to the divine. The instrument’s ethereal tone makes it a staple alongside other classical Turkish instruments like the tanbur and kemençe.” | This is the unedited description of each object which was pulled directly from the object imagery source. This is useful for reference on the instrument context, but is not visible in the Collection Builder website.  |
| **description** | Description of the object including use and history | “The ney is a reed flute instrument with various regional variations with altered mouthpieces. The ney is notoriously difficult to produce sound from and requires lots of musculature around the lips to maintain a proper embouchure. When learning the instrument, some may not be able to produce a single sound for up to a month. While the Arabic ney is played directly into the reed body of the instrument, the Turkish ney has a circular mouth piece that reduces some of the difficulty of the instrument's embouchure but does not completely eliminate it.” | This is the description of each object which is visible on the website. It is a reworded and refined description of each instrument which focuses on the instrument’s Turkish context.  |
| **date**  | The time period that each instrument was created | “1900-02-01” (Feb. 1st, 1900\) | Most instruments in this collection were not created on a specific date, or have existence dating to BC. Broad historical markers were used when establishing the date, and instruments created during BC are listed as 0000 (CE).  |
| **subject** | What is this object? | “instrument” | While every entry in this collection is an instrument, this field provides some data future-proofing if the contents of this collection needed to be combined with non-instrument objects.  |
| **rights** | Name of original owner of images and description | “Organology”, “MET”, “Wikipedia” | This field lists the name of the entity from which images were sourced for each object.  |
| **inst\_type** | Family of instruments  | “string”, “flute”, “drum”, “brass” | This custom field denotes the general family of instruments each object falls into. Instrument types are kept broad.  |
| **material** | The material of the instrument’s body | “wood”, “reed” | This field describes the main material used in the instrument’s body.  |
| **sound\_source** | What is the source of the instrument’s vibration | “animal skin”, “string”, “reed” | This field describes the material that is vibrated in the instrument to create sound. For example, in a drum, animal skin is vibrated to make sound which is amplified and influenced by the body of the instrument.  |
| **action** | The action required to play the instrument | “pluck”, “blow”, “strike” | This is the action done by the performer to create the sound of the instrument. By including descriptors of the instrument's body (passive sound material), sound source (active sound material) and action (sound initiation) the instrument is broken into fundamental elements. This abstraction helps explain the functionality of the instrument to somebody who is not yet familiar with it.  |

