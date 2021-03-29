## History of Seaside dataset

1. The first Seaside building inventory was probably made by Dylan with 4,000+ buildings. It is a shape file of **ergo:buildingInventoryVer5** type, id `5df40388b9219c06cf8b0c80` as of March 21, 2001. This file does NOT have 
   structure id and cannot be used for chaining/linking House unit allocation and Population dislocation analyses.

2. The second, original dataset for Social analyses was created by Nathanael Rosenheim as a csv file (type **ergo:buildingInventory**. It contained 3,000+ buildings. [This NCSA Wiki page](https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Population+Dislocation) summarizes his previous versions  
   and history. The file **IN-CORE_1bv6_SetupSeaside_FourInventories_2019-08-02_buildinginventory.csv** is being used in Dataservice with an id `5d5433edb9219c0689b98344`. This file has the structure id.

Metadata of the shapefile:

```
{
    "id": "5df40388b9219c06cf8b0c80",
    "deleted": false,
    "title": "Seaside Buildings",
    "description": "Seaside buildings with building period",
    "date": "2019-12-13T21:32:56+0000",
    "creator": "cnavarro",
    "spaces": [
        "cnavarro",
        "incore"
    ],
    "contributors": [],
    "fileDescriptors": [
        {
            "id": "5df4045db9219c06cf8b0c9e",
            "deleted": false,
            "filename": "seaside_bldg.dbf",
            "mimeType": "application/octet-stream",
            "size": 2574636,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0c9e/seaside_bldg.dbf",
            "md5sum": "b140fe2ca0855269e656298f007038ad"
        },
        {
            "id": "5df4045db9219c06cf8b0ca1",
            "deleted": false,
            "filename": "seaside_bldg.fix",
            "mimeType": "application/octet-stream",
            "size": 56161,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0ca1/seaside_bldg.fix",
            "md5sum": "6988fdcfa4e77f47bc106e0faad9d5dc"
        },
        {
            "id": "5df4045db9219c06cf8b0ca4",
            "deleted": false,
            "filename": "seaside_bldg.prj",
            "mimeType": "application/octet-stream",
            "size": 205,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0ca4/seaside_bldg.prj",
            "md5sum": "30e5566d68356bfc059d296c42c0480e"
        },
        {
            "id": "5df4045db9219c06cf8b0ca7",
            "deleted": false,
            "filename": "seaside_bldg.qix",
            "mimeType": "application/octet-stream",
            "size": 63392,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0ca7/seaside_bldg.qix",
            "md5sum": "a64ca45a071e5a03af64921ddff5be75"
        },
        {
            "id": "5df4045db9219c06cf8b0caa",
            "deleted": false,
            "filename": "seaside_bldg.shp",
            "mimeType": "application/octet-stream",
            "size": 131112,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0caa/seaside_bldg.shp",
            "md5sum": "c0c1e8472358c922669b6865980a6c47"
        },
        {
            "id": "5df4045db9219c06cf8b0cad",
            "deleted": false,
            "filename": "seaside_bldg.shx",
            "mimeType": "application/octet-stream",
            "size": 37532,
            "dataURL": "5d/f4/5df4045db9219c06cf8b0cad/seaside_bldg.shx",
            "md5sum": "cf2b424679d630f7e7d26bdd2456f245"
        }
    ],
    "dataType": "ergo:buildingInventoryVer5",
    "storedUrl": "",
    "format": "shapefile",
    "sourceDataset": "",
    "boundingBox": [
        -123.9552452924777,
        45.97138528822377,
        -123.8853334778418,
        46.01756831594854
    ],
    "networkDataset": null
}
```

Metadata of the csv file:

```
{
    "id": "5d5433edb9219c0689b98344",
    "deleted": false,
    "title": "Seaside Building Inventory",
    "description": "Building inventory data for Seaside, OR for Housing unit allocation.",
    "date": "2019-08-14T16:16:45+0000",
    "creator": "mondrejc",
    "spaces": [
        "coe",
        "mondrejc",
        "incore"
    ],
    "contributors": [],
    "fileDescriptors": [
        {
            "id": "5d5433ffb9219c0689b98360",
            "deleted": false,
            "filename": "IN-CORE_1bv6_SetupSeaside_FourInventories_2019-08-02_buildinginventory.csv",
            "mimeType": "application/octet-stream",
            "size": 572729,
            "dataURL": "5d/54/5d5433ffb9219c0689b98360/IN-CORE_1bv6_SetupSeaside_FourInventories_2019-08-02_buildinginventory.csv",
            "md5sum": "cdaef8e3d695b8b5e77ad98a02f6a3e6"
        }
    ],
    "dataType": "ergo:buildingInventory",
    "storedUrl": "",
    "format": "table",
    "sourceDataset": "",
    "boundingBox": null,
    "networkDataset": null
}
```

