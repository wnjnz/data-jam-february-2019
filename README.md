# data-jam-february-2019
Cleveland Museum of Art API


## Important Links to original dataset information

### The datasets github page https://github.com/ClevelandMuseumArt/openaccess
The main pieces in this github repository are a README markdown file with information, a CSV, and a JSON. The CSV and the JSON are very very large, 59MB and 172MB respectively. You probably don't want to work with these files directly as they would take up a lot of space and be slow to work with.

The API equivelant of the JSON Provided at the link above is: `https://openaccess-api.clevelandart.org/api/artworks/`

### The datasets webpage http://openaccess-api.clevelandart.org/
This webpage has general information as well as fields, query parameters, and examples requests to the API. 

## A smaller data subset to work with in CSV format

## Important things you might want to know
1. About half the artworks have a creative commons license and about have don't. You may want to limit your calls to only artworks that have a creative commons licesnse so that way you don't have to worry about a license that precludes... things? An example of quering all the artworks that have the creative commons zero license is `https://openaccess-api.clevelandart.org/api/artworks/?cc0=0`. That will return a json of ~27,000 artworks.
2. You can combine two queries using a & like so `https://openaccess-api.clevelandart.org/api/artworks/?cc0=1&department=Textiles&has_image=1` To get a list of queries see, the Parameters table at http://openaccess-api.clevelandart.org/
3. You can either do a query for a json of artworks or request a json for a specific piece of art. To do the later, you can use <b>either</b> Athena id or accession number. Both return the same result. For example, both `https://openaccess-api.clevelandart.org/api/artworks/130707?indent=1` and `https://openaccess-api.clevelandart.org/api/artworks/1953.424?indent=1` return the same json. One uses the Athena id and the other the accession number for the API call. The syntax is the same, just different numbers used.
4. Not all the artwork results you'll get back have an image but some do. You can use the `has_image` parameter to limit your search to those that have an image. This looks like `https://openaccess-api.clevelandart.org/api/artworks/?cc0=1&department=Textiles&has_image=1`. You won't get back the image yet, however. There are several image files in the returned json. Different ones lead to different sized images. The smallest is `"images":{"web":{"url":`<url you want is here>`}}` as seen below.

"url": "https://clevelandart.org/art/1998.78.14",
   "images": {
    "web": {
     "url": "https://openaccess-cdn.clevelandart.org/1998.78.14/1998.78.14_web.jpg",
     "filename": "1998.78.14_web.jpg",
     "filesize": "718224",
     "width": "956",
     "height": "893"
    },
    "print": {
     "url": "https://openaccess-cdn.clevelandart.org/1998.78.14/1998.78.14_print.jpg",
     "filename": "1998.78.14_print.jpg",
     "filesize": "10933890",
     "width": "3400",
     "height": "3177"
    },
    "full": {
     "url": "https://openaccess-cdn.clevelandart.org/1998.78.14/1998.78.14_full.tif",
     "filename": "1998.78.14_full.tif",
     "filesize": "77605796",
     "width": "5260",
     "height": "4916"
    }
   },



## Possible ideas


## Twitter handles & hashtags to share your visualizations with


## Attribution 
You may wish to attribute or cite The Cleveland Museum of Art CC0 select datasets, especially with respect to research or publication. Attribution is not required, but does support efforts to release other datasets in the future. It also helps to retain source links and reduce “orphaned data.”  

### Do not misrepresent the dataset
Do not mislead others or misrepresent the datasets or their source. You must not use The Cleveland Museum of Art’s trademarks or otherwise claim or imply that the Museum or any other third party endorses you or your use of the dataset. 

Whenever you transform, translate or otherwise modify the dataset, you must make it clear that the resulting information has been modified. If you enrich or otherwise modify the dataset, consider publishing the derived dataset without reuse restrictions. 


## Example dataset return:
Other easier to read example returns can be found on http://openaccess-api.clevelandart.org/
`{"info": {"total": 3195, "parameters": {"cc0": "1", "department": "Textiles", "has_image": "1"}}, "data": [{"id": 130364, "accession_number": "1953.129", "share_license_status": "CC0", "tombstone": "Embroidered Tondo from an Altar Frontal: The Coronation of the Virgin, 1459. Italy, Florence. Embroidery with gold, silver, and silk thread; split, satin, and couching stitches, or nu\u00e9 (shaded\ngold); overall: 57.8 x 57.8 cm (22 3/4 x 22 3/4 in.). The Cleveland Museum of Art, Purchase from the J. H. Wade Fund 1953.129", "current_location": "115 Manuscripts & Textiles", "title": "Embroidered Tondo from an Altar Frontal: The Coronation of the Virgin", "title_in_original_language": null, "series": null, "series_in_original_language": null, "creation_date": "1459", "creation_date_earliest": 1459, "creation_date_latest": 1459, "creators": [], "culture": ["Italy, Florence"], "technique": "Embroidery with gold, silver, and silk thread; split, satin, and couching stitches, or nu\u00e9 (shaded\ngold)", "support_materials": [], "department": "Textiles", "collection": "T - Ecclesiastical", "type": "Embroidery", "measurements": "Overall: 57.8 x 57.8 cm (22 3/4 x 22 3/4 in.)", "dimensions": {"overall": {"height": 0.578, "width": 0.578}}, "state_of_the_work": null, "edition_of_the_work": null, "creditline": "Purchase from the J. H. Wade Fund", "copyright": null, "inscriptions": [{"inscription": "the embroidery is backed by an old reused parchment with Latin writing over which in Italian is penned an inscription:  \"This pallioto was embroidered in the year 1486 by the venerable Margherita del Caccia nun of this monastery. . .\"  [It is difficult to know to what extent one should rely on this inscription as the style and technique both point clearly to an earlier date.]", "inscription_translation": null, "inscription_remark": null}], "exhibitions": {"current": [{"title": "Gothic Art 1360-1440", "description": "<i>Gothic Art 1360-1440</i>. The Cleveland Museum of Art (August 6-September 15, 1963).", "opening_date": "1963-08-06T04:00:00"}, {"title": "Lutes, Lovers, and Lyres: Musical Imagery in the Collection", "description": "<i>Lutes, Lovers, and Lyres: Musical Imagery in the Collection</i>. The Cleveland Museum of Art, Cleveland, OH (organizer) (February 6-June 11, 1989).", "opening_date": "1989-02-06T05:00:00"}, {"title": "Draped in Splendor: Renaissance Textiles and the Church", "description": "<i>Draped in Splendor: Renaissance Textiles and the Church</i>. The Cleveland Museum of Art (organizer) (September 7, 2003-September 26, 2004).", "opening_date": "2003-09-07T00:00:00"}], "legacy": ["London, Royal Academy of the Arts, \"Exhibition of Italian Art 1200-1900\" [1930].<br>Vienna, Kunsthistorische Museum, \"Kleinkunst der italienischen Fr\u00fchrenaissance\" [1936].<br>Minneapolis, The University Gallery, \"Types of Musical Instruments\" [Fall, 1956].<br>Detroit, Detroit Institute of Arts, \"Decorative Arts of the Italian Renaissance 1400-1600,\" [Nov. 18, 1958 - Jan. 4, 1959].<br>CMA: 6/91 new installation in Gallery 216.<br>Baltimore, The Walters Art Gallery, \"The International Style\" [Oct. 23 - Dec. 30, 1962].<br>Cleveland, The Cleveland Museum of Art, \"Gothic Art, 1360-1440\" [Aug. 8 - Sept. 15, 1963].<br>CMA, \"Textiles in Daily Life in the Middle Ages,\" [Jan. 22-March 17, 1985].<br>CMA: Draped in Splendor: Renaissance Textiles and the Church, Sept. 7, 2003-Sept. 26, 2004, no catalogue<br><br>Textiles installation (gallery 115): November 27 2012 - December 9, 2013."]}, "provenance": [{"description": "(Erich Lederer, Geneva, Switzerland).", "citations": [], "footnotes": null, "date": null}], "find_spot": null, "related_works": [], "fun_fact": null, "digital_description": null, "wall_description": "This exquisite embroidered scene of the Coronation of the Virgin features extravagant quantities of gold thread-in the haloes, clothing, background, and circular border with three-dimensional padded areas. Gold thread is also partially covered by at least 20 shades of silk thread so that varying amounts of gold radiate, according to the design, in an exemplary technique called or nu\u00e9, or shaded gold. The figures were embroidered separately and then sewed on the ground. Christ and the Virgin are surrounded by Saints Verdiana and John Gualberto, and six angels playing musical instruments. In Florence, renowned for embroidery, painters usually sketched designs which professionals embroidered, most of whom were men by the 1400s. This design is attributed to the Florentine painter Paolo Schiavo.", "citations": [{"citation": "The Cleveland Museum of Art. <em>The Cleveland Museum of Art Handbook.</em> Cleveland, OH: The Cleveland Museum of Art, 1958.", "page_number": "Mentioned and Reproduced: cat. no. 223", "url": "https://archive.org/details/CMAHandbook1958#page=50"}, {"citation": "The Cleveland Museum of Art. <em>Handbook of the Cleveland Museum of Art/1966</em>. Cleveland, OH: The Cleveland Museum of Art, 1966.", "page_number": "Reproduced: p. 61", "url": "https://archive.org/details/CMAHandbook1966#page=85"}, {"citation": "The Cleveland Museum of Art. <em>Handbook of the Cleveland Museum of Art/1969</em>. Cleveland, OH: The Cleveland Museum of Art, 1969.", "page_number": "Reproduced: p. 61", "url": "https://archive.org/details/CMAHandbook1969#page=85"}, {"citation": "The Cleveland Museum of Art. <em>Handbook of the Cleveland Museum of Art/1978</em>. Cleveland, OH: The Cleveland Museum of Art, 1978.", "page_number": "Reproduced: p. 68", "url": "https://archive.org/details/CMAHandbook1978#page=88"}], "catalogue_raisonne": null, "url": "https://clevelandart.org/art/1953.129", "images": {"web": {"url": "https://openaccess-cdn.clevelandart.org/1953.129/1953.129_web.jpg", "filename": "1953.129_web.jpg", "filesize": "775411", "width": "880", "height": "893"}, "print": {"url": "https://openaccess-cdn.clevelandart.org/1953.129/1953.129_print.jpg", "filename": "1953.129_print.jpg", "filesize": "10098539", "width": "3351", "height": "3400"}, "full": {"url": "https://openaccess-cdn.clevelandart.org/1953.129/1953.129_full.tif", "filename": "1953.129_full.tif", "filesize": "38705660", "width": "3564", "height": "3616"}}, "updated_at": "2019-02-18 08:03:35.294000"},,,,]}`


