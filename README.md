<br />
<div align="center">
  <a href="https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm">
    <img src="./files/ABAP_Keyword_Documentation.png" alt="ABAP Keyword Documentation" >
  </a>
  <h3 align="center" style="font-size: 40px; color: #FCB913;">ABAP Cheat Sheets(미완)</h3>
<h5 align="center" style="font-size: 20px; color: #CCBFFF;">ABAP Cheat Sheets 한국어 버전(비공식)</h5>
  <p align="center">
    실행해볼 수 있는 예제와 함께 ABAP 문법을 간략하게 살펴봅시다.
    <br />
    <!--<a href=""><strong>Expore ABAP syntax in a nutshell & executable examples</strong></a>
    <br />-->
    <br />
    <a href="#%EF%B8%8F-활용-방법">활용 방법</a>
    ·
    <a href="#-abap-cheat-sheets-개요">Cheat Sheets</a>
    ·
    <a href="#-getting-started-with-the-examples">Examples</a>
  </p>
</div>
<br>
<hr>
<br>

[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/abap-cheat-sheets)](https://api.reuse.software/info/github.com/SAP-samples/abap-cheat-sheets)

ABAP cheat sheets[^1] ...
<h3 style="color: #FFAAAA">(注) 원 레포지토리 READ_ME에서는 SAP에서 contribution 용도가 아니라고 밝히고 있습니다. 본 문서 한국어 번역은 비공식 번역임을 알려드립니다.
</h3>

본 문서는 의역이 포함되어 있으므로 정확한 내용은 [원문](https://github.com/malcano/abap-cheat-sheets)을 참고하여 주세요.

- **주제를 선택**하여 여러분이 참고할 수 있는 **ABAP** 레퍼런스를 확인할 수 있습니다.
- 본 문서는 **ABAP구문**을 중점으로 다룹니다.
- **코드 스니펫을 포함하고 있습니다.**
-  [SAP BTP ABAP 환경](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abensap_btp_abap_env_glosry.htm) (*main* branch; ABAP language version: [ABAP for Cloud Development](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_for_cloud_dev_glosry.htm))과 온프레미스 ABAP 시스템 ([classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm); the repository branches other than *main*)에서 [abapGit](https://abapgit.org/)을 사용하여 간단한 실행 가능한 데모 예제를 작동시키고, 확인해볼 수 있습니다. 
- 각 챕터의 링크를 통해 용어집과 **ABAP 키워드 문서** (*F1 도움말*)를 통해 더 자세한 내용을 확인할 수 있습니다.

<summary>💡 확인해주세요!</summary>
<br>

- ABAP 치트 시트는 개괄적인 정보를 제공할 뿐, 구문과 콘셉트에 대한 포괄적인 내용임을 보장하지는 않습니다. 더 많은 정보는 코드 내 키워드의 *F1* 또는 온라인 및 system-internal 버전에서 직접 검색하는 등의 방법으로 ABAP 키워드 문서를 참조해주시기 바랍니다.
- 본 치트 시트에서 별도로 명시되지 않는 한, 본 문서의 내용은 아래 ABAP 언어 버전을 기준으로 합니다.
(첫 항목 중심):
  - [ABAP for Cloud Development](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap_for_sap_cloud_glosry.htm): Restricted ABAP language scope for [ABAP Cloud](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_cloud_glosry.htm) → [Online version of the documentation](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm)
  - [Standard ABAP](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenstandard_abap_glosry.htm): Unrestricted ABAP language scope, for example, for [classic ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm) → [Online version of the documentation (latest version)](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm)
- [알려진 이슈](#-알려진-이슈)와 [면책조항](#%EF%B8%8F-면책조항)을 확인해주세요.
- 본 치트시트는 ABAP 키워드 문서의 항목과 토픽에 대한 링크를 제공합니다. 
기존의 ABAP-only 치트 시트와 달리, ABAP for Cloud Development의 링크를 참조합니다.
- [여기](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenrestricted_abap_elements.htm)를 눌러 
ABAP 버전에 따른 ABAP 언어 요소의 차이를 확인할 수 있습니다. &nbsp;&nbsp; i. e. ABAP Cloud 허용 여부 등<br>
또한, [여기](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenreleased_apis.htm)를 눌러 릴리즈된 API를 확인할 수 있습니다.
- 모든 ABAP 치트 시트를 한 레포지토리에 보관할 목적으로, 클래식 ABAP에만 해당하는 ABAP 치트 시트 문서도 ABAP Cloud 예제를 위한 *main* 브랜치에 포함됩니다.
- 클래식 ABAP용 브랜치에 포함된 예제 class는 대부분 ABAP for Cloud Development에서도 사용할 수 있습니다. 서브패키지 `TEST_ABAP_CHEAT_SHEETS_CLASSIC`는 스탠다드 ABAP과 관련된 구문을 포함하고 있으며, dynpro ABAP과 같은 키워드는 ABAP for Cloud Development에서 사용할 수 없습니다.

<br>

## 🏗️ 활용 방법

1. **ABAP 구문 정보**: [ABAP cheat sheets](#-abap-cheat-sheets-overview)에서 간단한 설명을 통해 다양한 ABAP 구문과 개념을 익혀보세요.
2. **예제**: [abapGit](https://abapgit.org/)을 사용하여 ABAP development object를 레포지토리로 가져오고([여기](#-getting-started-with-the-examples)를 참조) [ABAP development tools for Eclipse (ADT)](https://tools.eu1.hana.ondemand.com/)환경에서 *F9*를 눌러 데모 클래스를 실행시켜 ABAP구문이 작동되는 것을 확인할 수 있어요.
<br>

## 📝 ABAP Cheat Sheets 개요

| Cheat Sheet        | 내 용           |  Demo 예제  |
| ------------- | ------------- | ----- |
|[ABAP for Cloud Development](19_ABAP_for_Cloud_Development.md)| ABAP Cloud 용어 개괄 및 ABAP for Cloud Development 환경을 위한 클래식 ABAP | [zcl_demo_abap_cloud_excursion](./src/zcl_demo_abap_cloud_excursion.clas.abap) (cheat sheet 내용 참조) |
|[데이터 타입과 데이터 오브젝트 (Data Types and Data Objects)](16_Data_Types_and_Objects.md)| ABAP의 데이터 타입과 데이터 오브젝트에 대한 기본적인 설명 | [zcl_demo_abap_dtype_dobj](./src/zcl_demo_abap_dtype_dobj.clas.abap)   |
|[인터널 테이블 (Internal Tables)](01_Internal_Tables.md)| 인터널 테이블 생성, 삽입, 읽기, 정렬, 수정 | [zcl_demo_abap_internal_tables](./src/zcl_demo_abap_internal_tables.clas.abap)   |
|[스트럭쳐 (구조체) (Structures)](02_Structures.md)| 스트럭쳐 활용 기초 |  [zcl_demo_abap_structures](./src/zcl_demo_abap_structures.clas.abap)  |
|[ABAP SQL](03_ABAP_SQL.md)| `SELECT`를 사용하여 데이터베이스 테이블 읽기, `INSERT`, `UPDATE`,`MODIFY`,`DELETE`를 사용하여 데이터베이스 테이블의 데이터 수정하기 | [zcl_demo_abap_sql](./src/zcl_demo_abap_sql.clas.abap)   |
|[ABAP 오브젝트에 대해 알아보기 (ABAP Object Orientation) ](04_ABAP_Object_Orientation.md)|상속, 인터페이스 등 오브젝트와 컴포넌트 활용하기 | [zcl_demo_abap_objects](./src/zcl_demo_abap_objects.clas.abap) |
|[생성자 표현식(Constructor Expressions)](05_Constructor_Expressions.md)| `VALUE`, `CORRESPONDING`, `NEW`, `CONV`, `EXACT`, `REF`, `CAST`, `COND`, `SWITCH`, `FILTER`, `REDUCE` 등의 연산자를 활용한 생성자 표현식과 `FOR`, `LET`를 활용한 반복자 표현식 | [zcl_demo_abap_constructor_expr](./src/zcl_demo_abap_constructor_expr.clas.abap) |
|[동적 프로그래밍(Dynamic Programming)](06_Dynamic_Programming.md)| 동적 프로그래밍을 위한 요소로서의 필드 심볼과 데이터 레퍼런스, 동적 ABAP 구문 구성과 runtime type services (RTTS) i. e. runtime type identification (RTTI), runtime type creation (RTTC) |  [zcl_demo_abap_dynamic_prog](./src/zcl_demo_abap_dynamic_prog.clas.abap)  |
|[문자열 처리 (String Processing)](07_String_Processing.md)| 문자열 생성, 값 할당, 문자열 변경, 문자열 템플릿, 문자열 힙치기, 나누기, 수정, 탐색, 대치, 정규표현식 |  [zcl_demo_abap_string_proc](./src/zcl_demo_abap_string_proc.clas.abap)  |
|[ABAP for RAP: Entity Manipulation Language (ABAP EML)](08_EML_ABAP_for_RAP.md)| RAP 의 EML 환경설정, 표준(생성, 읽기, 갱신, 삭제), 비표준 작업 (actions) | <ul><li>[Demo RAP scenario with a managed RAP BO, external numbering (zcl_demo_abap_rap_ext_num_m)](./src/zcl_demo_abap_rap_ext_num_m.clas.abap)</li><br><li>[Demo RAP scenario with an unmanaged RAP BO, external numbering (zcl_demo_abap_rap_ext_num_u)](./src/zcl_demo_abap_rap_ext_num_u.clas.abap)</li><br><li>[Demo RAP scenario ("RAP calculator") with a managed, draft-enabled RAP BO,  late numbering (zcl_demo_abap_rap_draft_ln_m)](./src/zcl_demo_abap_rap_draft_ln_m.clas.abap) <br>해당 예제는 SAP Fiori UI 프리뷰 버전을 사용하여 확인할 수 있어요. 본 클래스 내 코멘트를 확인해주세요.</li><br><li>[Demonstrating the local consumption of RAP business events in the context of a RAP demo scenario, managed RAP BO with managed internal numbering and additional save (zcl_demo_abap_rap_m_as)](./src/zcl_demo_abap_rap_m_as.clas.abap)</li></ul>  |
|[Bit와 Byte에 대해 알아보기 (Excursion Down to Bits and Bytes)](09_Bits_and_Bytes.md)|데이터 타입과 데이터 오브젝트에 대한 기술적 배경|-|
|[ABAP SQL: 계층구조 활용하기 (Working with Hierarchies)](10_ABAP_SQL_Hierarchies.md)|DB 테이블에 저장되어 있는 계층적 데이터를 활용하기 위한 ABAP CDS와 함께 제공되는 ABAP SQL 기능|-|
|[인터널 테이블 그룹짓기 (Internal Tables: Grouping)](11_Internal_Tables_Grouping.md)|인터널 테이블 구문에서의 `GROUP BY` 조건 |[zcl_demo_abap_sql_group_by](./src/zcl_demo_abap_sql_group_by.clas.abap)|
|[ABAP Managed Database Procedures (AMDP)](12_AMDP.md)| AMDP(ABAP Managed Database Procedures)와 AMDP Functions (CDS Table Functions 포함)|[zcl_demo_abap_amdp](./src/zcl_demo_abap_amdp.clas.abap)|
|[프로그램 흐름 로직 (Program Flow Logic)](13_Program_Flow_Logic.md)|흐름 제어(`IF`, `CASE`)와 반복(`DO`, `WHILE`), 예외 처리|[zcl_demo_abap_prog_flow_logic](./src/zcl_demo_abap_prog_flow_logic.clas.abap)|
|[ABAP 단위 테스트](14_ABAP_Unit_Tests.md)|ABAP 내 단위 테스트에 대한 기본적인 설명|[zcl_demo_abap_unit_test](./src/zcl_demo_abap_unit_test.clas.abap)|
|[CDS 뷰 엔터티](15_CDS_View_Entities.md)|[여기](https://blogs.sap.com/2022/10/24/feature-matrix-data-modeling-with-abap-core-data-services/)에서 cheat sheet 콘텐츠를 확인할 수 있습니다. 본 문서에서는 CDS artifacts와 [실행가능한 예제 클래스](./src/zcl_demo_abap_cds_ve.clas.abap)에 중점을 두고 있습니다. (코멘트 포함)|[zcl_demo_abap_cds_ve](./src/zcl_demo_abap_cds_ve.clas.abap)|
|[SAP LUW](17_SAP_LUW.md)|SAP LUW 구문을 중점으로 관련된 데이터 정합성에 관한 [SAP LUW](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abensap_luw_glosry.htm) 콘셉트 <br>💡실행 예제의 일부 구문은 [클래식 ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm)에만 해당하는 내용을 포함하고 있습니다.|프로그램 `ZDEMO_ABAP_SAP_LUW`|
|[Dynpro](18_Dynpro.md)|Dynpro를 중심으로 한 구문 개요 <br>💡[클래식 ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm)에만 해당하는 예제를 포함하고 있습니다.|프로그램 `ZDEMO_ABAP_DYNPRO`|
|[Selection Screen과 클래식 List (Selection Screens and Classic Lists)](20_Selection_Screens_Lists.md)|Selection-Screen과 class list에 대한 개요. SAP List Viewr (ALV)와 관련된 내용을 포함하고 있습니다. <br>💡[클래식 ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm)에만 해당하는 예제를 포함하고 있습니다.|프로그램 `ZDEMO_ABAP_SELSCR_LISTS_INTRO` ("intro" 프로그램: 다른 예제 프로그램을 실행할 수 있는 프로그램)|
|[ABAP에서 XML과 JSON 활용하기 (Working with XML and JSON in ABAP)](21_XML_JSON.md)| 클래스 라이브러리를 활용하여 XML처리와 XSLT와 Simple Transformations (ST)를 활용한 XML 변환, serialization(직렬화, ABAP -> XML ), deserealization(역직렬화, XML -> ABAP), JSON 데이터 활용|[zcl_demo_abap_xml_json](./src/zcl_demo_abap_xml_json.clas.abap) |
|[기타 ABAP 클래스(Misc ABAP Classes)](22_Misc_ABAP_Classes.md)|ABAP 클래스의 selection 소개, 기능들을 살펴볼 수 있는 코드 스니펫|-|

<br>

## 🎬 Getting Started with the Examples

ABAP Cheat Sheets는 ABAP Cloud에 중점을 두고 있습니다. 레포지토리 상 *main*브랜치의 예제는 SAP BTP ABAP 환경으로 가져올 수 있도록 설계되어 있습니다.
Classic ABAP의 경우, 레포지토리의 다른 브랜치에서 적절한 버전 (*v757* 는 ABAP 버전 7.57입니다)을 선택하여 샌드박스 SAP 시스템으로 예제를 가져올 수 있습니다. 
시스템 환경에 맞는 정보를 아래에서 확인하고 필요한 작업을 수행해주세요.

  <summary>1) General info</summary>
  <br>

- 데이터베이스 테이블과 같은 일부 **DDIC 아티팩트**는 리포지토리의 일부입니다. 이 테이블은 예제가 독립적으로 작동될 수 있기 위해 사용되는 항목입니다. 예제의 정상적인 작동을 위해선 모든 항목을 임포팅하여야 합니다. 
- 예제의 대부분은 **ADT 콘솔에 출력되도록** 설계되어 있습니다. 임포팅 후 *F9*을 통해 예제를 ADT에서 실행하고 츌력값을 ADT 콘솔에서 확인할 수 있습니다. classic ABAP용 브랜치에 포함된 프로그램은 *F8*을 통해 실행할 수 있습니다.
- 예제 코드에는 해설과 콘텍스트 설정을 위한 **주석과 설명**을 포함하고 있습니다.

  <summary>2a) SAP BTP ABAP 환경</summary>
  <br>

**필수조건**
- SAP BTP ABAP 환경 인스턴스에 접근 가능해야 합니다. (추가 정보는 [링크](https://blogs.sap.com/2018/09/04/sap-cloud-platform-abap-environment) 참조)
- Eclipse 용 ABAP Development Tool (ADT)를 다운로드 및 설치해야 합니다. [설치 페이지](https://tools.hana.ondemand.com/#abap)에서 최신 버전을 사용중인지 확인하세요.
- 코드를 가져오기 전, `ZCL_DEMO_ABAP*`과 같은 이름의 클래스가 이미 시스템에 존재하는지 확인하여 코드 임포팅 시 에러가 발생하지 않도록 하세요. 이미 시스템에 임포팅된 경우, 사전에 임포팅된 항목의 버전을 확인한 후 *3) 코드 실행* 단계를 진행하시면 됩니다.
- SAP BTP ABAP 환경 인스턴스에 접근할 수 있도록 ABAP cloud project in ADT 를 생성(더 많은 정보는 [여기](https://help.sap.com/viewer/5371047f1273405bb46725a417f95433/Cloud/en-US/99cc54393e4c4e77a5b7f05567d4d14c.html) 를 통해 확인).
- [여기](http://eclipse.abapgit.org/updatesite/)에서 [abapGit](https://github.com/abapGit/eclipse.abapgit.org) plug-in for ADT 설치.

**코드 임포팅**

abapGit 플러그인을 사용하여 <em>ABAP Cheat Sheets</em>를 설치하세요. 
아래 절차 참조:

1. ABAP 클라우드 프로젝트에서 *ZABAP_CHEAT_SHEETS*과 같은 형테로 패키지를 생성하세요. 데모 컨텐츠를 위한 transport request 에 패키지를 할당하는 것을 권장합니다.
2. ADT의 *Project Explorer* 뷰에서 패키지를 *Favorite Packages*에 추가합니다.
3. <em>abapGit Repositories</em>뷰를 <em>ABAP</em> perspective에 추가하기 위해선, 메뉴 바에서 *Window* → *Show View* → *Other...*를 선택하고 *abapGit Repositories*를 선택하세요.
4. <em>abapGit Repositories</em> 뷰에서 ADT 탭 우상단의 `+` 아이콘을 클릭하여 새 abapGit 리포지토리를 연결합니다.
  <br>![ADT](./files/abapGit_Repositories.png)

5. *Link abapGit Repository* 팝업이 나타나면 아래 URL을 입력하세요.
```
https://github.com/SAP-samples/abap-cheat-sheets.git
```
6. *Next* 선택.
7. *Branch and Package Selection* 화면에서, 앞서 생성한 *ZABAP_CHEAT_SHEETS*과 같은 이름으로 생성한 패키지명을 *Package* 에 입력하세요.
8. *Next* 선택.
9. *Select Transport Request* 화면에서, 데모 콘텐츠를 위해 생성한 Transport Request 를 선택하고 *Finish*를 눌러 ABAP cloud project에 Git 저장소를 연결하세요. 이미 데모 콘텐츠를 위한 Transport Request에 생성한 패키지가 assign되어있다면, 락이 잡혔다는 메세지가 표시되고 이런 경우에도 *Finish*를 누르시면 됩니다.
10. *abapGit Repositories* 뷰에서 패키지를 필터링합니다. *abapGit Repositories* 뷰에 리포지토리가  <em>Linked</em> 상태로 표시됩니다.
11. 신규 생성된 new abapGit repository를 마우스 우클릭하고 *Pull...* 를 선택하여 리포지토리 콘텐츠를 cloning합니다. 
12. *Branch and Package Selection* 화면에서 *Next* 선택.
13. *Locally Modified Object* 가 화면에 표시되면, 목록에서 오브젝트(ex. the package to automatically select all artifacts)를 선택하고 *Next* 선택.
14. 다음 화면에서 Transport Request 를 선택하고 *Finish* 선택. 앞서 기술한 것과 같이,  *object already locked* 메세지가 보여지는 경우에도 *Finish* 선택. *abapGit Repositories* 뷰가 <em>Pull running...</em> 상태로 변경됩니다. 이 작업은 수 십분이 소요될 수 있습니다.
15. Cloning 작업이 완료되면, *Pulled Successfully* 상태로 변경됩니다. 뷰의 우상단 *Refresh* 아이콘을 눌러 *abapGit Repositories*를 새로고침하면 Imporing 진행상태를 확인할 수 있습니다.
16. Project Tree를 새로고침 하세요. ADT에서는 패키지를 우클릭하여 *Refresh*를 선택합니다. 패키지에는 GitHub의 모든 아티팩트가 포함되어 있어야 합니다.
17. 모든 아티팩트가 활성화되었는지 확인합니다. 메뉴의 *Activate all inactive ABAP development objects* 버튼이나 단축키 *CTRL+Shift+F3*를 눌러 비활성화된 모든 개발 오브젝트를 활성화할 수 있습니다.

  <summary>2b) Classic ABAP (on-premise ABAP systems)</summary>
<br>

**필수조건**
- 예제를 정상적으로 실행하기 위해선 [ABAP release](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abennews-75.htm)를 확인해야 합니다. 리포지토리의 다른 브랜치를 확인해주세요. `sy-saprl`값을 확인하여 사용 중인 ABAP release를 확인할 수 있습니다.:  
  ```abap
  DATA rel LIKE sy-saprl.
  rel = sy-saprl.
  BREAK-POINT.
  ```
- 코드를 가져오기 전, `ZCL_DEMO_ABAP*`과 같은 이름의 클래스가 이미 시스템에 존재하는지 확인하여 코드 임포팅 시 에러가 발생하지 않도록 하세요. 이미 시스템에 임포팅된 경우, 사전에 임포팅된 항목의 버전을 확인한 후 *3) 코드 실행* 단계를 진행하시면 됩니다.
- Eclipse 용 ABAP Development Tool (ADT)를 다운로드 및 설치해야 합니다. [설치 페이지](https://tools.hana.ondemand.com/#abap)에서 최신 버전을 사용중인지 확인하세요.
앞서 언급한 바와 같이, application 서버에 접근할 수 있도록 ABAP project in ADT 를 생성해야 합니다. 로그인 언어는 영어로 설정.
- standalone 버전 abapGit Report 를 다운로드 하여 설치합니다. [설치 페이지](https://docs.abapgit.org/)에서 최신 버전을 사용하고 있는지 확인하세요.
*zabapgit_standalone*과 같은 이름으로 Report 를 생성한 후, [이 코드](https://raw.githubusercontent.com/abapGit/build/main/zabapgit_standalone.prog.abap)를 복사-붙여넣기하세요.

**코드 임포팅**

아래 순서대로 standalone 버전 abapGit 리포트 프로그램을 사용하여 ABAP cheat sheets의 예제 코드를 가져오세요.:

1. ABAP 프로젝트에서 *TEST_ABAP_CHEAT_SHEETS*와 같은 이름으로 데모 콘텐츠용 대상 패키지를 생성합니다(예: 소프트웨어 컴포넌트로 *LOCAL* 사용).
2. ADT의 *Project Explorer* 뷰에서 *Favorite Packages*에 위에서 생성한 패키지를 추가합니다.
3. standalone 버전 abapGit report 프로그램 실행.
4. *New Online* 버튼 선택. 
다른 리포지토리가 이미 열려있는 등, 버튼이 사용불가한 경우 *Repository List* 버튼을 클릭합니다.
5. *New Online Repository* 화면에서, 아래 항목을 입력합니다.:
   - ***Git 리포지토리 URL***:
      ```
      https://github.com/SAP-samples/abap-cheat-sheets.git
      ```
   - ***Package***: 데모 패키지명, ex. *TEST_ABAP_CHEAT_SHEETS*
   - ***Branch***: 
   입력란 우측의 점 3개 버튼을 선택. 팝업 화면에서, 적잘한 브랜치 선택. (만약, ABAP release가 7.57이면, *v757* 선택) *Continue* (✔️) 버튼 선택. **참고**: *main* 브랜치의 예제는 ABAP Cloud 전용.
   - ***Folder Logic***: *Full*
6. *Create Online Repo* 선택.
7. ABAP system으로 가져올 수 있는 ABAP 아티팩트가 *Repository* 화면에 표시됩니다.
8. *Pull* 버튼을 선택하면 아티팩트를 가져오기 시작합니다. 이 작업은 시간이 다소 소요될 수 있습니다.
9. *Inactive Objects* 팝업이 표시되면, 모든 아티팩트를 선택하고 *Continue* (✔️) 버튼을 선택합니다.
10.	Cloning 작업이 완료되면, project tree를 새로고침하세요. 
ADT 환경의 경우, 패키지를 우클릭하여 *Refresh*를 선택합니다. 패키지에는 GitHub 리포지토리의 모든 아티팩트가 포함되어있어야 합니다.
11. 모든 아티팩트가 활성화되었는지 확인합니다. 메뉴의 *Activate all inactive ABAP development objects* 버튼이나 단축키 *CTRL+Shift+F3*를 눌러 비활성화된 모든 개발 오브젝트를 활성화할 수 있습니다.

  <summary>3) 코드 실행</summary>
<br>

- ABAP development tools for Eclipse (ADT)에서 임포팅한 ABAP 아티팩트가 포함된 패키지를 엽니다.
- 클래스: 
- [ABAP Cheat Sheets Overview](#-abap-cheat-sheets-overview) 섹션에 나열된 ABAP 치트 시트 예제 클래스 중 하나를 엽니다. 예를 들어, *zcl_demo_abap_string_proc*는 *Source Code Library* → *Classes* 폴더에서 찾을 수 있습니다.
- *F9*를 눌러 클래스를 실행합니다. 메뉴에서 *Run* → *Run As* → *2 ABAP Application (Console)*와 같이 선택하여 실행할 수도 있습니다.
  - 콘솔 출력 결과를 확인하세요.
    > **💡 참고**<br>
    >- 클래스 내 주석으로 포함된 내용과 ABPA 구문 용례를 확인하세요.
    >- 콘솔에 출력되는 양이 많기 때문에, 예제에서는 각 예제 코드 섹션의 헤더를 나타내는 번호 (e.g. 1) ..., 2) ..., 3) ...) 가 포함됩니다. 또한, 대부분의 변수명은 콘솔에 표시되며 콘솔에서 관련 출력값을 찾으려면 해당 출력에 해당하는 번호나 변수명을 콘솔에서 검색(*CTRL+F*)하거나, breakpoint를 사용하여 debugger에서 변수값을 확인하세요.
    >- 데모 클래스의 출력값이 헷갈리지 않도록 다른 예제를 실행하기 전에 콘솔에서 마우스 우클릭을 하여 *Clear*를 선택하고 콘솔을 비우는 것이 좋습니다.
- 프로그램:
  - 리포지토리에 저장된 프로그램은 *F8* (또는 *Run* → *Run As* → *1 ABAP Application*) 로 실행할 수 있습니다. 

<br>

## ⚡ 알려진 이슈
- 모든 오브젝트의 이름은 전역적(globally)으로 유일해야 하므로 시스템의 한 사용자만 본 레포지토리를 import할 수 있습니다. **ZCL_DEMO_ABAP** 클래스를 가져온다면, 해당 이름으로 된 클래스를 시스템 전체에서 찾아본 후 본 코드를 import 해주세요. 이미 시스템으로 가져온 클래스라면 앞서 import된 코드를 참조하세요.
- 코드 체크 시 다음과 같은 warning이 발생할 수 있습니다. , e.g. 코드 길이가 길어지는 것을 방지하기 위하여 `ORDER BY` 조건을 사용하지 않거나 `SELECT * `을 사용하였습니다.(for the many strings in the code, not using an `ORDER BY` clause, or messages regarding using `SELECT *`), ABAP 구문에 집중하기 위해 의도적으로 [pragmas](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenpragma_glosry.htm)와 [pseudo comments](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenpseudo_comment_glosry.htm)를 사용하지 않습니다. [면책조항](#%EF%B8%8F-disclaimer)도 함께 확인해주세요.
- 온 프레미스 ABAP 시스템으로 예제를 import 하는 경우, 다음과 같은 사안을 유의해주세요: 본 문서는 정보의 분산을 방지하고 용이한 관리를 위해 ABAP릴리즈를 고려하지 않고 ABAP 문법을 다룹니다. 따라서, 릴리즈 버전이 낮을수록 유효한 예제가 적습니다. 특히, RAP 예제는 ABAP 7.56 이상의 버전이 요구됩니다.
클래식 ABAP 브랜치의 예제의 경우, 특정 ABAP 릴리즈와 클래식 ABAP에 대한 문법 활용과 설정을 모두 반영하고 있지는 않습니다.
- XSLT/ST 오브젝트 import 문제가 발생하였다면, 세 `...source.xml`파일 ([zdemo_abap_st_carrhtml](./src/zdemo_abap_st_carrhtml.xslt.source.xml), [zdemo_abap_st_strhtml](./src/zdemo_abap_st_strhtml.xslt.source.xml), [zdemo_abap_xslt_fl](./src/zdemo_abap_xslt_fl.xslt.source.xml))의 코드를 직접 붙여넣고 모든 오브젝트를 활성화해보세요.
<br>

## ℹ️ 더 많은 정보 
- 시스템 내부 버전에 따른 ABAP Keyword 문서:
  - **클래식 ABAP**: T-Code `ABAPDOCU`(문서 직접 열기)와 `ABAPHELP`(문서 내용을 검색할 수 있는 인풋 필드 보기, `SELECT`와 같은 키워드를 검색 가능)를 통해 SAP GUI의 문서를 조회합니다. 물론 코드의 키워드에서 `F1`을 눌러서 확인할 수도 있습니다. SAP GUI(e.g. in `SE80`)에서 접근할 경우, 시스템 내장 버전이 열립니다. ADT 환경에서는 *ABAP Language 도움말* 보기에서 열립니다.
  - **ABAP Cloud**: 
  ADT 환경에서 `ABAP Language 도움말` 보기에서 검색기능을 사용하여 문서를 탐색할 수 있습니다.코드의 키워드에서 `F1`을 눌러서 확인할 수도 있습니다. 
- 온라인 버전 ABAP Keyword 문서:
  - **스탠다드 ABAP**: ABAP 언어 버전 무관 [클래식 ABAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclassic_abap_glosry.htm)문서 → [온라인 버전 문서 (최신 버전)](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap.htm). 7.54와 같이 특정 ABAP 버전의 온라인 문서를 확인하려면 [여기](https://help.sap.com/docs/ABAP?locale=en-US)의 드롭다운 리스트에서 해당 버전을 선택해주세요.(기본적으로 *최신* 버전이 선택됩니다.) *Development* 하단 *ABAP* 링크를 클릭하면 선택한 문서로 이동합니다.
  - **ABAP for Cloud Development**: SAP BTP ABAP환경과 같은 특정 ABAP 언어 → [온라인 버전 문서](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm)
- 클래식 ABAP에서 ABAP 키워드 문서의 예제는 `SABAPDEMOS` 패키지에서 확인하세요.
  ABAP 키워드 문서에서 사용된 모든 예제가 본 패키지에 포함되어 있습니다.
  context, 클래스/패키지 명 등은 [예제 페이지](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abenabap_examples.htm)에서 확인할 수 있으며, 시스템 내장 SAP GUI 버전에서도 예제별 내용을 트리 뷰를 통해 확인할 수 있습니다. 개별 주제에 대한 ABAP키워드 문서도 검색할 수 있으며, 예제별 토픽은 ⚙️ 아이콘으로 표기되어 있습니다. <br>
  ![](./files/example_topics.png)

<br>

## ⚠️ 면책조항
본 레포지토리가 제공하는 코드 예제는 구문 예제일 뿐, 업무 시스템 환경에서 직접 사용할 목적으로 작성되지 않았습니다. 예제 코드는 실질적인 프로그래밍 작업을 해결하기 위한 것이 아닌, ABAP 구문의 문법과 의미를 보다 효과적이고 시각적으로 전달하기 위함을 주 목적으로 합니다. 따라서, 실무 응용 프로그램에서는 개별 경우에 맞는 적절한 해결방안을 찾아 활용해야 합니다. 코드의 정확성과 완전성을 보장하지 않으며, 예제 코드 사용으로 인해 발생할 수 있는 오류와 결과에 대한 법적 책임 및 의무를 지지 않습니다.

<br>

## 📟 Support
본 레포지토리([원본 레포지토리](https://github.com/malcano/abap-cheat-sheets))는 Contribution 레포지토리가 아니므로 pull request를 하지 마세요. 구문과 관련된 이슈나 제안이 있을 경우, 'issue'를 만들어주세요. 하지만, 본 프로젝트는 "AS-IS"대로 제공되므로 이슈에 대한 답변이 이루어지거나, 향후 릴리즈에서 문제가 해결되리라는 보장을 하지 않습니다.

<br>

## 📜 License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.
### For Korean Versions..
Copyright (c) 2024 malcano. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSE) file.



[^1]: "A written [...] aid (such as a sheet of notes) that can be referred to for help in understanding or remembering something complex" (Definition for "cheat sheet" in Merriam-Webster Dictionary).