determine_REase
input:  subSequences, default_REase, REase_list
output: REase/None
process:
change the order of REase_list, make default one be the first
Iterate the REase_list
1. subSequences to overlapped_subSequences
2. check REase

Class REase
properties:
name, recognition_site, cleave_location
methods: 
get_name
get_recognition_site
cleave_location

Class OligoGroup
properties:
sequence, subsequences, REase, 
methods:
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzE0NjEzMTEsMTc5OTIyMzc1XX0=
-->