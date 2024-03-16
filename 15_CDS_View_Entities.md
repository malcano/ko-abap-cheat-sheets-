# CDS View Entities

- [CDS View Entities](#cds-view-entities)
  - [More Information](#more-information)
  - [Executable Example](#executable-example)

Core data services (CDS) are an infrastructure for defining and consuming semantically rich data models on the [standard database](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenstandard_db_glosry.htm) of an [AS ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenas_abap_glosry.htm).

> **💡 Note**<br>
> - For cheat sheet content on CDS views, check out [this blog](https://blogs.sap.com/2022/10/24/feature-matrix-data-modeling-with-abap-core-data-services/).
> - The executable example focuses on CDS view entities and covers a selection of features.
> - The sample CDS view entities are designed to demonstrate a selection of features with a limited number of artifacts. They are not intended to be role models for proper CDS view design. They focus on syntax options only. They are not intended to solve concrete programming tasks. You should always work out your own solution for each individual case.

## More Information

- Blogs:
  - [Feature Matrix: Data Modeling with ABAP Core Data Services](https://blogs.sap.com/2022/10/24/feature-matrix-data-modeling-with-abap-core-data-services/)
  - [ABAP CDS Cheat Sheet: Amounts and Quantities in ABAP CDS](https://blogs.sap.com/2022/07/07/abap-cds-cheat-sheet-amounts-and-quantities-in-abap-cds/)
  - [ABAP Data Models Guide](https://blogs.sap.com/2023/05/09/abap-data-models-guide/) (includes a link to the guide on the SAP Help Portal)
- ABAP Keyword Documentation: [ABAP - Core Data Services (ABAP CDS)](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abencds.htm)


## Executable Example

[zcl_demo_abap_cds_ve](./src/zcl_demo_abap_cds_ve.clas.abap)

> **💡 Note**<br>
> - The executable example covers the following topics:
>   - Operands, expressions, built-in functions, and input parameters in CDS view entities
>   - Selecting data from CDS view entities using ABAP SQL `SELECT` statements
>   - Joins  
>     - Note: A sample CDS view entity contains multiple joins. You can comment in/out code sections to see the effect. See the notes in the view. 
>     - Excursion: Joins in ABAP SQL
>   - Associations
>     - Defining views with associations
>     - Exposing associations
>     - Using exposed associations in ABAP statements
> - The example CDS view entities (`zdemo_abap_cds_ve...`) and the [class](./src/zcl_demo_abap_cds_ve.clas.abap) contains comments in the code for more information.
> - The steps to import and run the code are outlined [here](README.md#-getting-started-with-the-examples).
> - [Disclaimer](README.md#%EF%B8%8F-disclaimer)