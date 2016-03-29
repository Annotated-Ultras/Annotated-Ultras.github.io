---
layout: post_default
kramdown:
  input: GFM
---
## Check out the demo
Use the search bar to look for specific features or just click around.  
[Demo site](http://collinschwantes.github.io/Annotated_Ultras/)

## Create an Annotated Image

updated: {{ site.time | date_to_long_string }}

Follow these instructions to create an annotated image in [inkscape](https://inkscape.org/en/) and the corresponding website. 

1.  [Fork](https://github.com/Annotated-Ultras/Template_Site#fork-destination-box) this project to create a copy for your github account or 
[Download](https://github.com/Annotated-Ultras/Template_Site/archive/master.zip) the repository and transfer the files to a folder with an appropriate name
2.  Places to find images:
    - [Specimage](http://specimage.osu.edu/)
    - [USGS Bee Inventory](https://www.flickr.com/photos/usgsbiml/)
    - [Alex Wild's Ants](http://www.alexanderwild.com/Ants/Taxonomic-List-of-Ant-Genera)
    - Please give proper attribution when necessary
3.  Open the **_data** folder and then open the **hao_terms.json** file
    -  you will notice that each entry has 5 attributes including a unique `ID`  
    
    ```
    {  
    "title": "Antenna",  
    "definition": "The appendage that is composed of ringlike sclerites and the anatomical structures encircled by these sclerites and that is articulated with the cranium.",  
    "URI": "http://purl.obolibrary.org/obo/HAO_0000101",  
    "Preferred.Term": "antenna",  
    "ID": "HAO_0000101"  
    },  
    ```

    -  Leave this file open, you will use it as you annotate the SVG
5.  Open template.svg from the **_includes** folder with inkscape
6.  Import (`ctrl+i`) the image file from the **images** folder into template.svg 
    - select **embed**
    - resize the image to fit within the page (solid lines) 
    - alternatively, you can resize the document (`ctrl+shift+d`) to fit the image
7.  Save the document as a plain SVG and rename it
7.  Start by outlining larger features - order is important for the click functionality 
    - Pressing `B` will bring up the bezier tool, this allows you to place points around a feature and modify them to create curves. 
    - `ctrl l` autosmooths the shape
8.  After you have outlined the segment, change the fill `ctrl+shift+f` to RGBA **97cafcff** and the stroke to none
    * use `ctrl d` to bring up the dropper tool 
    * holding shift with the dropper tool allows you to change the outline color
9.  Select the feature you just created (quickly switch to the selection tool by pressing `S`) and press `ctrl+shift+x` to open the XML editor. 
    - press `ctrl g` to make a new group (do this even if the feature is a single path)
    - ![xml editor](https://raw.githubusercontent.com/collinschwantes/Annotated_Ultras/master/Screenshot%202016-03-21%2013.00.40.png)
10. Click on `id` in the Name column
    - ![xml editor selected](https://raw.githubusercontent.com/collinschwantes/Annotated_Ultras/master/Screenshot%202016-03-21%2013.05.37.png)
11. Change the group id to the proper id in **HAO_terms.json**
    - ![xml editor changed](https://raw.githubusercontent.com/collinschwantes/Annotated_Ultras/master/Screenshot%202016-03-21%2013.07.36.png)
    - *NOTE* use `ctrl v` to paste in inkscape
    - click `set` to change the id
12. Give the feature the `class` "bodypart" by entering "class" into the attribute name bar and "bodypart" into the attribute value box
    - ![xml editor class](https://raw.githubusercontent.com/collinschwantes/Annotated_Ultras/master/Screenshot%202016-03-21%2013.23.56.png)
    - click `set` to change the class
    - this a good place to save
13. Repeat steps 7-12 until all visible HAO terms have been added. 
14. Open your SVG in a text editor (eg TextEdit or NotePad) and delete the first line 
    - delete the line selected in this image
    - ![textedit_delete](https://raw.githubusercontent.com/collinschwantes/Annotated_Ultras/master/Screenshot%202016-03-21%2013.31.42.png)
15. Copy the remaining text and paste it into the file `svg.html` that lives in the **_includes** folder 
    - You can use TextEdit for this as well
    - If there is already text in the `svg.html` file, replace it with the new svg text
16. Open `index.html` and change the title
17. If you have downloaded the files and this is your first time working on them, log on to github and click the new repository button
    - Initialize with a read.me and write something nice about your image
    - click create repository
    - drag and drop all the files into your repository
      - *do not add the containg folder*   
18. If you are doing everything in github, change the name of your repository in the **settings** tab
19. Create a new [branch](https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/) in your repository called `gh-pages`
19. Request that your annotated image be added to the organization page and pat yourself on the back. 

## Running the site locally

This site is built with [jekyll](https://jekyllrb.com/). 

To run the site locally make sure that jekyll is installed 
`gem install jekyll`

`which -a jekyll` should return a ruby shim path (not a blank)
and/or running `jekyll` returns a list of options

Navigate to the folder in the commandline `cd path/to/folder` 

After that, `jekyll serve` should boot up the site at localhost:4000


If that doesn't work. Check out the instructions for installing jekyll [here](https://jekyllrb.com/docs/installation/) 

If you don't have rubygems installed you might need to install the following:  

*  [Homebrew](http://brew.sh/)
*  [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
*  [Rubygems](https://rubygems.org/pages/download)
