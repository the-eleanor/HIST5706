-there are library courses for doing the really detailed stuff vis a vis programming and machine setup
	-can contribute to certificate in digital humanities training

-github tracks when you're doing stuff, tracking snapshots
	-links to other snapshots, but no reason to use it in this class

forvm.ca - network analysis as a board game

serendipitous encounters - trying to get out of narrow rut of research interests
-twitter used to be a great place for these serendipitous encounters, as a water cooler sort of space for digital humanities
-twitter's undeath killed this sorta, bluesky isn't quite the same and some people moved to mastodon

serendipity -> platforms/intra -> playfulness

-platforms are watching you and may surface connections (i.e. popular hashtags)
	-not necessarily sinister, could be just watching trends
-lead to unexpected and foster exploration


-historic england imagery is all offline because of reliance on live feeds instead of images

critiquing is only so useful: you can't build anything with sledgehammers, just break it

digital platforms:
-omeka
-mukurtu.org
meant to make discovery, sharing, playfulness of exploration possible

-digital preservation: making images and metadata digital, living on a computer connected to the internet
	-who pays for the server? who pays for digital file upkeep? who pays for electricity?

-budget for a project is a theoretical document - shows project value
-grant application-writing isn't busywork or fantasy, it's a statement of where value is

-the infrastructure of learning, thus theories of learning, are embedded in classroom itself
	-e.g. desks and chairs bolted down facing forward, leading to directional transmission of knowledge, vs whatever the heck is going on in this classroom

-playfulness and serendipity are tools for fighting back against strict spatial rhetorics

-digihist is more fun and interesting if serendipity is part of the process from the beginning
-platforms that we use to do the work can foster/have impact on serendipitous encounters

-digital history does different things, kaleidoscope of perspectives
	-computational history is about Finding The Answer

![[Pasted image 20261001121701.png|214]]

-four different kinds of digihist that one might do
replicate/reproduce someone else's study 
	-do you end up with the same result?
	-reproducible study increases value of study 
	-robust: same result with different method means result is robust

-fragile to have one result that only came from one study
-archaeology destroys relationships between objects if there's no recording of data as archaology is done

-in general it is extremely good to share your results and data
	-definitely some instances where it isn't (not your data to share, etc)
	-FAIR and CARE

-data gets lost - losing access to email, losing access to hardware, etc.
-also some people are assholes and don't wanna share data
	-pressure on those people means that standpoint is gradually less common

-a lot of digital history is mucking about
-if you can appreciate the mucking around you can also spot the bullshit
	-spot someone using methodologies that aren't supported by their data


DO NOT rm-rf in a command line

Pay attention to difference between mac and windows in command line shenanigans

split command and csplit command:
-csplit will look for a pattern and chop a file up accordingly

command line for windows to be splitting files
```
$i=0; (Get-Content pg2087.txt -Raw) -split '(?m)(?=^CHARLES DARWIN TO)' | ForEach-Object { Set-Content "darwin$("{0:D3}.txt" -f $i++)" $_ }
```
command line for mac to be splitting files
```
csplit -f darwin -n 3 pg2087.txt '/CHARLES DARWIN TO/' '{212}' 
```
voyant gives you a way to explore text and trends with topic modelling, local to your computer
-mcgill did not keep the servers going after the creator passed

-look at the last stage of your project and consider how it might degrade
	-if you include paradata, methodologies, etc, you'll better be able to repeat it

project: something useful for future research
-something that pushes you out of comfort zone
-it's okay if it's not fully complete project
-look at mallory papers for potential content
-work on something that's meaningful to you

unessay - reflection on experiment of project

unessay reference: epoiesen.carleton.ca