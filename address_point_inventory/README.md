# Address Point Inventory
Current ongoing information is in https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Address+Point+Inventory+Datatype+Schema

## Column definitions and examples
* ADDRPTID - Address point ID: Value: XREF2965-0160-0011-000AP001

    * Primary key for the AP inventory
    * The AP ID combines the unique parcel ID XREF which is based on the Galveston County Appraisal District data and a counter for number of address points in the parcel.
* APPR_BLDG - Appraised valueis available in the Galveston CAD data. The data is missing from this (Galveston) inventory.

* BLDGOBS - The variable is designed to help identify address points that are linked to a building. This variable is binary

    * 0 = AP is not in a building or is not the first AP in the building
    * 1 = AP is in a building and this is the first or only AP in the building. The number of observations with bldgobs = 1 is designed to be the same as the number of buildings  in the Building Inventory.

* BLOCKID - The block ID. Value: 481677244002047

* BLOCKIDSTR - The block ID with letters CD added tot the start. Value: CB481677244002047

* GUID

* HUESTIMATE - An estimate of the number of housing units in the parcel.

    * The huestimate can be used to identify multi-family parcels.
    * The number of housing units is based on an iterative process that compares number of housing inits reported in the 2010 Census, the size of the building footprint, land use information, and zoning information.
    * Full workflow to replicate file has been lost.

* PAR_ID -  Parcel Identifier. The parcel ID is based on the parcel ID XREF.  Value: XREF2965-0160-0011-000

* RESIDENTIAL - boolean. Residential only - if this inventory only includes residential parcels.

* STRCID - The structure ID is based on the parcel ID XREF. Value: XREF2965-0160-0011-000

* YEAR_BUILT - It comes from County Appraisal District Data.