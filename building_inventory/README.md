#Building Inventory

Current ongoing information is in https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Building+Inventory+Datatype+Schema

## Columns
* A_STORIES     -           Total number of above-ground stories for the building

This information was extracted from the Tax Records and specifies the number of above-ground stories for the building. 

* AGE_GROUP

* APPR_BLDG      -           Appraised value of the building in dollars

Derived from the Tax Records, we directly recorded this information for single-family residential buildings.  For some non-single-family buildings, appraisal and assessment information was available at the parcel level.  For these records, we divided the appraised value of the parcel in the same proportion as the square footage of the various buildings in the parcel to the total parcel built square footage.  For instance, if a parcel had an appraised value of $5,636,700 and had only one building on it, that buildings appraised value was computed as $5,636,700.  For another parcel with an appraised value of $ 105,200 and two buildings of square footage 5352 and 4000 respectively, the appraised value of the smaller building is computed as $44,996 and that of the larger, as $60,204.  This is not particularly troublesome in most cases, because multiple structures within parcels generally tend to be developed in relatively short time frames.  Note that building values within a parcel may exhibit significant variation that is not captured here, if the year of construction, type of use and structure vary widely for the buildings within the parcel in question.

* APPR_LAND

* APPR_TOT

* ARCHETYPE

* B_STORIES     -           Total number of below-ground stories for the building

This information was extracted from the Tax Records and specifies the number of below-ground stories for the building. 

* BLDG_ID         -           Building Identifier

Unique Identifier (Primary Key) for each building record – Duplicates are not allowed in this field. 

* BROAD_OCC   -           General Occupancy Class for the structure

The building use is categorized into categories based on reconciling several land use and zoning descriptions in various tables from the Tax Assessor’s Database.  These general occupancy categories are widely used for summary information and cross tabulations in the accompanying workbook.  The table below contains examples of the general occupancy types. 

|General Occupancy Category|
| ------------------------ |
|Education|
|Food and Entertainment|
|Health Care|
|Heavy Industrial|
|Light Industrial|
|Multi-family Residential|
|Office Commercial|
|Parking Garage|
|Places of Worship|
|Retail Trade|
|Single-family Residential|
|Wholesale Trade|

* BSMT_TYPE    -           Basement classification for the building

Derived from a detailed analysis of the Tax Records, this field specifies the type of basement for the building, as seen in the table below. 

|Basement Category|Amount of Basement|
| --------------- | ---------------- |
|COMMERCIAL| BSMT|	
|CRAWL|	0-24%|
|FULL|	>75%|
|NONE| |	
|PART|	25-75%|
|SLAB| |	

* CONT_VAL      -           Value of contents contained within the building

Borrowing FEMA’s methodology, the content value is estimated as a function of the replacement cost – the table below shows the relationship between replacement costs and content value. 

|Occupancy Type|Content Value|Occupancy Type|Content Value|
| ------------------- | --- | ------------------- | --- | 
|All Residential Units|	50%|	Food and Entertainment|	100%|
|Retail Trade|	100%|	Parking Garages|	50%|
|Wholesale Trade|	100%|	All Industrial|	150%|
|Personal/Repair Services|	100%|	Religious|	100%|
|Commercial Offices|	100%|	Emergency Response|	150%|
|Banks|	100%|	Schools|	100%|
|Health care related|	150%|	Colleges and Universities|	150%|

* CT_LAT           -           Latitude of Census tract in which the building is located

The Latitude coordinate of the census tract within which the building is sited, in the North American Datum of 1983. 

* CT_LON           -           Longitude of Census tract in which the building is located

The Longitude coordinate of the census tract within which the building is sited, in the North American Datum of 1983.

* DGN_LVL         -           Design Level and Building Quality Indicator

Following FEMA’s specifications in HAZUS MR-3 of design level and building quality, we coded all the buildings in the database as one of the four combinations listed in the table below.  This field has been created in order to facilitate comparative analyses between HAZUS MR-2 and MAEViz 4, using the same inventory and hazard parameters. 

|Design Level and Building Quality|
| --------------------------------|
|High - Code|
|Moderate - Code|
|Low - Code|
|Pre - Code|

* DWELL_UNIT            -           Total number of dwelling units in the building

Derived from the Tax Records, we set the single-family dwellings to one dwelling unit, duplexes to two and triplexes to three, directly from the single-family unit tabular records.  Similarly, for non-residential buildings, we directly used the number of dwelling units as recorded in the Tax Records.  There are 17,906 non-residential buildings in the building dataset, of which 17,609 buildings have no dwelling units, 266 have one dwelling unit and 31 have more than one dwelling unit.  For multi-family residential, where available, we extracted the dwelling unit information from several tables.  Where the dwelling unit count was not available or obviously unreliable, we imputed the number of dwelling units.  See notes under field “IMPUTED” for additional information. 

* EFACILITY        -           Essential Facility designation

Derived from multiple sources (Tax Records, FEMA, internet sources, etc.), this field follows FEMA conventions for the designations of essential facilities.  Buildings designated as Essential Facilities are expected to provide services to the community and should be functional in the aftermath of a disaster.  Essential facilities include hospitals, police stations, fire stations and schools.  This dataset could be improved by including the number of beds for hospitals and the number of fire trucks at each fire-station location.  For the most part, buildings eventually classified as essential facilities were not available in the Tax Records and those parcels were either listed as “Vacant Land” or “Exempt”.  We derived additional police and fire stations from HAZUS MR-3 with address information, geocoded them and then physically moved the points to the correct parcel location.  In addition, several fields, including structure type and square footage were imputed.  We also obtained information about private schools from the internet and other incidental databases.  We then geocoded these as points and physically moved them to the correct parcel location by analyzing building footprints from aerial photographs.  Again, other fields for these records were imputed.  See notes under field “IMPUTED” for additional information.  The table below shows the various Essential Facility classifications and codes in the building inventory database. 

|Code|Description|
| --- | ---------------------- |
|EFFS|	Fire Stations|
|EFHM|	Small Hospital|
|EFHL|	Medium Hospital|
|EFHS|	Large Hospital|
|EFMC|	Medical Offices/Clinics|
|EFPS|	Police Stations|
|EFS1|	Grade Schools|
|EFS2|	Colleges and Universities|


* FAILURE

* FF_ELEV

* FUN

* G_ELEV

* GEOMETRY

* GSQ_FOOT      -           Ground-level Square Footage of the building

Derived from the Tax Records, the ground floor square footage for single-family residential structures was readily available.  For non-single-family structures, the ground floor square footage was estimated simply by dividing the total square footage of the entire structure by the number of stories in the structure. 

* GUID

* IMPUTED         -           Imputed Record Indicator

This field identifies if any of the building’s attributes have been imputed by a “T” or “F” code.  Several buildings in the Tax records lacked complete information – missing information included combinations of square footage, number of dwelling units, stories, year built, etc.  In addition, we acquired information on several churches, fire- and police stations and schools from a variety of other sources that lacked similar information.  In the interests of completing the database and not discarding otherwise useful information, we chose to impute the missing information.  Imputations were based on similarity between the record with incomplete information with other similar building records, with similarities based on decade of construction, mode measures in exterior walls and structure types, building sizes, etc.  For instance, if a multi-family residential building did not have information on the number of dwelling units, we imputed the number of dwelling units by computing the square footage per dwelling unit for structures similar in area and built in the same decade.  A similar approach was used if the number of dwelling units was available, but not the square footage.  If neither dwelling unit nor square footage was available, we inspected the parcel through aerial photographs and approximated the square footage through crude digitizing measurements. 

We also acquired information on churches and schools from GDT, Inc. and physically moved them to the correct parcel (churches were often identifiable through shadows of steeples and domes, while school buildings had distinctive footprints and often had baseball or athletic tracks in the vicinity).  We digitized a subsample of each and computed average area measures for two size categories, small and large churches, and elementary and high schools.  We followed a similar approach for police- and fire-stations, except that we crudely calculated the area of each of the buildings and recorded them.  For year of construction, we analyzed the improvements in the vicinity, particularly if the imputed buildings were part of a multiple use parcel.  For structure type, we used the most probable structure type for that occupancy in that decade. 

|Occupancy Type|Occupancy Description|
| ------------- | ------------------- |
|COM3|	Repair Services|
|COM4|	Commercial Offices|
|COM5|	Banks|
|COM8|	Restaurants|
|EDU1|	Schools|
|EDU2|	Colleges|
|GOV2|	Emergency Response|
|REL1|	Religious|
|RES1|	Single-family|
|RES2|	Mobile Homes|
|RES3|	Apartments|
|RES4|	Hotel/Motel|
The imputations are of primary concern because they provide input to other calculated fields.  In addition, most of the imputations occurred in buildings that have a higher concentration of capital invested per unit.  In terms of the replacement costs, imputed records make up almost 14% of the total replacement value for all structures (about $87 billion). 

|Decade|Imputed SqFtperDU|Not Imputed SqFtperDU|Total SqFtperDU|
| ------ | ---------------- | ------------------ | -------------|
|Pre-1939|	911|	972|	968|
|40-49|	725|	790|	778|
|50-59|	684|	691|	690|
|60-69|	797|	814|	808|
|70-79|	946|	943|	944|
|80-89|	897|	875|	886|
|90-99|	751|	773|	759|
|Post-2000|	899|  	953|	922|
|Totals|	864|	871|	868|
Of the total replacement cost for all buildings in the database, apartments account for nearly 7%, while the remaining is divided between schools (1.94%), colleges and universities (3.14%) and relatively smaller proportions for churches and emergency response.  Of the 16 colleges and universities buildings, 4 are extremely large (part of University buildings), while the others are vocational or training colleges.  For the Universities, since we did not have any detailed information, we imputed the entire University as one building of about 1.2 million square feet.  In all the multi-family imputations, our average square footage per dwelling unit imputation ratios corresponded almost exactly with averages for similar units in that decade, as seen in Table 16 above.  Details of the imputations are provided in the accompanying workbook. 

* LHSM_ELEV

* LAT                  -           Latitude of structure location

Each building is spatially located at the centroid of the parcel polygon that contains it.  This field contains the latitude of the parcel centroid in the Geographic Coordinate System using the North American Datum of 1983.  This process of spatial location, while not absolutely accurate and precise, ensures that the building point feature is necessarily located within each parcel polygon.  In the case of parcels with more than one building, all building point features within that parcels will share a coincident location at the centroid of that parcel. 

* LON                 -           Longitude of structure location:

Each building was spatially located at the centroid of the parcel polygon that contained it.  This field contains the longitude of the parcel centroid in the Geographic Coordinate System using the North American Datum of 1983.  This process of spatial location, while not absolutely accurate and precise, ensures that the building point feature is necessarily located within each parcel polygon.  In the case of parcels with more than one building, all building point features within that parcels will share a coincident location at the centroid of that parcel. 

* MAJOR_OCC   -           Year that the structure was constructed

Derived from the Tax Records, this field categorizes the major occupancy category for the parcel in which the building is sited.  This value may not correspond to the value in the “OCC_DETAIL” field owing to inaccuracies in the Tax Records, or because the value may reflect the primary use of a parcel that sites several occupancies.  For instance, a particular parcel may have three buildings used as a Church, a Day-care facility and an Elementary School respectively.  In this case, the “MAJOR_OCC” value would be specified as “Religious” and would not correspond with the specific use of two of the three buildings sited in it. 

* NO_STORIES         -           Total number of stories for the building

Derived from the Tax Records, this field specifies the total number of stories for the building.  In the Tax Record tables, one particular table listed the improvement by building section – the building section could potentially include two different parts of the building, one wing from floors 2 to 4 and another wing just for floor 2.  Top stories were listed with alphanumeric “Penthouse Codes” and below-ground stories as “Basement Codes”.  We included only top and basement stories as legitimate floors if they had areas greater than 2500 sq. ft. in order to avoid small service floors (typically for elevators, etc.).  Below-ground floors were distinguished from above-ground floors and this field reflects the sum of the above- and below-ground floors. 

* NSTRA_CST     -          Acceleration-sensitive Non-structural Component of Replacement Cost in dollars

Based on the estimated replacement value of the building, this field represents the cost of the non-structural acceleration-sensitive component in dollars. 

* NSTRD_CST     -          Displacement-sensitive Non-structural Component of Replacement Cost in dollars

Based on the estimated replacement value of the building, this field represents the cost of the non-structural drift-sensitive component in dollars. 

* OCC_DETAIL   -           Detailed and Specific Occupancy (use) of the building

Derived directly from the Tax Records, this field contains the detailed and specific use of the building for each building record.  Single-family residential units have been divided into four categories listed in the table below, based on a combination of their square footage and physical condition, desirability and utility information collected in the Tax Records. 

| Detailed Occupancy | Description |
| -------------------------------------- | ------ |
|RES ON COMMLAND|	Single-family, Average|
|SINGLE-FAMILY RESIDENTIAL 1|	Single-family, Economy|
|SINGLE-FAMILY RESIDENTIAL 2|	Single-family, Average|
|SINGLE-FAMILY RESIDENTIAL 3|	Single-family, Custom|
|SINGLE-FAMILY RESIDENTIAL 4|	Single-family, Luxury|

* OCC_TYPE      -           Broad HAZUS Occupancy Category

This field translates the Tax Records information on the specific use of the building into the corresponding HAZUS MR-3 categories.  It is broad in the sense that all multi-family residential uses have been listed as “RES3”, rather than broken up in greater detail.  See additional documentation in the accompanying workbook. 

* OCC_TYPE2    -           Detailed HAZUS MR-3 Occupancy Category for the building

This field translates the Tax Records information on the specific use of the building into the corresponding HAZUS MR-3 categories.  Multi-family residential units are divided into more detailed groups as RES3A through RES3F, based on the number of units in the building. 

* PAR_ID            -           Parcel Identifier

Parcel Identifier – the building(s) is(are) located in this parcel.  Since one parcel can contain many buildings, parcel identifier values may be duplicated

* PARID_CARD  -           Improvement Identifier

Identifier for each improvement in the parcel – however, improvements do not correspond to buildings on a one-to-one basis, and values in this field may be duplicated.  Identical buildings are represented as a single improvement, and therefore, a single improvement record could potentially represent several buildings. 

* REPL_CST       -           Replacement Costs for the building in dollars

|Specific Building Use Desc|Code|Structure Type Desc|Code|Stories Desc|Code|Exterior Wall Desc|Code|Full Code|
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|Apartment|	001|	Wood|	AAAWF|	1-3	|0103|	Brick on Concrete Block|	04|	001AAAWF010304|
|Apartment|	001|	Steel|	AAASF|	4-7|	0407|	Brick Veneer|	01|	001AAASF040701|
|Apartment|	001|	Concrete|	AARCC|	8-24|	0824|	Concrete Block|	03|	001AARCC082403|
|Factory|	021|	Concrete|	AARCC|	1|	0001|	Brick on Concrete Block|	04|	021AARCC000104|
|Factory|	021|	Steel|	AAASF|	3|	0003|	Titlup Concrete Panel|	14|	021AAASF000314|
|Garage, Parking|	101|	Precast	AAAPC|	all|	0000|	Precast Concrete|	10|	101AAAPC000010|
|Garage, Repair|	035|	Metal|	AAALM|	all|	0000|	Galvanized Steel Siding|	07|	035AAALM000007|
|Hospital|	061|	Concrete|	AARCC|	2-3|	0203|	Brick on Concrete Block|	04|	061AARCC020304|
|Hospital|	061|	Steel|	AAASF|	4-8	0408|	Decorative Concrete Block|	03|	061AAASF040803|
|Hotel|	008|	Wood|	AAAWF|	4-7|	0407|	Brick Veneer|	01|	008AAAWF040701|
|Hotel|	008|	Steel	AAASF|	8-24|	0824|	Glass and Metal Curtain Wall|	11|	008AAASF082411|
|SF, Economy|	002|	URM	URMRM|	1|	0001|	Wood Siding|	25|	002URMRM000125|
|SF, Average|	003|	Wood|	AAAWF|	1|	0001|	Wood Siding|	26|	003AAAWF000126|
|SF, Custom|	003|	Wood|	AAAWF|	2|	0002|	Brick Veneer|	01|	003AAAWF000201|

Based on construction industry-standard estimation standards listed in Means Square Foot Costs for 2008, we estimated the building replacement costs. 

Information in the Means Square Foot Costs was available as $ per sq. ft national averages for a variety of building occupancy types and story ranges, further subdivided by combinations of structural system and external wall types.  The Tax Records had information on the detailed and specific use, the height and external wall, while the artificial neural network estimated the structural system of the building.  We standardized the specific occupancy types (for instance, “Discount Departments” and “Department Stores” were integrated into one category), the number of stories and the external wall types (for instance, “Brick on Concrete Block”, “Brick on Block”, “Brick Veneer on Block”, “Brick with Block Back-up”, “Brick with Concrete Block Back-up”, “Face Brick on Concrete Block”, “Face Brick with Concrete Block Backup” exterior wall descriptions in the Tax Records were all standardized to “Brick on Concrete Block”).  We concatenated symbolic codes for use, frame, stories and external wall to create identifiers for each of the 726 unique combinations.  The table above shows the development of the replacement value key code. 

We then recorded the per square foot costs to the overall square footage specified in the Means 2008 Square Foot Costs for each of the unique combinations.  Where the combinatory code and Means information didn’t coincide, we used our judgment in choosing an appropriate substitute (for instance, a small one-story factory building constructed in 1924, with external walls of concrete block would be disallowed by the modern building code, and hence, the replacement value equation would substitute the combination with a one-story service garage with a galvanized steel siding external wall on a light metal frame).  The table below shows an example of the Means per square foot costs for a specific apartment building type using different combinations of external wall and structure type.  Per square foot costs are listed for national averages and adjusted for Memphis, TN in the table. 

|External Wall 8000|Structure 12000|Area 15000|Area 19000|Area 22500|Area 25000|Area 29000|Area 32000|Area 36000| | | Region|
| ----------------- | ------------ | ----- | ----- | ----- | ---- | ---- | ----- | ---- | ---- | ---- | ------ |
|Brick, Concrete Block|	Steel|	185.55|	165.95|	158.10|	148.30|	144.50|	142.20|	137.50|	136.10|	134.10|	National Average|
|Brick, Concrete Block|	Wood|	182.10|	161.50|	153.20|	142.35|	138.35|	135.90|	130.60|	129.10|	126.95|	National Average|
|Brick Veneer|	Steel|	169.65|	149.95|	142.05|	132.10|	128.25|	126.00|	121.20|	119.70|	117.75|	National Average|
|Stucco, Concrete Block|	Steel|	173.65|	154.95|	147.50|	138.80|	135.15|	133.05|	128.95|	127.55|	125.75|	National Average|
|Stucco, Concrete Block|Wood|	160.35|	141.80|	134.35|	125.75|	122.15|	120.00|	116.00|	114.60|	112.80|	National Average|
|Wood Siding|	Wood|	159.05|	140.70|	133.30|	124.85|	121.25|	119.15|	115.25|	113.85|	112.10|	National Average|
|Brick, Concrete Block|	Steel|	159.57|	142.72|	135.97|	127.54|	124.27|	122.29|	118.25|	117.05|	115.33|	Adjusted for Memphis, TN|
|Brick, Concrete Block|Wood|	156.61|	138.89|	131.75|	122.42|	118.98|	116.87|	112.32|	111.03|	109.18|	Adjusted for Memphis, TN|
|Brick Veneer|	Steel|	145.90|	128.96|	122.16|	113.61|	110.30|	108.36|	104.23|	102.94|	101.27|	Adjusted for Memphis, TN|
|Stucco, Concrete Block|	Steel|	149.34|	133.26|	126.85|	119.37|	116.23|	114.42|	110.90|	109.69|	108.15|	Adjusted for Memphis, TN|
|Stucco, Concrete Block|Wood|	137.90|	121.95|	115.54|	108.15|	105.05|	103.20|	99.76|	98.56|	97.01|	Adjusted for Memphis, TN|
|Wood Siding|	Wood|	136.78|	121.00|	114.64|	107.37|	104.28|	102.47|	99.12|	97.91|	96.41|	Adjusted for Memphis, TN|
We analyzed this information through standard curve fitting techniques for linear, exponential, logarithmic and inverse models, and determined the best model for the combination based on the R-square criterion.  The parameters of the best model for that combination were then coded as model type, constant and slope.  Additionally, the ceiling and floor total square footage and per square footage costs from the Means data were also coded for each combination – this allowed the capping of per square foot rates to suit all Tax Record square footages that were outside the range of square footage for that specific use.  Finally, the parameterized values were related to each specific building record in the building database and the replacement value for the structure calculated, based on the recorded square footage of the building. 

|Model Description|	Model Code|	Structural Costs|	Non-Structural Costs|	Non-Structural Costs|
|-----------------------|-------------------------|-----------------------|----------| ---- |
|Foundations and Roofing|	Acceleration sensitive|	Displacement sensitive| |  |
|Apartment, 8-24 stories|	001_0824|	23.10%|	36.80%|	40.10%|
|SF, Average, 2 story|	003_0002|	23.40%|	26.60%|	50.00%|
|Hotel, 8-24 stories|	008_0824|	22.70%|	45.70%|	31.60%|
|Hotel, Motel, 1 story|	009_0001|	24.10%|	33.10%|	42.80%|
|Store, Department, 2-3 stories|	013_0003|	28.50%|	30.90%|	40.60%|
|Warehouse|	023_0000|	48.20%|	26.70%|	25.10%|
|Garage, Repair|	035_0000|	28.70%|	37.60%|	33.70%|
|Bank|	041_0000|	33.50%|	27.80%|	38.70%|
|Office, 11-20 stories|	043_1120|	29.20%|	40.00%|	30.80%|
|Police Stations|	055_0000|	11.40%|	32.50%|	56.10%|
|Mobile Home|	099_0000|	24.40%|	37.80%|	37.80%|
|Garage, Parking|	101_0000|	61.70%|	20.50%|	17.80%|
The same construct was used to specify the breakdown of replacement value of the building into structural, non-structural acceleration-sensitive and non-structural drift-sensitive components.  The Means Square Foot Costs also provided percentage breakdowns of costs for the various components of the building.  These included the Foundation and Substructure, Superstructure, Exterior Enclosure, Roofing, Interiors, Conveyance Equipment, Water supply and Plumbing, HVAC, Fire Protection and Electrical Services and Special Construction.  Foundations, Superstructure, Roofing and Special Construction formed the Structural component, while Interiors, Conveyance Equipment, Water supply and Plumbing, HVAC, Fire Protection and Electrical systems were grouped under Non-structural Acceleration-sensitive components.  The remaining Exterior Enclosure and Interior systems formed the drift-sensitive component.  The table above shows the cost breakdown percentage for a sample of building types. 

* SQ_FOOT         -           Square Footage of the entire building

Derived primarily from the Tax Records, for single-family dwellings (and some Duplexes and Triplexes), the square footage was readily available.  For non-single-family structures, we computed the square footage by summing each building record’s square footage.  In cases where the square footage information was unavailable or obviously wrong (especially for multi-family buildings), we imputed the square footage for those building records.  See notes under field “IMPUTED” for additional information. 

* STRCID

* STRUCT_TYP      -           General Structure Type

Buildings are classified into one of the following 11 structure types, as seen in the table below.  

| Code | General Structure Type |
| ---- | -----------------------------------|
|C1|	Concrete Moment Resisting Frame|
|C2|	Concrete Frame with Concrete Shear Wall|
|MH|	Mobile Homes|
|PC1|	Concrete Tilt-up|
|PC2| Precast Concrete Frame|
|RM|	Reinforced Masonry|
|S1|	Steel Frame|
|S3|	Light Metal Frame|
|URM|	Unreinforced Masonry|
|W1|	Light Wood Frame|
|W2|	Commercial Wood Frame|
Non-single-family structure types were predicted using an artificial neural network model calibrated with field data derived from two surveys conducted in 2002 and 2003.  The model predicted structural classifications as Concrete, Concrete Tilt-ups, Steel, Light Metal, Reinforced and Unreinforced Masonry and Wood.  Concrete structures were then reclassified into C1 and C2 categories based on height, and Wood structures into W1 and W2 categories based on area.  Mobile home parks, though not a structural category were included as a separate structure type by simply extracting the appropriate records from the Tax Records.  Single-family residential structures were classified predominantly as Wood structures, or as randomly generated Unreinforced Masonry structures for about 2.35% of the single-family stock, decreasing in frequency by increasing decades. 

* STR_CST         -           Structural Component of Replacement Cost in dollars

Based on the estimated replacement value of the building, this field represents the cost of the structural component in dollars. 

* STR_PROB      -           Model-predicted probability of classification

The artificial neural network attempts to reproduce the binary output of the calibration dataset (for instance, in the case of a Light Metal Frame sample structure, the value for S3 is set to 1, while the value for all other structure type categories is set to 0) implemented through a logistic threshold over several iterations.  The classification output for the model therefore yields values close to 0 for low-probability classes and positive values as close as possible to unity for the high-probability cases.  Based on the independent variable inputs, where the model is able to distinguish one particular category unambiguously, that category may get a score of .9867, while the others get scores very close to 0.  In other situations, the model may not be able to distinguish one class definitively, based on a particular input combination.  Here, class “RM” may get a score of .323, class “S1” a score of .291, class “S3” a score of .302, with other classes being close to 0.  The record is assigned to that class with the highest score, in this case “RM” even though “S1” and “S3” have similar scores.  In any case, the logistic threshold conversion of the input data yields a value between o and 1, therefore allowing the interpretation of the score as a direct probability measure.  The values in STR_PROB therefore may be construed as the likelihood of the structure type classification.  Note that all the sample data used for calibration gets a score of 1. 

* STR_TYP2       -           Detailed Structure Type as per HAZUS MR-3 specifications

This field contains the structure type of the building qualified by height as low, medium or high, and corresponds with HAZUS MR-3 specifications for structure type. 

* TRACT_ID        -           Census Tract Identifier in which the building is located

The STFID field from the US Census, or the FIPS Code that identifies the census tract in which the building is sited.

* TYPES

* XCOORD         -           X-Coordinate of Parcel centroid in feet

This field contains the X-Coordinate of the parcel centroid in the Tennessee State Plane Coordinate System with a linear measure of “feet” and uses the North American Datum of 1983. 

* YCOORD         -           X-Coordinate of Parcel centroid in feet

This field contains the Y-Coordinate of the parcel centroid in the Tennessee State Plane Coordinate System with a linear measure of “feet” and uses the North American Datum of 1983.

* YEAR_BUILT       -           Year that the structure was constructed

Derived from the Tax Records, this field specifies the year of construction of the building.

age_group is derived based on year_built. Age group of the buildings:
<ol>
* pre-1974
* 1974–1987
* 1987–1995
* 1995– 2008 (default)
</ol>
