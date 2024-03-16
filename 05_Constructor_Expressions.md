<a name="top"></a>

# Constructor Expressions

- [Constructor Expressions](#constructor-expressions)
  - [Introduction](#introduction)
  - [VALUE](#value)
  - [CORRESPONDING](#corresponding)
  - [NEW](#new)
  - [CONV](#conv)
  - [EXACT](#exact)
  - [REF](#ref)
  - [CAST](#cast)
  - [COND](#cond)
  - [SWITCH](#switch)
  - [FILTER](#filter)
  - [LET Expressions](#let-expressions)
  - [Iteration Expressions](#iteration-expressions)
    - [Iteration Expressions Using FOR](#iteration-expressions-using-for)
    - [REDUCE](#reduce)
  - [Executable Example](#executable-example)

## Introduction

-   [Constructor
    expressions](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_glosry.htm "Glossary Entry")
    include a [constructor
    operator](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_operator_glosry.htm "Glossary Entry")
    followed by the specification of a [data
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendata_type_glosry.htm "Glossary Entry")
    or [object
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenobject_type_glosry.htm "Glossary Entry")
    (or a `#` character that stands for such a type) and
    specific parameters specified within parentheses. Example using the
    `VALUE` operator:

    ``` abap
    ... VALUE some_type( ... ) ...
    ... VALUE #( ... ) ...
    ```

-   As the name implies, these expressions construct results of a
    specific type and their content. Either the type is specified
    explicitly before the first parenthesis or the said `#`
    character can be specified if the type can be derived implicitly
    from the [operand
    position](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenoperand_position_glosry.htm "Glossary Entry").
    The `#` character symbolizes the [operand
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenoperand_type_glosry.htm "Glossary Entry").
    If no type can be derived from the operand position, for some
    constructor operators, the type can also be derived from the
    arguments in the parentheses.
-   Why use them? Constructor expressions can make your code leaner and
    more readable since you can achieve the same with fewer statements.
-   Apart from the concept of deriving types from the context, another
    concept is very handy particularly in this context: [Inline
    declaration](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeninline_declaration_glosry.htm "Glossary Entry").
    -   This means that you can declare a variable using
        `DATA(var)` (or an immutable variable
        [`FINAL(var)`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenfinal_inline.htm))
        as an operand in the current [write
        position](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenwrite_position_glosry.htm "Glossary Entry").
        In doing so, such a variable declared inline can be given the
        appropriate type and result of the constructor expression in one
        go: `DATA(strtable) = VALUE string_table( ( `a` ) ( `b` ) ( `c` ) ).` or `DATA(dec) = CONV decfloat34( '1.23' ).`.

> **✔️ Hint**<br>
>-  The construction of a result, i. e. a target [data
object](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendata_object_glosry.htm "Glossary Entry"),
implies that the data object is initialized. However, for some
constructor operators, there is an addition with which the
initialization can be avoided.
>- As is true for many of the following syntax options, you can do a lot with constructor expressions, often with fewer lines (than older syntax equivalents) of code in a very elegant way. However, keep in mind the readability, maintainability, and debuggability of your code.

<p align="right"><a href="#top">⬆️ back to top</a></p>

## VALUE

-   Expressions with the
    [`VALUE`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_value.htm)
    operator construct a result in place based on a data type.
-   This result can be initial values for any non-generic data types,
    structures or internal tables.
> **💡 Note**<br>
> Elementary data types and reference types cannot be
    explicitly specified for the construction of values here.
-   Regarding the type specifications before and parameters within the
    parentheses:
    -   No parameter specified within the parentheses: The return value
        is set to its type-specific initial value. This is possible for
        any non-generic data types. See more information
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenvalue_constructor_params_init.htm).
    -   Structured and internal table type before the parentheses or
        `#` stands for such types: Individual components of
        structures can be specified as named arguments while each
        component of the return value can be assigned a data object that
        has the same data type as the component, or whose data type can
        be converted to this data type. See more information
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenvalue_constructor_params_struc.htm).
        To construct internal tables, you have multiple options, for
        example, you can add individual table lines using an inner pair
        of parentheses. More syntax options, for example, using the
        additions `BASE` and `FOR` are possible, too.
        See more information
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenvalue_constructor_params_itab.htm).
- As mentioned above, the concept of [inline declarations](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeninline_declarations.htm)
is very handy in this context. You can construct a new data object (for example, using `DATA(...)` or `FINAL(...)`), provide the desired type with the constructor expression and assign
values in one go.
- In case of [deep](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendeep_structure_glosry.htm "Glossary Entry")
and [nested structures](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abennested_structure_glosry.htm "Glossary Entry")
or [deep tables](https://help.sap.com/doc/abapdocu_latest_index_htm/latest/en-US/index.htm?file=abendeep_table_glosry.htm "Glossary Entry"),
the use of `VALUE` expressions is handy, too, because you can create corresponding values in place.

The following examples cover: 
- Populating structures and internal tables with `VALUE`
- Creating initial values (for all types possible)
- Possible additions, such as `BASE` (retaining existing content) and `LINES OF` (adding all or some lines from other internal tables; more additions are available here)
- Short form of `VALUE` constructor expressions for internal tables with structured line types
- Excursions 

```abap
"-------------- Populating structures/internal tables with VALUE --------------

"Declaring structured data type and structured data object
TYPES: BEGIN OF struc_type,
            a TYPE i,
            b TYPE c LENGTH 3,
        END OF struc_type.

DATA struc TYPE struc_type.

"Using VALUE constructor expression
"Note: The data type can be retrieved from the context. Then, # can
"be specified.
struc = VALUE #( a = 1 b = 'aaa' ).

"Using an inline declaration
"In the following example, the type cannot be retrieved from the
"context. Therefore, an explicit specification of the type is
"required.
DATA(struc2) = VALUE struc_type( a = 2 b = 'bbb' ).

"The following syntax is also possible (explicit data type
"specification although the type can be determined).
struc = VALUE struc_type( a = 3 b = 'ccc' ).

"Using such a VALUE constructor expression instead of, for example,
"assigning the component values individually using the component
"selector (-).
struc-a = 4.
struc-b = 'ddd'.

"Internal table
"Note the extra pair of parentheses for an individual table line.
DATA itab TYPE TABLE OF struc_type WITH EMPTY KEY.

itab = VALUE #( ( a = 5 b = 'eee' )
                ( a = 6 b = 'fff' ) ).

"Using such a VALUE constructor expression instead of, for example,
"APPEND statements (note the BASE addition for retaining existing
"table lines further down)
APPEND struc TO itab.
APPEND INITIAL LINE TO itab.

"Inline declaration, explicit table type specification after VALUE
TYPES itab_type TYPE TABLE OF struc_type WITH EMPTY KEY.
DATA(itab2) = VALUE itab_type( ( a = 7 b = 'ggg' )
                               ( a = 8 b = 'hhh' ) ).

"Internal table with an elementary line type
"Unstructured line types work without component names.
DATA(itab3) = VALUE string_table( ( `Hello` )
                                  ( `world` ) ).

"-------------- Creating initial values --------------

"Type-specific initial value for data objects by leaving the
"VALUE constructor expression empty
"Structure (the entire structure is initial)
struc = VALUE #( ).

"Internal table
DATA(itab4) = VALUE itab_type( ).
"This basically corresponds to the following data object declarations
"DATA itab5 TYPE itab_type.
"DATA itab6 TYPE itab_type VALUE IS INITIAL.

"Not specifying individual components means these components
"remain initial
"Component b not specified, i.e. b remains initial
struc = VALUE #( a = 2 ).
"Explicitly setting an initial value for a component
struc = VALUE #( a = 1 b = VALUE #( ) ).
"All component values of the first line added are initial
itab4 = VALUE #( ( ) ( a = 1 b = 'aaa' ) ).

"Initial values can be created for all types, e.g. also for elementary types.
"VALUE cannot be used to create elementary data objects and provide concrete
"values, however, an empty VALUE expression can be used to create elementary
"data objects with type-specific initial values.
DATA(int) = VALUE i( ).
DATA int2 TYPE i.
int2 = VALUE #( ).
DATA(xstr) = VALUE xstring( ).

"-------------- VALUE constructor used for nested/deep data objects  --------------

"Creating a nested structure
DATA: BEGIN OF nested_struc,
        a TYPE i,
        BEGIN OF struct,
            b TYPE i,
            c TYPE c LENGTH 3,
        END OF struct,
        END OF nested_struc.

"Populating a nested structure
nested_struc = VALUE #( a = 1 struct = VALUE #( b = 1 c = 'aaa' ) ).

"Instead of, for example, using the component selector
nested_struc-a = 2.
nested_struc-struct-b = 3.
nested_struc-struct-c = 'bbb'.

"Deep table
TYPES deep_itab_type LIKE TABLE OF nested_struc WITH EMPTY KEY.
DATA(deep_itab) = VALUE deep_itab_type( ( nested_struc ) "Adding an existing structure
                                        ( a = 3 struct = VALUE #( b = 3 c = 'ccc' ) )
                                        ( a = 4 struct = VALUE #( b = 4 c = 'ddd' ) ) ).

"-------------- Additions to VALUE constructor expressions --------------
"Note: LET and FOR expressions can be added to VALUE constructor expressions.
"Find more information further down.

"-------------- BASE addition --------------

"A constructor expression without the BASE addition initializes the target variable.
"Therefore, you can use the addition if you do not want to construct a structure or
"internal table from scratch but keep existing content.

"Populating a structure
struc = VALUE #( a = 1 b = 'aaa' ).

"struc is not initialized, only component b is modified, value of a is kept
struc = VALUE #( BASE struc b = 'bbb' ).

"Populating an internal table
itab = VALUE #( ( a = 1 b = 'aaa' )
                ( a = 2 b = 'bbb' ) ).

"Two more lines are added, existing content is preserved, the internal table is not
"initialized
itab = VALUE #( BASE itab
                ( a = 3 b = 'ccc' )
                ( a = 4 b = 'ddd' ) ).

"-------------- LINES OF addition -------------

"All or some lines of another table can be included in the target internal table
"(provided that they have appropriate line types).
"With the LINES OF addition, more additions can be specified.

DATA(itab5) = itab.
DATA(itab6) = itab.
itab = VALUE #( ( a = 1 b = 'aaa' )
                ( a = 2 b = 'bbb' )
                ( LINES OF itab5 )                 "All lines of itab5
                ( LINES OF itab6 FROM 2 TO 4 ) ).  "Specific lines of itab6

itab = VALUE #( ( LINES OF itab5 STEP 2 ) "Adding every second line
                ( LINES OF itab6 USING KEY primary_key ) ). "Specifying a table key


"-------------- Short form for internal tables with structured line types --------------
"- Assignments of values to individual structure components are possible outside of inner
"  parentheses
"- In that case, all of the following components in the inner parentheses are assigned that
"  value.
"- The assignment is made up to the next explicit assignment for the corresponding component.

TYPES: BEGIN OF structype,
            a TYPE i,
            b TYPE c LENGTH 3,
            c TYPE string,
        END OF structype.
TYPES tabtype TYPE TABLE OF structype WITH EMPTY KEY.

DATA(itab7) = VALUE tabtype( b = 'aaa'           ( a = 1 c = `xxx` )
                                                 ( a = 2 c = `yyy` )
                             b = 'bbb' c = `zzz` ( a = 3 )
                                                 ( a = 4 ) ).

*A    B      C
*1    aaa    xxx
*2    aaa    yyy
*3    bbb    zzz
*4    bbb    zzz

"This option can be handy in various contexts, for example, in a
"ranges table.
TYPES int_tab_type TYPE TABLE OF i WITH EMPTY KEY.
"Populating an integer table with values from 1 to 20 (see iteration
"expressions with FOR further down)
DATA(inttab) = VALUE int_tab_type( FOR x = 1 WHILE x <= 20 ( x ) ).

DATA rangetab TYPE RANGE OF i.

"Populating a range table using VALUE and the short form
rangetab = VALUE #( sign   = 'I'
                    option = 'BT' ( low = 1  high = 3 )
                                  ( low = 6  high = 8 )
                                  ( low = 12 high = 15 )
                    option = 'GE' ( low = 18 ) ).

"Using a SELECT statement to retrieve internal table content
"based on the range table specifications
SELECT * FROM @inttab AS tab
    WHERE table_line IN @rangetab
    INTO TABLE @DATA(result).
"result: 1, 2, 3, 6, 7, 8, 12, 13, 14, 15, 18, 19, 20

"The following EML statement creates RAP BO instances. The BDEF derived
"type is created inline. With the CREATE FROM addition, the %control values
"must be specified explicitly. You can provide the corresponding values
"for all table lines using the short form instead of individually
"specifying the values for each instance.
MODIFY ENTITIES OF zdemo_abap_rap_ro_m
    ENTITY root
    CREATE FROM VALUE #(
        %control-key_field = if_abap_behv=>mk-on
        %control-field1    = if_abap_behv=>mk-on
        %control-field2    = if_abap_behv=>mk-on
        %control-field3    = if_abap_behv=>mk-on
        %control-field4    = if_abap_behv=>mk-off
        ( %cid      = 'cid1'
          key_field = 1
          field1    = 'aaa'
          field2    = 'bbb'
          field3    = 10
          field4    = 100 )
        ( %cid      = 'cid2'
          key_field = 2
          field1    = 'ccc'
          field2    = 'ddd'
          field3    = 20
          field4    = 200 ) )
    MAPPED DATA(m)
    FAILED DATA(f)
    REPORTED DATA(r).
```

Using the inline construction of structures and internal tables, you can
avoid the declaration of extra variables in many contexts, for example,
ABAP statements like
[`MODIFY`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmodify_itab.htm)
for modifying internal tables or [ABAP
SQL](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenabap_sql_glosry.htm "Glossary Entry")
statements like
[`MODIFY`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmodify_dbtab.htm)
(which is not to be confused with the ABAP statement having the same
name) for modifying database tables.

Examples:
``` abap
"ABAP statements
"Modifiying individual internal table entries based on a structure created inline

"Modifying a table line
MODIFY TABLE some_itab FROM VALUE #( a = 1 ... ).

"Inserting a table line
INSERT VALUE #( a = 2 ... ) INTO TABLE some_itab.

"Deleting a table line
DELETE TABLE some_itab FROM VALUE #( a = 3 ).

"ABAP SQL statement
"Modifying multiple database table entries based on an internal table
"constructed inline within a host expression
MODIFY zdemo_abap_carr FROM TABLE @( VALUE #(
            ( carrid = 'XY'
              carrname = 'XY Airlines'
              currcode = 'USD'
              url =  'some_url' )
            ( carrid = 'ZZ'
              carrname = 'ZZ Airways'
              currcode = 'EUR'
              url =  'another_url' ) ) ).
```

> **💡 Note**<br>
> Some of the additions and concepts mentioned here are
also valid for other constructor expressions further down but not
necessarily mentioned explicitly. See the details on the syntax
options of the constructor operators in the ABAP Keyword Documentation.

<p align="right"><a href="#top">⬆️ back to top</a></p>

## CORRESPONDING

-   Expressions with the
    [`CORRESPONDING`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expr_corresponding.htm)
    operator construct structures and internal tables based on a data
    type (i. e. a [table
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abentable_type_glosry.htm "Glossary Entry")
    or [structured
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenstructured_type_glosry.htm "Glossary Entry")).
-   The components or columns of the target data object are populated using
    assignments of the parameters specified within the parentheses.
-   The assignments are made using identical names or based on [mapping
    relationships](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abencorresponding_constr_mapping.htm)
-   Note: Pay attention to the [assignment and conversion
    rules](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconversion_rules.htm)
    to avoid errors when using the operator. Consider, for example, the
    impact of assigning the values of identically named fields having
    different types (e. g. one field is of type `c` and another
    field is of type `string`).

The following table includes a selection of various possible additions to
this operator. There are more variants available (also 
[RAP](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenrap_glosry.htm "Glossary Entry")-specific ones)
that are not covered. Find more information in [this
topic](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expr_corresponding.htm) of the ABAP Keyword Documentation.

| Addition  | Details |
|---|---|
| `BASE` | Keeps original values. Unlike, for example, the operator `VALUE`, a pair of parentheses must be set around `BASE`.  |
| `MAPPING`  | Enables the mapping of component names, i. e. a component of a source structure or source table can be assigned to a differently named component of a target structure or target table (e. g. `MAPPING c1 = c2`).  |
| `EXCEPT`  | You can specify components that should not be assigned content in the target data object. They remain initial. In doing so, you exclude identically named components in the source and target object that are not compatible or convertible from the assignment to avoid syntax errors or runtime errors.  |
| `DISCARDING DUPLICATES`  | Relevant for tabular components. Handles duplicate lines and prevents exceptions when dealing with internal tables that have a unique primary or secondary table key. |
| `DEEP`  | Relevant for deep tabular components. They are resolved at every hierarchy level and identically named components are assigned line by line.  |
| `[DEEP] APPENDING`  | Relevant for (deep) tabular components. It ensures that the nested target tables are not deleted. The effect without `DEEP` is that lines of the nested source table are added using `CORRESPONDING` without addition. The effect with `DEEP` is that lines of the nested source table are added using `CORRESPONDING` with the addition `DEEP`.  |

Examples:
``` abap
"-------------- Patterns -------------

"The following examples demonstrate simple assignments
"with the CORRESPONDING operator using these syntax patterns.
"Note: 
"- The examples show only a selection of possible additions.
"- There are various combinations of additions possible.
"- The effect of the statements is shown in lines commented out.

"... CORRESPONDING #( z ) ...
"... CORRESPONDING #( BASE ( x ) z ) ...
"... CORRESPONDING #( z MAPPING a = b ) ...
"... CORRESPONDING #( z EXCEPT b ) ...
"... CORRESPONDING #( it DISCARDING DUPLICATES ) ...

"-------------- Structures -------------

"Data objects to work with in the examples
"Two different structures; one component differs.
DATA: BEGIN OF s1,
        a TYPE i,
        b TYPE c LENGTH 3,
        c TYPE c LENGTH 5,
      END OF s1.

DATA: BEGIN OF s2,
        a TYPE i,
        b TYPE c LENGTH 3,
        d TYPE string,
      END OF s2.

"Populating structures
s1 = VALUE #( a = 1 b = 'aaa' c = 'bbbbb' ).
s2 = VALUE #( a = 2 b = 'ccc' d = `dddd` ).

"Non-identical components in the target are initialized
s2 = CORRESPONDING #( s1 ).

*A    B      D
*1    aaa

"Populating structure for the BASE example
s2 = VALUE #( a = 3 b = 'eee' d = `ffff` ).

"BASE addition: Retaining original content in target, no initialization
s2 = CORRESPONDING #( BASE ( s2 ) s1 ).

*A    B      D
*1    aaa    ffff

"MAPPING addition: Mapping of component names
"For the assignment to work, note data convertibility.
s2 = CORRESPONDING #( s1 MAPPING d = c ).

*A    B      D
*1    aaa    bbbbb

"EXCEPT addition: Excluding components
s2 = CORRESPONDING #( s1 EXCEPT b ).

*A    B      D
*1

"As noted, there are various combinations possible for the additions.
"The following example shows MAPPING and EXCEPT.
s2 = CORRESPONDING #( s1 MAPPING d = c EXCEPT b ).

*A    B      D
*1           bbbbb

"Specifying an asterisk (*) after EXCEPT in combination with specifying mappings
"means that all non-specified components after MAPPING remain initial in the target
s2 = CORRESPONDING #( s1 MAPPING d = c EXCEPT * ).

*A    B      D
*0           bbbbb

"-------------- Internal tables -------------

"Internal tables to work with in the examples
DATA it1 LIKE TABLE OF s1 WITH EMPTY KEY.
DATA it2 LIKE SORTED TABLE OF s2 WITH UNIQUE KEY a.
DATA it3 LIKE TABLE OF s1 WITH EMPTY KEY.

"Populating internal tables
it1 = VALUE #( ( a = 1 b = 'aaa' c = 'bbbbb' )
                ( a = 2 b = 'ccc' c = 'ddddd' ) ).
it2 = VALUE #( ( a = 7 b = 'eee' d = 'fffff' ) ).
it3 = VALUE #( ( a = 3 b = 'eee' c = 'fffff' ) ).

it2 = CORRESPONDING #( it1 ).

*A    B      D
*1    aaa
*2    ccc

it2 = CORRESPONDING #( BASE ( it2 ) it3 ).

*A    B      D
*1    aaa
*2    ccc
*3    eee

it2 = CORRESPONDING #( it1 MAPPING d = c ).

*A    B      D
*1    aaa    bbbbb
*2    ccc    ddddd

it2 = CORRESPONDING #( it1 EXCEPT b ).

*A    B      D
*1
*2

"DISCARDING DUPLICATES: Handling duplicate lines and preventing exceptions
it1 = VALUE #( ( a = 4 b = 'aaa' c = 'bbbbb' )
               ( a = 4 b = 'ccc' c = 'ddddd' )
               ( a = 5 b = 'eee' c = 'fffff' ) ).

"Without the addition, the runtime error ITAB_DUPLICATE_KEY is raised.
it2 = CORRESPONDING #( it1 DISCARDING DUPLICATES ).

*A    B      D
*4    aaa
*5    eee
```

> **✔️ Hint**<br>
> `CORRESPONDING` operator versus
[`MOVE-CORRESPONDING`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmove-corresponding.htm) in the context of structures:
Although the functionality is the same, note that, as the name implies,
constructor operators construct and - without the addition
`BASE` - target objects are initialized. Hence, the following
two statements are  not the same:
>``` abap
>struc2 = CORRESPONDING #( struc1 ).
>
>"Not matching components are not initialized
>MOVE-CORRESPONDING struc1 TO struc2.
>```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## NEW

-   Using the instance operator
    [`NEW`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_new.htm),
    you can create [anonymous data
    objects](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenanonymous_data_object_glosry.htm "Glossary Entry")
    or
    [instances](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeninstance_glosry.htm "Glossary Entry")
    of a class and also assign values to the new object. As a result,
    you get a [reference
    variable](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenreference_variable_glosry.htm "Glossary Entry")
    that points to the created object. In doing so, the operator
    basically replaces [`CREATE DATA`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapcreate_data.htm)
    and [`CREATE OBJECT`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapcreate_object.htm).
-   For the type specification preceding the parentheses, you can use
    -   non-generic data types which creates a [data reference
        variable](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendata_reference_variable_glosry.htm "Glossary Entry")
        pointing to the anonymous data object.
    -   classes which creates objects of these classes. The result is an
        [object reference
        variable](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenobject_refer_variable_glosry.htm "Glossary Entry")
        pointing to an object.
-   Regarding the created object reference variables, you can use the
    [object component
    selector](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenobject_component_select_glosry.htm "Glossary Entry")
    `->` in certain contexts to ...
    -   point to a class attribute: `... NEW class( ... )->attr`
    -   introduce
        [standalone](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapcall_method_static_short.htm)
        and
        [functional](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapcall_method_functional.htm)
        method calls, including [chained method
        calls](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenchained_method_call_glosry.htm "Glossary Entry")
        which is a big advantage because you do not need to declare an
        extra variable: `... NEW class( ... )->meth( ... ) ...`
-   Regarding the type specifications before and parameters within the
    parentheses:
    -   No parameter specified within the parentheses: An anonymous data
        object retains its type-specific initial value. In case of
        classes, no parameter specification means that no values are
        passed to the instance constructor of an object. However, in
        case of mandatory [input
        parameters](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeninput_parameter_glosry.htm "Glossary Entry"),
        the parameters must be specified.
    -   Single parameter specified: If the type specified before the
        parentheses is a non-generic elementary, structured, table, or a
        reference type (or such a type can be derived using
        `#`), a single data object can be specified as an
        unnamed argument. Note the [assignment
        rules](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconversion_rules.htm)
        regarding the value assignments within the parentheses and that
        a constructor expression itself can be specified there.
    -   Structures and internal tables specified: If the type specified
        before the parentheses is a structured data type or `#`
        stands for it, you can specify the individual components as
        named arguments (`comp1 = 1 comp2 = 2 ...`; see more
        information
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abennew_constructor_params_struct.htm)).
        For the construction of anonymous internal tables, multiple
        options are available. Among them, there is the use of
        `LET` and `FOR` expressions and others. See more
        details
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abennew_constructor_params_itab.htm).
    -   Classes: As mentioned, non-optional input parameters of the
        instance constructor of the instantiated class must be filled.
        No parameters are passed for a class without an explicit
        instance constructor. See more information:
        [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abennew_constructor_params_class.htm).

The following examples cover: 
- Creating anonymous data objects
- Creating objects/instances of classes
  

``` abap
"-------------- Creating anonymous data objects -------------
"Note that optional additions (see for VALUE expressions) when dealing 
"with anonymous data objects (e.g. BASE). They are not covered here.

"Declaring data reference variables
DATA dref1 TYPE REF TO i.    "Complete type
DATA dref2 TYPE REF TO data. "Generic type

"In the following created anonymous data objects, no parameters are
"specified in the parentheses meaning the data objects retain their
"initial values.
dref1 = NEW #( ).
dref2 = NEW string( ).

"Such NEW expressions replace the older syntax CREATE DATA (however, in the 
"context of dynamic programming, using CREATE DATA is still required)
CREATE DATA dref1.
CREATE DATA dref2 TYPE string.

"Unlike above, the following examples specify values in the parentheses,
"this assigning single values.
dref1 = NEW #( 123 ).
dref2 = NEW string( `hallo` ).

"Using inline declarations to omit a prior declaration of a variable
"dref3 has the type TYPE REF TO i
DATA(dref3) = NEW i( 456 ).

"Creating an anonymous structure
"Components are assigned values.
DATA(dref4) = NEW zdemo_abap_carr( carrid = 'XY' carrname = 'XY Airlines' ).

"Creating an anonymous internal table
DATA dref5 TYPE REF TO string_table.
dref5 = NEW string_table( ( `c` ) ( `d` ) ).
DATA(dref6) = NEW string_table( VALUE #( ( `a` ) ( `b` ) ) ).

"-------------- Creating objects/instances of classes -------------

"Using a cheat sheet example class (the class does not implement constructors)
DATA oref1 TYPE REF TO zcl_demo_abap_objects.
DATA oref2 TYPE REF TO object.  "Generic type
"Creating an instance of a class
oref1 = NEW #( ).
oref2 = NEW zcl_demo_abap_objects( ).

"Such NEW expressions replace the older syntax CREATE OBJECT (however, in the 
"context of dynamic programming, using CREATE OBJECT is still required)
CREATE OBJECT oref1.
CREATE OBJECT oref2 TYPE zcl_demo_abap_objects.

"You can then, for example, use the object reference variable to access
"components such as attributes, or you can call methods (note: instance 
"and also static components can be addressed).
DATA(str) = oref1->public_string. "Static attribute
oref1->another_string = `Hello`.  "Instance attribute
oref1->string = `Hi`.             "Static attribute
oref1->hallo_instance_method( ).
oref1->hallo_static_method( ).

"Using inline declarations to create an object reference variable
"and an instance of a class
DATA(oref3) = NEW zcl_demo_abap_objects( ).
"Chainings are possible (the example accesses an instance attribute)
DATA(str2) = NEW zcl_demo_abap_objects( )->another_string.

"Example pattern for chainings
"... NEW some_class( ... )->meth( ... ) ...

"Chained attribute access
"... NEW some_class( ... )->attr ...

"Standalone method call with a NEW expression (in the case of the example 
"method, there is no parameter available)
NEW zcl_demo_abap_objects( )->hallo_instance_method( ).

"Assumption in the following examples: The classes have an instance constructor    
"Listing the parameter assignments for the constructor method
"If there is only one parameter, the explicit specification of the
"parameter name is not needed and the value can be specified directly.
DATA(oref4) = NEW cl_a( p1 = ... p2 = ... ).
"Assumption: Only one parameter (of type i)
DATA(oref5) = NEW cl_b( 123 ).
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## CONV

-   The
    [`CONV`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_conv.htm)
    operator enforces conversions from one type to another and creates
    an appropriate result.
-   Note that the conversion is carried out according to [conversion
    rules](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconversion_rules.htm).
    -   Further [special
        rules](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconv_constructor_inference.htm)
        apply if the constructor expression is passed to an [actual
        parameter](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenactual_parameter_glosry.htm "Glossary Entry")
        with a generically typed [formal
        parameter](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenformal_parameter_glosry.htm "Glossary Entry").
-   The operator is particularly suitable for avoiding the declaration
    of helper variables.

Examples:
``` abap
"Result: 0.2
DATA(conv_res) = CONV decfloat34( 1 / 5 ).

"Comparison with an expression without CONV
"The result is 0, the data type is i.
DATA(res) = 1 / 5.

"Example with internal table types
TYPES inttab_type TYPE TABLE OF i WITH EMPTY KEY.
DATA itab TYPE SORTED TABLE OF i WITH NON-UNIQUE DEFAULT KEY.
FIELD-SYMBOLS <fs> TYPE inttab_type.
itab = VALUE #( ( 1 ) ( 2 ) ( 3 ) ).

"The following assignment is not possible due to incompatible types. 
"The internal table has the same line type, but it has a different 
"table type and key.
"ASSIGN itab TO <fs>.

"Using CONV to convert the internal table to the required table type.
DATA(conv_itab) = CONV inttab_type( itab ).
ASSIGN conv_itab TO <fs>.
```

**Constructing data objects with the CONV operator**

As outlined above, you can construct structures and internal
tables using the `VALUE` operator. Using `VALUE` for
constructing [elementary data objects](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenelementary_data_object_glosry.htm "Glossary Entry") and providing values is not possible. You can only use it to create a data object with an initial value, for example `DATA(str) = VALUE string( ).`. The `CONV` operator closes this gap. 

``` abap
DATA(a) = CONV decfloat34( '0.4' ).

"Instead of
DATA b TYPE decfloat34 VALUE '0.4'.
"or
DATA c TYPE decfloat34.
c = '0.4'.

"Using the VALUE operator to construct elementary data objects 
"and provide values is not possible. 
"It is only possible to create an elementary data object with 
"an initial value. 
DATA(d) = VALUE string( ).
"This way it basically corresponds to a declaration as follows,
"which does not specify a start value with the addition VALUE.
DATA e TYPE string.

"Redundant conversion
"The variable derives the type (string) automatically from the 
"literal with the backquotes on the right-hand side.
DATA(f) = `hallo`.
"Produces a syntax warning
"DATA(g) = CONV string( `hallo` ).
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## EXACT

-   The
    [`EXACT`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_exact.htm)
    operator enforces either a [lossless
    assignment](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenlossless_move.htm)
    or a [lossless
    calculation](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenlossless_calculation.htm)
    depending on the data object specified within the parentheses and
    creates an appropriate result.
-   In case of calculations, [rules of lossless
    assignments](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmove_exact.htm)
    apply. In other cases, the result is created according to the
    [conversion
    rules](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconversion_rules.htm)
    mentioned above and an additional check is performed in accordance
    with the [rules of lossless
    assignments](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmove_exact.htm).

Examples:
``` abap
"-------------- Lossless assignments -------------

"Note: An assignment is made in accordance with conversion rules. Check
"the ABAP Keyword Documentation for these rules. An assignment is only 
"made if no values are lost. Otherwise, an error occurs. Either it is
"detected by static code checks or at runtime raising a catchable exception.
TYPES clen3 TYPE c LENGTH 3.
DATA(as1) = EXACT clen3( abap_true ).
DATA(as2) = EXACT clen3( 'XY' ).
"DATA(as3) = EXACT clen3( 'abcd' ).

"Catching exception
TRY.
    DATA(as4) = EXACT clen3( 'abcd' ).
    CATCH cx_sy_conversion_data_loss.
ENDTRY.

"-------------- Lossless calculations -------------

"The first statement works, whereas the second statement raises an exception.
"A rounding to two decimal places is required.
TYPES packednum TYPE p LENGTH 8 DECIMALS 2.
DATA(calc1) = EXACT packednum( 1 / 4 ).
"DATA(calc2) = EXACT packednum( 1 / 3 ).

"Catching exceptions when rounding in lossless calculations
TRY.
    DATA(calc3) = EXACT packednum( 1 / 3 ).
    CATCH cx_sy_conversion_rounding.
ENDTRY.
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## REF

-   The
    [`REF`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_ref.htm)
    operator creates a [data reference
    variable](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendata_reference_variable_glosry.htm "Glossary Entry")
    pointing to a specified data object.
-   The type specified after `REF` and directly before the first
    parenthesis determines the [static
    type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenstatic_type_glosry.htm "Glossary Entry")
    of the result.
-   The operator replaces [`GET REFERENCE`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapget_reference.htm), which should not be used anymore,
    and is particularly useful for avoiding the declaration of helper
    variables that are only necessary, for example, to specify data
    reference variables as actual parameters.
- The following can be specified after `REF` before the first parenthesis: A non-generic data type that satisfies the rules of [upcasts in data references](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconversion_references_data.htm), the generic type `data`, the `#` character if the type can be derived from the context.

Examples:
``` abap
"Data references
"Declaring data object and assign value
DATA num TYPE i VALUE 5.

"Declaring data reference variable
DATA dref_a TYPE REF TO i.

"Getting references
dref_a = REF #( num ).

"Inline declaration
DATA(dref_b) = REF #( `hallo` ).
"Inline declaration and explicit type specification
DATA(dref_c) = REF abap_bool( 'X' ).

"Specifying table expressions as arguments. The example code includes
"additions to avoid an exception if table lines are not found.
DATA int_tab TYPE TABLE OF i WITH EMPTY KEY.
int_tab = VALUE #( ( 1 ) ( 2 ) ( 3 ) ).
DATA(dref_d) = REF #( int_tab[ 2 ] ).
DATA(dref_e) = REF #( int_tab[ 6 ] OPTIONAL ). "Initial reference variable
DATA(dref_f) = REF #( int_tab[ 7 ] DEFAULT NEW #( 123 ) ). "Providing a default value

"Object references
DATA(oref_a) = NEW zcl_demo_abap_objects( ).
DATA(oref_b) = REF #( oref_a ).
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## CAST

-   Using the
    [`CAST`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_cast.htm)
    operator, you can carry out
    [upcasts](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenup_cast_glosry.htm "Glossary Entry")
    and
    [downcasts](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abendown_cast_glosry.htm "Glossary Entry")
    and create a reference variable of a static type as a result.
-   It replaces the
    [`?=`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapmove_cast.htm)
    operator and enables [chained method
    calls](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenchained_method_call_glosry.htm "Glossary Entry").
-   The operator is particularly helpful for avoiding the declaration of
    helper variables and more contexts.
-   Similar to the `NEW` operator, constructor expressions with
    `CAST` can be followed by the object component selector
    `->` to point to a class or interface attribute (`... CAST class( ... )->attr`) and methods (`... CAST class( ...
    )->meth( ... )`). Method chaining, standalone and
    functional method calls are possible, too. See more information
    [here](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_cast.htm).

Examples:
``` abap
"Performing casts on arguments and creating a reference variable that has the
"static type as specified as a result.

"Declaring data reference variables
DATA ref_i TYPE REF TO i.
DATA ref_gen TYPE REF TO data. "Generic type

"Creating an anonymous data object
ref_i = NEW #( 789 ).

"Upcast
"Static type of the target is less specific than or the same as the static
"type of the source
ref_gen = ref_i.
"The CAST operator can also be specified for upcasts. In this case, it can but
"need not be specified.
ref_gen = CAST #( ref_i ).

"Downcast
"Static type of the target is more specific than the static type of the source
"A check must be made at runtime before the assignment is done. If you indeed
"want to trigger such a downcast, you must do it explicitly in your code, for
"example, using the CAST operator (older operator: ?=).

"A syntax error occurs for the first statement. An explicit casting is required.
"ref_i = ref_gen.
ref_i = CAST #( ref_gen ).

"Like a data reference variable, the expressions can be followed by the
"dereferencing operator
ref_gen = NEW string( `hi` ).
CAST string( ref_gen )->* = `abap`.
DATA(str) = CAST string( ref_gen )->*.

"In case of static structured types, you can use the object component
"selector (->).
ref_gen = NEW zdemo_abap_carr( ).
CAST zdemo_abap_carr( ref_gen )->carrid = 'XY'.
DATA(comp) = CAST zdemo_abap_carr( ref_gen )->carrid.
"Dynamic specifications are possible.
CAST zdemo_abap_carr( ref_gen )->('CARRID') = 'ZZ'.
DATA(dyncomp) = |{ CAST zdemo_abap_carr( ref_gen )->('CARRID') }|.

"In the context of RTTS (see the cheat sheet about dynamic programming),
"helper variables are often required to perform a downcast of a type description
"object to a specialized class. The following examples, show how such helper
"variables can be reduced by using statements with CAST.
"Getting component information
DATA st TYPE zdemo_abap_carr.
DATA(components) = CAST cl_abap_structdescr(
    cl_abap_typedescr=>describe_by_data( st ) )->components.

"A constructor expression as above instead of, for example, using helper variables
"and the older ?= operator.
DATA ref_struc_type TYPE REF TO cl_abap_structdescr.
DATA comps TYPE abap_compdescr_tab.
ref_struc_type ?= cl_abap_typedescr=>describe_by_data( st ).
comps = ref_struc_type->components.

"Getting method information
DATA(methods) = CAST cl_abap_objectdescr(
    cl_abap_objectdescr=>describe_by_name( 'ZCL_DEMO_ABAP_OBJECTS' ) )->methods.
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## COND

-   The
    [`COND`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconditional_expression_cond.htm)
    operator is used for either creating a result depending on [logical
    expressions](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenlogical_expression_glosry.htm "Glossary Entry")
    or raising a [class-based
    exception](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenclass_based_exception_glosry.htm "Glossary Entry")
    (which is specified within the parentheses after the addition
    [`THROW`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconditional_expression_result.htm)).
-   There can be multiple logical expressions initiated by
    `WHEN` followed by the result specified after
    `THEN`. If none of the logical expressions are true, you can
    specify an `ELSE` clause at the end. If this clause is not
    specified, the result is the initial value of the specified or
    derived data type.
-   Note that all operands specified after `THEN` must be
    convertible to the specified or derived data type.

Example:
``` abap
DATA(day_or_night) = COND #( WHEN cl_abap_context_info=>get_system_time( ) BETWEEN '050000' AND '220000'
                             THEN `day`
                             ELSE `night` ).

"A constructor expression as above instead of, for example, an IF statement as follows.
IF cl_abap_context_info=>get_system_time( ) BETWEEN '050000' AND '220000'.
    day_or_night = `day`.
ELSE.
    day_or_night = `night`.
ENDIF.

"Multiple logical expressions initiated by WHEN
"Also LET expressions are possible. See more details further down.
DATA(time_of_day) = COND #( LET time = cl_abap_context_info=>get_system_time( ) IN
                            WHEN time BETWEEN '050001' AND '120000' THEN |Good morning, it's { time TIME = ISO }.|
                            WHEN time BETWEEN '120001' AND '180000' THEN |Good afternoon, it's { time TIME = ISO }.|
                            WHEN time BETWEEN '180001' AND '220000' THEN |Good evening, it's { time TIME = ISO }.|
                            ELSE |Good night, it's { time TIME = ISO }.| ).

"THROW addition to raise an exception (working like RAISE EXCEPTION TYPE statements)
"by specifying an exception class
"Note: It is possible to ...
"- specify the THROW addition also after THEN.
"- make exceptions resumable using the RESUMABLE addition.
DATA(num1) = 0.
DATA(num2) = 0.
TRY.
    "The example raises the exception because both operands have the value 0.
    DATA(div) = COND decfloat34( WHEN num1 <> 0 AND num2 <> 0 THEN num1 / num2
                                 WHEN num1 = 0  AND num2 <> 0 THEN num1 / num2
                                 ELSE THROW cx_sy_zerodivide( ) ).
   CATCH cx_sy_zerodivide.
    DATA(two_zeros) = `Zero division`.
ENDTRY.

"Excursion for the example above: The following statement does not result in an 
"error in ABAP (zero division 'allowed' if the first operand has also the value 0).
div = 0 / 0.

"THROW SHORTDUMP addition to raise a runtime error (working like RAISE SHORTDUMP
"TYPE statements) by specifying an exception class; a message can be also passed,
"and input parameters can be filled
div = COND decfloat34( WHEN num1 <> 0 AND num2 <> 0 THEN num1 / num2
                       WHEN num1 = 0  AND num2 <> 0 THEN num1 / num2
                       ELSE THROW SHORTDUMP cx_sy_zerodivide( ) ).
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## SWITCH

The
[`SWITCH`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconditional_expression_switch.htm)
operator is fairly similar to the `COND` operator and works in
the style of
[`CASE`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapcase.htm)
statements, i. e. it uses the value of only a single variable that is
checked in the case distinction.

``` abap
"The following example performs a calculation (no error handling implemented)
"if a valid operator is passed, and stores the result in a data object of
"type string.
"Note: Similar to the COND operator, the THROW addition is also possible
"for the SWITCH operator.
DATA(operator) = '*'.
DATA(num1) = 5.
DATA(num2) = 7.
DATA(calc_result) = SWITCH #( operator
                              WHEN '+' THEN |{ num1 + num2 STYLE = SIMPLE }|
                              WHEN '-' THEN |{ num1 - num2 STYLE = SIMPLE }|
                              WHEN '*' THEN |{ num1 * num2 STYLE = SIMPLE }|
                              WHEN '/' THEN |{ CONV decfloat34( num1 / num2 ) STYLE = SIMPLE }|
                              ELSE `Wrong operator.` ).

"A constructor expression as above instead of, for example, a CASE statement as follows.
CASE operator.
  WHEN '+'.
   calc_result = |{ num1 + num2 STYLE = SIMPLE }|.
  WHEN '-'.
   calc_result = |{ num1 - num2 STYLE = SIMPLE }|.
  WHEN '*'.
   calc_result = |{ num1 * num2 STYLE = SIMPLE }|.
  WHEN '/'.
   calc_result = |{ CONV decfloat34( num1 / num2 ) STYLE = SIMPLE }|.
  WHEN OTHERS.
   calc_result = `Wrong operator.`.
ENDCASE.
```

<p align="right"><a href="#top">⬆️ back to top</a></p>


## FILTER

-   The
    `FILTER` operator constructs an internal table according to a specified type (which can be an explicitly specified, non-generic table type or the # character as a symbol for the [operand type](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenoperand_type_glosry.htm) before the first parenthesis).
- The lines for the new internal table are taken from an
    existing internal table based on conditions specified in a `WHERE` clause. Note that the table type of the existing internal table must be convertible to the specified target type.
-   The conditions can either be based on single values or a [filter
    table](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expr_filter_table.htm).
- Additions:

|Addition |Details |
|---|---|
|`USING KEY`  | Specifies the [table key](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abentable_key_glosry.htm "Glossary Entry") with which the `WHERE` condition is evaluated: either a [sorted key](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abensorted_key_glosry.htm "Glossary Entry") or a [hash key](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenhash_key_glosry.htm "Glossary Entry"). If the internal table has neither of them, a [secondary table key](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abensecondary_table_key_glosry.htm "Glossary Entry") must be available for the internal table which must then be specified after `USING KEY`.  |
| `EXCEPT`   | The specification of `EXCEPT` means that those lines of the existing table are used that do not meet the condition specified in the `WHERE` clause. Hence, if `EXCEPT` is not specified, the lines of the existing table are used that meet the condition.  |


Examples:
```abap
"FILTER and conditions based on single values
"Assumption the component num is of type i.
DATA itab1 TYPE SORTED TABLE OF struc WITH NON-UNIQUE KEY num.
DATA itab2 TYPE STANDARD TABLE OF struc WITH NON-UNIQUE SORTED KEY sec_key COMPONENTS num.
DATA itab3 TYPE HASHED TABLE OF struc WITH UNIQUE KEY num.

"The lines meeting the condition are respected.
"Note: The source table must have at least one sorted or hashed key.
"Here, the primary key is used
DATA(f1) = FILTER #( itab1 WHERE num >= 3 ).

"USING KEY primary_key explicitly specified; same as above
DATA(f2) = FILTER #( itab1 USING KEY primary_key WHERE num >= 3 ).

"EXCEPT addition
DATA(f3) = FILTER #( itab1 EXCEPT WHERE num >= 3 ).
DATA(f4) = FILTER #( itab1 EXCEPT USING KEY primary_key WHERE num >= 3 ).

"Secondary table key specified after USING KEY
DATA(f5) = FILTER #( itab2 USING KEY sec_key WHERE num >= 4 ).
DATA(f6) = FILTER #( itab2 EXCEPT USING KEY sec_key WHERE num >= 3 ).

"Note: In case of a hash key, exactly one comparison expression for each key component is allowed;
"only = as comparison operator possible.
DATA(f7) = FILTER #( itab3 WHERE num = 3 ).

"Using a filter table
"In the WHERE condition, the columns of source and filter table are compared. Those lines in the source table
"are used for which at least one line in the filter table meets the condition. EXCEPT and USING KEY are also possible.

DATA filter_tab1 TYPE SORTED TABLE OF i
  WITH NON-UNIQUE KEY table_line.

DATA filter_tab2 TYPE STANDARD TABLE OF i
  WITH EMPTY KEY
  WITH UNIQUE SORTED KEY line COMPONENTS table_line.

DATA(f8) = FILTER #( itab1 IN filter_tab1 WHERE num = table_line ).

"EXCEPT addition
DATA(f9) = FILTER #( itab1 EXCEPT IN filter_tab1 WHERE num = table_line ).

"USING KEY is specified for the filter table
DATA(f10) = FILTER #( itab2 IN filter_tab2 USING KEY line WHERE num = table_line ).

"USING KEY is specified for the source table, including EXCEPT
DATA(f11) = FILTER #( itab2 USING KEY sec_key EXCEPT IN filter_tab2 WHERE num = table_line ).
```

<p align="right"><a href="#top">⬆️ back to top</a></p>


## LET Expressions

- Define one or more variables (field symbols are also possible) as local (i.e. local to the expression) helper fields and assigns values to them.
- In the definition, the right-hand side value is declared as if an inline declaration is used. The data type is derived accordingly. 
- Only to be used in constructor expressions (see the syntax diagrams in the ABAP Keyword Documentation where exactly [`LET`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abaplet.htm) expressions can be specified).

See the following simple examples to get an idea about the use:

```abap
"Data type and object to work with in the example
TYPES: BEGIN OF st_type,
            comp1 TYPE c LENGTH 5,
            comp2 TYPE i,
            comp3 TYPE i,
        END OF st_type.
DATA it TYPE TABLE OF st_type WITH EMPTY KEY.
it = VALUE #( ( comp1 = 'a' comp2 = 1 comp3 = 30 )
              ( comp1 = 'bb' comp2 = 2 comp3 = 10 )
              ( comp1 = 'ccc' comp2 = 3 comp3 = 20 ) ).

"Constructing a data object with elementary data type using the CONV operator
"One or more helper variables are possible specified after LET
DATA(hi) = CONV string(
        LET name = cl_abap_context_info=>get_user_technical_name( )
            date = cl_abap_context_info=>get_system_date( )
        IN |Hi { name }. Today's date is { date DATE = ISO }.| ).

"Construction similar to the previous example
"Depending on the time, a string is created. In the example, a LET expression
"is specified for each constructor expression.
DATA(time_of_day) = CONV string(
        LET time = cl_abap_context_info=>get_system_time( ) IN
        COND string( LET good = `Good` ending = `ing` IN
                    WHEN time BETWEEN '050001' AND '120000' THEN good && ` morn` && ending  "Good morning
                    WHEN time BETWEEN '120001' AND '180000' THEN good && ` afternoon`
                    WHEN time BETWEEN '180001' AND '220000' THEN good && ` even` && ending
                    ELSE good && ` night`  ) ).


"Getting a particular column name of an existing internal table using RTTI
"An internal table (it contains information on the table's structured type; the
"component names, among others) is assigned to a data object that is declared
"inline. This is an example of making code more concise with constructor expressions 
"and inline declarations. Assume you use extra declarations for the data objects, or 
"use the older ?= operator for the casts. Many more lines of code are required.
DATA(components) = CAST cl_abap_structdescr( CAST cl_abap_tabledescr(
    cl_abap_typedescr=>describe_by_data( it ) )->get_table_line_type( ) )->components.
DATA(comp2_a) = components[ 2 ]-name. "COMP2

"Achieving the result from above even in one statement using LET
DATA(comp2_b) = CONV abap_compname(
    LET comps = CAST cl_abap_structdescr( CAST cl_abap_tabledescr(
                 cl_abap_typedescr=>describe_by_data( it ) )->get_table_line_type( ) )->components
    IN comps[ 2 ]-name ).

"Constructing a structure using local variables
"The example uses the NEW operator to create an anonymous data object
DATA(new_struc) = NEW st_type( LET num = 2 ch = 'AP' IN
                                comp1 = 'AB' && ch comp2 = 2 * num comp3 = 3 * num ).
"Structure content:
"COMP1    COMP2    COMP3
"ABAP     4        6

"Constructing an internal table using local variables
"The example uses the VALUE operator.
"Note the parentheses ( ... ) representing table lines.
DATA(itab_value) = VALUE string_table( LET line = 1 IN
                                        ( |Line { line }| )
                                        ( |Line { line + 1 }| )
                                        ( |Line { line + 2 }| ) ).
"Table line content:
"Line 1
"Line 2
"Line 3

"Using a local field symbol in LET expressions
"- The right-hand side value must be the result of a writable expression, i.e.
"  an operand that can be written to
"- This value is then assigned to the local field symbol (as if ASSIGN is used)
"- In the examples above, a specification such as ... LET <a> = 1 IN ... is not
"  possible as they are not writable expressions.
"- Writable expressions:
"  - Constructor expressions NEW class( ... )->attr and CAST type( ... )->dobj
"  - Table expressions itab[ ... ] and their chainings, e.g. itab[ 1 ]-comp
"In the following example, an internal table is looped over. A string is created
"from the table line content. In the constructor expression, a LET expression is
"specified that uses a field symbol. It is assigned the line of the internal table.
"The sy-index value represents the table index value.
DATA str_tab TYPE string_table.
DO lines( it ) TIMES.
    DATA(concatenated_tab) = CONV string(
        LET <li>  = it[ sy-index ]
            comma =   `, `
        IN  |{ <li>-comp1 }{ comma }{ <li>-comp2 }{ comma }{ <li>-comp3 }| ).
    str_tab = VALUE #( BASE str_tab ( concatenated_tab ) ).
ENDDO.
"Table line content:
"a, 1, 30
"bb, 2, 10
"ccc, 3, 20
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## Iteration Expressions

- Iteration expressions are expressions ...
  - that perform an iteration and that are possible in specific constructor expressions (`NEW`, `VALUE`, `REDUCE`).
  - that are introduced by the iteration operator `FOR`. 
  - that can optionally be used to create lines in internal tables. 
- `REDUCE` operator: Special reduction operator that is based on [iteration expressions](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeniteration_expression_glosry.htm "Glossary Entry"), i.e. it is mandatory to specify iteration expressions with `FOR` when using `REDUCE`.

### Iteration Expressions Using FOR

- Two flavors for iterations using [`FOR`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenfor.htm):
  - [Conditional iterations](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenfor_conditional.htm)
    (including the ABAP words `UNTIL` and `WHILE` which
    have the semantics of ABAP statements
    [`DO`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapdo.htm)
    and
    [`WHILE`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abapwhile.htm))    
  - [Table iterations](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abentable_iteration_glosry.htm "Glossary Entry"): 
    Have the semantics of [`LOOP AT`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abaploop_at_itab_variants.htm) and 
    include the addition `IN`.
-   Where possible:
    - `REDUCE`: Mandatory `FOR` specification. The reduction result is created in the
       iteration steps. 
    - `NEW` and `VALUE`: Optional `FOR` specification. Used in the context of
        looping across internal tables. New table lines are created in
        the iteration steps and inserted into a target table.
-   The operand specified after `FOR` represents an iteration
    variable, i. e. a [work
    area](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenwork_area_glosry.htm "Glossary Entry")
    that contains the data while looping across the table.
-   This variable is only visible within the `FOR`
    expression, i. e. it cannot be used outside of the expression.
-   The type of the variable is determined by the type of the internal
    table specified after `IN`.
-   One or more iteration expressions can be specified using
    `FOR`.
-   The components or the whole table line that is to be returned are
    specified within the pair of parentheses before the closing
    parenthesis.
-   In contrast to `LOOP` statements, the sequential processing
    cannot be debugged.

```abap
"Data objects and types to work with in the examples
TYPES: BEGIN OF s,
            col1 TYPE c LENGTH 5,
            col2 TYPE i,
            col3 TYPE i,
        END OF s.
TYPES itab_type TYPE TABLE OF s WITH EMPTY KEY.
DATA(itab) = VALUE itab_type( ( col1 = 'a' col2 = 1 col3 = 30 )
                              ( col1 = 'bb' col2 = 2 col3 = 10 )
                              ( col1 = 'ccc' col2 = 3 col3 = 20 ) ).

"-------------- Table iterations --------------

DATA(it1) = VALUE itab_type( FOR wa IN itab ( col1 = wa-col1 && 'z'
                                              col2 = wa-col2 + 1 ) ).

"LOOP AT equivalent
CLEAR it1.
LOOP AT itab INTO DATA(wa_loop).
    APPEND VALUE #( col1 = wa_loop-col1 && 'z'
                    col2 = wa_loop-col2 + 1 ) TO it1.
ENDLOOP.

*COL1    COL2    COL3
*az      2       0
*bbz     3       0
*cccz    4       0

"The following example shows more syntax options
"- Field symbol specifed after FOR
"- LET expressions after FOR: Denotes that the LET
"  expressions is evaluated for each loop pass
"- INDEX INTO addition (the variable that follows implicitly
"  has the type i): Storing the sy-tabix value for each
"  loop pass
DATA(it2) = VALUE itab_type( FOR <line> IN itab INDEX INTO idx
                             LET idxplus1 = idx + 1 IN
                             ( col1 = <line>-col1 col2 = idx col3 = idxplus1 ) ).

*COL1    COL2    COL3
*a       1       2
*bb      2       3
*ccc     3       4

"Similar to the example above, the following example uses the INDEX INTO
"addition, as well as a LET expression with multiple local variables
DATA(it3) = VALUE string_table( FOR <str> IN itab INDEX INTO idx
                                LET col1            = |COL1: "{ <str>-col1 }"|
                                    col2            = |COL2: "{ <str>-col2 }"|
                                    col3            = |COL3: "{ <str>-col3 }"|
                                    str_to_be_added = |Table index { idx } -> { col1 } / { col2 } / { col3 }|
                                IN ( str_to_be_added ) ).

*Table index 1 -> COL1: "a" / COL2: "1" / COL3: "30"
*Table index 2 -> COL1: "bb" / COL2: "2" / COL3: "10"
*Table index 3 -> COL1: "ccc" / COL2: "3" / COL3: "20"

"---------- Excursions ----------

"FOR expression are very handy, for example, in EML and other statements.
"The following example commented out shows an EML statement in the implementation
"of a handler method taken from an EML cheat sheet example.
"'result' is an input parameter/internal table containing RAP BO instance data on whose
"basis an EML MODIFY statement is executed. A suitable internal table is constructed
"in place and that is used as operand of the MODIFY ... UPDATE FIELDS ... WITH ...
"statement.

"MODIFY ENTITIES OF zdemo_abap_rap_ro_u IN LOCAL MODE
"  ENTITY root
"  UPDATE FIELDS ( field3 field4 ) WITH VALUE #( FOR key IN result ( %tky   = key-%tky
"                                                                    field3 = key-field3 * 2
"                                                                    field4 = key-field4 * 2 ) ).

"Merging tables
"In the following example, the content of two existing internal tables is merged.
"In the simple example, the index is used for the table index. You can also imagine
"that you merge two internal tables, both having multiple columns. You could refer
"to the specific component values, for example, using a free key in a table expression
"such as ... VALUE #( some_itab[ comp_x = wa-comp_y ]-comp_z DEFAULT ... ) ...
TYPES int_tab_type TYPE TABLE OF i WITH EMPTY KEY.
DATA(inttab) = VALUE int_tab_type( ( 99 ) ( 100 ) ).

DATA(it4) = VALUE itab_type( FOR wa IN itab INDEX INTO idx
                             ( col1 = wa-col1 col2 = VALUE #( inttab[ idx ] DEFAULT 0 ) ) ).

*COL1    COL2    COL3
*a       99      0
*bb      100     0
*ccc     0       0

"Retaining non-specified column values using the BASE addition
"In the example, the original value of col3 is retained.
DATA(it5) = VALUE itab_type( FOR wa IN itab ( VALUE #( BASE wa col1 = wa-col1 && 'y'
                                                               col2 = wa-col2 + 3 ) ) ).

*COL1    COL2    COL3
*ay      4       30
*bby     5       10
*cccy    6       20

"Using the CORRESPONDING operator to handle different types
TYPES: BEGIN OF s2,
          col1 TYPE c LENGTH 5,
          col2 TYPE i,
          str  TYPE string,
       END OF s2.
TYPES itab_type_2 TYPE TABLE OF s2 WITH EMPTY KEY.

DATA(it6) = VALUE itab_type_2( FOR wa IN itab ( CORRESPONDING #( wa ) ) ).

*COL1    COL2    STR    
*a       1              
*bb      2              
*ccc     3              

"Multiple FOR expressions that work like nested loops
DATA(it7) = VALUE string_table( FOR wa1 IN itab
                                FOR wa2 IN inttab
                                ( |Comp. 1st itab: "{ wa1-col1 }", comp. 2nd itab: "{ wa2 }"| ) ).

*Comp. 1st itab: "a", comp. 2nd itab: "99"
*Comp. 1st itab: "a", comp. 2nd itab: "100"
*Comp. 1st itab: "bb", comp. 2nd itab: "99"
*Comp. 1st itab: "bb", comp. 2nd itab: "100"
*Comp. 1st itab: "ccc", comp. 2nd itab: "99"
*Comp. 1st itab: "ccc", comp. 2nd itab: "100"

"LOOP AT equivalent
CLEAR it7.
LOOP AT itab INTO DATA(wa3).
    LOOP AT inttab INTO DATA(wa4).
        it7 = VALUE #( BASE it7 ( |Comp. 1st itab: "{ wa3-col1 }", comp. 2nd itab: "{ wa4 }"| ) ).
    ENDLOOP.
ENDLOOP.

"More additions can be specified such as WHERE, USING KEY, FROM/TO, STEP 

"WHERE condition 
"The WHERE condition must be placed in parentheses.
DATA(it8) = VALUE itab_type( FOR wa IN itab WHERE ( col2 < 3 ) ( col1 = wa-col1 && 'w'
                                                                 col2 = 5
                                                                 col3 = wa-col2 ) ).
*COL1    COL2    COL3
*aw      5       1
*bbw     5       2

"FROM/TO additions
DATA(it9) = VALUE itab_type( FOR wa IN itab FROM 2 TO 3 ( col1 = wa-col1 && 'v'
                                                          col2 = 6
                                                          col3 = wa-col2 + 5   ) ).

*COL1    COL2    COL3
*bbv     6       7
*cccv    6       8

"STEP addition
DATA(it10) = VALUE itab_type( FOR wa IN itab STEP -1 ( col1 = wa-col1 && 'u'
                                                       col2 = 7
                                                       col3 = wa-col2 + 8 ) ).

*COL1    COL2    COL3
*cccu    7       11
*bbu     7       10
*au      7       9

"USING KEY addition
DATA(it11) = VALUE itab_type( FOR wa IN itab USING KEY primary_key ( col1 = wa-col1 && 't'
                                                                     col2 = 9
                                                                     col3 = wa-col2 + 10 ) ).
*COL1    COL2    COL3
*at      9       11
*bbt     9       12
*ccct    9       13

"---------- Conditional iterations ----------
"Notes:
"- When used with VALUE/NEW for internal tables: New table lines are created in
"  iteration steps and added to result
"- When used with REDUCE (as shown below): Reduction result is created in iteration steps
"- Regarding the THEN addition:
"  - Must be specified if the iteration variable specified after FOR is not a numeric data
"    type and not of type d/t
"  - If the iteration variable is a numeric type/type d or t, THEN is optional. If THEN
"    is not specified, the iteration variable is implicitly incremented by 1.

"FOR ... WHILE ...
"Implicit incrementing of the iteration variable
DATA(it12) = VALUE itab_type( FOR x = 1 WHILE x < 4
                              ( col1 = x col2 = x + 1 col3 = x + 2 ) ).

*COL1    COL2    COL3
*   1    2       3
*   2    3       4
*   3    4       5

"The following example corresponds to the previous one. Here, THEN
"is explicitly specified.
DATA(it13) = VALUE itab_type( FOR x = 1 THEN x + 1 WHILE x < 4
                              ( col1 = x col2 = x + 1 col3 = x + 2 ) ).

"THEN explicitly specified
DATA(it14) = VALUE itab_type( FOR x = 1 THEN x + 2 WHILE x < 8
                              ( col1 = x col2 = x + 1 col3 = x + 2 ) ).

*COL1    COL2    COL3
*   1    2       3
*   3    4       5
*   5    6       7
*   7    8       9

"THEN addition is required for non-numeric data types of the iteration
"variable
DATA(it15) = VALUE itab_type( FOR str = `x` THEN str && str WHILE strlen( str ) < 5
                              ( col1 = str col2 = strlen( str ) + 1 col3 = strlen( str ) + 2 ) ).

*COL1    COL2    COL3
*x       2       3
*xx      3       4
*xxxx    5       6

"FOR ... UNTIL ...
DATA(it16) = VALUE itab_type( FOR y = 10 UNTIL y > 12
                              ( col1 = y col2 = y + 1 col3 = y + 2 ) ).

*COL1    COL2    COL3
*  10    11      12
*  11    12      13
*  12    13      14

"THEN explicitly specified
DATA(it17) = VALUE itab_type( FOR y = 31 THEN y - 10 UNTIL y < 10
                              ( col1 = y col2 = y + 1 col3 = y + 2 ) ).

*COL1    COL2    COL3
*  31    32      33
*  21    22      23
*  11    12      13
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

### REDUCE

-   The
    [`REDUCE`](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abenconstructor_expression_reduce.htm)
    operator creates a result of a specified or derived type from one or
    more [iteration expressions](https://help.sap.com/doc/abapdocu_cp_index_htm/CLOUD/en-US/index.htm?file=abeniteration_expression_glosry.htm "Glossary Entry") with `FOR`.
-   As covered for `FOR`, conditional iterations (reducing sets of data objects to a single data object in custom iteration steps) and table iterations (evaluation of table lines, reducing the table content to summary value) are possible. For example, the numeric values of a table column are summed up. As a result, the total number is constructed. 
- Additions: 
  - Optional `LET` expressions (the following additions are mandatory)
  - `INIT ...`: A temporary variable (or field symbol) to specify an initial value for the result variable. At least, one variable/field symbol must be specified. The first specified determines the result of the expression (any others that are additionally specified can be used after `NEXT`).
  - `FOR ...`: Iteration expression as covered above.
  - `NEXT ...`: Represents the assignment to the temporary variable after every iteration. Once the loop has finished, the target variable is assigned the resulting value.


```abap
"Data objects and types to work with in the examples
TYPES: BEGIN OF s,
          col1 TYPE c LENGTH 5,
          col2 TYPE i,
          col3 TYPE i,
       END OF s.
TYPES itab_type TYPE TABLE OF s WITH EMPTY KEY.
DATA(itab) = VALUE itab_type( ( col1 = 'a' col2 = 1 col3 = 30 )
                              ( col1 = 'bb' col2 = 2 col3 = 10 )
                              ( col1 = 'ccc' col2 = 3 col3 = 20 ) ).

"---------- Table iterations ----------

"Calculating the sum of values in a table column
"Result: 6
DATA(sum_val) = REDUCE i( INIT len = 0
                          FOR <line> IN itab
                          NEXT len = len + <line>-col2 ).

"Getting the longest string in a table column
"Result: ccc
DATA(long_str) = REDUCE s-col1( INIT str = VALUE #( )
                                FOR <line> IN itab
                                NEXT str =  COND #( WHEN strlen( <line>-col1 ) > strlen( str )
                                                    THEN <line>-col1
                                                    ELSE str ) ).

"Getting the maximum value (other than, for example, using a SORT statement)
"Unlike above, a variable is used instead of a field symbol.
"Result: 3
DATA(max_val) = REDUCE i( INIT max = 0
                          FOR line IN itab
                          NEXT max =  COND #( WHEN line-col2 > max
                                              THEN line-col2
                                              ELSE max ) ).

"Creating a new internal table using REDUCE
"In the example, the sum of two values is calculated.
"A VALUE expression with the BASE addition is used to
"add a line to a table (retaining the existing lines).
DATA(itstr) = REDUCE string_table( INIT strtab = VALUE string_table( )
                                   FOR wa IN itab
                                   NEXT strtab = VALUE #( BASE strtab
                                    ( |The sum of { wa-col2 } and { wa-col3 } is { wa-col2 + wa-col3 }.| ) ) ).

*The sum of 1 and 30 is 31.
*The sum of 2 and 10 is 12.
*The sum of 3 and 20 is 23.

"More additions are possible, such as specifying a WHERE condition (which
"must be specified in parentheses). The following example creates a new
"internal table based on a WHERE condition.
TYPES: BEGIN OF s3,
          num1 TYPE i,
          num2 TYPE i,
          sum  TYPE i,
       END OF s3.
TYPES s3_tab_type TYPE TABLE OF s3 WITH EMPTY KEY.
DATA(itred) = REDUCE s3_tab_type( INIT tab = VALUE s3_tab_type( )
                                  FOR wa IN itab
                                  WHERE ( col2 < 3 )
                                  NEXT tab = VALUE #( BASE tab
                                   ( num1 = wa-col2 num2 = wa-col3 sum = wa-col2 + wa-col3 ) ) ).

*NUM1    NUM2    SUM
*1       30      31
*2       10      12

"---------- Conditional iterations ----------

"UNTIL addition
"Iteratively calculating the sum from 1 to 10
"Result: 55
DATA(reduce_until) = REDUCE i( INIT sum = 0
                               FOR  int = 1 UNTIL int > 10
                               NEXT sum += int ).

"WHILE addition
"The example corresponds to the previous one.
DATA(reduce_while) = REDUCE i( INIT sum = 0
                               FOR  int = 1 WHILE int <= 10
                               NEXT sum += int ).

"THEN addition
"The following example constructs a text string. The THEN addition is used
"to decrement the iteration variable. Additionally, a LET expression is used
"to specify a helper variable.
"Result: Counting downwards starting with 10: 10 9 8 7 6 5 4 3 2 1
DATA(count) = REDUCE string( LET start = 10 IN
                             INIT text = |Counting downwards starting with { start }:|
                             FOR n = start THEN n - 1 WHILE n > 0
                             NEXT text &&= | { n }| ).

"Example similar to the previous one. Using UNTIL, a text string is enlarged until
"it has reached a specific size.
"Result: ab abap abapap abapapap abapapapap abapapapapap abapapapapapap
DATA(abap_str) =  REDUCE string( INIT text = ``
                                 FOR t = `ab` THEN t && `ap` UNTIL strlen( t ) > 15
                                 NEXT text &&= |{ t } | ).

"---------- Excursion: Grouping lines in internal tables with VALUE/REDUCE ----------

"The following examples show equivalents of LOOP AT GROUP ... GROUP BY ... statements.
"Find more information and examples about grouping in the ABAP Keyword Documentation.

"Internal table to work with in the examples
DATA(itab4grp) = VALUE itab_type( ( col1 = 'a' col2 = 1 col3 = 2 )
                                  ( col1 = 'a' col2 = 3 col3 = 4 )
                                  ( col1 = 'a' col2 = 5 col3 = 6 )
                                  ( col1 = 'b' col2 = 7 col3 = 8 )
                                  ( col1 = 'b' col2 = 9 col3 = 10 )
                                  ( col1 = 'c' col2 = 11 col3 = 12 ) ).


"Constructing a result using VALUE
"The following example returns the values of identified groups in an internal table
"Table lines are evaluated by grouping all lines that meet the condition
"specified in GROUP BY (group key binding). The group key is stored in the variable
"after FOR GROUPS (gr). The constructed result just consists of the group keys in
"the example. The content of the members is not relevant.
DATA(it_val_1) = VALUE string_table( FOR GROUPS gr OF wa IN itab4grp
                                     GROUP BY wa-col1 ASCENDING
                                     WITHOUT MEMBERS
                                     ( |{ gr }| ) ).

*a
*b
*c

"As above, the following example returns the values of identified groups in an internal table.
"Additionally, a LET expression (that itself contains an iteration expression) is specified
"to collect column values by group in an internal table. The lines of this (string) table
"are concatenated and inserted in the target table.
DATA(it_val_2) = VALUE string_table(
    FOR GROUPS grp OF wa IN itab4grp
    GROUP BY wa-col1 ASCENDING
    LET members = VALUE string_table(
    FOR grpd IN GROUP grp ( |{ grpd-col2 }, { grpd-col3 }| ) ) IN
    ( |{ grp }: { concat_lines_of( table = members sep = ` / ` ) }| ) ).

*a: 1, 2 / 3, 4 / 5, 6
*b: 7, 8 / 9, 10
*c: 11, 12

"Constructing a result using REDUCE
"The example is similar to the previous one by filling a string table.
"The example uses a group key expression specified after GROUP BY.
"In the group key expression, additional components of a structured
"group key are specified which return specific information (group size,
"group index).
DATA(it_reduced) = REDUCE string_table(
    INIT li = VALUE string_table( )
    FOR GROUPS group OF grt IN itab4grp
    GROUP BY ( grpkey = grt-col1
                size = GROUP SIZE
                index = GROUP INDEX ) ASCENDING
    LET mem = VALUE string_table( FOR grpr IN GROUP group ( |{ grpr-col2 }, { grpr-col3 }| ) ) IN
    NEXT li = VALUE string_table( BASE li ( |Group key: "{ group-grpkey }" \| | &&
                                            |group size: {  group-size  } \| | &&
                                            |group index: { group-index } \| members: | &&
                                            |{ concat_lines_of( table = mem sep = ` / ` ) }| ) ) ).

*Group key: "a" | group size: 3 | group index: 1 | members: 1, 2 / 3, 4 / 5, 6
*Group key: "b" | group size: 2 | group index: 2 | members: 7, 8 / 9, 10
*Group key: "c" | group size: 1 | group index: 3 | members: 11, 12
```

<p align="right"><a href="#top">⬆️ back to top</a></p>

## Executable Example

[zcl_demo_abap_constructor_expr](./src/zcl_demo_abap_constructor_expr.clas.abap)

> **💡 Note**<br>
> - The steps to import and run the code are outlined [here](README.md#-getting-started-with-the-examples).
> - [Disclaimer](README.md#%EF%B8%8F-disclaimer)
