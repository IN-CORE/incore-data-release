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

Metadata:

```
{
    "id": "5dbc8478b9219c06dd242c0d",
    "deleted": false,
    "title": "Joplin Building Inventory v6",
    "description": "Building inventory data for Joplin, MO.",
    "date": "2019-11-01T19:16:08+0000",
    "creator": "mondrejc",
    "spaces": [
        "coe",
        "mondrejc",
        "incore"
    ],
    "contributors": [],
    "fileDescriptors": [
        {
            "id": "5dbc8497b9219c06dd242c2b",
            "deleted": false,
            "filename": "joplin_bldg_inventory_v6.dbf",
            "mimeType": "application/octet-stream",
            "size": 24352442,
            "dataURL": "5d/bc/5dbc8497b9219c06dd242c2b/joplin_bldg_inventory_v6.dbf",
            "md5sum": "f59dfd94c1df4d79c3263a2f68ce981b"
        },
        {
            "id": "5dbc8497b9219c06dd242c2e",
            "deleted": false,
            "filename": "joplin_bldg_inventory_v6.prj",
            "mimeType": "application/octet-stream",
            "size": 143,
            "dataURL": "5d/bc/5dbc8497b9219c06dd242c2e/joplin_bldg_inventory_v6.prj",
            "md5sum": "e729936bf5360b37a15365fc295a1901"
        },
        {
            "id": "5dbc8497b9219c06dd242c31",
            "deleted": false,
            "filename": "joplin_bldg_inventory_v6.shp",
            "mimeType": "application/octet-stream",
            "size": 788356,
            "dataURL": "5d/bc/5dbc8497b9219c06dd242c31/joplin_bldg_inventory_v6.shp",
            "md5sum": "2e45ea64ef6a0570554d62a0829d3f3b"
        },
        {
            "id": "5dbc8497b9219c06dd242c34",
            "deleted": false,
            "filename": "joplin_bldg_inventory_v6.shx",
            "mimeType": "application/octet-stream",
            "size": 225316,
            "dataURL": "5d/bc/5dbc8497b9219c06dd242c34/joplin_bldg_inventory_v6.shx",
            "md5sum": "bbb1b5186346a5e59633e87d7d1d770f"
        }
    ],
    "dataType": "ergo:buildingInventoryVer6",
    "storedUrl": "",
    "format": "shapefile",
    "sourceDataset": "",
    "boundingBox": [
        -94.5836409498227,
        37.0155449187188,
        -94.4057690294878,
        37.1472327766023
    ],
    "networkDataset": null
}
```

