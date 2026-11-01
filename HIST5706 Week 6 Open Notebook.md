-project: taking letters and look at correspondence as change over time

-open notebooks don't have to be unprofessional necessarily, they can be academic documents in their own right by organizing thoughts and processes

nodegoat
-database must be searchable to be a database
-relational database: connections between datapoints

nodegoat is a database managing system
-you need to request an account to be approved manually oof

-create project under management tab
-set up object types under model
	-tutorial looks at 20th c books by different publishing houses
		-categories: publishing house, author, work
		-interrelated categories and subcategories
	-create object type and then attributes
		-i.e. publishing house is name, location, author is name, nationality, place and date of birth
	-remember to check off type of data, i.e. name
	-link objects based on interconnected data, save the most interconnected category (in this case, books, which have both publishing house and author)

-connect object types to project
	-nodegoat already has a database for basic info like locations

-further define objects
	-sub-object to allow objects with unknown attributes like date

-add data objects
	-start with, in this case, authors and publishing houses because they're linked to works
	-can use a .csv if available
	-adding works will let you already choose the stuff you've already put in for other categories, like publishing house

node graphs: you can always easily come back to add data if need be

data is now in the database, can be sorted in various ways

-map function: data needs to be properly geographically/temporally linked or it won't work

-nodegoat video tutorials are a little hard to use because they're outdated for the site's current state, but can give some help on where to look

-sub-objects: a way to connect city to objects
	-adding sub-object option "city"
	-city is property of publishing house, location is property of city
	-can attach it to an object type, in this case city
	-temporally link it using date sub-object tab
	-and then update all the data, I.e. putting location into every publishing house etc.

-nodegoat also lets you see a timeline of the data when there's temporal info
-you can also add media, like mieke's embroidery samplers

-there is so much literature about database structures and platforms etc, can get overwhelming
-starting at the end: what is the end goal, work backwards from there

-immarkus is like nodegoat, lets you define a data model, but more image-based
	-can link specific info to specific things in photos
		-i.e. tents in mount everest photos
		-can add tags and info to these selections
	-after you do that, it can link and show interrelations between photos based on their contents

-graph databases aren't big in general history, historians still consider spreadsheets databases

-annotate things in documents, use regular expressions to remove rest of text
-pulled data can include any degree of information
	-i.e. material culture from mallory letter, describing size and type of objects
	-can link locations to material culture

diagrams and graphs are databases too!
-tables can be derived from network models etc

-create different kinds of objects with code and create a database by querying graph
-can show what the interrelations are
-can use code on the data to show what topics tend to be correlated or words that come up frequently with certain topics of words (i.e. religion -> monasteries, or location -> what foods were eaten there)
	-hard to do with a regular database

-everest documents:
	-lots of interaction between climbers and locals/local systems
	-i.e. photography being used to enforce local abbots' authority

-this is a way of creating assemblages, based on written text