# Data_Engineering
Fundamental concepts of data engineering including ETL, relational database principles, creating databases, and Snowflake
#### Big Data
- Data so large have to consider how to scale it
- Traditional data methodologies to manipulate data do not aooly
- Identified by:
    - Volume
    - Variey of data types
    - Velocity of how fast data is produced and processed
    - Veracity measuring data accuracy and trustwortheryness
    - Value measuring how actionable data is
#### Data Pipeline
- Automate flow of data from one system to another using ETL or ELT
- Provides up-to-date accurate, relevant data
- Extracted from source -> data lake -> data warehouses -> data marts
#### Structured Data
- Makes data easier to organize, model, group, and store and query in relational database
- Semi-Structured data
    - NoSQL databases
    - JSON, XML, YAML
    - Easy to organize
    - More flexibility to model
- Unstructured data
    - extremely valuable most common type of data structure
    - does not follow a model
        - cant be contained in rows and columns
        - Usually text, sound, picture, and video files
    - Stored in data lakes
#### SQL Databases
- Standard tool to query Relational Database Management Systems (RDMB)
- Schema governs relationship between tables
#### Data Warehouses and DATA lakes
- LAKE
    - Stors all unprocessed data wich is
    - Big DataVery large (petabytes)
    - stores all data structures
    - cost-effective
    - Difficult to analyze
    - Requires up-to-date data catalog
        - tracks source of data
        - where data is used
        - who owns the data
        - How often updated
        - Provides data governance
        - Ensures reproducibility
- Warehouses
    - Specific data for specific use
    - Reletively small
    - Stores manyally structured data
    - More costly to update
    - Optimized for analytics
    - Used to query data
 
#### Database vs Warehouse
- DB
    - General term for data stored and accessed on computer
- Warehouse
    - Type of db
## Cloud Computing
- Cloud computing is the delivery of technology services over the internet with pay-as-you-go pricing
    - Rent services to compute, store, network, and software
- Characteristics
    - Virtualization
        - Splits physical server into mupltiple virtual servers running own independant OS
        - Maximizes output of individual servers
        - Creates Scalability
    - Scalability
        - Easily add or remove resources as you need them
        - Scale up or down during peak or slow time
            - Vertical Scaling
                - Increase power of instance (stacking servers for more power)
              - Horizontal scaling
                - Adding more instances (parallel computing)
    - Cost
        - Only pay for what you use
        - No capital expenses or management expenses
    - Speed
        - On-demanad resourcing
        - Fast set-up time
        - Deploy services in minutes
    - Performance
        - Access to fast efficinet computing resources
        - Data Centers house organizitions IT operations and equipment
        - Cloud provides worldwide nework of data centers
    - Gorwth
        - On-demand resourcing limits growth constraints
        - Provision resources across cloud network
    - Reliability
        - Guaranteed durability and availability of data and servers
        - Data is duplicated across data centers
    - Security
        - External party responsibility for security
        - Risky for highly regulated sectors like health care
### Cloud Service Models
- Infrastructure as a Service (IaaS)
    - Rent fundimental elements of cloud computing
        - Networking
        - Storage
        - Servers
        - Virtualization
- Platform as a Service (PaaS)
    - Includes tools and software needed to build apps
        - Operating System
        - Middleware
        - Tuntime
- Software as a Service (Saas)
    - Access service via web browser or app
        - Data
        - Applications
  ![Screenshot (168)](https://github.com/bhammy27/Data_Engineering/assets/154477061/749a7809-cf7b-4c12-840e-644533b528ef)

- Function as a Service (Faas)
    - Focuses on a single function of software
        - Identity authentication, payment transactions
      - Serverless billing model
          - Pay for service vs renting serers
### Cloud Deployment Models
- Defines control you need over your cloud environment
- Public
      - Shared and open use infrastructure for general public
      - Owned and managed by cloud service provider
      - Internet asscessable
      - PRO: quick startup with minimal investment
            - Can buy more capacity making easy to scale
      - CON: No access to data centers and hardware
      
- Private
      - Exclusive use by tenants
      - Accessed by a network link and password
      - PRO: Provides direct control over resureces and data
      - CON: Requires most up front investment to set up vs other models
      - Unlike on-premise, uses virtilization for on-demand computing  and can be off-premises
- Hybrid
      - Organization uses combo of two or more models
      - Store sensetative data on private cloud and apps on public to process it 
       - ****Cloud Bursting**** when private cloud hits capacity temporariy moves overflow to public cloud to avoid disruption of services (seasonal spikes)
- Multicloud
    - combines different cloud provider services
    - Felxibility on procing plans and servic offerings
    - No reliance on one vendor
- Community
    - Infrastructure shared by specific community for exclusive use
    - Share common interest such as security, jurisdiction, mission
### Cloud Regulations
- General Data Protection Regulations (GDPR)
    - Regulates how personal data is collected, processed, and stored from users in EU
          - Users must explicity consent to data collection
          - Must notify users of data breaches
          - Personal info must be encryped, anonymized, and/or pseudomyzed
          - ****Personal data can't leave EU borders unless same level of protection is guaranteed****
      - Fine is 20 mill Euros or up to 4% of worldwide annual revenue
- What is personal data or Personally Identifiable Information (PII)
    - Any info that relates to an idntified or identifiable living individual
    - Pieces of info that can be combined to lead to an identification
        - Home address     - First name        - last name   
        - locaton          - IP address        - race / ethinic origin
        - political id     - sex orientation   -health related data
### AWS
- Storage = S3 AWS Simple Storage Services
- Computing = EC2 AWS Elastic Compute Cloud
- Database = RDS AWS Relational Database Service
- Data warehousing = Redshift
- Analytics service = Kinsesis
- Machine Learning = SageMaker
### Microsoft Azure
- Storage = Azure Blob Storage
- Computing = Azure Virtual Machines
- Database = Aure SQL Database
- Microsoft Fabric brings everyting toghether
- Data Lake = Data Lake Storage
- Analytics Service = Stram Analytics
- Machine Learning = Machine Learning
### Google Cloud
- Storage = Google Cloud Storage
- Computing = GC Compute Engine
- Database = GC SQL
- Data warehousing = Big Query
- Analytics Service = Dataflow
- Machine Learning = AutoML
## Creating Relataional Databases using SQL
- information_schema provides metadata on database
  - Find table names:
      SELECT table_schema, table_name
      FROM information_schema.tables;
  - Find column names:
      SELECT table_name, column_name, data_type
      FROM information_schema.columns
      WHERE table_name = 'pg_config';
### Tables
****Creating Tables****
  CREATE TABLE table_name (
      column_a data_type,
      column_b data_type,
      column_c data_type
      );
 ****Alter Tables****
 - Add columns to table
   ****ALTER TABLE**** table_name
   ****ADD COLUMN**** column_name data_type;
- Adding values into new columns
    ****INSERT **** table_name (column_a, column_b)
    ****VALUES**** ("value_a", "value_b");
      use existing values from columns use:
      SELECT colum name
      FROM table 
- Renaming columns
    ALTER TABLE table_name
    ****RENAME COLUMN**** old_name TO new_name;
- Removing columns from tables when columns are empty
    ALTER TABLE table_name
    ****DROP COLUMN**** column_name;
### Adding Constraints
#### Attribute constraints
    - #### data type constraints
    - defined when creating or altering columns
        ALTER TABLE students
        ALTER COLUMN average_grade
        ****TYPE**** integer  changes average grade to int from float
        ****USING**** ROUND(average_grade)  specifies value rounding reduces decimals
              - can select substrings of text
                  ****SUBSTRING**** (column_name FROM start_point FOR num_charagters)
    - change data type in query using CAST
        SELECT temperature + ****CAST****(wind_speed ****AS**** integer)
    - #### NULL, NOT NULL, UNIQUE constrains
        - add NOT NULL after data_type when creating column
            column_a integer ****NOT NULL****,
        - add NOT NULL to existing column
            ALTER TABLE table_name
            ALTER COLUMN column_name
            ****SET NOT NULL****;
        - Adding UNIQUE to existing table
            ALTER TABLE table_name
            ****ADD CONSTRAINT**** some_name ****UNIQUE****(column_name)
#### Key Constraints
- Super keys are keys made up of a combination of fields to create unique records
    - Candidate keys are minimal keys which refer to 1 field 
    - ****Primary Keys****
      - Selected from candidate keys
      - Uniquely identifies records
      - Unique and not-null constraints apply
      - Assign to new tables
            CREATE TABLE table_name (
            column_name data_type PRIMARY KEY,
        - Assign to existing tables
             ALTER TABLE table_name
             ADD CONSTRAINT some_name PRIMARY KEY (column_name)
        - ****id serial** creates a list of numbers great for creating id
    - ****Foreign keys****
        - Connects to Primary Key of another table to connect them
              - Domain of FK must equal domain of PK
        - Are not actual keys since duplicate and null values may exist
        - Created by referencing Primary key in another table
             CREATE TABLE table_name (
             column data_type PRIMARY KEY,
             column_b FOREIGN KEY 

              ALTER TABLE a
              ADD CONSTRAINT a_fkey FOREIGN KEY (b_id) References table(id)
                  - here foreing key 
  #### Referential Integrity constraints
- A record referencing another table must refer to an existing record in that table
- Enforced through foreign keys which helps to prevent errors
  - If record in table is deleated or record in table a does not exist then an error
        CREATE TABLE a (
        id integer PRIMARY KEY,
        column_a varchar(64),
        b_id integer REFERENCED table b(id) ****ON DELETE NO ACTION****
      - ON DELETE ****CASCASE****
            - Deletes record in table b then deletes all references in table a
        - ON DELETE ****SET NULL**** sets referencing column to Null
        - ON DELETE ****SET DEFULT**** changes referene column to set defult value
## Database Design
- Must consider
  - Schemas: how should data be logically organized?
  - Normalization: Should data have minimal dependency and redundancy?
  - Views: What joins will be done most?
  - Access Control: Should all users ahve same access level?
  - DBMS: how to choose between SQL and noSQL options?
#### OLTP vs OLAP
 - Online Transcation Processing (focus on day to day tasks)
    - Application orientated
    - Up-to-date operational data
    - Size is snapshot (gigabytes)
    - Queries simple transaction & frequent updates
    - More people use
 - Oline Analytical Processing (focus on business decision making)
   - Subject orienteated
   - Consoidated or historical data
   - Size is archives (terabytes)
   - Queries complex, aggregate queries with limited updates
   - Used by more select group of people
- OLTP stored in operational db wich is pulled and cleaned to create OLAP warehouse
#### Storing Data
  
