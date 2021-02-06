# TDR-DATA
TDR Completeness and Quality data analysis 

Because of widespread issues with invalid and/or non-standard TDR entries and
inconsistencies between transaction and Advantage catalog data, the quality of information entered into
fields such as Mfr Name and Mfr Part number need to checked for basic validation such as NULL, spaces,
"N/A", etc for products.

There also needs to be a way to "standardize" the TDR data.  The TDR data entries can be joined with the XSB 
processed advantage catalog to track a match rate which can be trended for improvements and analyized by vendor.


Restrictions on access and usage of TDR data cause work adround issues with it.  TDR data can only be stored on the Redshift servers on the jump host or on a local computer hard drive.  Joining the large XSB enhanced Advantage table to TDR data is diffculte due to it's size and location on the jump host.


METHODOLOGY:

(Will change once I have access to s3)

Step 0) Connect to jump host

Step 1)  Using Tableau, connecect to Server: rs-data.prod-lde.bsp.gsa.gov Database: tdr

Step 2) Select view: clean_tranactional_sales

Step 3) Create an extract (.hyper) file

Step 4) Copy saved extract to laptop hard drive

Step 6) Run SQL code to get list of all contracts that have transactions in TDR:

        SELECT distinct "contract_id"
        FROM "tdr"."clean_transactional_sales";
        
Step 7) In order to reduce the size of the advantage catalog file from XSB, run "Create Reduced ADVANTAGE with just TDR contracts MMDDYYYY.sql" to make a smaller table to join with the TDR data.

Step 8) Open TDR_data_analysis MMDDYYYY.twb and replace data sources with new TDR extract file from step 4 and new New reduced ADV catalog from step 7.








