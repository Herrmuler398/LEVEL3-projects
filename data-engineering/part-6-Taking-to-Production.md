# Part 6: Taking to Production (Optional)

1. Refactor (if necessary) the code, so that, same code base is executable in multiple environments. This could include adding parameters, usage of configuration files etc to remove hard coding of environment specific metadata.

1. Develop CICD pipelines to deploy components to another Databricks environment (or production).

1. The CICD pipelines should be able to deploy all components like tables (structure without data), notebooks, python scripts, workflows, delta live tables etc, which are required for replicating the development environment in another workspace and catalogue/schema.

1. The pipelines should be designed in a way, such that, deploying components to a third environment (in addition to dev and prod) is also achievable with minimum effort.

### Guardrails

1. Use Azure DevOps for implementing CICD pipelines.
1. If possible avoid usage of Personal Access Tokens (PAT).
1. Credentials used by the CICD pipelines should be stored securely, and should not be hard coded as plain text anywhere.
1. Try to create re-usable [Azure DevOps pipeline templates](https://learn.microsoft.com/en-us/azure/devops/pipelines/process/templates?view=azure-devops&pivots=templates-includes) during the process.


## Outline
- [CICD for data pipeline components](#cicd-for-data-pipeline-components)
- [Code refactoring for deployment](#code-refactoring-for-deployment)
- [Lakehouse Change management](#lakehouse-change-management)


## CICD for data pipeline components

Develop CICD pipelines (yaml based) in Azure DevOps which enables automatic deployment of all code components to production.

**What are data pipeline components?**

Data pipeline components here means all code components that are required to run the data pipelines like

1. Notebooks
1. Python scripts
1. Workflow definitions
1. Delta live table pipeline definitions
1. Any other supporting files

It doesn't include infrastructure components like Workspaces, sql warehouses, clusters etc.

📝 The list here need not contain all components that you use. So if you use any additional components, you can discuss this with the SKillMe team to decide if it needs to be deployed by you, or would be taken care by the platform team as part of infrastructure deployment.


**Deliverables**

1. Azure DevOps CICD pipelines (using YAML files) for CICD implemented and tested.
1. All credentials stored securely and not to be available in plain text anywhere.


💡 [Asset Bundles](https://docs.databricks.com/en/dev-tools/bundles/index.html) is a feature in public preview which could help in this regard. Feel free to use it if you think it makes sense.

## Code refactoring for deployment

1. Maintain same code base for dev and production. This means, there shouldn't be a separate copy of the code to be deployed to prod, rather the same code which runs in dev, should be able to be run in production also.
1. Make it possible, there shouldn't be any environment specific hard codings (like catalogue/schema names, cluster names, workspace names etc).
1. The environment specific metadata should be managed outside the code. This could be done using parameters or entries in an configuration file etc.

**Deliverables**

1. No environment specific hard codings.
1. Code base deployable to production without any change.

## Lakehouse Change management

1. Identify right tool to do change management for Lakehouse tables and views.
1. Implement change management using the tool identified.
1. Develop CICD pipeline[s] which can use the tool of choice to automatically deploy Tables and Views to another catalogue/schema in Unity Catalogue.
1. The pipeline should also be capable of deploying incremental changes to the Tables and Views (for example addition of a constraint, or addition of newer tables). In the best case, only the tables modified after last deployment should be affected during current deployment.
1. Deployment should not affect existing data in Tables.

**What does change management of Tables and Views mean?**

Change management in the context of this EPIC means, to be able to make changes to the database componentes (like tables and views), be able to version these changes and also be able to automatically replicate these changes to another environment.


**Deliverables**

1. Azure DevOps CICD pipelines (using YAML files) for change management implemented and tested.
1. All credentials stored securely and not to be available in plain text anywhere.

💡[Here](https://medium.com/dbsql-sme-engineering/database-change-management-on-lakehouse-with-databricks-sql-and-liquibase-c3c238781616) you have a possible solution to achieve the goal. As always, you don't need to follow this and can find any solution which solves the problem.
