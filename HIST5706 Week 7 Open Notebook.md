finding things

-static websites: creating sites with collections and their metadata
	-first vision of web
	-back and forth query between computers
	-tcip, http, etc etc

-emerging language: php
	-recursive acronym: php homepage
	-builds a website on your computer by querying every time
	-putting data into a form is not inherently secure
		-malicious code breaks it and can break out of the form

-static sites: there is no database to corrupt, nothing to hack

-security certificates must be bought from a trusted provider - one of these providers started fuckin with AI, including pushing code with a placeholder value of "4" for signature data
-whee

-ai services makes things harder to ping and get data
-api analogy: the difference between ordering a big mac on the touch screen and running up on foot to the drive-through window and yelling at them
	-you might get what you want but the restaurant will not be pleased

-inspecting element and messing with it shows how this lives in the browser cache

go sugimoto tutorial

-API: application programming interface
-accessing and distributing open data
-allows for software apps to communicate
-more dynamic sites - change based on user inputs
	-computer-to computer conversation instead of person-to-computer

-APIs can let you embed other sites' live data onto your site in the way you want to display it

-tutorial aims to make and populate a website obtained from another site via api
-learning html and php

-europeana api
	-really big cultual heritage info place in europe
	-you need to register for an API (personal, not project API - lets them make sure you're not a bad actor)
	-install XAMPP (free php dev platform)

API key goes into the URL to grant personalized access
-URL also contains the query

europeana uses JSON (javascript object notation), affects presentation of raw data

we can only see the raw data even with the JSON viewer
-structured more but not perfectly

xampp 
-make php file (helloworld.php), make sure it's .php and not .txt or .rtf
-gotta start and end the php file with tags
-php and html are friends
	-you can still use html tags in the php file
-tutorial has you do the basic bold, link, and photo into the .php file
-you can also host the photo locally
	-works the same except use local address instead of web address
	-better practice, cuz hotlinking is rude

-using variables with PHP
	-define terms before using them

-foundational storage containers for data
-useful for referring back to reusable things

-put the tutorial code in a PHP file and replace placeholder with your API
-tutorial has you basically get the same view as directly using the Europeana URL with the API
-add tutorial code: creates horizontal border line and the total number of data results

-next step is to make it a table
-deleting lines of code as per tutorial and adding what it says leads to an empty table
-add code to manipulate data to be stored in categories, which can be printed to the table

-error handling: what should happen if an operation fails
	-in this case telling it to only display what's available and ignore when it isn't, so it doesn't crash

-you can delete the JSON data above the tables in the tutorial 

-building an API template: can just set up a basic PHP/HTML-based table-maker and input API data later
(remember to respect other sites and explain why you need APIs when requesting them, if required)

-so basically APIs let you pull large amount of data from websites and play around with how it displays on sites
-this stuff lets machine-to-machine communication happen with automation (you don't have to manually build the whole table yourself, entry by entry)
-beneficial for sites that can dig deeper than the heritage sites directly

-your computer pretends to be a server - that's what the server software is for
-with APIs you don't need to be using PHP, you can use other programming languages
-you could even use multiple APIs in the same code

canadiana does not have an API
-adjustments and filters to the search query get added to the URL
	-it's like a query language
	-if you mess with it and try to treat it like an api you could seem like a bad actor if you're not careful, but it is possible to reverse-engineer things
-example code: creates parameters that can be built into the URL
-basically building a version of their search language
-import python packages that help request and parse the results
-code builds up a search URL that lies to the site that it's actually a web browser
-tell code to get the data to craft a URL and then print the result
-200 is code that means successful request, so it confirms that
-if-statement loops to parse the response using beautifulsoup
-get the Soup to find all the link tags (a),  put it into a bucket
-make a dictionary that finds the URL and splits it all apart piece by piece
	-regex, baby
	-what we end up getting is all of the links
-loads into pandas package, forms table of details about the URL
-another loop to tell the code to download all the images
	-fake browser again
-another loop does OCR with an old-school vision model
-csv is created that parses the text for each downloaded page

-shows how APIs are valuable and heritage sites should be doin it, cuz this is a pain in the ass

-APIs let you get the exact information you want, without any bells and whistles, from a service that understands that it will be giving you lots of data at once

-this colab notebook imitates manually doing each step of finding, downloading, OCR-ing the pictures

collection builder is static but you can use pseudo-API code
-because it's static and not a database the load is actually somewhat minimal


wget tutorial

-wget is a software package that manages and automatically downloads things through command line, crawls web for downloads, and makes local copies of sites
-get it downloaded without doing it manually
-especially if the site Sucks

-can tell the command line things that mean things to the computer
-command line does not inherently know wget - must be installed
-mac installation instructions are very slightly more involved with more things to download
	-possibly just poor instructions for windows

-do not let external agents do literally anything on your computer

-follow instructions for downloading homebrew from the homebrew site
-homebrew is a package manager, like installation wizards

-just typing wget (or wget.exe for windows) will test if it works without pulling anything

-make a new folder/directory so that everything doesn't just plop into your documents like loose M&Ms

-test run: you can download the course site
	-contents but not formatting, doesn't nab the css

wget lets you do recursive downloads: go through links and download all pages to a certain depth (default 5)
-other codes let you not move up in the directory (only down in the hierarchy), level of link depth, speed, wait a set amount of seconds
-and more!
wget manual has more

-build in a wait to make sure you're not flagged as a malicious bot

-sometimes it looks like nothing happens but that does not mean that nothing is happening
	-sometimes you gotta wait for confirmation of finished download

-details on the tutorial don't necessarily tell you WHY you're doing some things, making it frustrating to troubleshoot

-can tell it to look for specific words, download specific (or exclusionary) file types, etc.

windows: .\wget.exe
	-tells windows run the frickin program

-for windows, put it in the folder you're working in, not the windows folder
-get the one for your chipset

in colab it's !wget (tells it it's not python)
	-colab has its own terminal setup but not necessary

-figure out the commands for killing prompts just in case
-be specific with what you're trying to download

-wget in colab lets you use the files you get right in colab easily


