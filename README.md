# Yay IMDBs !

Overview
--------
Yet Another Ying IMDB Scraper

This is a simple imdb scraper, that I created as part of my [onbox](http://github.com/o-sam-o/onbox) project.  I have moved it out into it's own gem so I can share it across projects.

Features
--------
 * Basic search functionality, which can be limited based on: title, year and type (tv show or movie)
 * Build on Nokogiri rather than Hpricot
 * Support for scraping most info from a movie page
 * Support for getting a thumbnail and a large image url
 * Support for scraping tv show episodes

Installation
------------

	gem install yayimdbs

Examples
--------

	> require 'yay_imdbs'
	 => true
	> YayImdbs.search_for_imdb_id('Avatar')
	 => "0499549"
	> YayImdbs.search_for_imdb_id('Avatar', 2004)
	 => "0270841"
	> YayImdbs.search_for_imdb_id('Avatar', nil, :tv_show)
	 => "0417299"
	> info = YayImdbs.scrap_movie_info('0499549')
	 => {lots of stuff here}
	> info[:title]
	 => "Avatar"
	> info[:small_image]
	 => "http://ia.media-imdb.com/images/M/MV5BMTA3MzcxNTI2MjNeQTJeQWpwZ15BbWU3MDYwMTc0MzM@._V1._SX100_SY122_.jpg"
	> info[:large_image]
	 => "http://ia.media-imdb.com/images/M/MV5BMTA3MzcxNTI2MjNeQTJeQWpwZ15BbWU3MDYwMTc0MzM@._V1._SX488_SY595_.jpg"
	> info[:tagline]
	 => "Enter the World"
	> YayImdbs.scrap_movie_info('0411008')[:episodes].first
	 => {"series"=>1, "episode"=>1, "title"=>"Pilot: Part 1", "date"=>Wed, 22 Sep 2004, "plot"=>"Forty-eight survivors of an airline flight originating from Australia, bound for the U.S., which crash-lands onto an unknown island 1000 miles off course, struggle to figure out a way to survive, why trying to find a way to be rescued."}

Contributors
------------
[luisramalho](https://github.com/luisramalho)

Licence
-------
MIT

Contact
-------
Sam Cavenagh [(cavenaghweb@hotmail.com)](mailto:cavenaghweb@hotmail.com)
