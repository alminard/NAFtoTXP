Library to convert a NAF files in columns for TempRelPro, TimePro, EventPro.


In order to use NAFtoTXP we need the kaflib library v1.1.9 or highest, jdom v2.0.5, yamcha and tinysvm and a repository tools/ containing: 
* addDiscourse (http://www.cis.upenn.edu/~nlp/software/discourse.html)
* MorphoPro (http://hlt-services2.fbk.eu/textpro/?p=91)

Usage for creating training files for TempRel:
```
cat NAF_in_file | java -cp lib/kaflib-naf-1.1.9.jar:lib/jdom-2.0.5.jar:lib/NAFtoTXP_v11.jar eu.fbk.newsreader.naf.NAFtoTXP_v11 TXP_out_file TML_ref_file chunk+entity+event_ref+timex_ref+connectives+srl+dep+morpho+dct+main_verb+tlink_ref train
```

Usage for creating testing files for TempRel:
```
cat NAF_in_file | java -cp lib/kaflib-naf-1.1.9.jar:lib/jdom-2.0.5.jar:lib/NAFtoTXP_v11.jar eu.fbk.newsreader.naf.NAFtoTXP_v11 TXP_out_file chunk+entity+event+timex+connectives+srl+dep+morpho+coevent+dct+main_verb+pairs eval
```

Usage for adding new tlink/clink into the NAF file:
```
java -Dfile.encoding=UTF8 -cp lib/TXPtoNAF_v4.jar:lib/jdom-2.0.5.jar:lib/kaflib-naf-1.1.9.jar eu.fbk.newsreader.naf.TXPtoNAF_v4 $NAF output_temprel.tlinks [BEGINTIME] TLINK
```

