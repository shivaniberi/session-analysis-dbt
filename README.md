
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

## Additional Notes
- Include additional information or troubleshooting tips here if necessary.
