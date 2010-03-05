README
Created by: Simon Twigger
Date: March 5 2010
Software: Protege 3

TweakTheTweet Tags Ontology
----------------------------

This is an initial attempt to create a basic RDF/OWL ontology corresponding to the tags being suggested by the TweakTheTweet initiative from UC Boulder (see http://epic.cs.colorado.edu/helping_haiti_tweak_the_twe.html). Its still a work in progress so any suggestions are more than welcome!

I have taken many of the English and the French tags and created classes corresponding to the tags (eg location) and also properties such as has_location that can be used to tag something like a tweet, indicating that it has some location information in it. The domain of this property is set to be the Location class so in an appropriate triple store you can use RDFS inferencing to place anything that is the subject of a has_location predicate into the Location class. This works conceptually but might be overcomplicated and is only useful when there is inferencing available.

Im using this ontology to tag tweets captured via the http://tweetneed.org site for the Haiti earthquake. The ontology is being updated to handle TtT syntax from the Chile and the various spanish hashtags that are emerging from that event. I've added in SKOS as a better way to capture these tags as labels and altLabels.

As the data accumulates it should also be possible to map various tagged tweets into the Ushahidi '1c. Personnes prises au piege | People trapped' category and start to link up these two datasets. See http://wiki.github.com/simont/Ushahidi-Category-Ontology/ for a basic ontology describing the Ushahidi categories.

