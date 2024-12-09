## HubSpot CMS Development Command Document

<-- CMS Development -->


09-12-2024<br>
Basic setting in CMS in HubSpot are below

Setting -> Tools -> Content -> Pages (Template/Branding/personalzation/intergration/SEO & Crawlers/System Pages)
Setting -> Tools -> Blogs ->
Setting -> Tools -> Marketing -> Email 
Setting -> Tools -> Content -> Domaings & URLs
Setting -> Account Management -> Users & Team

Two Built-in Navigation options

* Menu module
* Simple Menu module


Setting -> Tools -> Navigation menus


HubL is a markUp Language which use some parts jija

## Fundamental of HubL
Statements sytax - {% set my_variable = "Example of Statements Systax"%}

{% set my_variable = "I'm a string!"%} 
String, int, Boolean

Expression Sytax -> {{ an_expression_evaluates_to_a_value_}}

{{my_variable}}

Comments Sytax -> {# Comments Aren't Rendered Client Side#} 

{#OUTPUT: I'm a String!#}




List:  Creating a list and retriving the first value 
{% set my_list =["String1, "String2", "String3"] %} //List Statement
{{my_list[0]}} //List Expression
{#OUTPUT: String 1#} /List Comments




Dictionary: Creating a dictionary and retrieving a value


{% set my_dictionary ={"name":"Varghese" "age":26, "eye_color":"blue"} %} //DictionaryStatement
{{my_dictionary.eye_color}} //Dictionary Expression. Dictionary items accessed through dot eye_color
{#OUTPUT: blue#} /Dictionary Comments




Creating and calling macro
{% macro add_numbers(n1, n2)%}
{{n1+n2}}
{%end macro%}
{{add_numbers(4,5)}}
{#Output: 9#}






Conditional Statements 	and Expression tests

{%set friends =['Serah','Benia','Evan']%}
{%if friends is iterable%}
<p>My friends are {{friends|join(', ')}}</p>
{%else %}
 <p>My Friends is {{friends}}</p>
 {% endif %}
 
 {#OUTPUT: My Friends are Serah, Benia, Evan #}
 
 
 
 Loops with properties and filters
 
 {%set numbers =['one', 'two', 'three']%}
 {% for number in numbers|reverse %}
 <p>Loop index:{{loop.index}} number:{{ number}}</p>
 {% endfor %}
 
 {#
 OUTPUT:
 Loop index:1 number:3
 Loop index:2 number:2
 Loop index:3 number:1
 #}
 
 
 
 
 
 ## Module markup in coded templates
 
 Two flavors of syntax
 
 * Basic module systax {% text "movie_name" Label="move_name", value="Citizen kane" %}
 * Block sytax
 
 
 
 
 
 
 ## HubL Filters
 
 Length Filter
 {% set mySeq =['thing1', 'thing2', 'thing3']%}
 {{mySeq|length}}
 {#OUTPUT: 3#}
 
 
 reject attribute
 {% set unreadBooks = myBooks|rejectattr('read')%}
 
 ShortHand application of reject attribute
 {% for book in myBooks|rejectattr('read') %}
 
 
 pretty print filters (Debuggin)
 {{ site_setting|pprint}}
 
 
 
 
 
 {% macro rem(values) %}
  {% set baselineFontSize =16 %}
     {% set remValue = value/baselineFontSize %}
{{ remValue }}rem

{% endmacro %}



{% macro rem(values) %}
  {% set baselineFontSize =16 %}
  {% set cssValues =[] %}
  {% for v in values %}
{% set thisVal = v/baselineFontSize~'rem' %}
 {% do cssValue.append(thisVal) %}
{% endfor %}
{{ cssValues|join(', ')}}
{% endmacro %}

<------------------------------------------------------------------------------------------->

-> Create a Folder in Desktop Open in VSCode
-> VSCode Terminal enter the 
S C:\Users\u\Desktop\LOCAL-DEV-DEMO> npm install @hubspot/cli

->S C:\Users\u\Desktop\LOCAL-DEV-DEMO> npx hs init


## Create Yml file and load node_module 

PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> npx hs init  
(node:6576) ExperimentalWarning: CommonJS module C:\Users\u\AppData\Roaming\npm\node_modules\npm\node_modules\debug\src\node.js is loading ES Module 
C:\Users\u\AppData\Roaming\npm\node_modules\npm\node_modules\supports-color\index.js using require().
Support for loading ES Module in require() is an experimental feature and might change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
(node:4532) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
--------------------------------------------------
HubSpot Personal Access Key Setup

A personal access key is required to authenticate the CLI to interact with your HubSpot account. We'll open a secure page in your default browser where you can view and copy your personal access key.

--------------------------------------------------
? Open hubspot.com to copy your personal access key? Yes
Opening https://app.hubspot.com/l/personal-access-key in your web browser
? Enter your personal access key:  ***********************************************************************************************************
? Enter a unique name to reference this account in the CLI: demo

[SUCCESS] Created config file "C:\Users\u\Desktop\LOCAL-DEV-DEMO/hubspot.config.yml"
[SUCCESS] Connected account "demo" using "Personal Access Key" and set it as the default account



## test-theme will created below is command

PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> npx @hubspot/create-cms-project test-theme 
(node:5708) ExperimentalWarning: CommonJS module C:\Users\u\AppData\Roaming\npm\node_modules\npm\node_modules\debug\src\node.js is loading ES Module 
C:\Users\u\AppData\Roaming\npm\node_modules\npm\node_modules\supports-color\index.js using require().
Support for loading ES Module in require() is an experimental feature and might change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
Need to install the following packages:
@hubspot/create-cms-project@2.2.3
Ok to proceed? (y) y

'yarn' is not recognized as an internal or external command,
operable program or batch file.
Cloning repo with HTTPS...
Clone completed
Installing deps...
...installing with `npm`...
Deps installed
Success: your new HubSpot/cms-theme-boilerplate project has been created in C:\Users\u\Desktop\LOCAL-DEV-DEMO\test-theme.


## How to upload image in hubspot account or sandBox Accunt
 
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> npx hs upload test-theme/src test-theme

installed test-theme in my HubSpot Accout path   Content->Design Manager  ##test-theme uploaded what ever in Vscode i can see in Hubspot Account


content->Website Pages ## Read made pages available


https://app.hubspot.com/design-manager/48440318/?tfid=183598018164 // Acces key path





-----------------------------------------------------------------------------------------------
## Install npm/node.js/uuid

## Latest version npm installed 

PS C:\Users\u> npm install glob@latest --save

added 40 packages in 31s

13 packages are looking for funding
  run `npm fund` for details
PS C:\Users\u> npm install glob@latest --save

up to date, audited 41 packages in 4s

13 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities


## Latest version npm uuid@ installed 

PS C:\Users\u> npm install uuid@latest --save

added 1 package, and audited 42 packages in 5s

14 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities


## Check for other dependencies Outdated:
PS C:\Users\u> npm outdated


## Check for other dependencies & Updated:
PS C:\Users\u> npm update

up to date, audited 42 packages in 2s

14 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities


## Node Latest Version

PS C:\Users\u> winget install --id OpenJS.Nodejs --source winget
Found an existing package already installed. Trying to upgrade the installed package...
Found Node.js [OpenJS.NodeJS] Version 23.3.0
This application is licensed to you by its owner.
Microsoft is not responsible for, nor does it grant any licenses to, third-party packages.
Downloading https://nodejs.org/dist/v23.3.0/node-v23.3.0-x64.msi
  ██████████████████████████████  29.8 MB / 29.8 MB
Successfully verified installer hash
Starting package install...
The installer will request to run as administrator, expect a prompt.
Successfully installed
PS C:\Users\u> node --version
v23.3.0
