# Liquibase Update To Tag Sql Action

⚠️ **VERSION SUPPORT NOTICE**: This action supports Liquibase versions up to 4.x. For Liquibase 5.0+ features, please migrate to [`liquibase/setup-liquibase`](https://github.com/liquibase/setup-liquibase).

## Migration Guide

### Current Approach (Supports Liquibase 4.x)
```yaml
- uses: liquibase-github-actions/update-to-tag-sql@v4.33.0
  with:
    # your parameters here
```

### Recommended for Liquibase 5.0+ Features
```yaml
- uses: liquibase/setup-liquibase@v1
  with:
    version: '5.0.0'  # Supports latest features
    edition: 'oss'
- run: liquibase update-to-tag-sql # add your parameters as CLI flags
```

---

Official GitHub Action to run Liquibase Update To Tag Sql in your GitHub Action Workflow. For more information on how update to tag sql works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Update To Tag Sql
Generate the SQL to deploy changes up to the tag
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/update-to-tag-sql@v4.33.0
  with:
    # The root changelog
    # string
    # Required
    changelogFile: ""

    # The tag to generate SQL up to
    # string
    # Required
    tag: ""

    # The JDBC database connection URL
    # string
    # Required
    url: ""

    # Fully-qualified class which specifies a ChangeExecListener
    # string
    # Optional
    changeExecListenerClass: ""

    # Path to a properties file for the ChangeExecListenerClass
    # string
    # Optional
    changeExecListenerPropertiesFile: ""

    # Changeset contexts to match
    # string
    # Optional
    contextFilter: ""

    # The default catalog name to use for the database connection
    # string
    # Optional
    defaultCatalogName: ""

    # The default schema name to use for the database connection
    # string
    # Optional
    defaultSchemaName: ""

    # The JDBC driver class
    # string
    # Optional
    driver: ""

    # The JDBC driver properties file
    # string
    # Optional
    driverPropertiesFile: ""

    # Changeset labels to match
    # string
    # Optional
    labelFilter: ""

    # Control whether names of objects in the default catalog are fully qualified or not. If true they are. If false, only objects outside the default catalog are fully qualified
    # bool
    # Optional
    outputDefaultCatalog: ""

    # Control whether names of objects in the default schema are fully qualified or not. If true they are. If false, only objects outside the default schema are fully qualified
    # bool
    # Optional
    outputDefaultSchema: ""

    # Password to use to connect to the database
    # string
    # Optional
    password: ""

    # Username to use to connect to the database
    # string
    # Optional
    username: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase update to tag sql action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/update-to-tag-sql@v4.33.0
    with:
      changelogFile: ""
      tag: ""
      url: ""
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
