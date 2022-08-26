---
sidebar_position: 2
---

# Uploading reports

**re_cloud** library has one command for uploading all the reports: `re_cloud upload`

You can upload 4 currently supported reports with this command. Here the list of how to do it: 😊

## commands

### dbt-docs

```
re_cloud upload dbt-docs --name TEXT --project-dir TEXT

Options:
  --project-dir TEXT  Which directory to look in for the dbt_project.yml file.
                      Default is the current working directory and its parents
  --name TEXT         Name of the upload used for identification
```

You don't need to pass project-dir paramter if calling this command from witin dbt main directory. Otherwise pass `project-dir` to upload generated docs from this directory.

### pandas-profiling

```
re_cloud upload pandas-profiling --name TEXT  --report-file TEXT

Options:
--report-file TEXT  Pandas profiling file with html report  [required]
--name TEXT         Name of the upload used for identification
```

For pandas profiling --report-file is required paramter. re_data will upload your docs in `uncommitted/data_docs/local_site/` path then.

### great-expectations

```
re_cloud upload great-expectations --name TEXT

Options:
  --name TEXT  Name of the upload used for identification
```

For great-expectation `cd` to great-expectations directory. re_data uploads 

### re-data

```
re_cloud upload re-data --name TEXT --project-dir TEXT --re-data-target-dir TEXT

Options:
  --project-dir TEXT         Which directory to look in for the
                             dbt_project.yml file. Default is the current
                             working directory and its parents

  --re-data-target-dir TEXT  Which directory to store artefacts generated by
                             re_data Defaults to the 'target-path' used in
                             dbt_project.yml

  --name TEXT                Name of the upload used for identification
```

If you are inside dbt project dir and didn't changed default `target` directory for docs and re_data both `project-dir` and `re-data-target-dir` are optional.

## common parameters

### `name`

Name which you would like to give to the report, this will show in the interface. Names don't need to and often will not be unique, given that in most of the pipelines you will be uploading similar reports every day / hours, etc.

## Help

Are you not familiar with some the mentioned tools and reports mentioned? We include sample reports from all of the tools on re_cloud [free account 😊](https://cloud.getre.io/#/register)**

If you need any help with setting up the upload, let us know on **[Slack](https://www.getre.io/slack)**, we will try to help right away 😊