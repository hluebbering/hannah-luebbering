---
title: Adding citations into Markdown 
subtitle: References to cite in Markdown document
abstract: References to cite in Markdown document
date: 2020-07-01
math: true
diagram: true
image:
  placement: 2

links:
- icon: github
  icon_pack: fab
  name: Follow
  url: https://github.com/hluebbering

---


<span style="color: #f2cf4a; font-family: Babas; font-size: 2em;">Cite in Markdown</span>

***
[<span style="color:#0c008f; font-family: Babas;">**CLICK HERE**</span>](https://github.com/benmarwick/atom-for-scholarly-writing-with-markdown) 
for more documentation

###  Collecting references to cite in Markdown document

There are two simple methods from getting scholarly references into your Markdown document: with Google Scholar, or with Zotero.

1. search for article using Google Scholar

2. select the quote icon under the article being cited

![](images/figure1.png)


3. click on Bibtex option in the following popup

![](images/figure2.png)


4. Select and copy text


5. Paste the text into a .bib file 

![](images/figure3.png)

6. Save the .bib file into the same directory as the .Rmd file


<p>&nbsp;</p>


### Adding citations into the Markdown text

Make sure the .bib file is in the same directory as the .md or .Rmd file

Then in the Markdown document,

7. Use the YAML front matter to Link the .bib file to your Markdown document


![](images/figure4.png)


<p>&nbsp;</p>

#### Convert Markdown to PDF or HTML

8. Use the YAML front matter to add the following outputs: `pdf_document` and/or `html_document`


![](images/figure5.png)

Now when you knit the markdown document, you should see that the output contains your citations in the footnote. 



### References

https://github.com/benmarwick/atom-for-scholarly-writing-with-markdown




