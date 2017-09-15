# Scrapping with Cheerio and storing with Mongoose

Live website can be found here:

[https://davesrose-mongo-scrapper.herokuapp.com](https://davesrose-mongo-scrapper.herokuapp.com)

We're tasked to scrape a news page, and store articles in monogoDB.  Required npm packages are express, express-handlebars, mongoose, body-parser, cheerio, and request.  As we have used them before, express and body-parser are used for providing routing: express-handlebars for rendering a view of the scraped articles.  Cheerio is used for finding and scrapping elements in the website we're scrapping from.  Request is used for querying our news site.  Mongoose is used for defining two models (Article and Comment), and refer comments to the Article model.  MongoLab addon is used in the heroku deployment for an online mongoDB.

I've picked BBC News as my news site to scrape from. The targeted section is the day's featured news (so the list of articles isn't too long).  I also tried scrapping BBC's RSS feed, but didn't have much luck selecting each title and summary.  I have an Article model which gets populated from the scrapped BBC headlines, and references the Comment model (which stores a name and comment).  The controller.js file also has a route for deleting a comment from it's ID using findByIdAndRemove method.




## File structure used:

```
.
├── controllers
│   └── controller.js
│ 
├── models
│   ├── Article.js
│   └── Comment.js
│
├── node_modules
│
├── public
│   └── assets
│       ├── css
│       │   └── style.css
│       ├── js
│       │    └── app.js
│		└── images
│           └── scrapper.png
│
├── views
│   ├── index.handlebars
│   └── layouts
│       └── main.handlebars
│
└─ server.js
```

- - -