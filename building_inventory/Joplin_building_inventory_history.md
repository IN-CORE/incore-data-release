## History of Joplin dataset


1. Original dataset was created by Nathanael Rosenheim as csv files based on Navid's inventory. They contained 28,160 object ids. [This NCSA Wiki page](https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Joplin+Datasets) summarizes his versioning 
   and history. The file **IN-CORE_2ev2_SetupJoplin_FourInventories_2019-08-05_buildinginventory.csv** was used for creating the original building inventory.

2. NCSA curated the file and removed 8 duplicates with disjoint geo data. These were removed and shape file was created. This was a base dataset for Lisa Wang's shape file reffered to as an "old" file. 
   The dataset is on Development Dataservice as **Joplin Building Inventory v6 LW** with an id `60622b01c57ada48e48d7013`.
   
3. At some point there was a revision of the shape file above and that is the current (as of March 21, 2021) version. The changes included:
    
- renaming `archtype` attribute to `archetype`
- strict type definition of attributes; strings, integers, doubles of certain length. For details see [Confluence page with types](https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Building+Inventory+Datatype+Schema).
   
Current dataset, version 6 and its id:

**Joplin Building Inventory v6**: `5dbc8478b9219c06dd242c0d`.