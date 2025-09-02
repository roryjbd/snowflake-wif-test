# snowflake-wif-test

Create the user in Snowflake as follows:

```sql

CREATE USER IF NOT EXISTS GHA_WIF_USER
  TYPE = SERVICE
  WORKLOAD_IDENTITY = (
    TYPE = OIDC,
    ISSUER = 'https://token.actions.githubusercontent.com',
    SUBJECT = 'repo:roryjbd/snowflake-wif-test:ref:refs/heads/main',
    OIDC_AUDIENCE_LIST = ('snowflakecomputing.com')
  );


```