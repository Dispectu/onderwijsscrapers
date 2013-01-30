Onderwijsscrapers
=================

Features
----------------------
* Export scraped items to ElasticSearch (ES)
* Export scraped items as JSON files to disk
* Data sources/scrapers:
  * [SchoolVenstersOnline](http://schoolvo.nl/)
    * General information (name, address, BRIN, etc.)
    * Indicator 2 ("Resultaten - Slaagpercentage")
  * [DUO](http://data.duo.nl/)
    * General branch information ("02. Adressen alle vestigingen")
    * Students per branch by ZIP code ("02. Leerlingen per vestiging naar postcode leerling en leerjaar")
  * [Onderwijsinspectie](http://tkrtp.owinsp.nl/schoolwijzer/zoek_scholen)
    * All Voorgezet Onderwijs (VO) schools
      * General information (name, address, BRIN, etc.)
      * Rating history (per branch and education structure)
      * Reports (per branch and education structure)

Install and run
----------------------
    $ pip install -r requirements.txt
    $ cd onderwijsscrapers/
    $ scrapy crawl <crawler_name>

Available crawlers: ``vo.owinsp.nl``, ``schoolvo.nl``, ``data.duo.nl``.

Todo
-----------------------
* Replace this README with proper documentation
* Document schema's of different sources
* Add datetime information to items when scraped
* Add ES index schema's
* SchoolVenstersOnline:
  * Extend to scrape more data (try to get as much data as possible that is not available through DUO)
* DUO
  * Add other VO data
  * Add Primair Onderwijs (PO) data
* Onderwijsinspectie
  * Add PO data
  * Also scrape reports on the education sector overview page (see for example "Feliceum"), these reports are not included on the detail pages of a specific education structure/branch
