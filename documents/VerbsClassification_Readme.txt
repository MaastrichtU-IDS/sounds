Procedure for verbs classification:
(see file: "Verbs_organizedbySynsets.xlsx")

1) From the "master" dictionary select all words ["Word"] (and number of occurrence ["Occ"]) that:

	1a) are POS-tagged as "Verb" for the majority of entries 
	1b) have at least one Wordnet (WN) synset with pos=Verb (wn.synsets('WORD',pos='v') -> ["WN_synset"]

2) For each selected word:
	 
	2a) Select all WN synsets associated with the word morphy (e.g. wn.morphy('burning')->"burn" ["WN_morph"]), and
	2b) for each synset:
		Select Wordnet definition  -> ["WN_def"]
		Select Wordnet root_hypernym  -> ["WN_root"]
		Check if WN synset is present in Verbnet (using nltk.verbnet.classids(wordnetid=synsetKey))
			if True -> classify synset using Verbnet classes -> ["VNFlag"] = 1, ["VN_cat"]->["VN_classNum"]
			->["VN_class"]
			Discard unclassified synsets for this word
		Check if WN synset is present in Framenet (using mapping file from https://web.eecs.umich.edu/~mihalcea/downloads.html#verbmap) 
		-> ["FN_cat"]

3) Select all words for which step 2) did not produce at least one classified synset
	3a) Inspect and assign manually a Verbnet class to the relevant synsets (at least one per word) -> 
	["ManFlag"]=1, ["VN_classNum"] -> ["VN_class"]  -> ["VN_cat"] = VN_classNum.x
	3b) Discard irrelevant synsets (not in the file)

4) Review synsets discarded in step 2 and add synsets (as in 3) in case of relevant omissions.  
5) Convert the Verb class hierarchy to OWL format -> file: "WNVN_Verbs_withcomment0_RDF.owl"
  



 "
 		 

 

	
	  



   
