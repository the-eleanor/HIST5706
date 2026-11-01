-transformations!
-digitization
	-copyright becomes unnecessary when you destroy the book you're scanning
		-which sucks so bad
		-I hate AI
	-digital formats that are meant to capture as much data as possible, in as high a resolution as possible
	-but these are not the versions you get from copies disseminated online - usually lower quality or the file size would be huge

-devices exist to scan 2D objects and 3D objects
	-recording in different light spectrums exist, resulting in different results in the digital object
	-there is therefore something meaningfully different between the physical and digital
	-life cycle of digital objects - raw data, annotations/semantic enrichment, connections between the digital object and related objects, metadata, paradata, data data data
	-and then you can put it back into the 3D world by printing or 3D printing or otherwise recreating
	-a copy can be copious - it becomes something meaningful

-restructuring, remixing, filtering our research data into a new product
-digitization is not about creating a facsimile, it's creating something new

-metadata: tons of energy spent in creating consistent metadata schemes (i.e. dublin core)
-this is how one digital object can speak to another

-the idea of being remixable isn't always discussed or prioritized

-OCR is not a new thing
-you need to correcting, manipulating, etc, making it recreatable
	-the tutorial did not do that
-OCR is a hard problem that suddenly got solved in the last 6 months
	-tutorial is trying to show a lot of different things but takes unformed, unfinished digital object and turns it into an object for physical research

-OCR was meant to help sight-impaired people
-patterns of light and dark into electrical pulses

multi-layer perceptron
-sensors on a grid that perceived light and dark, sending info to gates that trigger in different ways depending on the signal
	-trips another layer and another, which lights up lights in a specific way that says what the character being scanned is
	-creates font used on things like cheques that can automatically be read as back as the 1950s

-works well with clean typewritten texts
	-legal field loves this
	-image being scanned must be as clean as possible for an accurate scan
		-removing noise, skewing, etc.
		-colour image must be turned to black and white

-OCR models are learning patterns to turn image into text
-if it encounters things in text that is not in model, it can't deal with it

-you need to explicitly say when you've consulted a digital vs physical edition because sometimes the system can't pull everything

-if you feed a computer thousands of examples it can average things and detect things more efficiently
	-feed forward approach
-measure difference between what the computer thinks is a cat and what is actually a cat, and adjust the system accordingly, and run the system again, and cycle to keep reducing margin of error
	-called back-propagation
	-eventually end up with guess that is correct
	-machine learning

-for ocr it makes a big difference, it can now process things that are skewed, noisy, etc.
	-phones can now do this in their own cameras

-historical documents can be more of a problem because of handwritten styles
	-but now there are plenty of systems that can do it and have been trained on a lot of data

-tutorial is using much earlier flavour of OCR

gwen's tutorial!
-optical character recognition
	-author of tutorial is using a scanned book
	-very messy in plain text
	-getting a lot of gibberish and incorrect text, no formatting

goal: clean OCR file and make ordered data set from it

not the goal: to clean the text itself too much
	-just intending to get the text formatted so that you can proofread more effectively
	-OCR'd book is in italian and system was trained on english
		-there are some differences in orthography (accents, long S of german, proper noun capitalization, etc) 
		-affects how old school model sees boundaries, especially if the model is trained on words vs letters

-coding: regular expressions
-detects regular patterns of texts and corrects them (i.e. year-month-day patterns, you can write regular expression what the shape of the date should look like)
	-the OCR does not give us much regular text
-most of the code is just helping to flag the errors and tells where to correct them
	-not doing it for you

-data coming from a book: formatting like headers and footers are unnecessary for cleanup and ordering data

-tutorial assumed you would have the .txt file - had to convert pdf to txt online
	-if you can select text in a pdf scan it means someone already did the OCR on the image of the text
	-mapped the text file output back to pdf

-getting text into colab
	-upload them into colab and find the path there
	-you can copy the path once it's in colab

-r means reading your file, w means writing to it

-tutorial has you copy and paste a ton of info into a code cell
-importing a ton of text
	-saying to colab/python what to do and how to do it

-regular expression is "re"
	-re.xxxx means pull out a specific function
	-annoying but powerful
-regular expressions mix their flags in with the normal text
-I.e.: PAGE (\d+) has a flag looking for any digit of any length
	-two slashes before a character that might be a flag means it'll parse it as normal text
-compiled regular expressions section of tutorial is finding formatting things that aren't required for the digitization

-code creates buckets to read the document, to format it, etc.

-tutorial spat errors when just copypasted

-splitting up text by page number was a pain in the ass
-OCR is not superb for this so you can't rely on OCR'd page number, but you can use longer strings in the headings
	-use regular expression to find them and use them for page breaks
	
-levenshtein distance: give it a number, it measures similarity from OCR'd string of text to model text
	-number determines how different the OCR string can be from the model text provided

-the reason the tutorial didn't work as well as it should have is because gwen had to pull the .txt. herself and not the one the author was using
	-wget was used to find the actual same source file
	-!wget: the exclamation point allows for command line commands in colab/jupiter

-regular expressions have changed in python since the tutorial was written
-must add "r" in front of quotation marks so that it works
	-author was basically writing mini programs and storing them as variables
		-reducing amount of repetitive work
	-but python changed how regular expressions worked
		-idea that you could just put a pattern and compile it into a variable is "bad form"
	-the "r" is indicating that this is a raw regular expression, python will treat it the way it used to treat it
	-this is not something to stumble upon and be able to fix yourself
		-stupid error

-some code was also missing for the levenshtein distance
-setting up how many changes between first and second piece's letters, a ratio
-measuring distance between two words' similarities, not the physical positional distance between them in text
-setting up counters to calculate cost of changes (deletions, insertions, substitutions), and trying to keep count as low as possible
-if this code is working it will appear to do nothing, if not it will throw errors

-indentation and order in python matters

-make sure to change roman numerals into arabic numbers
-code teaches computer how to convert the numbers
-this is a function that is defined ("def") in a chunk of code
-also does nothing at first

-next chunk of text defines what the lev part is looking for
	-providing what the actual text to be looked for is
	-with the shitty OCR, if the text score is a certain value (I.e. 26), increase counter to say yes
		-print out the actual score and the line in the OCR
		-write which page number it's on and show how many have been counted
	-and then do it again for the right-hand side of the page
	-elif is else-if

fin = a bin for the input
fout = a bin for the output
GScriba (name pulled from text, not a universal python term) = turns input into lines

-code takes each line and compares it to the lev text

-print all the things it found that seem close to what you wanted and where to find them
-print total headers, tells you how many pages it found
-if incorrect you gotta play with it some more, like how different it'll allow for
-also writing out file with page breaks
	-don't necessarily wanna keep making new files for incorrect output
	-you can turn code into a comment to disable it, and then enable it when it's working properly

-now there's page breaks in the output file!
-puts ~~~~ (page n) ~~~~ in it to make it an easy expression to search

then making breaks by book's charter
-use code that counts up by sequence, and flags where it doesn't count up by sequence (to find bad OCR)
-detects roman numerals and whether they're counting up properly
-manually fix the OCR'd numbers until no more errors

-code for replacing roman numerals with a more clear definition between them, turning roman numerals to arabic

-now it should be separated by charter too!

-the same process can be applied for folio markers, and where the errors are so that they can be fixed
-also noting italian summaries, which appear after charter number
-same thing with footnotes
	-now it's looking at the bottom of the page, and making sure each number appears twice (once in text, once it footnote) and in consecutive order

making a dictionary
-python dictionary "stores information in key-value pairs"
-I.e. key is cow; holstein, geurnsy, etc is value

-eventually end up with charter dictionary for this source
-detect each part of the text because it's been defined (i.e. charter, page, summary, etc) and then populate the charter dictionary
-search for a specific term, like "every charter that contains mention of the catholic church" and then it will give you the charter and its details

-can use python ton store all the dates in the charter dictionary. should populate itself when running pprint (pretty print)
	-in an ideal world it would spit out info for all the charters in order and you could look up details
	-can also use some html to make it look nicer and more readable
	-formatted even if OCR'd text isn't correct

-could be used to clean up handwritten OCR'd text

describing the pattern of the work you want to do from a scholarly perspective is more important than being able to write the code precisely - you need to understand the code to tell what the flow is but you can find guides and AI to write the code for you


OCR software
-tessaract is old-school but still good
	-looks at pixels but is also trained to predict next word based on previous
-vision model called qwen3.8-27b 
	-cannot be run locally, needs too much power
	-do not use with anything sensitive, if doing so, you must use a smaller local version or one of carleton's computers
	-groq, which can run this, predates musky boy's bullshit
		-based in france, so there is privacy compliance

-handwritten transcription requires a bit more effort

-API key functions as login when using someone else's computational service
-in colab, click the key symbol and add new "secret", name it in a way that the code can use it, and provide the key string

-start with wget to upload image
-drops image through its 27 billion parameters and makes its best guess


scanning in 3D
-all the commands and codes to turn a photo into a 3D model are handled by the 3D scanner
-you can merge scans when scanning different angles or interior and exterior
-.stl is stereolithography, good for 3D printing

-tropy: managing photos for research
-immarkus


https://regexr.com/
https://tesseractocr.org/ocr-online/
https://console.groq.com/home
