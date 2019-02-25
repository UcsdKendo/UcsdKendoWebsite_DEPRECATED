# Kendo Club at UCSD Webpage
This repository contains the code for the Kendo Club at UCSD webpage.

## Getting Started
To begin editing:
1. Clone the repository: `https://github.com/UcsdKendo/UcsdKendoWebsite.git`
2. Create a new branch: `git checkout -b [new branch name]`
3. Edit files

## Directory
#### `/css`
This folder contains the CSS for the webpage. If you need to change any styling, files in here will be where you want to look.

#### `/img`
This folder holds all the pictures on the webpage. To reference images in this folder use the path `img/[image file name]`.

#### `/img/achievement`
This folder holds the pictures in the Achievements section. Unfortunately, this template uses a very specific size for the icons. Specifications will be stated in the changes section.

#### `/img/gallery`
This folder holds the pictures in the Gallery section. Any photos with the file name `[name]_i.jpg` is used as an icon. Again these icons need to follow the size 900 x 650 if you want to keep the proportions. Resize photos accordingly.

#### `/img/portfolio`
This folder contains stock images you may use for fillers.

#### `/img/coaches`
This folder should hold pictures in the Coaches section. As of now, it is empty because that section was not entirely complete. To reference images in this folder use `image/coaches/[image file name]`.

#### `/js`
This folder contains the JavaScript code for the webpage. You probably don't need to change anything here unless you plan to change the functionality of the website.

#### `/less`
This folder does not need to be touched.

#### `/mail`
This folder contains the PHP code for the Contact Us portion. It should forward the message sent in the webpage to our team email.

#### `/vendor`
This folder contains dependencies. This folder does not need to be touched unless you have new dependencies.

#### `.gitignore`
This file is used to list files and folders that you do not want to push into the repository. You probably don't need to change anything here.

#### `gulpfile.js`
You probably don't need to change anything here. 

#### `index.html`
This file is where the webpage lives. **You will be doing most of your changes here**.

#### `package.json`
You probably don't need to change anything here, unless you are adding dependencies.

#### `README.md`
This file contains what you are reading.

## Making Changes
You can see the changes you make as you make them. Simply drag the `index.html` page into your browser. You should see a local copy of the webpage. Every time you make a change, refresh that page and you should see it reflected.

At the end of your update, make sure to change the year in the footer to the current year. You can do so by going to line 523 or searching for `div class="footer-below"`. You will see the copyright text and year, change accordingly.

### Cover Picture
1. Name your image `UCSDKendoLogo.png`.
2. Place your image into the `img` folder.
3. Refresh page and see if you like it.

### Officers
Lines 98 - 117 contains the code for the officers section. The tag `<b>...</b>` contains the officer title in bold and the name following the tag is the officer.

Lines 107 - 110 is the left column and lines 111 - 114 is the right column. To add new offices, add:
```
<br><b>[office title]</b> [officer name]
```
after the previous officer name in the respective column. To delete offices, delete the respective
```
<br><b>[office title]</b> [officer name]
```

### Coaches
Lines 120 - 161 in `index.html` contains the icons for the coaches section. Code to change the modal information is in the modal section at the bottom of the file.

#### Add a coach
You can also replace the information respectively so you do not need to add a whole new icon and modal. The information to change would be in the divs mentioned below. You can change the details and images accordingly.

##### Add a coach icon
1. Place icon image into `img/coaches` folder. Make sure image is 900 x 650.
2. Place the code below at the end of the `<div class ="row">`.
```
<div class="col-sm-4 portfolio-item">
    <a href="#coachModal1" class="portfolio-link" data-toggle="modal">
        <div class="caption">
            <div class="caption-content">
                <i class="fa fa-search-plus fa-3x"></i>
            </div>
        </div>
        <img src="img/portfolio/game.png" class="img-responsive" alt="Cabin">
    </a>
</div>
```
3. Change `"#coachModal[number]"` to the next number. 
4. Place the image file name in `<img src="[image file name]" class="img-responsive" alt="Cabin">`. The file name must include the path to the folder. This will likely be `img/coaches/[image file name]`.

##### Add a coach modal
1. Search the file for "coachModal1". At around line 538, you will see a long list of modal divs. This section will be where you change anything in any modal.
2. Find the last div with the id `coachModal[number]`. After that `<div>` place the following code. 
```
<div class="portfolio-modal modal fade" id="coachModal[number]" tabindex="-1" role="dialog" aria-hidden="true">
  <div class="modal-content">
      <div class="container">
          <div class="row">
              <div class="col-lg-8 col-lg-offset-2">
                  <div class="modal-body">
                      <h2>[sensei name]</h2>
                      <hr class="star-primary">
                      <img src="[image file name]" class="img-responsive img-centered" alt="">
                      <ul class="list-inline item-details">
                          <li><strong>Rank:</strong>
                              [rank]
                          </li>
                      </ul>
                      <button type="button" class="btn btn-default" data-dismiss="modal"><i class="fa fa-times"></i> Close</button>
                  </div>
              </div>
          </div>
      </div>
  </div>
</div>
```
3. Replace `coachModal[number]` with the number you used in the icon portion.
4. Replace `[sensei name]` with the name.
5. Replace `[rank]` with their rank.
6. Replace `[image file name]` with the image file in `img/coaches`. Remember to include that path.
7. You can add more details by copying the `<li>...</li>` part containing the rank, adding it after, and replacing the information with the new detail.

#### Delete a coach
You can delete a coach icon and modal by deleting the two corresponding divs mentioned above. Remember to delete the images in `img/coaches` as well to keep the repository clutter free.

### Achievements
This section will probably change the most since we will need to add one every year.

#### Add an achievement icon
1. Create an icon in some Paint-like software. As of now the specifications for the icons with the years is:
* Size: 900 x 650
* Background color: r:44, g:62, b:80
* Font color: white
* Font: Bauhaus 93
* Font size: 130

2. Save that image as "year[next number].jpg". Take the number of the last image and increment that for the [next number].
3. Place that image in `img/achievement`.
4. In the Acheivements section, add the code below the comment about icon specifications:
```
<div class="col-sm-4 portfolio-item">
    <a href="#portfolioModal[number]" class="portfolio-link" data-toggle="modal">
        <div class="caption">
            <div class="caption-content">
                <i class="fa fa-search-plus fa-3x"></i>
            </div>
        </div>
        <img src="[image file name]" class="img-responsive" alt="Cabin">
    </a>
</div>
```
5. Replace `[number]` with the same number used in the icon image name.
6. Replace `[image file name]` with the icon we just made. Remember to include the file path `img/achievement`.

##### Add an achievement modal
1. Seach for the last "coachModal[number]". Place the following code right after that div:
```
<div class="portfolio-modal modal fade" id="portfolioModal[number]" tabindex="-1" role="dialog" aria-hidden="true">
    <div class="modal-content">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 col-lg-offset-2">
                    <div class="modal-body">
                        <h2>2018-2019</h2>
                        <hr class="star-primary">
                        [achievements]
                        <button type="button" class="btn btn-default" data-dismiss="modal"><i class="fa fa-times"></i> Close</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
```
2. Replace `portfolioModal[number]` number with the same number used for the icon image.
3. Replace `[achievements]` with these examples:
```
<img src="img/achievement/2018yuhihai.jpg" class="img-responsive img-centered" alt="">
<h3>Yuhihai</h3>
<p> 2nd Place Yudansha Tournament - Christopher Piggot </p>
<p> 2nd Place Kyu Team Tournament - UCSD Kyu Team A </p>
<p> 2nd Place Team Tournament - UCSD Team </p>
<br>
```
You can add multiple of these back to back to create multiple lists. You can change the image in the `<img>` div, the tournament name between `<h3>...</h3>`, and each title in `<p>...</p>`. You can add more titles with that div too.

You can also use the following placeholder for the next year:
```
<h3>Fighting!</h3>
<br>
```

### Gallery
The gallery is ordered chronologically from top left to bottom right, oldest being at the bottom right. Ideally, we keep only 6 pictures in the gallery for relevancy. You can add more images by adding a new icon and modal but it will look weird if you do not have a total number that is a multiple of 3. You can follow the instructions in the previous sections on how to add an icon and modal. The following instructions for change will be how to preserve the chronological order and how to replace the pictures.

##### Replace and move the gallery icons
1. Search for the "Gallery Grid Section" in `index.html`. This section should have 6 of these divs:
```
<div class="col-sm-4 portfolio-item">
    <a href="#galleryModal[number]" class="portfolio-link" data-toggle="modal">
        <div class="caption">
            <div class="caption-content">
                <i class="fa fa-search-plus fa-3x"></i>
            </div>
        </div>
        <img src="[image file name]" class="img-responsive" alt="Game controller">
    </a>
</div>
```
2. The easiest way to maintain the order is to copy the last div and paste it before the div with `galleryModal1`. 
3. Change `galleryModal6` in the newly pasted div to `galleryModal1`, and increment all the following `galleryModal[number]` in the other divs.
4. In the newly pasted div, you can change the `[image file name]` to the new icon. Again, make sure the icon image is 900 x 650.

##### Replace and move the gallery modals
1. Search for `id="galleryModal6"`. Copy that div that looks like the code below:
```
<div class="portfolio-modal modal fade" id="galleryModal6" tabindex="-1" role="dialog" aria-hidden="true">
    <div class="modal-content">
        <div class="container">
            <div class="row">
                <div class="col-lg-8 col-lg-offset-2">
                    <div class="modal-body">
                        <h2>2017 Senior Sendoff</h2>
                        <hr class="star-primary">
                        [image list]
                        <p>[caption]</p>
                        <ul class="list-inline item-details">
                            <li><strong>Date:</strong>
                                [date]
                            </li>
                        </ul>
                        <button type="button" class="btn btn-default" data-dismiss="modal"><i class="fa fa-times"></i> Close</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
```
2. Search for `id="galleryModal1"` and paste the copied code above this div.
3. Again, change `galleryModal6` in the newly pasted div to `galleryModal1`, and increment all the following `galleryModal[number]` in the other divs.
4. Add an image with
```
<img src="[image file name]" class="img-responsive img-centered" alt="">
```
in `[image list]`. You can add consecutive pictures.
5. Change `[caption]` to a caption for the pictures. Or remove it by deleting the whole `<p>...</p>` div.
6. Change `[date]` to the month and year of the pictures.

### Title
If you want to make changes to the title of the webpage, which is what shows up on the browser tab, go to `index.html` line 11. Replace what is inside the `<title>...</title>` with the new webpage title.

If you want to change the title in the top menu bar, change the text inside `<a class="navbar-brand" href="#page-top">...</a>` on line 43.

If you want to change the title at the head of the webpage, change the text inside `<h1 class="name">...</h1>` on line 87.

### Section Names
If you want to change the names of sections, you will need to do so for the top menu bar and for the section headers. To change the top menu bar, go to `index.html` lines 52 to 69. You will see the section names and you rename them accordingly there.

To change the section headers, you must go to the respective section. If you search (`ctrl + f`) the file for `section id="[section name]"`, you should find the code for that section. The fifth row of under the comment should be `h2>...</h2>`. To change the section header, you can replace the text within those tags.

### Location in Footer
1. Search "Location".
2. Change the address within `<p>...</p>`. Add `<br>` for a new line.

### "Around the Web" Links in Footer
1. Search "Around the Web"
2. You will see the facebook link. You can change the link accordingly. Make sure to keep it within the quotes `<a href="[facebook link]"`.
3. You can add additional links. There are commented-out templates for Google Plus, Twitter, LinkedIn, and Dribble.

### Rec Class Link in Footer
1. Search "UCSD Rec Class"
2. Change link in `<a href="[rec class link]">here</a>`
3. Be careful with this link as UCSD rec class webpage may change.

## Save Your Changes
1. Run the following code
```
git add --all
git commit -m "update"
git push
```
If you run into issues at this stage, reach out for help.

2. Ask George how to update the webpage.