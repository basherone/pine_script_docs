.. image:: /images/Pine_Script_logo.svg
   :alt: Pine Script™ logo
   :target: https://www.tradingview.com/pine-script-docs/en/v5/Introduction.html
   :align: right
   :width: 100
   :height: 100


.. _PagePineGrammar:


Pine Script™ v5 grammar
=======================

.. contents:: :local:
    :depth: 3



Introduction
------------

This page contains a formal definition of the grammar of Pine Script™. 
A programming language's grammar expresses how language keywords, special characters and literal values can be combined to form valid programs.



Conventions
-----------

- ``{}`` Curly braces content can be repeated zero or more times: {, <parameter>}
- ``[]`` Square brackets content can appear zero or one time: [ by <expression>]
- ``()`` Parentheses group syntactic elements
- ``\``  Backslash escapes one character: ``\[`` means a literal ``[`` in the syntax.
- ``|``  Pipe means "or".
- Token names (non-terminal symbols) use uppercase: ``TOKEN_NAME``.
- Lowercase is used for language keywords.




Grammar
-------

::

    PINE_INDICATOR
        [VERSION]
        DECLARATION_STATEMENT
        {STATEMENT{,STATEMENT}}
        DISPLAY_STATEMENT

    PINE_STRATEGY
        [VERSION]
        DECLARATION_STATEMENT
        {STATEMENT{,STATEMENT}}
        STRATEGY_STATEMENT

    PINE_LIBRARY
        [VERSION]
        DECLARATION_STATEMENT
        {STATEMENT{,STATEMENT}}

    VERSION
        //@version = (1 | 2 | 3 | 4 | 5)

    DECLARATION_STATEMENT
        indicator() | strategy() | library()

    STATEMENT
        <variable_declaration> | <variable_reassignment> | <function_declaration> | <function_call> | <structure>

    DISPLAY_STATEMENT
        plot() | plotcandle() | plotbar() | plotchar() | plotarrow() | label.new() | line.new() | table.cell() | alertcondition()

    <variable_initialization>
        <variable_declaration> = <expression> | <structure>

    <variable_declaration>
        [<declaration_mode>] [<type>] <identifier>
        |
        <tuple_declaration>

    <declaration_mode>
        [var | varip]

    <type>
        [int  | float   | bool   | color   | string   | label   | line   | box   | table |
        int[] | float[] | bool[] | color[] | string[] | label[] | line[] | box[] | table[]]

    <variable_reassignment>
        <identifier> := <expression> | <function_call> | <structure>

    <function_declaration>
        <identifier>(<parameter_list>) => 
            <local_block>
        |
        <identifier>(<parameter_list>) => <return_value>

    <parameter_list>
        {<parameter_definition>{, <parameter_definition>}}

    <parameter_definition>
        [<identifier> = <default_value>]

    <structure>
        <if_structure> | <for_structure> | <while_structure> | <switch_structure>

    <if_structure>
        if <expression>
            <local_block>
        {else if <expression>
            <local_block>}
        [else
            <local_block>]

    <for_structure>
        for <identifier> = <expression> to <expression>[ by <expression>]
            <local_block_loop>

    <for_structure>
        for <identifier> = <expression> to <expression>[ by <expression>]
            <local_block_loop>

    <while_structure>
        while <expression>
            <local_block_loop>

    <local_block_loop>
        {<statement> | break | continue}
        <return_value>

    <switch_structure>
        <switch_structure_expression> | <switch_structure_values>

    <switch_structure_expression>
        switch <expression>
            {<expression> => <local_block>}
            => <local_block>

    <switch_structure_values>
        switch
            {<expression> => <local_block>}
            => <local_block>

    <local_block>
        {<statement>}
        <return_value>

    <return_value>
        <statement> | <expression> | <tuple>

    <tuple_declaration>
        \[<identifier>{, <identifier>}\]

    <tuple>
        \[<expression>{, <expression>]\]

    <expression>
        <literal> | <identifier> | <function_call> | 
        <arithmetic_expression> | <comparison_expression> | <logical_expression>

    <function_call>
        functionName({<expression>{, <expression>}})

    <arithmetic_expression>


    <comparison_expression>


    <logical_expression>


    <ternary_expression>


    <identifier>
        <letter> | <underscore> {<letter><underscore><digit>}

    <arithmetic_operators>::
        + | - | * | / | %

    <comparison_operators>::
        < | <= | != | == | > | >=

    <logical_operators>::
        not | and | or

    <literal>
        <literal_int> | <literal_float> | <literal_bool> | <literal_color> | <literal_string>

    <literal_int>
        [- | +]<digit>{<digit>}

    <literal_float>
        [- | +]<digit>{<digit>}[.][E|e<digit>{<digit>}]

    <literal_bool>
        true | false | bool(na)

    <literal_color>
        #RRGGBB | #RRGGBBAA | <built-in_color_constant>

    <literal_string>
        "<characters>" | '<characters>'


.. image:: /images/TradingView-Logo-Block.svg
    :width: 200px
    :align: center
    :target: https://www.tradingview.com/