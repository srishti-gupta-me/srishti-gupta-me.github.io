---
layout: post
title:  "Jekyll Resources to Build Your Page!"
date:   2021-05-28 05:38:32 +0530
categories: jekyll update
---

Firstly, building a Jekyll Github Page took me quite sometime (around 2 days, distributed over a week's time) even when I had some HTML and CSS experience. This means that if you read it is very easy for others don't stop feeling that you can't do it. I faced a lot of issues, and particularly that my webpage was developing fine locally, but not on remotely. Means that I was not able to host it on Guthub Pages. 

This is a resource directory I used to create a page like this. Refer to them in order or as you like. 

1. [Mike Dane](https://www.youtube.com/watch?v=gsYqPL9EFwQ) I learnt mostly from his videos. He explains step-by-step and it will be good to do things with him.

2. However, if you like me are able to build the website locally(on the server that is run from your computer) but when you take it to Github pages the CSS vanishes. CSS vanishes means that design is removed and you are mostly see plain text spreading on the sheet, then this source may help you [CSS Vanish](https://github.community/t/css-not-being-applied-in-pages/10466).Root cause for mine was cache and I also learnt the other problems that might be the root cause for the failures. Most useful and thorough answer is by *Tammy Metz (tmetz)*<br>

3. [To embed files](https://www.w3docs.com/snippets/html/how-to-embed-pdf-in-html.html) like pdfs, for example by Resume. 


4. [How to delete Git Repository](https://www.w3docs.com/snippets/git/how-to-delete-git-repository-created-with-init.html) . This was also my first experience working with git and I created many repositories and ended up deleting all and restarted the whole process. At this point it will be good to have some knowledge on git, [see this resource](https://www.atlassian.com/git/tutorials)


**Updated on 26th June 2021**

**Favicons**: I have been trying to upload favicon to my webpage. Well, what is Favicon?? <br>A favicon, also known as a shortcut icon, website icon, tab icon, URL icon, or bookmark icon, is a file containing one or more small icons, associated with a particular website or web page.So the small image or icon on the leftmost side of the tab that you can see (is my image). 

It took me more than 24 hours distributed over days to implement it. Understanding was easier, but in my case the solution given online weren't working. Once I was able to get the Favicon on my website, but the whole CSS vanished. Will explain reason behind this. At this point understanding about [layouts is good](https://learn.cloudcannon.com/jekyll/introduction-to-jekyll-layouts/). Using layouts help in avoiding repetition and utilising existing layouts/designs to build pages. 

1. To get favicon on your website, you need your image/test/emoji to be converted into a format that can be utilised by the browser for displaying. There are online websites that do the task for you. Like [Favicon Generator for perfect icons on all browsers](https://realfavicongenerator.net/)
2. The site is intuitive, you have to upload your image (which you want to display as favicon). The generator will process and suggest you to give another picture if dimensions aren't right or suggest to add margin and proceed with the current selection. Any option will have you created your favicon, look may asethically change.
3. Now, it will display how your favicon will look on different browsers and devices. Against every browser and device (ios, android chrome, safari.. etc) it will give you options to improve the look of favicon as per choice and decide whether you want to keep it or not. 
4. Once you are done, at the last *Favicon Generator Options* asks you the path you want. This will help generate the right code to be placed in html files for browser to display favicons. Root Directory here means where your *index.md* or *index.html* file is present.
     
     1. Many Jeykll Themes (if you are following [Mike Dane](https://www.youtube.com/watch?v=gsYqPL9EFwQ), you might be using the default theme: minima) recommend that static files (pdf, images) should be kept inside *assets* folder/directory. In that case, in above point number 4 choose option 2 (I cannot or I do not want to place favicon files at the root of my web site. Instead I will place them here:) 
     2. What path to give?? If you want to keep in *assets* then **/assets** is your path
     3. There are additional options also like Version/refresh, Compression. You can opt as per choice or leave it default only, unselected. 

5. Now *Generate Favicons and HTML Code*, this will download a zipped file and give a block of code. 
6. 




