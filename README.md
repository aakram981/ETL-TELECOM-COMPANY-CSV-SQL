# ETL
📊 SSIS ETL Project - Telecom Transaction Processing Pipeline
🎯 Project Description
ETL (Extract, Transform, Load) pipeline developed with SQL Server Integration Services (SSIS) to process and load telecom transaction data into a data warehouse. This project implements complex transformations including data enrichment, validation, and cleansing.
📋 Data Flow Components
1. FF SRC read transaction - Data Source

Type: Flat File Source (CSV)
Function: Reading telecom transactions from a flat file
Input Columns:

id: Unique transaction identifier
subscriber_id: Subscriber identifier
imei: International Mobile Equipment Identity
imsi: International Mobile Subscriber Identity
cell: Network cell identifier
lac: Location Area Code
event_type: Event type
event_ts: Event timestamp
event_ts: Event timestamp



2. lk_subscribe ensi - Lookup Transformation

Type: Lookup Transformation
Function: Data enrichment by searching for detailed subscriber information
Logic:

Joins transaction data with subscriber reference table
Returns NULL for subscriber_id when no match is found
Allows handling of unknown subscribers in the next step



3. Derived Column - Transformations
Transformation 1: Handling NULL subscriber_id
