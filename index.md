
## Hunting ET With Sinatra


I built an MVC Sinatra app called “UFO Tracker” which allows users to post recent UFO sightings and there location as well as read past UFO sightings posted. MVC is a design pattern or structure to the interface of a web app. It efficiently separates functionality of the interface into three parts; models, views, and controllers. 

	Models are the Ruby objects used within the app. For my app I have two basic objects; users and controllers. Users can create post many encounters. This is known as a “has_many/belongs_to” relationship, as the user “has_many” encounters and the encounter “belongs_to” the user.

	Views are the are different HTML files for displaying the different states or pages within the app such as a page to log in or to report a UFO encounter. In this instance I’m using the file.erb(embedded ruby code) format which is essentially HTML with additional syntax to embed ruby code into the HTML file. For instance this in erb: 
```<h1><%= 2 * 2 %></h1>
is the same as: 
```<h1>4</h1>

	Controllers are classes that join the models and the views together by creating what is known as RESTful (representational state transfer) routes.

	Different pages on a site are actually considered different states of that application. As we click links to navigate to different pages on a site what occurs is a state transition. RESTful routes is a conventional way of linking CRUD (create, read, update, delete) actions with HTTP verbs (get, post, patch, delete). 
 The beauty of this is how it allows us to tie the functionality of Ruby objects to the content on our web app.

 I used ActiveRecord in conjunction with Sinatra to store all the data. 

 The models I used were User and Encounter as well as some modular methods including “slugifiable”  and “ci_search” which allows me to search for instances of an object without case sensitivity. A user can have many encounters  and an encounter belongs to a user.


A user can sign up, sign in, log out and update their user info. I used both the username and email to validate the uniqueness of each user. 

Once logged in a user can create, read, update, or delete a  report of a UFO encounter. I created methods to ensure only the creator of an encounter can edit the encounter.

 I validate the user input so bad data cannot be persisted to the database. Then I displayed that data in the ‘encounters/index’ view by  creating a google API map.

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/AustinRhoads/project_blog_2/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/AustinRhoads/project_blog_2/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
