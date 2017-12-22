# scrapyd-arm64v8

I couldn't find a docker ARM image for scrapyd based on python3, so I made one myself. It's in use on a Raspberry Pi 3 running RancherOS (64bit). Relying on alpine because image size matters.

My crawlers usually persist into MySQL databases, therefore I baked mysqlclient and it's dependencies into the image. This was the easiest way to deploy scrapy projects relying on mysqlclient as the dependency install via scrapyd fails due to missing build dependencies.

---

* [Scrapy][scrapy] is a fast high-level web crawling and web scraping framework, used to crawl websites and extract structured data from their pages. It can be used for a wide range of purposes, from data mining to monitoring and automated testing.
* [Scrapyd][scrapyd] is a service for running scrapy spiders.
* [Mysqlclient][mysqlclient] was chosen because of https://stackoverflow.com/questions/4960048/python-3-and-mysql.


[scrapy]: https://github.com/scrapy/scrapy
[scrapyd]: https://github.com/scrapy/scrapyd
[mysqlclient]: https://github.com/PyMySQL/mysqlclient-python