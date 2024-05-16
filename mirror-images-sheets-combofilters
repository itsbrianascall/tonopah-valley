<!DOCTYPE html>

    <!--MIRROR IMAGES w/ Spreadsheets 2.0 by @nonspace.
    Find more of my work at https://nonspace.tumblr.com

    Don't steal.
    Don't claim as your own.
    Don't use as base code.
    I will find and haunt you.
    Editing for personal use is fine!-->

<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <link rel="icon" type="image/png" href="{Favicon}">
  <link rel="alternate" type="application/rss+xml" href="{RSS}">
  <title>{Title}</title>
  <meta name="description" content="{MetaDescription}" />

   <!--FONTS-->
  <link href="https://fonts.googleapis.com/css?family=Roboto:300,300i,400,400i,500,500i,700,700i|Chivo:300,300i,400,400i,700,700i&amp;subset=latin-ext" rel="stylesheet">

  <!--jQUERY-->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" crossorigin="anonymous"></script>

  <!--HANDLEBARS.JS-->
  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/handlebars.js/4.7.8/handlebars.min.js"></script>

  <!--PAGE SETTINGS-->
  <script>
    /*TO GET THE SHEET ID:
    1. Go to your spreadsheet > File > Publish to web.
    2. Click on "Entire Document" and select the speficic sheet (in the
       example it is called "MAIN") > publish, ignore the URL.
    3. File > Share > Anyone with link can share. This URL is important.
    4. Copy the following string from the URL and paste it in sheetID:
       Example:
       https://docs.google.com/spreadsheets/d/
         1jKi9Knw7e5qr4bXr_zQib8FwpGM7E6eqRx1tH3JruIA (this part)
      /edit?usp=sharing
      
    TO GET API KEY:
    1. Go to https://console.cloud.google.com/projectselector2/apis/dashboard 
    (of the account the sheet is under)
    2. Create new project
    3. Create credentials, choose API key (copy this)
    4. Restrict application access to HTTP referrer and add the wildcard yoururl.tumblr.com/* (or for multipe sites if needed)
    5. Libraries > search for Google Sheets > Enable*/

    const sheetID = '1L0dAaRzJUMPPLCEQWKqn7J3H533Y4jC09YI7CMXN_VI';
    const sheetTab = 'MAIN';
    const APIkey = 'AIzaSyDN0ygUd9hpxWxVtt1IM_bO3SGv2TCt-PE';
    
    /*This lets you enable/disable different colors per tab.
      true = enabled, false = disabled*/
    var colorPerTab = false;

  </script>

  <!--SHEET INTEGRATION-->
  <script type="text/javascript" src="https://www.dl.dropboxusercontent.com/s/wlxk3q4wkqxescn/nnspc-sheets.js"></script>

<style>

/*INSTRUCTIONS*/

/*ICONS
This theme supports both fontawesome and feathericons. By default it uses fontawesome.
To find these icons, check their respective websites. The menu icons is added through
pseudo elements. If you want a feather icon in its place you have to get the SVG url,
(you can get it from here by copying the image url:
https://github.com/feathericons/feather/tree/master/icons)
delete the "content:" value (e.g. content: "") and use the SVG as a background URL
like so:

#sidebar_controls::before {
  content: "";
  background-image: url(data:image/svg+xml;base64,PHN2ZwogIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIKICB3aWR0aD0iMjQiCiAgaGVpZ2h0PSIyNCIKICB2aWV3Qm94PSIwIDAgMjQgMjQiCiAgZmlsbD0ibm9uZSIKICBzdHJva2U9ImN1cnJlbnRDb2xvciIKICBzdHJva2Utd2lkdGg9IjIiCiAgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIgogIHN0cm9rZS1saW5lam9pbj0icm91bmQiCj4KICA8bGluZSB4MT0iMyIgeTE9IjEyIiB4Mj0iMjEiIHkyPSIxMiIgLz4KICA8bGluZSB4MT0iMyIgeTE9IjYiIHgyPSIyMSIgeTI9IjYiIC8+CiAgPGxpbmUgeDE9IjMiIHkxPSIxOCIgeDI9IjIxIiB5Mj0iMTgiIC8+Cjwvc3ZnPgo=);
  background-repeat: no-repeat;
}*/

/*1. FILTER OPTIONS*/
/*Down in the navigation are filter options. You you can set the filter they "link" to through the 'data-filter' attribute. Set it to the classes you want to filter (including the dot to denoate a class) and add the respective class to the .grid-item in the 'class' attribute. E.g.

Your filter group one if called 'f1'
-> data-filter=".f1"
-><div class="grid-item f1">

Links:
  https://isotope.metafizzy.co/filtering.html
  https://nonspace.io/tagged/theme%20help:%20filters
*/

/*2. GRID*/
/*In the HTML you will find the template for the grid item within a script tag
and the ID: handlebars-template-grid. This will be the base of all generated items.

The content in it is replace by variables that look like this:
  {{this.spreadsheetcolumnname}}
They are placeholders for the content of each item. You can customise the html
as you usually would. Any content you want to pull from the spreadsheet needs
to be written like the above. "spreadsheetcolumnname" is what you replace with
the column name in your spreadsheet. Important: The it needs to be in all
lowercase and without the space.

Example:

You want to add a character's age to the grid item. The headline of the column
in your spreadsheet with the info is "AGE". Where you would usually write the
age in the html you instead put: {{this.age}}

HTML IN SPREADSHEET

If you want to be able to use HTML tags in the spreadsheet and have them carry
over to the theme (for example paragraphs for biography text) you can do that
by wrapping the variables in 3 curly bracketsinstead of 2.

{{{this.bio}}} will escape HTML {{this.bio}} will write HTML tags as text.

*/

/*3. TABS*/
/*Same as the above. The template ID is: handlebars-template-tabs.
*/

/*variables*/
:root {
  /*layout*/
  --postWidth: 1200px; /*character sheet container*/
  --barWidth: 80px;

  /*font styles*/
  --fontSize: 16px;
  --headlineSize: 32px;
  --lineHeight: 150%;
  --textColor: #57565b;
  --headlines: #5e6060;
  --fontFamily: 'Roboto';
  --fontFamilySecondary: 'Chivo';
  --fontWeight: 400;

  /*colors*/
  --background: #f8fafb;
  --postBackground: #fff;
  --navigationText: #a1a3a3;
  --navigationBackground: #111;
  --navigationBorders: #2f2f2f;

  --accentColor: #6d69a0;
  --accentColorRGB: 109, 105, 160;
  --accentText: #fff;
  --accentLightColor: #d8d9d9; /*social links, title*/
  --postBorders: #e8e8e8; /*character card border*/

  /*misc*/
  --bulletIcon: "\f00d";
  --borderRadius: 20px;

  /*grid*/
  --gridItemWidth: 255px;
  --gridItemImageHeight: 375px;

  /*responsive*/
  --mediaBreak1: var(--barWidth) + var(--postWidth) + 50px);

  /*color per tab if enabled above*/

  --accentColor-1: #F5C2A2;
  --accentText-1: #FFF;
  --accentColor-2: #303A36;
  --accentText-2: #FFF;
  --accentColor-3: #E1313B;
  --accentText-3: #FFF;
  --accentColor-4: #B08A71;
  --accentText-4: #FFF;
  --accentColor-5: #B69F97;
  --accentText-5: #FFF;
  --accentColor-6: #A97F5C;
  --accentText-6: #FFF;
}

/*reset styles*/
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
  position: relative;
  font-size: var(--fontSize);
  line-height: var(--lineHeight);
  font-family: var(--fontFamily);
  min-height: 100vh;
  background: var(--background);
  color: var(--textColor);
  font-weight: var(--fontWeight);
}

/*GENERAL STYLES*/

::selection {
  background: var(--accentColor);
  color: var(--accentText);
}

::-moz-selection {
  background: var(--accentColor);
  color: var(--accentText);
}

/* width */
::-webkit-scrollbar {
  width: 2px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px rgba(var(--accentColorRGB),0.7);
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: var(--accentColor);
  border-radius: 10px;
}

pre {
  margin 20px 10px;
  background: var(--accentColor);
  padding: 10px 10px;
  font: var(--fontSize) monospace;
  letter-spacing: 0px;
  text-align: left;
  width: 100%;
  line-height: var(--lineHeight);
  overflow: wrap;
  color: var(--accentText);
  white-space: pre-wrap;       /* css-3 */
  white-space: -moz-pre-wrap;  /* Mozilla, since 1999 */
  white-space: -pre-wrap;      /* Opera 4-6 */
  white-space: -o-pre-wrap;    /* Opera 7 */
  word-wrap: break-word;
}

code {
  font-family: monospace;
}

small, sub {
  font-size: 0.9rem;
}

.caption ul {
  margin: 20px 0 20px 35px;
  text-align: justify;
}

.caption li {
  margin: 10px 0 10px 15px;
  list-style-type: none;
}

.headlines {
  text-align: left;
  font-family: var(--fontFamilySecondary), sans-serif;
  font-size: var(--headlineSize);
}

.headlines a {
  text-decoration: none;
}

.headlines,
.headlines a {
  color: var(--headlines);
  font-family: var(--fontFamilySecondary);
  font-size: 1.55rem;
  font-weight: normal;
  letter-spacing: 2px;
}

p {
  margin-bottom: 25px;
}

blockquote {
  margin: 15px 0 15px 15px;
  padding-left: 15px;
  width: 96%;
  border-left: 3px solid var(--accentColor);
}

.flex {display: flex;}
.flex-column {flex-direction: column;}
.flex-wrap {flex-wrap: wrap;}


/* NAVIGATION */

nav,
.character_nav {
  position: fixed;
  height: 100%;
  width: 80px;
  background: var(--navigationBackground);
  left: -0px;
}

nav {
  z-index: 6;
}

nav li,
.character_nav li {
  list-style-type: none;
  margin-bottom: 25px;
  text-align: center;
}

nav li a,
.character_nav li a {
  text-transform: uppercase;
  letter-spacing: 5px;
  text-decoration: none;
  color: var(--navigationText);
}

nav a[data-filter] > * {
  opacity: 0.5;
}

nav a.default > * {
  opacity: 1;
}

nav li i,
.character_nav li i {
  font-size: 1.3rem;
}

#icon_nav,
.icon_nav {
  position: relative;
  width: 80px;
  margin: 120px 0 40px auto;
  align-items: center;
  overflow-y: auto;
}

input#sidebar_button {
  display: none;
}

#sidebar_controls {
  position: fixed;
  top: 0px;
  left: 0px;
  z-index: 9;
  cursor: pointer;
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-bottom: 1px solid var(--navigationBorders);
}

#sidebar_controls::before,
input#sidebar_button:checked ~ #sidebar_controls::before {
  display: inline-block;
  font-style: normal;
  font-variant: normal;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  font-size: 1.3rem;
}

#sidebar_controls::before {
  font-family: "Font Awesome 6 Pro";
  font-weight: 900;
  content: "\f0c9";
  color: var(--navigationText);
}

input#sidebar_button:checked ~ #sidebar_controls::before {
  font-family: "Font Awesome 6 Pro";
  font-weight: 900;
  content: "\f00d";
  color: var(--navigationText);
}

/* CSS PRELOADER (loading.io) */
.lds-ring {
  display: inline-block;
  position: fixed;
  width: 80px;
  height: 80px;
  top: 50%;
  margin-top: -40px;
  left: 50%;
  right: -40px;
  z-index: 99;
}
.lds-ring div {
  box-sizing: border-box;
  display: block;
  position: absolute;
  width: 64px;
  height: 64px;
  margin: 8px;
  border: 8px solid var(--accentColor);
  border-radius: 50%;
  animation: lds-ring 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
  border-color: var(--accentColor) transparent transparent transparent;
}
.lds-ring div:nth-child(1) {
  animation-delay: -0.45s;
}
.lds-ring div:nth-child(2) {
  animation-delay: -0.3s;
}
.lds-ring div:nth-child(3) {
  animation-delay: -0.15s;
}
@keyframes lds-ring {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/* MAIN CONTAINER */

.container {
  position: relative;
  width: 100%;
  min-width: 250px;
  height: 100vh;
  margin: auto;
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
}

.content_wrapper {
  position: relative;
  max-width: 100%;
  -webkit-animation-duration: 1.2s;
  animation-name: fadeIn;
  animation-duration: 1.2s;
  margin-left: var(--barWidth);
}

.content_wrapper.grid {
  padding: 0 80px;
}

.content_wrapper.tab {
  display: none;
  z-index: 7;
}

.page_wrapper {
  position: relative;
  color: var(--textColor);
  text-align: justify;
  min-width: 250px;
  display: block;
  width: 100%;
  min-height: 100vh;
  background: var(--background);
}

.page_wrapper .article_wrapper {
   border: none;
   min-height: 100vh;
}

.page_wrapper .headlines {
  margin-bottom: 50px;
}

.row {
  position: relative;
  width: 100%;
  margin-bottom: 65px;
}

.col-2:last-of-type .row:last-of-type {
  margin-bottom: 0;
}

.row.no-margin-bottom {
  margin-bottom: 40px;
}

.col {
  width: 100%;
}

.col-2 {
  max-width: 100%;
}

.outer_col {
  padding: 0 25px;
  flex: 1;
  min-width: 300px;
}

/* SOCIAL */

.social {
  margin: auto 0 0 0;
}

.social i {
  font-size: 1.55rem;
  margin-right: 25px;
}

.social a {
  color: var(--accentLightColor);
}

/*POST HEADER & FOOTER*/

.article_wrapper {
  margin: 0 auto;
  padding: 80px 0px;
  width: 100%;
  border-bottom: 1px solid var(--postBorders);
}

.article_wrapper:last-of-type {
  border-bottom: none;
}

.post {
  position: relative;
  height: auto;
  margin: auto;
  padding: 0 25px;
  max-width: var(--postWidth);
  flex-wrap: wrap;
}

.post_body {
  max-width: var(--postWidth);
  padding-left: 50px;
  width: 100%;
}

.cpt {
  max-width: var(--postWidth);
}

/*OVERLAY*/
.overlay {
  background: rgba(var(--accentColorRGB),0.7);
  position: absolute;
  height: 100%;
  width: 100%;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  opacity: 0;
}

.overlay-text {
  position: absolute;
  width: 100%;
  top: 0;
  opacity: 0;
  font-size: 0.85rem;
  padding: 8px;
  color: var(--accentText);
  text-align: center;
  line-height: 0.9rem;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  height: 100%;
}

/*CAPTIONS & UNNEST*/
.caption {
  margin-top: 0px;
  line-height: var(--lineHeight);
  text-align: justify;
  font-size: var(--fontSize);
  color: var(--textColor);
}

.caption p a,
.caption ul a,
.caption a {
  padding: 0 0px;
  color: var(--accentColor);
}

.caption a:hover,
.caption ul a:hover,
.caption p a:hover {
  box-shadow: none;
  color: var(--accentColor);
}

.caption li:before,
.caption li:before {
  content: var(--bulletIcon);
  font-family: "Font Awesome 6 Pro";
  font-weight: 900;
  display: inline-block;
  width: 15px;
  margin-right: 10px;
}

.caption a b {
  color: var(--accentText);
}

.caption a b:hover {
  color: var(--textColor);
}

.caption * {
  margin: 15px 0;
}

.caption code * {
  margin: 0px 0 !important;
}

.caption p:empty {margin: 0;}
.caption :last-child {margin-bottom: 0;}

.caption blockquote p {
  margin: 0 auto;
}

.caption img {
  width: 100%;
  height: auto;
}

.caption.has-border-radius {
  padding: 25px;
  background: var(--postBackground);
}

/*GRID*/

.grid_wrapper {
  width: 100%;
  margin: 40px auto;
}

/*GRID ITEMS*/

.grid-item {
  width: var(--gridItemWidth);
  overflow: hidden;
  margin: 15px;
  opacity: 0;
}

.grid-item > a {
  line-height: 0;
  position: relative;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
}

.grid-item img {
  width: var(--gridItemWidth);
  height: var(--gridItemImageHeight);
  object-fit: cover;
  line-height: 0;
}

.grid-item .overlay-text:hover {
  cursor: pointer;
}

.grid-item {
  position: relative;
  background: var(--postBackground);
  height: auto;
  line-height: 160%;
  overflow: hidden;
  border-bottom: 15px solid var(--postBackground);
}

.grid-item .overlay-text i {
  font-size: 100px;
}

.sep {
  height: 1px;
  width: 100%;
  background: var(--postBorders);
  margin: 20px 0 20px;
}

.item-content {
  padding: 25px;
}

.item-content .desc {
  position: relative;
  height: 100%;
  overflow-y: auto;
}

.item-content .desc p:not(first-of-type) {
  margin-top: 15px;
}

.item-content a {
  color: var(--accentColor);
  text-decoration: none;
  box-shadow: inset 0 -5px var(--accentColor);
}

.item-head i {
  color: var(--accentLightColor);
}

.item-head .headlines {
  font-size: 1.25rem;
}

.item-head .far {
  font-size: 1.66rem;
  margin-left: 10px;
}

.item-head {
  justify-content: space-between;
  align-items: center;
}


/*CHARACTER DETAIL PAGE*/

.intro_quote {
  margin-bottom: 50px;
}

.intro_quote img {
  width: var(--gridItemWidth);
  height: var(--gridItemImageHeight);
  object-fit: cover;
  o-object-fit: cover;
  margin: 0 25px 25px 0;
}

.cinfo_wrap {
  flex: 1;
  padding-bottom: 25px;
  min-width: 128px;
}

.qt {
  font-style: italic;
  font-size: 0.9rem;
  overflow-y: auto;
}

/*info table*/
.character_page table {
  flex-basis:550px
  display: block;
}

.character_page tbody {
  display: block;
  width: 100%;
}

.character_page tr {
  display: flex;
  align-items: center;
  margin: 0 5px 25px 5px;
  justify-content: space-between;
  background: var(--postBackground);
  overflow-x:auto;
  overflow-y: hidden;
  text-transform:lowercase;
  height:auto;
}

.character_page td {
  padding: 14px 0;
}

.character_page td:first-of-type {
  background: rgba(var(--accentColorRGB), 0.05);
  padding-right: 14px;
  font-weight: bold;
  border-right: 1px solid var(--accentText);
}

.character_page td:last-of-type {
  padding-right: 20px;
  width: 100%;
  margin-left: 15px;
}

.character_page table:nth-of-type(1) tr:nth-of-type(1) td:nth-of-type(1)::before,
.character_page table:nth-of-type(1) tr:nth-of-type(2) td:nth-of-type(1)::before,
.character_page table:nth-of-type(1) tr:nth-of-type(3) td:nth-of-type(1)::before,
.character_page table:nth-of-type(1) tr:nth-of-type(4) td:nth-of-type(1)::before,
.character_page table:nth-of-type(2) tr:nth-of-type(1) td:nth-of-type(1)::before,
.character_page table:nth-of-type(2) tr:nth-of-type(2) td:nth-of-type(1)::before,
.character_page table:nth-of-type(2) tr:nth-of-type(3) td:nth-of-type(1)::before, .character_page table:nth-of-type(2) tr:nth-of-type(4) td:nth-of-type(1)::before {
  font-family: "Font Awesome 6 Pro";
  font-weight: 400;
  padding: 60px 20px;
  background: var(--accentColor);
  color: var(--accentText);
  margin-right: 10px;
}

.character_page table:nth-of-type(1) tr:nth-of-type(1) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(1) tr:nth-of-type(2) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(1) tr:nth-of-type(3) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(1) tr:nth-of-type(4) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(2) tr:nth-of-type(1) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(2) tr:nth-of-type(2) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(2) tr:nth-of-type(3) td:nth-of-type(1)::before {
  content: "\f005";
}
.character_page table:nth-of-type(2) tr:nth-of-type(4) td:nth-of-type(1)::before {
  content: "\f005";
}

/*links*/
.character_page .headlines,
.character_page .clinks {
  margin-bottom: 25px;
  
}

.character_page .clinks {
  margin: auto 0 0 0;
  padding: 25px 0px 0 0px;
  display: flex;
  justify-content: left;
  align-items: left;
}

.clinks button {
 display: inline-block;
 border-radius: 15px;
 background-color: var(--accentColor);
 border: none;
 color: #FFFFFF;
 text-align: center;
 text-transform:uppercase;
 font-weight:600;
 font-size: 12px;
 padding: 16px;
 width: 90px;
 transition: all 0.5s;
 cursor: pointer;
 margin: 5px 5px 10px 5px;
}


.clinks button span {
 cursor: pointer;
 display: inline-block;
 position: relative;
 transition: 0.5s;
}

.clinks button:hover {
    width:110px;
}

.clinks button span i {
    font-size:12px;
    margin-right:3px;
}

.clinks button span:after {
 content: '»';
 position: absolute;
 opacity: 0;
 top: 0;
 right: -15px;
 transition: 0.5s;
}

.clinks button:hover span {
 padding-right: 15px;
}

.clinks button:hover span:after {
 opacity: 1;
 right: 0;
}

/*SHADOWS & BORDER RADIUS*/

.has-border-radius,
.pos_traits li,
.neg_traits li,
.cskills .track,
.cskills .track span,
.cconnections img,
.cconnections .overlay,
.character_page tr,
.cpinterest span[class$="_img"] {
  border-radius: var(--borderRadius) !important;
}

.lighter-shadow,
.character_page tr,
.pos_traits li,
.neg_traits li {
  -webkit-box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.1);
  -moz-box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.1);
  box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.1);
}

.stronger-shadow,
.cconnections img {
  -webkit-box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.2);
  -moz-box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.2);
  box-shadow: 0px 0px 20px 0px rgba(17,17,17,0.2);
}

/*TOOLTIPS*/
.tooltipster-default {
  border-radius: var(--borderRadius) !important;
  border: none !important;
  background: var(--postBackground) !important;
  color: var(--textColor) !important;
}

/* Use this next selector to style things like font-size and line-height: */
.tooltipster-default .tooltipster-content {
	font-family: var(--fontFamily) !important;
	font-size: var(--fontSize) !important;
	line-height: var(--lineHeight) !important;
	padding: 8px 10px;
	overflow: hidden;
}

/*CREDIT*/

#nnspc {
  position: absolute;
  bottom: 0;
  padding: 5px 10px;
  font-family: helvetica;
  font-size: 18px;
  font-weight: bold;
  z-index: 99;
}

#nnspc a {
  text-decoration: none;
  color: var(--navigationText);
}

/* TRANSITIONS */
/*ANIMATION KEYFRAMES*/
@-webkit-keyframes fadeIn  {
  0% { opacity: 0; }
  100% { opacity: 1; }
}
@keyframes fadeIn {
  0% { opacity: 0; }
  100% { opacity: 1; }
}

.social a,
#nnspc,
#nnspc a,
nav,
.character_nav,
#sidebar_controls,
.row .quest,
.overlay,
.overlay-text,
.grid-item {
  transition: all 0.5s ease;
}

.cconnections li:hover .overlay,
.cconnections li:hover .overlay-text,
.grid-item:hover > a .overlay,
.grid-item:hover > a .overlay-text,
.is-visible {
  opacity: 1;
}

/* MEDIA QUERIES */

@media only screen and (max-width: 850px) {
  .content_wrapper {
    margin: 0 auto;
    padding: 0 25px !important;
  }

  #sidebar_controls {
    border-bottom: none;
    display: flex;
  }

  #sidebar_controls::before {
    color: var(--headlines);
  }

  .about_page table:first-of-type {
    margin-right: 0px;
  }

  nav,
  .icon_nav,
  .character_nav {
    display: none !important;
  }

  .cconnections {
    justify-content: space-around;
  }

}

</style>

</head>

<body>

<!--CONTROLS END-------------------------------------------------------->

  <input id="sidebar_button" type="checkbox" name="mobile-menu" />
  <label id="sidebar_controls" for="sidebar_button"></label>

  <!--loading.io preloader-->
  <div class="lds-ring"><div></div><div></div><div></div><div></div></div>

<!--NAVIGATION---------------------------------------------------------->
  <nav class="flex">

    <!--icon navigation-->
    <ul id="icon_nav" class="flex flex-column">
      <li><a href="/" title="{lang:Home}"><i class="fas fa-home"></i></a></li>
      <li><a href="/ask" title="post office"><i class="far fa-question-circle"></i></a></li>

    <!--filters-->
    <!--COPY HERE-->
    <li><a href="#" title="show all" data-filter="*" class="default tooltip">
      <i class="far fa-star"></i></a></li>
    <!--COPY END-->
    <li><a href="#" title="filter 1" data-filter=".f1" class="tooltip">
      <i class="far fa-star"></i></a></li>
    <li><a href="#" title="filter 2" data-filter=".f2" class="tooltip">
      <i class="far fa-star"></i></a></li>
    <li><a href="#" title="filter 3" data-filter=".f3" class="tooltip">
      <i class="far fa-star"></i></a></li>

    <!--PASTE MORE FILTERS HERE-->
    
    <div class="filters">

    <ul class="filter option-set" data-filter-group="affiliations">
    
      <li style="font-size:9px;color:var(--accentText); font-weight:bold; text-transform:uppercase;background-color:var(--accentColor); padding:3px 5px;border-radius:10px;">affiliation</li>
      
      <li><a href="#"  title="all" data-filter-value="" class="selected" class="tooltip"><i class="fa-duotone fa-users"></i></a></li>
      
      <li><a href="#" title="none" data-filter-value=".na" class="tooltip"><i class="fa-duotone fa-person-simple"></i></a></li>
      
      <li><a href="#" title="criminal justice" data-filter-value=".law" class="tooltip"><i class="fa-duotone fa-scale-balanced"></i></a></li>
      
      <li><a href="#" title="" data-filter-value=".gov" class="tooltip"><i class="fa-duotone fa-book-section"></i></a></li>
      
      <li><a href="#" title="los santos" data-filter-value=".ls" class="tooltip"><i class="fa-duotone fa-skull"></i></a></li>
      
      <li><a href="#" title="sons of silence" data-filter-value=".sos" class="tooltip"><i class="fa-duotone fa-motorcycle"></i></a></li>
      
      <li><a href="#" title="the drifters" data-filter-value=".td" class="tooltip"><i class="fa-duotone fa-car-bolt"></i></a></li>
      
      <li><a href="#" title="the enterprise" data-filter-value=".te" class="tooltip"><i class="fa-duotone fa-cards"></i></a></li>
    </ul>

    <ul class="filter option-set combine" data-filter-group="ranks">
      <li style="font-size:9px;color:var(--accentText); font-weight:bold; text-transform:uppercase;background-color:var(--accentColor); padding:3px 5px;border-radius:10px;">ranks</li>
      <li><a href="#" data-filter-value="" class="selected"><i class="fa-duotone fa-people-group"></i></a></li>
      <li><a href="#" title="civilian" data-filter-value=".civ" class="tooltip"><i class="fa-duotone fa-house-turret"></i></a></li>
      <li><a href="#" title="gang member" data-filter-value=".mem" class="tooltip"><i class="fa-duotone fa-swords"></i></a></li>
      <li><a href="#" title="affiliated" data-filter-value=".aff" class="tooltip"><i class="fa-duotone fa-shield-halved"></i></a></li>
    </ul>
    
    <ul class="filter option-set combine" data-filter-group="status">
      <li style="font-size:9px;color:var(--accentText); font-weight:bold; text-transform:uppercase;background-color:var(--accentColor); padding:3px 5px;border-radius:10px;">status</li>
      <li><a href="#" title="all" data-filter-value="" class="selected" class="tooltip"><i class="fa-duotone fa-universal-access"></i></a></li>
      <li><a href="#" title="active" data-filter-value=".active" class="tooltip"><i class="fa-duotone fa-person-circle-plus"></i></a></li>
      <li><a href="#" title="deceased" data-filter-value=".dead" class="tooltip"><i class="fa-duotone fa-person-circle-xmark"></i></a></li>
      <li><a href="#" title="former character" data-filter-value=".fc" class="tooltip"><i class="fa-duotone fa-person-circle-exclamation"></i></a></li>
      <li><a href="#" title="non-playable character" data-filter-value=".npc" class="tooltip"><i class="fa-duotone fa-person-circle-minus"></i></a></li>
    </ul>

  </div>

      <!--CREDIT-->
      <div id="nnspc"><a href="//nonspace.tumblr.com" target="_blank">n.</a></div>
      </ul>

  </nav>

<!--NAVIGATION END------------------------------------------------------>

<!--CONTAINER----------------------------------------------------------->
  <div class="container">
    <!--CHARACTER GRID-->
    <div id="content_wrapper" class="content_wrapper grid flex flex-wrap">
      <div id="grid" class="grid_wrapper">

        <!--GRID ITEM TEMPLATE-->
        <script id="handlebars-template-grid" type="text/x-handlebars-template">
          {{#each []}}
            <!--GRID ITEM START-->
            <div class="{{this.filters}} grid-item has-border-radius lighter-shadow">
              <!--change id for the right tab here-->
              <a href="#{{this.nick}}">
                <div class="overlay"></div>
                <img src="{{this.image}}">
                <div class="overlay-text">
                  <i class="fas fa-info"></i>
                </div>
              </a>
              <div class="item-content">
                <div class="item-head flex">
                  <div class="item-head-left">
                    <i>{{this.title}}</i>
                    <div class="headlines item-name">{{this.name}}</div>
                  </div>
                  <i class="far fa-user-circle"></i>
                </div>
                <div class="sep"></div>
                <div class="desc">{{this.quote}}
                </div>
              </div>
            </div>
            <!--GRID ITEM END-->
          {{/each}}
        </script>

      </div>
      <!--grid_wrapper end-->

      <!--GRID END-------------------------------------------------------->

      <!--TAB TEMPLATE-->
      <script id="handlebars-template-tabs" type="text/x-handlebars-template">
        {{#each []}}
          <div id="{{this.nick}}" class="content_wrapper tab">
            <!--charater navigation-->
            <div class="character_nav">
              <ul class="icon_nav flex flex-column">
                <li><a href="{{this.playlist}}">
                    <i class="fas fa-music"></i></a></li>
                <li><a href="{{this.pinterest}}">
                    <i class="fab fa-pinterest-p"></i></a></li>
              </ul>
            </div>

            <!--character-->
            <div class="page_wrapper character_page about_page">
              <div class="article_wrapper">
                <article class="post flex flex-wrap">
                  <!--intro-->
                  <div class="col-2 outer_col">
                    <div class="row flex flex-wrap intro_quote">
                      <img src="{{this.image}}" class="has-border-radius stronger-shadow">
                      <div class="cinfo_wrap flex flex-column">
                        <!--character name-->
                        <h2 class="headlines">{{this.name}}</h2>
                        <!--character pronouns-->
                        <h3>{{this.gender}} • {{this.pron}}</h3>
                        <hr>
                        <!--character quote-->
                        <div class="col qt">
                          {{this.quote}}
                        </div>
                        <!--character links-->
                        <div class="clinks social flex">
                          <a href="{{this.biourl}}"><button><span><i class="fa-duotone fa-book-user"></i> bio</span></button></a>
                          <a href="{{this.blogurl}}"><button><span><i class="fa-duotone fa-user-pen"></i> blog</span></button></a>
                        </div>
                      </div>
                    </div>
                    <!--table-->
                    <div class="row flex flex-wrap no-margin-bottom">
                      <!--left-->
                      <table class="col-2">
                        <tbody>
                          <tr>
                            <td>fullname</td>
                            <td>{{this.fullname}}</td>
                          </tr>
                          <tr>
                            <td>moniker</td>
                            <td>{{this.nick}}</td>
                          </tr>
                          <tr>
                            <td>faceclaim</td>
                            <td>{{this.faceclaim}}</td>
                          </tr>
                        </tbody>
                      </table>
                      <!--right-->
                      <table class="col-2">
                        <tbody>
                          <tr>
                            <td>age</td>
                            <td>{{this.age}}</td>
                          </tr>
                          <tr>
                            <td>birthday</td>
                            <td>{{this.birthdate}}</td>
                          </tr>
                          <tr>
                            <td>career</td>
                            <td>{{this.occupation}}</td>
                          </tr>
                          <tr>
                            <td>affiliation</td>
                            <td>{{this.affiliation}}</td>
                          </tr>
                        </tbody>
                      </table>
                    </div>
                  </div>
                  <div class="col-2 outer_col">
                    <!--text-->
                    <div class="row caption has-border-radius lighter-shadow">
                      {{{this.bioone}}}
                    </div>
                    <!--pinterest-->
                    <div class="row cpinterest">
                      <!--add your pinterest board url-->
                      <a data-pin-do="embedBoard" data-pin-board-width="700" data-pin-scale-height="750" data-pin-scale-width="60" href="{{this.pinterest}}"></a>
                    </div>

                  </div>
                  <!--col 2 end-->
                </article>
              </div>
              <!--article_wrapper end-->
            </div>
            <!--page_wrapper end-->
          </div>
          <!--tab end / content_wrapper.tab-->
        {{/each}}
      </script>

    </div>
    <!--content_wrapper.grid end-->

  </div>
  <!--container-->

<!--CONTAINER END------------------------------------------------------->

  <script>
  //TEMPLATE LIST
  //id + selector
  var templateList = [
    ['#handlebars-template-grid', '#grid'],
    ['#handlebars-template-tabs', '.container']
  ];
  </script>

  <!--MIRROR IMAGES SHEETS SCRIPTS w/ Papa Parse-->
  <script src="https://www.dl.dropboxusercontent.com/s/6x9gqyymrb1vkyi/mirror-images-sheets-3-0-pp.js"></script>
  
  <script>
//after spreadsheet content is generated
const contentLoaded = function() {
  buildLayout();
  tabFunctions();
  feather.replace();
  $('.tooltip').tooltipster({
    side: 'right'
  });
} //end contentLoaded

//BUILD LAYOUT FUNCTION
function buildLayout() {
  $('.lds-ring').fadeOut();
  //initialise isotope
  $( document ).ready(function() {
    const $container = $(".grid_wraper"); // the container with all the elements to filter inside
  var filters = {}; //should be outside the scope of the filtering function

var $grid = $container.isotope({
    itemSelector: '.grid-item',
    masonry: {
      fitWidth: true
    }
  });

 });
var $defaults = $("a." + activeClass + '[data-filter-value=""]');
  $('.option-set a').on('click', function(e) {
   var $this = $(this); // cache the clicked link
   var comboFilter,
      filterAttr = "data-filter-value";
    if (resetClass && !$this.hasClass(resetClass)) {
      // defining variables
     var filterValue = $this.attr('filterAttr'); // cache the filter
     var $optionSet = $this.parents(".option-set"); // cache the parent element
     var group = $optionSet.attr("data-filter-group"); // cache the parent filter group
     var filterGroup = filters[group];
     if (!filterGroup) {
       filterGroup = filters[group] = [];
     }
     var $selectAll = $optionSet.find('a['+filterAttr+'=""]'); // the 'select all' button in the current group
     var activeClass = "selected", // the class for active links
         comboClass = "combine", // the class that indicates that the filter group is a chain filter, i.e. if you select two filters, only items with BOTH filters will be shown
         exclClass = "exclusive"; // the class that indicates that the filter group is an exclusion filter, i.e. you can only select one filter from that group at a time
   
  comboFiltering(
          $this,
          filters,
          filterAttr,
          filterValue,
          $optionSet,
          group,
          $selectAll,
          activeClass,
          comboClass,
          exclClass
        );
 comboFilter = getComboFilter(filters);
  if (!comboFilter.length) $("a." + resetClass).addClass(activeClass);
      $this.toggleClass(activeClass);
    } else {
      filters = {};
      comboFilter = "";
      $(".option-set a").removeClass(activeClass);
      $(this).addClass(activeClass);
      $defaults.addClass(activeClass);
    } 
  $grid.isotope({
     filter: comboFilter
   });
   e.preventDefault();
 });
});

function comboFiltering(
  $this,
  filters,
  filterAttr,
  filterValue,
  $optionSet,
  group,
  $selectAll,
  activeClass,
  comboClass,
  exclClass
) {
  // for non-exclusive groups of filters
  if (!$optionSet.hasClass(exclClass)) {
    // replace 'exclusive' with the class of your exclusive filter groups
    // if link is a filter that isn't selected
    if (!$this.hasClass(activeClass) && filterValue.length) {
      filters[group].push(filterValue); // add filter to array
      $selectAll.removeClass(activeClass); // remove the selected class from the 'select all' button
    } else if (filterValue.length) {
      // if link is a selected filter
      // remove filter from array
      // check if the filter group we're concerned with is a combination filter (.one.two instead of .one,.two)
      if ($optionSet.hasClass(comboClass)) {
        filters[group][0] = filters[group][0].replace(filterValue, ""); // delete the filter from the combined string
        if (!filters[group][0].length)
          // check if there is anything left in the string after deletion
          filters[group].splice(0, 1); // if no, remove the empty string
      } else {
        // if filter group is not a combo filter
        var curIndex = filters[group].indexOf(filterValue); // get index of filter string in array
        if (curIndex > -1) filters[group].splice(curIndex, 1); // remove the filter
      }
      if (!$optionSet.find("a." + activeClass).not($this).length)
        // if there are no remaining filters
        $selectAll.addClass(activeClass); // add the active class to the 'select all' button
    } else {
      // if link is the show all button for that group
      $optionSet.find("a." + activeClass).removeClass(activeClass); // remove the active class from all other buttons
      filters[group] = []; // clear the array of all filters
    }
    // join everything to a single string for the combined filtering groups
    if ($optionSet.hasClass(comboClass) && filters[group].length)
      filters[group] = [filters[group].join("")];
  } else {
    // for exclusive groups
    // if link is a filter that isn't selected
    if (!$this.hasClass(activeClass) && filterValue.length) {
      // run a loop for all active filters
      $optionSet.find("a." + activeClass).each(function(k, filterLink) {
        // remove all active filters in the same group from the array
        var removeFilter = $(filterLink).attr(filterAttr);
        var removeIndex = filters[group].indexOf(removeFilter);
        filters[group].splice(removeIndex, 1);
      });
      filters[group].push(filterValue); // add selected filter to array
      $optionSet.find("a." + activeClass).removeClass(activeClass); // remove the active class from all other links in the group
    } else if (filterValue.length) {
      // if link is a selected filter
      // remove filter from array
      var curIndex = filters[group].indexOf(filterValue);
      if (curIndex > -1) filters[group].splice(curIndex, 1);
      if (!$optionSet.find("a." + activeClass).not($this).length)
        // if there are no remaining filters
        $selectAll.addClass(activeClass); // add active class to 'select all' button
    } else {
      // if link is the show all button for that group
      $optionSet.find("a." + activeClass).removeClass(activeClass); // remove active class from all other buttons
      filters[group] = []; // reset all filters for this group
    }
  }
}
/* --- concat filters --- */
function getComboFilter(filters) {
  // pass the entire array of filters to the function
  var i = 0; // set counter variable as zero
  var comboFilters = []; // make a new array to save the string of filters

  for (var prop in filters) {
    // loop through all the properties in the filter array passed to the function
    var filterGroup = filters[prop]; // define variable
    // skip to next filter group if it doesn't have any values
    if (!filterGroup.length) {
      continue; // exit loop and move on with next iteration
    }
    if (i === 0) {
      // copy to new array
      comboFilters = filterGroup.slice(0);
    } else {
      var filterSelectors = [];
      // copy to fresh array
      var groupCombo = comboFilters.slice(0);
      // merge filter Groups
      for (var k = 0, len3 = filterGroup.length; k < len3; k++) {
        for (var j = 0, len2 = groupCombo.length; j < len2; j++) {
          filterSelectors.push(groupCombo[j] + filterGroup[k]);
        }
      }
      // apply filter selectors to combo filters for next group
      comboFilters = filterSelectors;
    }
    i++; // increment
  }

  var comboFilter = comboFilters.join(", ");
  return comboFilter;
}
  
  $('.grid-item').each(function(i) {
    setTimeout(function() {
      $('.grid-item').eq(i).addClass('is-visible');
    }, 100 * i);
  });

}

/*TABS*/
function tabFunctions() {
  //TRIGGER ON EVENTS
  $(".grid-item > a").on('click', function() {
    let attr = $(this).attr('href');
    openTab(attr, '.tab');
  });

  $("#sidebar_controls").on("click", function() {
    if ($(".active").is(":visible")) {
      $(".active").fadeOut(function() {
        $(".content_wrapper.grid").fadeIn();
      });
    } else {
      $('#sidebar_button').prop('checked', true);
    }
  });

  var hash = $.trim(window.location.hash);
  if (hash) {
    openTab('.tab', hash);
  }

  /*color per tab*/
  if (colorPerTab === true) {
    var i = 1;
    $(".tab").each(function() {
      let rgbColor = getComputedStyle(document.body).getPropertyValue("--accentColor-" + i);
      //if css variables is defined do
      if (rgbColor) {
        let elemID = '#' + $(this).attr('id');
        let style = document.head.appendChild(document.createElement("style"));
        style.innerHTML = elemID + " .cskills .track span, " + elemID + " .pos_traits li, " + elemID + " .neg_traits li, " + elemID + " .character_page table td::before {background: var(--accentColor-" + i + "); color: var(--accentText-" + i + ");} " + elemID + " .cconnections .overlay {background: " + hexToRGB(rgbColor, 0.3) + ";} " + elemID + " .character_page td:first-of-type { background:" + hexToRGB(rgbColor, 0.03) + ";}";
      }
      i++;
    });
  }
}

//TABS
function openTab(attr, tab) {
  var page = $(tab + attr);

  if (page.is(":hidden")) {
    $('.content_wrapper.grid').fadeOut(function() {
      page.fadeIn(800);
      $("#sidebar_button").prop("checked", true);
      page.addClass('active');
    });
  }
  loadPinterest(document);
}

/*hex to rgba*/
function hexToRGB(h, opacity) {
  h = h.slice(1);
  let r = 0,
    g = 0,
    b = 0;

  // 3 digits
  if (h.length == 4) {
    r = "0x" + h[1] + h[1];
    g = "0x" + h[2] + h[2];
    b = "0x" + h[3] + h[3];

    // 6 digits
  } else if (h.length == 7) {
    r = "0x" + h[1] + h[2];
    g = "0x" + h[3] + h[4];
    b = "0x" + h[5] + h[6];
  }

  return "rgba(" + +r + "," + +g + "," + +b + "," + opacity + ")";
}

//load pinterest boards
function loadPinterest(d) {
  var f = d.getElementsByTagName('SCRIPT')[0],
    p = d.createElement('SCRIPT');
  p.type = 'text/javascript';
  p.setAttribute('data-pin-hover', false);
  p.async = true;
  p.src = 'https://assets.pinterest.com/js/pinit.js';
  f.parentNode.insertBefore(p, f);
};</script>

  <!--ISOTOPE PLUGIN https://isotope.metafizzy.co/ (for filtering)-->
  <script src="https://unpkg.com/isotope-layout@3.0.6/dist/isotope.pkgd.min.js"></script>

  <!--FONT AWESOME-->
  <link rel="stylesheet" href="https://kit.fontawesome.com/75c12b5af9.css">

  <!--FEATHER ICONS-->
  <script src="https://static.tumblr.com/2pnwama/DLppehqvd/feathericons.js"></script>

  <!--TOOLTIPSTER-->
  <link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/tooltipster/3.3.0/css/tooltipster.min.css" />
  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/tooltipster/3.3.0/js/jquery.tooltipster.min.js"></script>

  <script>
    feather.replace();
  </script>

</body>
</html>
