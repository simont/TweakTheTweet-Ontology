README
Created by: Simon Twigger
Date: January 22 2010
Software: Protege 3

TweakTheTweet Tags Ontology
----------------------------

This is an initial attempt to create a basic RDF/OWL ontology corresponding to the tags being suggested by the TweakTheTweet initiative from UC Boulder (see http://epic.cs.colorado.edu/helping_haiti_tweak_the_twe.html). Its still a work in progress so any suggestions are more than welcome!

I have taken many of the English and the French tags and created classes corresponding to the tags (eg location) and also properties such as has_location that can be used to tag something like a tweet, indicating that it has some location information in it. The domain of this property is set to be the Location class so in an appropriate triple store you can use RDFS inferencing to place anything that is the subject of a has_location predicate into the Location class. This works conceptually but might be overcomplicated and is only useful when there is inferencing available.

The various properties like 'has_location' also have one or more tag_terms associated with them - these are the words/abbreviations that you could look for in a tweet that might indicate that you should tag it with an appropriate property. For example, has_location has tag_terms: loc, location, emplacement, if you had a tweet containing any of these words then you could create an RDF triple like this:

tweet:123456789 has_location "true"

If this also has #need or #trapped or similar tags you could create triples like these

tweet:123456789 has_trapped "true"

and this would drop this tweet into the Trapped and Location Classes. A SPARQL query looking for tweets mentioning people who are Trapped and where there is location info available could then pull this out. We could also map the Trapped class to the Ushahidi '1c. Personnes prises au piege | People trapped' category and start to link up these two datasets. See http://wiki.github.com/simont/Ushahidi-Category-Ontology/ for a basic ontology describing the Ushahidi categories.

