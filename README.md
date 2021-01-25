# TDR-DATA
TDR Completeness and Quality data analysis 

Because of widespread issues with invalid and/or non-standard TDR entries and
inconsistencies between transaction and Advantage catalog data, the quality of information entered into
fields such as Mfr Name and Mfr Part number need to checked for basic validation such as NULL, spaces,
"N/A", etc for products.

There also needs to be a way to "standardize" the TDR data.  The TDR data entries can be joined with the XSB 
processed advantage catalog to track a match rate which can be trended for improvements and analyized by vendor.


Restrictions on access and usage of TDR data cause workadround issueswith.  TDR data can only be stored on the Redshift servers behing the jump host on on a local computer harddrive
