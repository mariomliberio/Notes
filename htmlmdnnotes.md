# Working with HTML
***
**Notes from the start**
###### cos why not. 

- Metadata: Present in our ```<head>``` tags. We signal metadata with our ```<meta>``` tags. Most common example is character encoding ```<meta charset="UTF-8">```. Necessary element for our browser to display text. Meta elements often have ```name=""``` & ```content=""``` attributes. For example let's add an author and a description: 
```
<meta name="author" content="Mario Liberio">
<meta name="description" content="This is our basic HTML notes markdown file.">
```
- ! Advanved note: Specifying keywords in your description ```<meta>``` tag is a good way to improve SEO (search engine optimization).

- Other types of metadata: Open Graph Data. Invented by facebook. Specially useful when sharing your website to a social media like facebook. For example: 
```
<meta property="og:image" content="https://cdn.tutsplus.com/webdesign/authors/ian-yates/howdy.png">
<meta property="og:description" content="These are my notes in HTML, I will do the following aswell for CSS & Vanilla JS maybe even PHP if i find better sources">
<meta property="og:title" content="Mario HTML notes">
```
- Twitter also has their own propietary metadata system. It looks like so:
```
<meta name="twitter:title" content="Mario HTML notes">
```
- Adding Favicon's to your site!: Favicon's are 16x16 px images which can be used in many places, for example on your browser bar next to your url and in your bookmarks. Adding a favicon is pretty simple, you only need to:
    1. Saving it in the same directory as your index.html file. Usually saving it in ```.png``` or ```.svg``` is the most normal, however if you want to make sure all legacy browser are compatible, you can save this image in ```.ico``` format.
    2. Adding the following tags to your HTML head: ```<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">``` (Note: your href, can also be an url.)
- However there are other types of 'fav'icons out there nowadays such as icons formatted for ipad's, for iphone & android phone's etc. Here is an example of other ```<link>``` tags targetting these specific devices:
```
<!-- third-generation iPad with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="144x144" href="your144iconhere.png">
<!-- iPhone with high-resolution Retina display: -->
<link rel="apple-touch-icon-precomposed" sizes="114x114" href="your114iconhere.png">
<!-- first- and second-generation iPad: -->
<link rel="apple-touch-icon-precomposed" sizes="72x72" href="your72iconhere.png">
<!-- non-Retina iPhone, iPod Touch, and Android 2.1+ devices: -->
<link rel="apple-touch-icon-precomposed" href="youridkwhichsizebutohwellicon.png">
<!-- basic favicon -->
<link rel="shortcut icon" href="favicon.png">
```
- While it is not vital to create high resolution icons for each specific device, if you want your user's experience on these devices to be optimized it is recommandable.
***
**Linking CSS & JS to your HTML**
- If you wanna make a decent website you are going to need to use some CSS and some JS in order to have a styled layout and interactivity.
- The ```<link>``` tag always goes inside the ```<head></head>``` of your document, it takes two attributes rel="stylesheet" and href="" like so: ```<link rel="stylesheet" href="style.css">```
- The ```<script>``` tag does not necesarily go in the head, actually it is recommended to be inserted at the bottom of a document body, just before the closing ```</body>``` tag, to make sure that all html has been loaded before the javascript script is executed. It looks like so ```<script src="main.js"></script>``` Make sure to always close your script tag, it may look empty but it is loading the javascript code in that space. Because of that you could also put your javascript code simpy inside ```<script>yourjscode</script>```.
***
**Setting the language of your document**
- Finally it is important to tell your web browser which language is the content displayed in. 