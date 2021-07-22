# Bridge Inventory

Current ongoing information is in https://opensource.ncsa.illinois.edu/confluence/display/INCORE1/Bridge+Inventory+Datatype+Schema

## Columns
* id: Unique Bridge Id
* class: Structure Class/li>
* spans: Number of Spans/li>
* str_lng: Structure Length
* dckwidth: Deck Width
* name: Name of the Bridge
* span_mass (SpanMass): Span unit mass (ton/m) coming from bridge inventory
* clearence  (Clearance): Height clearance of bridge deck (m) coming from bridge inventory
* g_elev (G_Elev): Bridge ground elevation (m) coming from bridge inventory
* fc: Concrete Strength (MPa)
* fy: Steel Strength (MPa)
* EBL: The natural logarithm of coefficient of friction of expansion bearings in longitudinal direction
* EBT: The natural logarithm of coefficient of friction of expansion bearings in transverse direction
* FBL: The natural logarithm of coefficient of friction of fixed bearings in longitudinal direction
* FBT: The natural logarithm of coefficient of friction of fixed bearings in transverse direction
* pass_stf: Abutment passive stiffness (N/mm/mm)
* act_stf: Abutment active stiffness (N/pile)
* rot_stf: Abutment rotational stiffness (N/mm/pile)
* trns_stf: Abutment transverse stiffness (N/pile)
* damp: damping ratio
* abt_gp_L1: Left abutment gap (mm)
* abt_gp_L2: Right abutment gap (mm)
* hng_gp_L1: Left hinge gap (mm)
* hng_gp_L2: Right hinge gap (mm)
* span_lng: Span length (mm)
* col_thck: Thickness of column in longitudinal direction (mm)
