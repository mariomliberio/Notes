# Working with HTML &#129303;
***
**Notes from the start**
###### cos why not. 

- Best way to familiarize yourself with HTML (& programming languages, not only markup) is to look at existing code. So go on a website that hasnt been created with a cms (content management system like wordpress or wix) and view their source. Reading code is the best way to learn!

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

**Inline Quotations**

- We can also create a quotation inline inside our paragraph. To do this we use the ```<q>``` tags. This will simply add quotation marks to the text inside the ```<q>``` tags. 

**Abbreviations**

- ```<abbr>``` tags are used to contain the full names of abbreviations inside your HTML text. Using the abbreviation tag with a title attribute inside it allows us to see the whole text it represents when we hover over it. Here is an example: ``` <abbr title="Hyper Markup Text Language">HTML</abbr>```

**Contact Details**

- HTML has an inbuilt tag for marking up the contact address of the author. This is the ```<address>``` tag. Here is an example:
```
<address>
  <p>Mario Liberio, Cock street, Brussels</p>
</address>
```
- Remember this element is supposed to be used for the author of the document, not any address.
- Inserting an ```<a>``` tag inside our ```<address>``` tags redirecting to a contact page is also OK.

**Superscript and Subscript**

- Ocasionally you will need to use superscript or subscript in your HTML documents, especially if you are dealing with Mathematics or Science. For that purpose we use the ```<sup>``` & ```<sub>``` tags. For Example:
```
<p>My Birthday is on the 1<sup>st</sup> of December.</p>
<p>Water's chemical formula is H<sub>2</sub>O</p>
```

**Representing computer code**

- There are numerous ways of representing computer code in HTML:
  1. ```<code>```: For representing generic snippets of code.
  2. ```<pre>```: For retaining whitespace in code blocks, can be very useful when working with JSON data for  example. We will use this again in the future in our JS notes.
  3. ```<var>```: For specifically displaying variables.
  4. ```<kbd>```: For marking up (keyboard) input into the computer.
  5. ```<samp>```: For displaying output of a computer program.


**Time & Dates**

- ```<time>``` Used for specifically marking up time and dates. With the use of the ```datetime=""``` attribute we can become more specific on the time that will be output. Here are some examples from the MDN:
```
<!-- Standard simple date -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- Just year and month -->
<time datetime="2016-01">January 2016</time>
<!-- Just month and day -->
<time datetime="01-20">20 January</time>
<!-- Just time, hours and minutes -->
<time datetime="19:30">19:30</time>
<!-- You can do seconds and milliseconds too! -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- Date and time -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- Date and time with timezone offset -->
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
<!-- Calling out a specific week number -->
<time datetime="2016-W04">The fourth week of 2016</time>
```
***

**Document & Website structure**

- Although Websites can have many different layouts and display information in different ways, they all generally follow certain structural components:  
  1. Header: Usually a stripe at the top of the webpage, Logo goes here.
  2. Navbar: Links to the site's main section, often merged with header. Can be present at the top of the website or on the right in most cases.
  3. Main content/Body: Central area which contains most of the website's content. Part of the website which will vary from page to page. 
  4. Sidebar: Peripheral info such as links, quotes, advertisement can be used instead of a navbar in some websites. Contians recurring elements across pages.
  5. Footer: Bottom of the website can containe fine print and legal information, a sitemap, notices or contact info. Place to put non-critical/secondary recurring information. Sometimes used for SEO to link useful information. 

**Structuring content with HTML**

- To implement the semantics discussed before we have our own HTML tags for each section. These can be used to contain the rest of elements that make up a website. 
  1. Header: ```<Header>```
  2. Navigation Bar: ```<navbar>```
  3. Main Content: Most commonly used is ```<div>``` (divider). Many web developers use ```<div>``` tags combined with classes and id's to divide all of the content in their website, including the other sections ennumerated here. ```<article>``` & ```<section>``` can also be used. 
  4. Sidebar: ```<aside>``` (rarely used irl)
  5. Footer: ```<footer>```

- Important! : All of these tags go inside the ```<body>``` tags of an html document. 

**Less common structure tags in detail**

- Although it is never necessary to use most of these tags (as mentioned before most webdev's use ```<div>```); here are some of the previous tags explained in more detail. 

- ```<main>```: Used for content unique to the page. Use it only once per page.
- ```<article>```: Encloses a block of content that makes sense on its own.
- ```<section>```: Similar to article, used more to group a single part of the page which contains one piece of functionality. 
- ```<aside>```: Contains content that is generally not related to the main content but can link us to it or indirectly reference it. 
- ```<header>```: Represents a group of introductory content. Can define a global header or the header of a section. 
- ```<nav>```: Contains the main navigation information of a webpage. 
- ```<footer>```: represents the ending content of a webpage.

**Non-Semantic wrappers**

- Usually favored by web-developers (except maybe in the case of ```<nav>``` & ```<footer>``` tags) Non-semantic wrappers are used throught all sections of a webpage to divide content and apply specific style rules through the use of class attributes and CSS. The main two non-semantic wrappers are ```<div>``` & ```<span>```.

- ```<div>```: Div (for divider) is the most common wrapper in 2018 websites. It is used (and often abused) when another tag is not available for that content. Usually through the use of a class it will be specified to what this ```<div>``` wrapper refers too. While a lot of web developers use ```<div>``` for everything and anything it is usually recommended to use only if another specific HTML tag does not exist for what you want to do. 

- ```<span>```: Is an inline non-semantic wrapper. It is used mostly in combination with a ```class=""``` attribute to change the styling of a specific piece of content inside another one. For example:
```
<p>The King walked drunkenly back to his room at 01:00, the beer doing nothing to aid
him as he staggered through the door <span class="editor-note">[Editor's note: At this point in the
play, the lights should be down low]</span>.</p>
```

**Line breaks & Horizontal Wrappers**

- Used occasionally, these two elements will help you structure text and content in a clean and quick way. 

- ```<br>```: Creates a line break in a paragraph. Only way to force a rigid structure where you want short lines. Used extensively if you would like to markup poetry. Also used extensively when echo'ing in php.
- ```<hr>```: Horizontal rule. Displays a horizontal line therefore creating a separation between different pieces of text. 

***
**Debugging HTML (LOL)**

- Tbh this title made me cringe and I thought about skipping this part, but the mdn includes it in its basic tutorial so might aswell include it.

- HTML is permissive! It is interpreted not compiled (compared to actual programming languages).

- Two main types of errors:
  1. Syntax errors: Spelling errors in your code. Usually easy to fix if you know a language.
  2. Logic errors: When spelling is correct but a program does not run, these are logic errors. Harder to fix than spelling errors especially when a programming language doesn't or barely gives you information on what the error is. 

- In html you wont get syntax errors therefore if you make one, content may not be displayed as intented but it wont make your page crash and not be displayed at all. 

- Most common error in HTML is forgetting a closing tag. Another common error is forgetting double quotes when giving an attribute. 

- Best way to check if your HTML code is error less is to use a validator! The w3c offers this [https://validator.w3.org/](Markup Validator) to check no errors are present in html.
***

### Multimedia and Embedding

***

**Images in HTML**

- In order to put images in an HTML page we use the ```<img>`` tag. This tag doesn't have a closing tag unlike all of the ones we've seen before. It doesn't contain any text either.

- It requires at least one attribute: ```src=""``` meaning source. This is similar to ```href=""``` when creating hyperlinks. 

- If our image is in the same directory as our html page the only thing we need to do is give the filename in the ```src=""``` like so: ```<img src="panda.jpg">``` This will display our image of a panda. 

- If we have a separate images directory for organization we simply have to adapt our source like so: ```<img src="images/panda.jpg">.

- If our image is in a parent directory like so: ```<img src="../panda.jpg">```.

- And if our image is in a separate directory which is located in the parent directory like so: ```<img src="../images/panda.jpg">```.

- We can also use a link to another website as our source like so: ```<img src="http://www.images.com/panda.jpg">``` However you should try to avoid this and keep your images in your directories. 

**Alternative text attribute**

- Similar to attributes when creating hyperlinks, the ```alt=""``` attribute  will  replace the image in the case that the image is not loading onto our website hence the name alternative text. For example:
``` 
<img src="panda.jpg" alt="A panda.">
```

**Width & Height**

- You can directly insert ```width=""``` & ```height=""``` attributes onto an image tag. However if we want to keep in mind mobile responsiveness and adaptability, it is better to do this through CSS. If you still want to use width & height attributes in HTML it is important to know the units used are pixels. However, I strongly recommend you to ignore this and use responsive images in CSS through media queries.

**Image Titles**

- Same as our ```title=""``` attribute with hyperlink's, in ```<img>``` elements it will create a hover box with information about our image. We could use the same information as with our ```alt=""``` attributes for coherence. 

***

**Annotating images with figures and figure captions**

- A good solution to create figures and figure captions in HTML was introduced in HTML5 with the ```<figure>``` & ```<figcaption>``` tags. This could previously be done with ```<div>``` tags however it is prefered to use semantically related tags like ```<figure>```. Here is an example:
```
<figure>
  <img src="images/dinosaur.jpg"
       alt="The head and torso of a dinosaur skeleton;
            it has a large head with long sharp teeth">
  <figcaption>A T-Rex on display in the Manchester University Museum.</figcaption>
</figure>
```
- A figure doesn't need to be an image, it is an independent unit of content which can express your meaning in a compact way and provide essential information to your main text.

- Figures can be several images, audio, a code snippet, video, equations, a table and so on and so forth.

***

#### Audio & Video content 

- Thanks to HTML5 we can now insert audio and video directly using the ```<audio>``` & ```<video>``` tags.

***

**Video elements**

- The ```<video>``` tags allow you to set a video element really easily. The two main attributes are ```src=""``` and and ```controls```.
  1. ```src=""``` works in the same way as it would with an img element, specifying a path to the desired content.
  2. ```controls``` allows us to use the browser's inbuilt video controls for playing, pausing, controlling volumen and navigating through video content. 

- We can insert ```<p>``` tags inside the video tags as fallback content. This text will be displayed if the video cannot be loaded for a certain reason. 

**Video Formats**

- See mozilla's [Compatibility table](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility).
- It is recommended to use H.264 encoded mp4's as they are supported most widely. However these are propietary codec's so it is recommended to not use them if we are concerned about using only open source tools. 

#### So how do we support multiple codecs and formats for our videos??

- We can take the source attribute out of the video tag and make it a ```<source>``` tag directly inside the ```<video>``` tag. 

- Inside our source tags we can then specify the actual source with a ```src=""``` attribute and its corresponding filepath.

- Inside our source tags we also have to give a ```type=``` attribute. This specifies the video type and therefore browser can directly skip the  possible unsupported formats. Let's look at an example:
```
<video controls>
  <source src="rabbit320.mp4" type="video/mp4">
  <source src="rabbit320.webm" type="video/webm">
  <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
</video>
```

 **More features for our videos.**

- These are not the only features present for our videos. We can also add a whole series of conditions. For example we can define:
  1. ```width=""``` & ```height=""``` Although i would rather do this in CSS for complaince with all types of screen sizes.
  2. ```autoplay``` to make the video play on load. 
  3. ```loop``` to make the video loop.
  4. ```muted``` to make our video mute by default
  5. ```poster=""``` this attribute takes the url of an image so it is displayed before the video is played.
  6. ```preload=""``` Can be set to 3 different values: 
    - ```"none"```: Does not buffer the file. 
    - ```"auto"```: Buffers the file.
    - ```"metadata"```: Only buffers the metadata for the file. 

**The ```<audio>``` element**

- Works in the same way as the video element with some slight differences.
  1. It does not support the ```width=""``` & ```height=""``` attributes.
  2. There is no ```poster``` attribute. Although you could just stick an image on top of it and remove it onclick with javascript to recreate the same effect.

**Displaying video text tracks**

- It is important to think about accesibility when developing a website. For example, many people have auditary impediments which difficult hearing audio from a video. It can also be that the video is being played in a loud public environment or that a person is learning the language in which the video is recorded.

- Thanks to HTML5 we can provide a transcript of the contents with the ```<track>``` tag & ```WEBVTT`` format.

- WEBVTT is a text file format for displaying text on video. It is often used for subtitles, captions & timed descriptions. A typical WEBVTT text file looks like this:
```
WEBVTT

1
00:00:22.230 --> 00:00:24.606
This is the first subtitle.

2
00:00:30.739 --> 00:00:34.074
This is the second.

  ...
```
 #### So how do we link a vtt file with our video?

 - First we save the .vtt file in a sensible place, like the same directory as the page of the video.
 - Then we link it using ```<track>``` tags. This has to be placed inside ```<audio>``` or ```<video>``` tags after the ```<source>``` elements. We assign it 3 attributes to specify this content:
  1. ```kind=""```: Which can take a value of ```subtitles```, ```captions``` & ```descriptions```.
  2. ```src=""```: Which specifies the filepath.
  3. ```srclang=""```: Which specifies the language of this text.

  ***

  **Object, iFrame & other embedding Technologies**

  **```<iframe>```**

  - 