
# dbt-Snowflake Session Analysis

## Project Overview
This project demonstrates how to set up a dbt (Data Build Tool) project using Snowflake for session analysis, including creating input and output models, snapshots, and adding tests.

## Setup Instructions

### Prerequisites
- Ensure you have `dbt` and the `dbt-snowflake` connector installed.

### Commands

1. **Install dbt Snowflake**:
   ```bash
   pip3 install dbt-snowflake
   ```

2. **Initialize dbt Project**:
   ```bash
   dbt init build_mau
   ```

3. **Create Models and Snapshots**:
   ```bash
   touch models/input/user_session_channel.sql
   touch models/input/session_timestamp.sql
   touch models/output/session_summary.sql
   mkdir snapshots
   touch snapshots/snapshot_session_summary.sql
   ```

4. **Run Models**:
   ```bash
   dbt run
   ```

5. **Create Schema File**:
   ```bash
   touch models/schema.yml
   ```
6. **Edit models/schema.yml to add tests for sessionId in session_summary:**:
   ```bash
   version: 2
   models:
     - name: session_summary
       columns:
         - name: sessionId
           tests:
         - not_null
         - unique
      - name: my_second_dbt_model
       columns:
         - name: id
           tests:
         - not_null
         - unique
        - name: session_summary
          columns:
         - name: sessionId
           tests:
          - not_null
          - unique

   ```


## Additional Notes
- Include additional information or troubleshooting tips here if necessary.
- To run the tests on the sessionId field in session_summary, use the following command:
 ```bash
   dbt test
   ```

