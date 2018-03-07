# Working with HTML
***
**Notes from the start**
###### cos why not. 
***
**Metadata**

- Metadata is Present in our ```<head>``` tags. We signal metadata with our ```<meta>``` tags. Most common example is character encoding ```<meta charset="UTF-8">```. Necessary element for our browser to display text. Meta elements often have ```name=""``` & ```content=""``` attributes. For example let's add an author and a description: 
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
- Finally it is important to tell your web browser which language the is content displayed in. 
- We can do this by giving the ```lang=""``` attribute on our opening html tag like so ```<html lang="en-US">``` if our document is written in American English.
***
**Headings & Paragraphs**
- In HTML each paragraph is located inside ```<p></p>``` tags.
- Headings are located inside ```<h1></h1>``` tags. Headings tags are made up of ```h``` and a number ranging from 1-6 depending on how important our heading is and how we want it to be displayed. To clarify ```<h1></h1>``` will be used for the main title of the page. ```<h2></h2>``` will be used for sub-headings.```<h3></h3>``` for subsubheadings and so on until ```h6```.
- Obviously we could modify any heading be it small or large to a different size and style using a css document or ```<h1 style="">``` attributes. But this built-in heirarchy should not be ignored even if we can alter it. It helps keeping a simple internal structure and makes code easily readable for others.
***
**Lists**
- There are two types of lists in HTML: Ordered & Unordered.
    1. Ordered lists use ```<ol></ol>``` tags.
    2. Unordered lists use ```<ul></ul>``` tags.
- Elements inside a list are called list items and use ```<li></li>``` tags, doesnt matter if we are using ```<ol>``` or ```<ul>```.
- Nesting lists: It is perfectly fine to put lists inside of lists. Let's look at the example hummous reciepe that the MDN provides us:
```
<ol>
  <li>Remove the skin from the garlic, and chop coarsely.</li>
  <li>Remove all the seeds and stalk from the pepper, and chop coarsely.</li>
  <li>Add all the ingredients into a food processor.</li>
  <li>Process all the ingredients into a paste.
    <ul>
      <li>If you want a coarse "chunky" hummus, process it for a short time.</li>
      <li>If you want a smooth hummus, process it for a longer time.</li>
    </ul>
  </li>
</ol>
```
- As you can see if you text this snippet in an HTML file it works perfectly fine and gives us an unordered list as one of the list items in an ordered list.
***
**Emphasis and Importance**
- If we want to use italics or bold in HTML directly without the use of ```style=""``` attributes or CSS, we have tags for that!
- Let's start with emphasis! Elements contained in ```<em></em>``` tags will be displayed in *italic* , Remember in HTML *emphasis* = *italic*.  For example:
```
<p>This is an example sentance using <em>emphasis</em> tags</p>
```
- As you can see the word emphasis is nested inside ```<em></em>``` tags which means that it will be displayed in Italic. 
- We can continue with importance! In HTML **importance** (or sometimes called strong importance) is the same as **bold**. We show importance through the usage of ```<strong></strong>``` tags. For example:
```
<p>American's are <strong>FAT</strong></p>
```
- In an HTML document, the word **FAT** would appear in bold now thanks to ```<strong>``` tags. 
- We can combine these tags and nest them inside each other, just like pretty much anything in HTML. 
***
**Creating Hyperlinks**
- Hyperlinks are the bread and butter of the internet. At the end of the day, this technology allows us to connect different points of information and link it to each other, recontextualizing its purpose. 
- To link to another page, on our website or outside we use ```<a>``` tags.
- For example if you wanna create a link to the stib website to check bus times we would do it like so:
```
<p> Check the <a href="http://m.stib.be"> Bus times</a> </p>
```
- As you can see the words Bus times would link us to the STIB's mobile website therefore allowing us to open a new tab and check bus times. 
- We can nest hyperlinks inside any element in HTML not only text. 
- We can also give this link a ```title=""``` attribute. Content inside this title attribute is what we see when we hover over a link in any webpage. Let's update our previous example:
```
<p> Check the <a href="http://m.stib.be" title="Stib's mobile website to check bus, metro & tram times"> Bus times</a> </p>
```
- If you insert this into an html document you would see that when we hover over the words Bus times the content of our title attribute will pop up in a little box next to our cursor. 
- This can be useful if we want to give our users a little preview of what is the website which we redirect them to if they click that link.
#### What about when we want to link another page on our website?
- t