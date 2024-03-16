<br />
<div align="center">
  <a href="https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm">
    <img src="./files/ABAP_Keyword_Documentation.png" alt="ABAP Keyword Documentation" >
  </a>

  <h3 align="center" style="font-size: 40px; color: #FCB913;">ABAP Cheat Sheets</h3>
<h5 align="center" style="font-size: 20px; color: #CCBFFF;">ABAP Cheat Sheets 한국어 버전(비공식)</h5>
  <p align="center">
    실행해볼 수 있는 예제와 함께 ABAP 문법을 간략하게 살펴봅시다.
    <br />
    <!--<a href=""><strong>Expore ABAP syntax in a nutshell & executable examples</strong></a>
    <br />-->
    <br />
    <a href="#%EF%B8%8F-how-to-use">How to Use</a>
    ·
    <a href="#-abap-cheat-sheets-overview">Cheat Sheets</a>
    ·
    <a href="#-getting-started-with-the-examples">Examples</a>
  </p>
</div>
<br>
<hr>
<br>

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/abap-cheat-sheets)](https://api.reuse.software/info/github.com/SAP-samples/abap-cheat-sheets)

ABAP cheat sheets[^1] ...
<h5 style="color: #FFAAAA">(注) 원 레포지토리 READ_ME에서는 SAP에서 contribution 용도가 아니라고 밝히고 있습니다. 본 문서 한국어 번역은 비공식 번역임을 알려
드립니다.
</h5>

- **주제를 선택**하여 여러분이 참고할 수 있는 **ABAP** 레퍼런스를 확인할 수 있습니다.
- focus on **ABAP syntax**.
- 본 문서는 **ABAP구문**을 중점으로 다룹니다.
- **코드 스니펫을 포함하고 있습니다.**
-  [SAP BTP ABAP 환경](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abensap_btp_abap_env_glosry.htm) (*main* branch; ABAP language version: [ABAP for Cloud Development](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_for_cloud_dev_glosry.htm))과 온프레미스 ABAP 시스템 ([classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm); the repository branches other than *main*)에서 [abapGit](https://abapgit.org/)을 사용하여 간단한 실행 가능한 데모 예제를 작동시키고, 확인해볼 수 있습니다. 
- 각 챕터의 링크를 통해 용어집과 **ABAP 키워드 문서** (*F1 도움말*)를 통해 더 자세한 내용을 확인할 수 있습니다.

<details>
<summary>💡 Note</summary>
<br>

- ABAP 치트 시트는 개괄적인 정보를 제공할 뿐, 구문과 콘셉트에 대한 포괄적인 내용임을 보장하지는 않습니다. 더 많은 정보는 코드 내 키워드의 *F1* 또는 온라인 및 system-internal 버전에서 직접 검색하는 등의 방법으로 ABAP 키워드 문서를 참조해주시기 바랍니다.
- 본 치트 시트에서 별도로 명시되지 않는 한, 본 문서의 내용은 아래 ABAP 언어 버전을 기준으로 합니다.
(첫 항목 중심):
  - [ABAP for Cloud Development](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap_for_sap_cloud_glosry.htm): Restricted ABAP language scope for [ABAP Cloud](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_cloud_glosry.htm) → [Online version of the documentation](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm)
  - [Standard ABAP](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenstandard_abap_glosry.htm): Unrestricted ABAP language scope, for example, for [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm) → [Online version of the documentation (latest version)](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm)
- [알려진 이슈](#-known-issues)와 [면책조항](#%EF%B8%8F-disclaimer)을 확인해주세요.
- 본 치트시트는 ABAP 키워드 문서의 항목과 토픽에 대한 링크를 제공합니다. 
기존의 ABAP-only 치트 시트와 달리, ABAP for Cloud Development의 링크를 참조합니다.
- [여기](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenrestricted_abap_elements.htm)를 눌러 
ABAP 버전에 따른 ABAP 언어 요소의 차이를 확인할 수 있습니다. &nbsp;&nbsp; i. e. ABAP Cloud 허용 여부 등<br>
또한, [여기](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenreleased_apis.htm)를 눌러 릴리즈된 API를 확인할 수 있습니다.
- 모든 ABAP 치트 시트를 한 레포지토리에 보관할 목적으로, 클래식 ABAP에만 해당하는 ABAP 치트 시트 문서도 ABAP Cloud 예제를 위한 *main* 브랜치에 포함됩니다.
- 클래식 ABAP용 브랜치에 포함된 예제 class는 대부분 ABAP for Cloud Development에서도 사용할 수 있습니다. `TEST_ABAP_CHEAT_SHEETS_CLASSIC` 하위 패키지의 경우에만 
- The example classes contained in the branches for classic ABAP mostly use syntax that is also available in ABAP for Cloud Development. Only the  `TEST_ABAP_CHEAT_SHEETS_CLASSIC` subpackage contains syntax relevant to Standard ABAP and that is not available in ABAP for Cloud Development, such as dynpro-related ABAP keywords.
</details>

<br>

## 🏗️ How to Use

1. **ABAP syntax info**: Get info in a nutshell on ABAP syntax and concepts related to various ABAP topics in the [ABAP cheat sheets](#-abap-cheat-sheets-overview).
2. **Demo examples**: Import the ABAP development objects of this repository (Note: *main* branch for ABAP Cloud only) into your system using [abapGit](https://abapgit.org/) as described [here](#-getting-started-with-the-examples) and run the demo classes by choosing *F9* in the [ABAP development tools for Eclipse (ADT)](https://tools.eu1.hana.ondemand.com/) for checking out the ABAP syntax in action.

<br>

## 📝 ABAP Cheat Sheets Overview

| Cheat Sheet        | Topics Covered           |  Demo Example  |
| ------------- | ------------- | ----- |
|[ABAP for Cloud Development](19_ABAP_for_Cloud_Development.md)| Briefly outlines the terms ABAP Cloud and classic ABAP to set the context for ABAP for Cloud Development | [zcl_demo_abap_cloud_excursion](./src/zcl_demo_abap_cloud_excursion.clas.abap) (see the notes in the cheat sheet) |
|[Data Types and Data Objects](16_Data_Types_and_Objects.md)| Contains basic information about data types and data objects in ABAP  | [zcl_demo_abap_dtype_dobj](./src/zcl_demo_abap_dtype_dobj.clas.abap)   |
|[Internal Tables](01_Internal_Tables.md)| Creating, filling, reading from, sorting, modifying internal tables  | [zcl_demo_abap_internal_tables](./src/zcl_demo_abap_internal_tables.clas.abap)   |
|[Structures](02_Structures.md)| Some basics when working with structures  |  [zcl_demo_abap_structures](./src/zcl_demo_abap_structures.clas.abap)  |
|[ABAP SQL](03_ABAP_SQL.md)| Reading from database tables using `SELECT`, changing data in database tables using `INSERT`, `UPDATE`, `MODIFY` and `DELETE`    | [zcl_demo_abap_sql](./src/zcl_demo_abap_sql.clas.abap)   |
|[ABAP Object Orientation](04_ABAP_Object_Orientation.md)| Working with objects and components, concepts such as inheritance, interfaces, and more | [zcl_demo_abap_objects](./src/zcl_demo_abap_objects.clas.abap) |
|[Constructor Expressions](05_Constructor_Expressions.md)| Covers constructor expressions with operators such as `VALUE`, `CORRESPONDING`, `NEW`, `CONV`, `EXACT`, `REF`, `CAST`, `COND`, `SWITCH`, `FILTER`, `REDUCE`, iteration expressions with `FOR`, `LET` expressions  | [zcl_demo_abap_constructor_expr](./src/zcl_demo_abap_constructor_expr.clas.abap) |
|[Dynamic Programming](06_Dynamic_Programming.md)| Covers field symbols and data references as supporting elements for dynamic programming, dynamic ABAP syntax components, runtime type services (RTTS), i. e. runtime type identification (RTTI) and runtime type creation (RTTC) |  [zcl_demo_abap_dynamic_prog](./src/zcl_demo_abap_dynamic_prog.clas.abap)  |
|[String Processing](07_String_Processing.md)| Creating strings and assigning values, chaining strings, string templates, concatenating, splitting, modifying strings, searching and replacing, regular expressions  |  [zcl_demo_abap_string_proc](./src/zcl_demo_abap_string_proc.clas.abap)  |
|[ABAP for RAP: Entity Manipulation Language (ABAP EML)](08_EML_ABAP_for_RAP.md)| Setting EML in the context of RAP, standard (create, read, update, delete) and non-standard operations (actions) | <ul><li>[Demo RAP scenario with a managed RAP BO, external numbering (zcl_demo_abap_rap_ext_num_m)](./src/zcl_demo_abap_rap_ext_num_m.clas.abap)</li><br><li>[Demo RAP scenario with an unmanaged RAP BO, external numbering (zcl_demo_abap_rap_ext_num_u)](./src/zcl_demo_abap_rap_ext_num_u.clas.abap)</li><br><li>[Demo RAP scenario ("RAP calculator") with a managed, draft-enabled RAP BO,  late numbering (zcl_demo_abap_rap_draft_ln_m)](./src/zcl_demo_abap_rap_draft_ln_m.clas.abap) <br>Note that this example can also be checked out using the preview version of an SAP Fiori UI. Check the comments in the class for the steps.</li><br><li>[Demonstrating the local consumption of RAP business events in the context of a RAP demo scenario, managed RAP BO with managed internal numbering and additional save (zcl_demo_abap_rap_m_as)](./src/zcl_demo_abap_rap_m_as.clas.abap)</li></ul>  |
|[Excursion Down to Bits and Bytes](09_Bits_and_Bytes.md)|Covers the technical background of data types and data objects|-|
|[ABAP SQL: Working with Hierarchies](10_ABAP_SQL_Hierarchies.md)|Summarizes the functions ABAP SQL offers together with ABAP CDS for working with hierarchical data that is stored in database tables|-|
|[Internal Tables: Grouping](11_Internal_Tables_Grouping.md)|Covers the `GROUP BY` clause in statements for internal tables.|[zcl_demo_abap_sql_group_by](./src/zcl_demo_abap_sql_group_by.clas.abap)|
|[ABAP Managed Database Procedures (AMDP)](12_AMDP.md)|Covers ABAP Managed Database Procedures (AMDP): AMDP Procedures and AMDP Functions (including CDS Table Functions)|[zcl_demo_abap_amdp](./src/zcl_demo_abap_amdp.clas.abap)|
|[Program Flow Logic](13_Program_Flow_Logic.md)|Deals with control structures (`IF`, `CASE`), loops (`DO`, `WHILE`) and exception handling|[zcl_demo_abap_prog_flow_logic](./src/zcl_demo_abap_prog_flow_logic.clas.abap)|
|[ABAP Unit Tests](14_ABAP_Unit_Tests.md)|Contains basic information about unit testing in ABAP|[zcl_demo_abap_unit_test](./src/zcl_demo_abap_unit_test.clas.abap)|
|[CDS View Entities](15_CDS_View_Entities.md)|Note that cheat sheet content is available in [this blog](https://blogs.sap.com/2022/10/24/feature-matrix-data-modeling-with-abap-core-data-services/). The focus here is on the example CDS artifacts and the [executable example class](./src/zcl_demo_abap_cds_ve.clas.abap), which include comments.|[zcl_demo_abap_cds_ve](./src/zcl_demo_abap_cds_ve.clas.abap)|
|[SAP LUW](17_SAP_LUW.md)|Provides a high-level overview of the [SAP LUW](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abensap_luw_glosry.htm) concept that deals with data consistency with a focus on SAP LUW-related statements <br> 💡 Several statements covered in the cheat sheet and the executable example are only relevant to [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm).|Program `ZDEMO_ABAP_SAP_LUW`|
|[Dynpro](18_Dynpro.md)|Provides a high-level overview of dynpro topics with a focus on dynpro-related statements <br> 💡 The content of this cheat sheet and the executable example are only relevant to [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm).|Program `ZDEMO_ABAP_DYNPRO`|
|[Selection Screens and Classic Lists](20_Selection_Screens_Lists.md)|Provides a high-level overview of selection screens and classic lists with a focus on related statements. It includes an excursion into the SAP List Viewer (ALV). <br> 💡 The content of this cheat sheet and the executable examples are only relevant to [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm).|Program `ZDEMO_ABAP_SELSCR_LISTS_INTRO` (the "intro" program, from which the other related example programs can be started)|
|[Working with XML and JSON in ABAP](21_XML_JSON.md)|Covers processing XML using class libraries, XML transformations using XSLT and Simple Transformations (ST), serializations (ABAP to XML) and deserializations (XML to ABAP), dealing with JSON data|[zcl_demo_abap_xml_json](./src/zcl_demo_abap_xml_json.clas.abap)|
|[Misc ABAP Classes](22_Misc_ABAP_Classes.md)|Contains a selection of ABAP classes, serving as a quick introduction, along with code snippets to explore the functionality in action|-|

<br>

## 🎬 Getting Started with the Examples

The main focus of the ABAP Cheat Sheets is ABAP Cloud. The examples in the *main* branch of the repository are designed to be imported into the SAP BTP ABAP environment.
For classic ABAP, you can find examples in the other branches of the repository that you can import into your sandbox SAP system. Just select the appropriate version (*v757* stands for ABAP version 7.57). Check the information in the following collapsible sections for your system environment and perform the required steps.

<details>
  <summary>1) General info</summary>
  <br>

- Some **DDIC artifacts**, such as database tables, are part of the repository. They are used by the examples to ensure self-contained examples. All artifacts must be imported for all examples to work.
- Most examples are designed to **display some output in the ADT console**. Once successfully imported, you can **run** the examples in ADT by choosing *F9* to display the output in the ADT console. The programs included in the branches for classic ABAP can be executed with *F8*.
- The examples **include descriptions and comments** in the code to provide explanations and set the context.
</details>

<details>
  <summary>2a) SAP BTP ABAP environment</summary>
  <br>

**Prerequisites**
- [x] You have access to an SAP BTP ABAP Environment instance (see [here](https://blogs.sap.com/2018/09/04/sap-cloud-platform-abap-environment) for additional information).
- [x] You have downloaded and installed the ABAP development tools for Eclipse (ADT). Make sure that you are using the latest version, as indicated on the [installation page](https://tools.hana.ondemand.com/#abap).
- [x] Before importing the code, you have performed a system-wide search for classes named `ZCL_DEMO_ABAP*`, for example, so that you do not run into errors when you try to import the code. If someone has already imported the content into the system, you can simply check out that imported version and proceed to the step *3) Run the code*.
- [x] You have created an ABAP cloud project in ADT that allows you to access your SAP BTP ABAP Environment instance (see [here](https://help.sap.com/viewer/5371047f1273405bb46725a417f95433/Cloud/en-US/99cc54393e4c4e77a5b7f05567d4d14c.html) for more information). Your login language is English.
- [x] You have installed the [abapGit](https://github.com/abapGit/eclipse.abapgit.org) plug-in for ADT from the [update site](http://eclipse.abapgit.org/updatesite/).


**Import Code**

Use the abapGit plug-in to install the <em>ABAP Cheat Sheets</em> by carrying out the following steps:

1. In your ABAP cloud project, create a package, for example, *ZABAP_CHEAT_SHEETS* as the target package. It is recommended that you assign the package to a transport request that is suitable for demo content.
2. Add the package to the *Favorite Packages* in the *Project Explorer* view in ADT.
3. To add the <em>abapGit Repositories</em> view to the <em>ABAP</em> perspective, choose *Window* → *Show View* → *Other...* from the menu bar and choose *abapGit Repositories*.
4. In the <em>abapGit Repositories</em> view, click the `+` icon in the upper right corner of the ADT tab to link a new abapGit repository.
  <br>![ADT](./files/abapGit_Repositories.png)

5. The *Link abapGit Repository* popup appears. Enter the following URL:

```
https://github.com/SAP-samples/abap-cheat-sheets.git
```

6. Choose *Next*.

7. On the *Branch and Package Selection* screen, enter the name of the created package (for example, *ZABAP_CHEAT_SHEETS*) in the *Package* field.
8. Choose *Next*.
9.  On the *Select Transport Request* screen, select the created transport request that is suitable for the demo content and choose *Finish* to link the Git repository to your ABAP cloud project. If the created package is already assigned to a transport request for the demo content, and a message appears that an object is already locked in a transport request, choose *Finish*, too.
10. In the *abapGit Repositories* view, filter for your package. The repository appears in the *abapGit Repositories* view with the status <em>Linked</em>.
11. Right-click on the new abapGit repository and choose *Pull...* to start the cloning of the repository contents.
12. On the *Branch and Package Selection* screen, choose *Next*.
13. If the *Locally Modified Object* screen is displayed, select the objects (for example, the package to automatically select all artifacts) from the list and choose *Next*.
14. On the next screen, select a transport request and choose *Finish*. Same as above, if an *object already locked* message is displayed, choose *Finish* as well. The status in the *abapGit Repositories* view changes to <em>Pull running...</em>. Note that the pull run may take several minutes.
15. Once the cloning is complete, the status changes to *Pulled Successfully*. You may need to refresh the *abapGit Repositories* view to see the progress of the import. To do this, choose the  *Refresh* icon in the upper right corner of the view.
16. Refresh your project tree. For example, in ADT, right-click the package and choose *Refresh*. The package should contain all the artifacts from the GitHub repository.
17. Make sure that all artifacts are active. To activate all inactive development objects, choose the *Activate all inactive ABAP development objects* button from the menu (or choose *CTRL+Shift+F3*).
</details>

<details>
  <summary>2b) Classic ABAP (on-premise ABAP systems)</summary>
<br>

**Prerequisites**
- [x] You are running an [ABAP release](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abennews-75.htm) for which examples are available. See the different branches of the repository. For example, you can find out about your ABAP release by checking the value of `sy-saprl`:  
  ```abap
  DATA rel LIKE sy-saprl.
  rel = sy-saprl.
  BREAK-POINT.
  ```
- [x] Before importing the code, you have performed a system-wide search for classes named *ZCL_DEMO_ABAP**, for example, to avoid errors when you try to import the code. If someone has already imported the content into the system, you can simply check out that imported version and proceed to the step *3) Run the code*.
- [x] You have downloaded and installed the ABAP development tools for Eclipse (ADT). Make sure that you are using the latest version, as indicated on the [installation page](https://tools.hana.ondemand.com/#abap).
- [x] You have created an ABAP project in ADT that allows you to access your application server as mentioned above. Your login language is English.
- [x] You have downloaded and installed the standalone version of the abapGit report. Make sure you are using the latest version, as indicated on the [installation page](https://docs.abapgit.org/). You can create a report, for example, *zabapgit_standalone*, and copy and paste [this code](https://raw.githubusercontent.com/abapGit/build/main/zabapgit_standalone.prog.abap) into the program.

**Import Code**

Use the standalone version of the abapGit report to import the demo examples of the ABAP cheat sheets by performing the following steps:
1. In your ABAP project, create a package, such as *TEST_ABAP_CHEAT_SHEETS* as a target package suitable for demo content (for example, by using *LOCAL* as the software component).
2. Add the package to the *Favorite Packages* in the *Project Explorer* view in ADT.
3. Run the standalone version of the abapGit report.
4. Choose the *New Online* button. If the button is not available, for example, if another repository is already open, choose the *Repository List* button.
5. On the *New Online Repository* screen, make the following entries:
   - ***Git Repository URL***:

      ```
      https://github.com/SAP-samples/abap-cheat-sheets.git
      ```

   - ***Package***: Your demo package, for example, *TEST_ABAP_CHEAT_SHEETS*
   - ***Branch***: Choose the button with the 3 dots to the right of the input field. In the pop-up window, select the appropriate branch, e.g. *v757* if your ABAP release is 7.57, and choose the *Continue* (✔️) button. **Note**: The examples in the *main* branch are for ABAP Cloud only. 
   - ***Folder Logic***: *Full*
6. Choose *Create Online Repo*.
7. The *Repository* screen displays the available ABAP artifacts to be imported into your ABAP system.
8. Choose the *Pull* button. The import of the artifacts is triggered. This may take a while.
9. If the *Inactive Objects* popup is displayed, select all artifacts and choose *Continue* (✔️).
10.	When the cloning is complete, refresh your project tree. For example, in ADT, right-click on the package and choose *Refresh*. The package should contain all artifacts from the GitHub repository.
11. Make sure that all artifacts are active. To activate all inactive development objects, choose the *Activate all inactive ABAP development objects* button from the menu (or choose *CTRL+Shift+F3*).

</details>

<details>
  <summary>3) Run the code</summary>
<br>

- Open the package you created containing the imported ABAP artifacts in the ABAP development tools for Eclipse (ADT).
- Classes: 
  - Open one of the ABAP cheat sheet example classes listed in the [ABAP Cheat Sheets Overview](#-abap-cheat-sheets-overview) section, for example, *zcl_demo_abap_string_proc*. The classes are located in the *Source Code Library* → *Classes* folder.
  - Choose *F9* to run the class. Alternatively, choose *Run* → *Run As* → *2 ABAP Application (Console)* from the menu. 
  - Check the console output.
    > **💡 Note**<br>
    >- Check the notes on the context and the ABAP syntax used that are included as comments in the class.
    >- Due to the amount of output in the console, the examples include numbers (e.g. 1) ..., 2) ..., 3) ...) that represent the headers of each example code section. Also, in most cases, the variable name is displayed in the console. Therefore, to find the relevant output in the console more easily and quickly, simply search the console for the number (e.g. search for *3)* for the particular output) or variable name (*CTRL+F* in the console), or use breakpoints in the code to check variables in the debugger.
    >- You may want to clear the console by right-clicking in the console and choosing *Clear* before running another demo class to avoid confusing the output of multiple classes.
- Programs:
  - The programs included in the repository can be executed with *F8* (or *Run* → *Run As* → *1 ABAP Application*). 


</details>

<br>

## ⚡ Known Issues
- Only one user on the system can import this repository because all object names must be globally unique. Before importing the code, you should perform a system-wide search for classes named *ZCL_DEMO_ABAP**, for example. If someone has already imported the content into the system, you can simply check out that imported code.
- Regarding possible code check warnings, e.g. for the many strings in the code, not using an `ORDER BY` clause, or messages regarding using `SELECT *`, the code deliberately avoids [pragmas](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenpragma_glosry.htm) and [pseudo comments](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenpseudo_comment_glosry.htm) in order to focus on the available ABAP syntax. See also the [Disclaimer](#%EF%B8%8F-disclaimer).
- Regarding the examples to be imported into on-premise ABAP systems, note the following: The cheat sheet documents cover ABAP syntax regardless of the ABAP release to avoid scattering information and to have the information in one place. Therefore, the lower the release, the fewer syntax options and examples are available. For example, the RAP examples in particular require at least ABAP version 7.56. The code examples in the classic ABAP branches do not necessarily reflect all (described) syntax variations and options that are available in classic ABAP and in the particular ABAP release. 
- If you encounter import problems with the XSLT/ST objects, try to manually paste the code from the 3 `...source.xml` files ([zdemo_abap_st_carrhtml](./src/zdemo_abap_st_carrhtml.xslt.source.xml), [zdemo_abap_st_strhtml](./src/zdemo_abap_st_strhtml.xslt.source.xml), [zdemo_abap_xslt_fl](./src/zdemo_abap_xslt_fl.xslt.source.xml)) into the improperly imported objects and activate all non-active objects.

<br>

## ℹ️ More Information
- For the system-internal version of the ABAP Keyword Documentation in 
  - ... **classic ABAP**: Access the documentation in the SAP GUI via the transactions `ABAPDOCU` (opens the documentation directly) and `ABAPHELP` (opens an input field with which you can search the documentation content, for example, you can search for a keyword such as `SELECT`). Or, of course, choose `F1` on a keyword in your code. If you are in the SAP GUI (e.g. in `SE80`), the system-internal version opens. If you are in ADT, the documentation opens in the *ABAP Language Help* view.
  - ... **ABAP Cloud**: In ADT, the documentation is in the *ABAP Language Help* view, where you can also search. If you choose `F1` on a keyword in your code, the documentation opens there.
- Links to the online version of the ABAP Keyword Documentation for:
  - **Standard ABAP**: Unrestricted ABAP language scope for [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm) → [Online version of the documentation (latest version)](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm). To access the online documentation for a specific ABAP version, e.g. 7.54, you can select the version from the drop-down list [here](https://help.sap.com/docs/ABAP?locale=en-US) (*latest* is preselected). The *ABAP* link under *Development* will take you to the documentation of choice.
  - **ABAP for Cloud Development**: Restricted ABAP language scope for developments, for example, in the SAP BTP ABAP environment → [Online version of the documentation](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm)
- For demonstration examples of the ABAP Keyword Documentation in classic ABAP, see the `SABAPDEMOS` package.  This package contains all the examples used in the ABAP Keyword Documentation. For the context, class/program name, etc., see the [example page](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap_examples.htm), which is also available in the system-internal SAP GUI version as a node in the topic tree and which summarizes the executable examples. Of course, you can also find the example topics in the context of the individual topic of the ABAP keyword documentation. The example topics are marked with a ⚙️ icon:

  ![](./files/example_topics.png)

<br>

## ⚠️ Disclaimer
The code examples presented in this repository are only syntax examples and are not intended for direct use in a production system environment. The code examples are primarily intended to provide a better explanation and visualization of the syntax and semantics of ABAP statements and not to solve concrete programming tasks. For production application programs, a dedicated solution should therefore always be worked out for each individual case.
There is no guarantee for either the correctness or the completeness of the code. In addition, there is no legal responsibility or liability for possible errors or their consequences, which occur through the use of the example code.

<br>

## 📟 Support
This is not intended to be a contribution repository, so please do not create pull requests. If you like to address issues or suggestions regarding additional syntax to be covered, please create an issue. However, this project is provided "as-is": there is no guarantee that raised issues will be answered or addressed in future releases.

<br>

## 📜 License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.

[^1]: "A written [...] aid (such as a sheet of notes) that can be referred to for help in understanding or remembering something complex" (Definition for "cheat sheet" in Merriam-Webster Dictionary).