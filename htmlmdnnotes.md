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
- It is important to underline that ```<a>``` tags are also used when we are linking our website with other pages in our domain. Therefore folder path and structure are crucial to this. For example if we were linking to another page on the same domain and on the same folder we would just do like so: ``` <a href="contactpage.html">Contact</a>```.
- However it is also possible we put the linked page inside a folder, for organization purposes. Lets say we have a media folder with html pages for pictures and video. If we want to link to any of these two pages we have to first specify the folder they are contained in and then the actual page name like so: ```<a href="media/pictures.html">Pictures</a>``` 
- Now imagine we are in our videos html page but we want to go to our contact form which is located inside a contact folder outside of our media folder.. We would have to specify the parent directory, however there is an extra detail we need to add to make our link go back to the main page and then into our contact folder and our contact html page. To go back to our parent directory we use ```..```. An example would look like so:
``` <a href="../contact/contact.html">Contact Form</a>```.
#### And what if we want to link another part of the same page?
- We can do this by giving an ```id``` to a specific part of the page. For example say we are making a one page website for an artist and we have different sections in one page, one for his portfolio, one for his contact form etc etc. We would give the ```<div>``` containing these areas a unique id eg. ```<div id="portfolio"></div><div id="contactarea"></div>```. To link these pages from the navigation bar we would create an ```<a>``` tag like so: ```<a href="#portfolio">Portfolio</a>```.
- We can also link a specific part of another page using the same tools as we previously showed and the id marker. ```<a href="contact.html#contactform">Contact us</a>```.
#### How about downloading files?
- When linking to files such as PDF, MP3, or DOC we should specify this inside our ```<a>``` tag to avoid people on low bandwith downloading something that would be uneccesary and too time consuming. Therefore if we were linking to an MP3 it would be best practice to do it like so: ```<a href="http://www.example.com/song.mp3"> Download the song (MP3, 10MB)</a>```.
- We can also provide a default filename when linking to a download using the ```download=""``` attribute inside our ```<a>``` tags. Eg.: ```<a href="http://www.example.com/song.mp3" download="sicksongbro.mp3">Download the song (MP3, 10MB)</a>```.
#### And email links?
- It is also possible to create links that will open a new email to a specific address instead of linking to a page, pagesection or file. For example: ```<a href="mailto:cunt@gmail.com"> Send an email to Cunt </a>```
- The email address itself is optional, if our href contains the ```mailto:``` text it will generate a new blank email to send without a destination address.
- However we can also specify more in our ```mailto:``` sections for example a series of CC's, a Subject and an email Body. We can do this like so: ```<a href="mailto:cunt@gmail.com?cc=prick@gmail.com&cc=asshole@gmail.com&subject=You%20are%20a%20bunch%20of%20little%20shits&body=Hello%20Assholes"> ```
- This previous example would send a mail to cunt, prick and asshole with the subject You are a bunch of little shits and the body of Hello Assholes. 
***
**Advanced Text Formatting**
- We are going to review some less known HTML elements which are not necessary to create a basic website, however they can be handy to execute specific roles for text without the need to style them through CSS.
#### Description Lists
- Used for terms and definitions or questions and awnsers. Use different tags compared to ordered and unordered lists but are based on the same principles.
- Description lists are contained inside ```<dl>``` tags, once again same principle as ```<ol>``` and ```<ul>``` tags. Inside these tags we have two types of elements: Description terms ```<dt>``` and description definitions ```<dd>```. Here is an example straight outta the MDN:
```
<dl>
  <dt>soliloquy</dt>
  <dd>In drama, where a character speaks to themselves, representing their inner thoughts or feelings and in the process relaying them to the audience (but not to other characters.)</dd>
  <dt>monologue</dt>
  <dd>In drama, where a character speaks their thoughts out loud to share them with the audience and any other characters present.</dd>
  <dt>aside</dt>
  <dd>In drama, where a character shares a comment only with the audience for humorous or dramatic effect. This is usually a feeling, thought, or piece of additional background information.</dd>
</dl>
```
- As you can see this is pretty simple, if you test it in an HTML document you will see it creates a nice formatting style which helps readability when dealing with questions and awnsers (useful for FAQ's) and terms and definitions (useful for technical websites). It is important to underline that a description term can contain several description definitions.
 
#### Quotations

- There are several types of quotations we can use in HTML such as ```<blockquotes>```, ```<code>``` and others. Let's go through them.

**Blockquotes**

- If you are quoting text from an external source it is nice to use ```<blockquote>``` tags to mark this in HTML formatting directly. For example:
```
<blockquote>
  <p>To be fair, you have to have a very high IQ to understand Rick and Morty. The humour is extremely subtle, and without a solid grasp of theoretical physics most of the jokes will go over a typical viewer’s head. There’s also Rick’s nihilistic outlook, which is deftly woven into his characterisation- his personal philosophy draws heavily from Narodnaya Volya literature, for instance. The fans understand this stuff; they have the intellectual capacity to truly appreciate the depths of these jokes, to realise that they’re not just funny- they say something deep about LIFE. As a consequence people who dislike Rick & Morty truly ARE idiots- of course they wouldn’t appreciate, for instance, the humour in Rick’s existential catchphrase “Wubba Lubba Dub Dub,” which itself is a cryptic reference to Turgenev’s Russian epic Fathers and Sons. I’m smirking right now just imagining one of those addlepated simpletons scratching their heads in confusion as Dan Harmon’s genius wit unfolds itself on their television screens. What fools.. how I pity them. 😂

  And yes, by the way, i DO have a Rick & Morty tattoo. And no, you cannot see it. It’s for the ladies’ eyes only- and even then they have to demonstrate that they’re within 5 IQ points of my own (preferably lower) beforehand. Nothin personnel kid 😎</p>
</blockquote> 
```
- As seen above the OG Rick & Morty copypasta is formatted to see that we are not the author of this infamy.

