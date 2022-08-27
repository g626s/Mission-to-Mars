# Mission-to-Mars

# Resources
* `Web Pages/Sources Scraped:`
  - https://data-class-mars.s3.amazonaws.com/Mars/index.html
  - https://spaceimages-mars.com
  - https://galaxyfacts-mars.com
  - https://marshemispheres.com/
 * `Software and Applications:`
    - Python
    - Pandas libraries
    - Jupyter Notebook
    - BeautifulSoup, Splinter, Selenium, Flask 
    - MongoDB, MongoShell, PyMongo 
    - Chrome Developer Tools
    - HTML5
    - Bootstrap 3
# Code
* `To view the code:`
  - App script: [app.py](https://github.com/g626s/Mission-to-Mars/blob/main/app.py)
  - HTML code: [index.html](https://github.com/g626s/Mission-to-Mars/blob/main/templates/index.html)
  - Scraping script: [scraping.py](https://github.com/g626s/Mission-to-Mars/blob/main/scraping.py)

# Project Overview
Web scraping is a method used by organizations worldwide to extract online data for analysis. Large companies employ web scraping to assess their reputations or track their competitors' online presence. With this in mind, this HTML/CSS web scraping project implemented a Python script to scrape text and images from multiple website sources and automated a browser that referenced the Mission to Mars project. 
Data was stored in a NoSQL database MongoDB, and then the data was rendered in a web application created with Flask to display the data from the web scrape. Chrome Developer tools was also used to identify and explore HTML components. In addition, there was also a rendered HTML template designed using BeautifulSoup, Splinter and Bootstrap components to display all the data in a central location automatically. A `Scrape New Data` button was created using the `scraping.py` script to allow users to interact with the website and populate new data and images at the time of use.

# Summary and Website Stylization using Bootstrap 3
The current web app was adjusted to include all four of the hemisphere images of Mars. In order to accomplish this task, we used BeautifulSoup and Splinter to scrape full-resolution images of Mars’s hemispheres and the titles of those images. We then stored the scraped data on a Mongo database, used a web application to display the data, and then alter the design of the web app to accommodate these images.

<p align="center">
  <img width="899" alt="Screen Shot 2022-08-26 at 3 27 49 PM" src="https://user-images.githubusercontent.com/107281474/187041006-b03cd8d3-8ca6-48ee-9c86-655fca9aae90.png">
</p>

Lastly, we updated the web app to make it mobile responsive using the dimensions of the `iPhone SE` and added two additional Bootstrap 3 components in which we included a background NASA logo image in the jumbotron and changed the grid layout of the images of Mar's hemispheres all in one horizontal row.

<p align="center">
  <img width="526" src="https://user-images.githubusercontent.com/107281474/187041011-fdb6927c-22de-4e59-9ac3-0141ee2b4e49.png">
</p>

Two additional Bootstrap Components:
* `Component 1:`
    
        <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <meta http-equiv="X-UA-Compatible" content="ie=edge" />
      <title>Mission to Mars</title>
      <link
        rel="stylesheet"
        href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
      />
      <style>
        .jumbotron{
          background: url(https://upload.wikimedia.org/wikipedia/commons/a/a3/NASA_Worm_logo.svg);
          background-repeat: no-repeat;
          background-position: center;
        }
      </style>
    </head>
    
    
* `Component 2:`

        <div class="col-md-3">
          <div class="thumbnail">
            <img src="{{hemisphere.img_url | default('static/images/error.png', true)}}" alt="...">
            <div class="caption">
              <h3>{{hemisphere.title}}</h3>
            </div>
          </div>
        </div>
