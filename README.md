## HubSpot CMS Development Command Document

<-- CMS Development -->

## 11-12-2024

## Create a Module in HubSpot (Building Hubspot CMS Modules)

module.html (Hubl + HTML)
<div class="two-col-feature {{ module.choice_field }}">
  <div class="col text">

{% inline_rich_text field="feature_text" value="{{ module.feature_text }}" %}
  </div>
  
  <div class="col image">
    {% if module.feature_image.src %}
	{% set sizeAttrs = 'width="{{ module.feature_image.width|escape_attr }}" height="{{ module.feature_image.height|escape_attr }}"' %}
	{% if module.feature_image.size_type == 'auto' %}
		{% set sizeAttrs = 'width="{{ module.feature_image.width|escape_attr }}" height="{{ module.feature_image.height|escape_attr }}" style="max-width: 100%; height: auto;"' %}
	{% elif module.feature_image.size_type == 'auto_custom_max' %}
		{% set sizeAttrs = 'width="{{ module.feature_image.max_width|escape_attr }}" height="{{ module.feature_image.max_height|escape_attr }}" style="max-width: 100%; height: auto;"' %}
	{% endif %}
	 {% set loadingAttr = module.feature_image.loading != 'disabled' ? 'loading="{{ module.feature_image.loading|escape_attr }}"' : '' %}
	<img src="{{ module.feature_image.src|escape_url }}" alt="{{ module.feature_image.alt|escape_attr }}" {{ loadingAttr }} {{ sizeAttrs }}>
{% endif %}
    
  </div>
</div>


## Module.css
.two-col-feature{
  display: flex;
}
.two-col-featue.img-left{
  flex-direction: row-reverse;
}

Note: this two feature rich text & image which can be move from left to right row-reverse like to check https://app.hubspot.com/design-manager/48440318/modules/183775650332



## 11-12-2024 - Practise and Completed DND
## Drag & Drop arears in the Hubspot CMS (10/12/2024 Study material video is older. Lot of thing changed when i working)


Step1: npx @hubspot/create-cms-project dnd-demo

npx hs watch dnd-demo/src boilerplate

if we have a Security Issue with hubspot.config.yml
Step 2: Move the hubspot.config.yml file to a secure location, such as your home directory
mv C:\Users\u\Desktop\LOCAL-DEV-DEMO\hubspot.config.yml C:\Users\u\

Update the CLI to use the new location
npx hs watch dnd-demo/src boilerplate --config=C:\Users\u\hubspot.config.yml



Step 3: dnd-demo Will created in the Content -> Website Pages (dnd-demo)will displayed // it will take some time reflect in the hubspot account and in website page dashBoard.
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> npx hs upload dnd-demo/src boilerplate






<------------------------------------------------------------------------------------------->

## 10-12-2024
## Building hubSpot Template (Follow same steps)

PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> hs create template basic-template-demo /create basic template/
(node:4228) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create page
Creating file at C:\Users\u\Desktop\LOCAL-DEV-DEMO\basic-template-demo.html


<!--
    templateType: page
    label: Page template
    isAvailableForNewContent: true
-->
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ content.html_title }}</title>
    <meta name="description" content="{{ content.meta_description }}">
    {{ standard_header_includes }}
  </head>
  <body>
    {% module "page_template_logo" path="@hubspot/logo" label="Logo" %}

    <h1>This headline is static</h1> // add this line its not able to change it static

    {% module "page_template_rich_text" path="@hubspot/rich_text" label="My First Rich Text Field Module" %} //changed in label as My First Rich Text Field Module//
     {% module_attribute "html"%}

     <h2>This headline is not static</h2> // add this line its able to change it not a static
     <p>This paragraph isn't either!</p>// add this line
     {% end_module_attribute %}// add this line
     {% end_module_block %}// add this line

     {% module "page_template_rich_text" path="@hubspot/rich_text" label="Rich Text" %} // add this line


    {{ standard_footer_includes }}
  </body>

</html>



PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> hs upload basic-template-demo.html basic-template-demo.html // change done use this cmd to upload see change hubl account
[WARNING] Security Issue Detected
[WARNING] The HubSpot config file can be tracked by git.
[WARNING] File: "C:\Users\u\Desktop\LOCAL-DEV-DEMO\hubspot.config.yml"
[WARNING] To remediate:
[WARNING] - Move the config file to your home directory: 'C:\Users\u' 
[WARNING] - Add gitignore pattern 'C:\Users\u\Desktop\LOCAL-DEV-DEMO\hubspot.config.yml' to a .gitignore file in root of your repository.
[WARNING] - Ensure that the config file has not already been pushed to a remote repository.
(node:13176) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
[SUCCESS] Uploaded file from "basic-template-demo.html" to "basic-template-demo.html" in the Design Manager of account 48440318



HubSpot Account -> Content -> Design Manager // here we can see our basic-template-demo.html
HubSpot Account -> Content -> Website page -> create -> page name is basic-template-demo -> basic-template-demo Available in website pages  // here we can upload our template //





<------------------------------------------------------------------------------------------->

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
