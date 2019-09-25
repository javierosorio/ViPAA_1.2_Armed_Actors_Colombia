===========================================================
===========================================================
= README
= Violent Presence of Armed Actors in Colombia
= ViPPA v1.2
= Javier Osorio, University of Arizona
= 09/25/2019
===========================================================
===========================================================

This repository contains the replication files and database to generate the Violent Presence of Armed Actors in Colombia (ViPPA) v1.2 event database.

ViPPA provides geo-referenced data at the daily municipal level related to the violent presence of armed actors in Colombia between 1988 and 2017.

The data categorizes armed actors in four main types:
- Government forces
- Insurgent organizations
- Paramilitary groups
- Criminal organizations

Each of these types of actors is further disaggregated in a multitude of specific organizations.   

ViPPA is generated using computerized text annotation with Eventus ID, a protocol for supervised event coding capable of geo-referencing actors mentioned in text written in Spanish (Osorio & Reyes 2016).

The information used as an input for the computerized coding came from Noche y Niebla, a collection of narratives of human rights violations published by the Centro de Investigación y Educación Popular, CINEP.

More detials available at https://www.colombiaarmedactors.org/


===========================================================
= 1. Event Coding
===========================================================


This folder contains the files for generating the event data for the database of Violent Presence of Armed Actors in Colombia using Eventus ID.

Users can find the details of Eventus ID, system requirements, and manual at:
https://github.com/javierosorio/Eventus_ID_2.0

The folder contains the following files:
- config_COL_5.txt: is the main configuration file.
- EVENTUS_ID.pl: is the main software file containing Eventus ID.
- corpus_nocheyniebla_1988_2017.txt: is the corpus file containing the Noche y Niebla narratives from CINEP.
- actors_COL_20180828.txt: is the list of all actors.
- departamentos_COL.txt: is the list of department names.
- municipios_COL.txt: is the list of municipality names.
- filtros_COL_3.txt: is the filter of locations for geographic disambiguation.
- blank_DEMO.txt: is a blank file.


After following the installation procedures of Eventus ID, users can run the coding task by opening the command line and entering the following command:

perl EVENTUS_ID.pl config_COL_5.txt

After completing the coding task, Eventus ID will generate two output files:
- texto_COL_20180919: contains the textual event coding output
- codigos_COL_20180919.txt: contains the numeric event coding output


===========================================================
= 2. Recoding dofiles
===========================================================

This folder contains the Stata dofiles to clean, recode, and structure the database of Violent Presence of Armed Actors in Colombia.

The dofiles included in this folder are:
- codigos_COL_20180919.txt: is the raw database of event data coded in the previous step
- 0_run_all.do: is the master dofile controlling all other procedures (1-5)
- 1_setup.do: conducts the first cleaning pass of the data
- 2_actor.do: generates data by main actor categories

To run the recoding dofiles, users will need Stata 15.

===========================================================
= 3. Methodology and Codebook
===========================================================

The "Methodology_ViPPA_v1.2.pdf" contains the metodological details and codebook.




