# Datagraft-RDF-to-Arango-DB-
A node script to transform datagraft RDF mappings to Arango DB values

## How to
To run the script localy start a comand-window to run node localy

1. Add / Edit the RDF mapping values, and vocabulary for the RDF mapping. The RDF mapping is in the value ```const data``` and the vocab in ```data_vocab```
2. load the ```transformscript.js``` into Node. (In node repl it can be done with `.load transformscript.js`)
3. Read the csv file with ```read([path_to_file]);``` specifying the file path as input.
4. Build a list of haddings with ```build();``` this is used to get the propper colum when inserting data trhought the transformation
5. Now run the mapping function with ```run();``` this should start the entire process and outputs a .json file for edges and for values corresponding to the arangoformat.

The json files is with one object per line, therby noe filesize limitation to importing into Arango DB

## Future improvments
- Implementing a csv parser, so we ensure it is not braking on bad formatting / different formatting than whats coded.
- Run the mapping per line while reading the csv, don't read everything in to memory before transforming.