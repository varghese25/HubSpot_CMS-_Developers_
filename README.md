


## HubSpot-Exam Certfication 


## 28-12-2024
<!--
    templateType: global_partial
    label: Page Header
    isAvailableForNewContent: false
-->
<!-- Begin partial -->

{{standard_header_includes}}

<!-- Container for horizontal headers -->
<div style="display: flex; gap: 15px;">
  {% header "Home" header_tag="h4", overrideable=True, value="Home", label="Header" %}
  {% header "About" header_tag="h4", overrideable=True, value="About", label="Header" %}
  {% header "Blog" header_tag="h4", overrideable=True, value="Blog", label="Header" %}
</div>

{% textarea "my_textarea" label="Sub Heading", value="The naming of the cat is difficult matter" no_wrapper=True %}
{% menu "menu" %}
{% menu "my_menu" id=456, site_map_name='Default', overrideable=False, root_type='site_root', flyouts='true', max_levels='2', flow='vertical', label='Advanced Menu' %}

<!-- End partial -->


<!--
    templateType: global_partial
    label: Global partial
    isAvailableForNewContent: false
-->
<!-- Begin partial -->
<footer>
    <div class="container">
        {% module "footer_menu" path="@hubspot/menu", label="Footer Menu" id="66210624182" %}
    </div>
</footer>
<!-- End partial -->


<!--
    templateType: page
    label: page template
    isAvailableForNewContent: true
-->
<!doctype html>
<html>
  <head>
    <meta charset="utf-8">
    <title>{{ content.html_title }}</title>
    <meta name="description" content="{{ content.meta_description }}">
    {{ require_css(get_asset_url('../css/layout.css')) }}
    {{ require_css(get_asset_url('../css/main.css')) }}
    {{ standard_header_includes }}
  </head>
  <body>
    {% global_partial path="./partials/header.html" %}

    <main id="content">
      <div class="container">
        <section class="mission-section">
          <h1>Our Mission</h1>

          {% dnd_area "mission_area" label="Mission Area" %}
            {% dnd_section
              padding={
                top: 10,
                bottom: 10,
                left: 0,
                right: 0
              }
            %}
              {% dnd_column width=6 %}
                {% dnd_row %}
                  <div class="featured-image">
                    {% dnd_module "image" path="@hubspot/image" flexbox_positioning="MIDDLE_CENTER", label="Featured Image" %}
                    {% end_dnd_module %}
                  </div>
                {% end_dnd_row %}
              {% end_dnd_column %}
              {% dnd_column width=6, offset=6 %}
                {% dnd_row %}
                  {% dnd_module "rich_text" path="@hubspot/rich_text" label="Mission Statement" %}
                  {% end_dnd_module %}
                {% end_dnd_row %}
              {% end_dnd_column %}
            {% end_dnd_section %}
          {% end_dnd_area %}
        </section>

        <section class="team-section">
          <h1>Our Team</h1>
          {% module "team_module" path="../modules/team", label="Team" %}
        </section>
      </div>
    </main>

    {% global_partial path="./partials/footer.html" %}

    {{ standard_footer_includes }}
  </body>
</html>

##27-12-2024
[
 {
  "type": "text",
  "id": "ebf36aa5-be35-bd50-efd5-2ae544cd3460",
  "validation_regex": "",
  "label": "Team Header",
  "name": "team_header",
  "default": "Our Team",
  "required": false,
  "locked": false,
  "visibility": null,
  "occurrence": null
 },
 {
  "type": "image",
  "id": "9b4d7ebf-c1e9-3954-4e04-db3f675af022",
  "default": {
   "size_type": "exact",
   "src": "https://48440318.fs1.hubspotusercontent-na1.net/hubfs/48440318/person_1.jpg",
   "alt": "person_1",
   "loading": "lazy",
   "width": 235,
   "height": 148,
   "max_width": 235,
   "max_height": 148
  },
  "resizable": true,
  "responsive": true,
  "show_loading": false,
  "label": "Member Image",
  "name": "image_field",
  "visibility": {
   "operator": "NOT_EMPTY"
  },
  "required": true,
  "locked": true
 },
 {
  "type": "text",
  "id": "0a9eb312-c0db-6da5-973e-2096e4a7783d",
  "validation_regex": "",
  "label": "Member_Name",
  "name": "member_name",
  "show_emoji_picker": false,
  "default": "John Doe",
  "occurrence": null
 },
 {
  "type": "group",
  "id": "4bac2acd-c236-f683-48a7-e33680a738f6",
  "label": "member_position",
  "children": [
   {
    "type": "text",
    "id": "74050be0-a8e8-020f-4f70-3f76f7968419",
    "validation_regex": "",
    "label": "Member Position",
    "name": "member_position",
    "default": "CEO",
    "required": false
   }
  ],
  "name": "member_position",
  "default": {
   "member_position": "CEO"
  }
 }
]


## 23-12-2024
Library -> File -> Click image -> Copy URL

 "src": "https://48440318.fs1.hubspotusercontent-na1.net/hubfs/48440318/cat_1.jpg",


 ## 20-12-2024


 //Upload LocalCode to HubSpot Accout ((Whole Folder))
 
 u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum 
$ hs upload 'hubspot-praticum' 'hubspot-exam'


// /Upload LocalCode to HubSpot Accout (Only File path)
u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam (master)
$ hs upload 'hubspot-praticum' 'hubspot-exam'   (Only File path)


u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam (master) 
$ hs upload 'hubspot-praticum' 'hubspot-exam'


Create Section/Mission (Partial Page)

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam (master)
$ cd hubspot-praticum

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum (master)
$ hs create template section/mission // partial Page
(node:7004) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create partial
Creating file at E:\HubSpot-Exam\hubspot-praticum\section\mission.html



u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam (master)
$ hs upload 'hubspot-praticum' 'hubspot-exam'
[WARNING] Security Issue Detected
[WARNING] The HubSpot config file can be tracked by git.
[WARNING] File: "E:\HubSpot-Exam\hubspot.config.yml"
[WARNING] To remediate:
[WARNING] - Move the config file to your home directory: 'C:\Users\u'
[WARNING] - Add gitignore pattern 'E:\HubSpot-Exam\hubspot.config.yml' to a .gitignore file in root of your repository.
[WARNING] - Ensure that the config file has not already been pushed to a remote repository.
(node:13200) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
Uploading files from "hubspot-praticum" to "hubspot-exam" in the Design Manager of account 48440318
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\css\main.css" to "hubspot-exam/css/main.css"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\section\mission.html" to "hubspot-exam/section/mission.html"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\templates\partials\footer.html" to "hubspot-exam/templates/partials/footer.html"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\templates\partials\header.html" to "hubspot-exam/templates/partials/header.html"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\theme.json" to "hubspot-exam/theme.json"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\fields.json" to "hubspot-exam/fields.json"
Uploaded file "E:\HubSpot-Exam\hubspot-praticum\templates\basic-page.html" to "hubspot-exam/templates/basic-page.html"
[SUCCESS] Uploading files to "hubspot-exam" in the Design Manager is complete



## https://app.hubspot.com/design-manager/48440318/code/184097013871?tfid=184096497052

## 48440318 : HubSpot Account Number
## code/184097013871: Module number

 {% module "module_184097013871" path="@hubspot/email_cta", label="email_cta.module" %}

tfid=184096497052: a reference to another resource (e.g., a template, folder, or linked file) within the same workspace

-------------------------------------------------------------------------------------------------------

Themes (Steps 19-12-2024)

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam
$ npm install  @hubspot/cli

hs init

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam
$ hs init
(node:10784) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
--------------------------------------------------
HubSpot Personal Access Key Setup

A personal access key is required to authenticate the CLI to interact with your HubSpot account. We'll open a secure page in your default browser where you can view and copy your personal 
access key.

--------------------------------------------------
? Open hubspot.com to copy your personal access key? Yes
Opening https://app.hubspot.com/l/personal-access-key in your web browser
? Enter your personal access key:  ***********************************************************************************************************
? Enter a unique name to reference this account in the CLI: varghesebaby

[SUCCESS] Created config file "E:\HubSpot-Exam/hubspot.config.yml"
[SUCCESS] Connected account "varghesebaby" using "Personal Access Key" and set it as the default account
--------------------------------------------------
What's next?

Run `hs help` to see a list of available commands

Run `hs auth` to connect the CLI to additional HubSpot accounts

Run `hs accounts list` to see a list of configured HubSpot accounts

--------------------------------------------------

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam



Folder Creation

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam
$ mkdir hubspot-praticum

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam
$ cd hubspot-praticum

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ mkdir templates modules js images css

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ cd templates

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum/templates
$ mkdir partials



u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam
$ cd hubspot-praticum

u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ hs create template templates/basic-page
(node:7496) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create (Use arrow keys)
? Select the type of template to create page
Creating file at E:\HubSpot-Exam\hubspot-praticum\templates\basic-page.html


u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ hs create template templates/partials/header  // select global partials
(node:3896) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create (Use arrow keys)
? Select the type of template to create 
? Select the type of template to create 
? Select the type of template to create 
? Select the type of template to create global partial
Creating file at E:\HubSpot-Exam\hubspot-praticum\templates\partials\header.html



u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ hs create template templates/partials/footer // select global partials 
(node:9268) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create (Use arrow keys)
? Select the type of template to create 
? Select the type of template to create 
? Select the type of template to create 
? Select the type of template to create global partial
Creating file at E:\HubSpot-Exam\hubspot-praticum\templates\partials\footer.html



u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ touch fileds.json
[
    {
        "label": "Text Color",
        "name": "text_color",
        "type": "color",
        "default": {
            "color": "#000"

        }

    }
]


u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ touch theme.json

{
    "label": "HubSpot Exam theme",
    "preview": "./template/basic-page.html"
}


CSS folder -> create #main.css file 



templates->basic-page.html
 {{require_css (get_asset_url('../css/main.css'))}} <!-- inclue this line-->>
 
 
 
 
 //Upload LocalCode to HubSpot Accout
 
 u@DESKTOP-OODIU93 MINGW64 /e/HubSpot-Exam/hubspot-praticum
$ hs upload 'HUBSPOT-EXAM' 'hubspot-exam'








<------------------------------------------------------------------------>

## HubSpot CMS Development Command Document

<-- CMS Development -->

## 17-12-2024
## Building a Theme

Vscode 
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> mkdir tiju-theme
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> cd tiju-theme 
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme> mkdir templates, modules, js, images, css
PS C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme> hs create template templates/basic-page
(node:2540) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create page
Creating file at C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme\templates\basic-page.html


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
    <div class="page-wrap">  //add this line
      <header>   //add this line
    {% module "page_template_logo" path="@hubspot/logo" label="Logo" %}
    </header>  //add this line
    {% module "page_template_rich_text" path="@hubspot/rich_text" label="Rich Text" %}
  </div> //add this line
    {{ standard_footer_includes }}
  </body>
</html>

PS C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme> mkdir templates/partials


PS C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme> hs create template templates/partials/header
(node:9660) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? Select the type of template to create 
  page
  email
  partial
> global partial // select this



## // add below line in folder partials->header.html
<!--
    templateType: global_partial
    label: Global partial
    isAvailableForNewContent: false
-->
<!-- Begin partial -->

<header>
    {% module "page_template_logo" path="@hubspot/logo" label="Logo" %}
    </header>

<!-- End partial -->




## // add the partial line here the basic-html.page

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
    <div class="page-wrap">
      {% global_partial path='./partials/header.html'} // add the partial line here the basic-html.page
    {% module "page_template_rich_text" path="@hubspot/rich_text" label="Rich Text" %}
  </div>
    {{ standard_footer_includes }}
  </body>
</html>


create empty css->main.css // using ttouch css/main.css command or PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> "" > css/main.css 


## // add this line basic-page.html

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
    
    {{require_css(get_asset_url('../css/main.css'))}} // add this line 

    {{ standard_header_includes }}
  </head>
  <body>
    <div class="page-wrap">
      {% global_partial path='./partials/header.html'}
    {% module "page_template_rich_text" path="@hubspot/rich_text" label="Rich Text" %}
  </div>
    {{ standard_footer_includes }}
  </body>
</html>


## main.css

*{
    box-sizing: border-box;
    font-family: Helvetica, sans-serif;
}
html,
body{
    margin: 0;
    padding: 0;
    background-color: #eee;
}

.page-wrap{
    color: #000;
    max-width: 1100px;
    margin: 0 auto;
    background-color: #ddd;
    padding: 1em;
    min-height: 100vh;
}
header{
    text-transform: uppercase;
    letter-spacing: .3em;
    background-color: #eee;
    background: url({{get_asset_url('../images/ttm-Icon-16x16')}}) 0 39% no-repeat #333;
    background-size: cover;
    color: #fff;
    padding: 1em 50% 1em 2em;
    margin-bottom: 3em;

}

PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> "" > fields.json  
[
    {
        "label": "Text Color",
        "name": "text_color",
        "type": "color",
        "default":{
            "color": "#000"
        }
    }
]



PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> "" > theme.json 

{
    "lable": "tiju",
    "preview_path" : "./templates/basic-page.html"
}




## main.css change this line // refer the css 
.page-wrap{
    color: {{theme.text_color.color}};



PS C:\Users\u\Desktop\LOCAL-DEV-DEMO> hs upload tiju-theme
[WARNING] Security Issue Detected
[WARNING] The HubSpot config file can be tracked by git.
[WARNING] File: "C:\Users\u\Desktop\LOCAL-DEV-DEMO\hubspot.config.yml"
[WARNING] To remediate:
[WARNING] - Move the config file to your home directory: 'C:\Users\u'
[WARNING] - Add gitignore pattern 'C:\Users\u\Desktop\LOCAL-DEV-DEMO\hubspot.config.yml' to a .gitignore file in root of your repository.     
[WARNING] - Ensure that the config file has not already been pushed to a remote repository.
(node:7416) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
? [--dest] Enter the destination path:  hs upload tiju-theme /themes/tiju-theme
Uploading files from "tiju-theme" to "hs upload tiju-theme /themes/tiju-theme" in the Design Manager of account 48440318
Uploaded file "C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme\css\main.css" to "hs upload tiju-theme /themes/tiju-theme/css/main.css"
Uploaded file "C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme\templates\basic-page.html" to "hs upload tiju-theme /themes/tiju-theme/templates/basic-page.html"
Uploaded file "C:\Users\u\Desktop\LOCAL-DEV-DEMO\tiju-theme\templates\partials\header.html" to "hs upload tiju-theme /themes/tiju-theme/templates/partials/header.html"
[SUCCESS] Uploading files to "hs upload tiju-theme /themes/tiju-theme" in the Design Manager is complete

<------------------------------------------------------------------------------------------->

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
