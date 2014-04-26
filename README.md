Ruby on Rails Curriculum at Blue1647
=====================

## Overview

The following curriculum and content was created for the [Code Chicago] "Beginning Ruby on
Rails" course at [Blue1647] by [@johnnycon]. The class includes 66 hours of in-class lectures
and hands-on labs spanning 11 weeks.


## Pre-requisites
This class assumes you are using either a Mac or Linux computer. While it is possible to do
rails development using Windows, this curriculum assumes Linux or Mac OS.

You'll need the following tools in order to complete the class.

## Miscellaneous Resources
*   [Common Vocabulary] and Terms in Ruby,  Ruby on  Rails, and Web Development

*   [Complimentary Tools] and Technologies

#### Tools
The following instructions apply to Mac OS installation. Some of these installs
will work on Linux, but others will require a separate Linux install and
installation process.

1.  Rails
2.  Ruby
3.  Git
4.  SQLite
5.  A text editor
6.  Postgresql
7.  iTerm2 (optional, provides nice enhancements over default)


#### Installs
*   [Install Rails] to install the first 4 tools
*   [Sublime Text] or [Atom] as your text editor
*   [Postgresapp] to install the PostgreSQL database
*   [iTerm2] installer to install the optional iTerm2 terminal tool


## Weekly Schedule

#### Week 1

* **Saturday** (4 hours)
    * Overview of class
    * Class expectations
    * Command line basics
    * The Ruby Programming Language
    * Writing first ruby program
    * [View Content](weeks/week1a.md "Week 1 - saturday")
* **Wednesday** (2 hours)
    * Ruby on Rails Overview
    * The MVC Pattern
    * Models, Views, and Controllers
    * Routes
    * Creating your first Rails project
    * Using Scaffolds and Generators
    * Common Rails commands
    * Rake
    * Gems
    * Bundler
    * [View Content](weeks/week1b.md "Week 1 - wednesday")

#### Week 2
* **Saturday** (4 hours)
    * Classes
    * Objects
    * Building our group project (Blue Directory)
    * Building blue using scaffolds
    * The problem with the scaffolds approach
    * Building blue the Rails way
    * CRUD
    * REST
    * Rails conventions
    * Building out Blue company index, show, and new/create
* **Wednesday** (2 hours)
    * Adding edit/update and destroy actions
    * Rails Form Helpers
    * Rails Partials
    * Reusing the form partial for new/edit actions
    * Strong parameters
    * Rails layouts
    * Adding Navigation to application


#### Week 3
* **Saturday** (4 hours)
    * Adding members to our project
    * Route resources
    * Route resources as flat hierarchy
    * Active Record Associations
    * Rolling back migrations
    * Rails model generators with associations
* **Wednesday** (2 hours)
    * Rails routes best practices
    * Moving members as a nested resource of company
    * Update application based on this change

#### Week 4
* **Saturday** (4 hours)
    * Rails validations
    * Most common validation types
    * Adding validation to company model
    * Adding validation to member model
    * Validation based on model life-cycle
    * Validation error messages
    * ActiveRecord helper attributes (valid? etc..)
    * Accessing model errors
    * Displaying errors in UI
    * Adding style to fields with errors
    * Flash message
    * Displaying flash messages
* **Wednesday** (2 hours)
    * HTML Overview
    * CSS Frameworks overview
    * Adding CSS styles to application
    * Overview on default Rails CSS conventions
    * Thoughts on better css organization approaches
    * Installing Zurb Foundation
    * Enhancing our navigation to use Foundation styles
    * The Grid system

#### Week 5
* **Saturday** (4 hours)
    * In-depth on rails models and associations
    * Modelling techniques
    * Class modeling exercise for individual projects
* **Wednesay** (2 hours)
    * Seed data
    * Best practices for seed data
    * Creating custom rake tasks for test data

#### Week 6
* **Saturday** (4 hours)
    * Deep dive into ActiveRecord
    * The need for SQL and relational DBs
    * Finding single records
    * Finding multiple filtered records
    * Limiting results
    * Built-in aggregates
    * Updating multiple records efficiently
    * Lazy loading vs. Eager loading
    * Joining
    * Includes
    * Select
    * Adding events model to group project
* **Wednesday** (2 hours)
    * [View Content](weeks/week6b.md "Week 6 - wednesday")
    * Enhancing our group project
    * Additional html/form helpers
    * Select lists
    * Regular expression validations
    * Uniqueness validations

#### Week 7
* **Saturday** (4 hours)
    * [View Content](weeks/week7a.md "Week 7 - saturday")
    * Authentication
    * Authorization
    * Sessions
    * Cookies
    * Using clearance
    * Using devise
    * Authorizing actions
    * Adding role
    * Conditionally displaying UI by role
* **Wednesday** (2 hours)
    * [View Content](weeks/week7b.md "Week 7 - wednesday")
    * Omniauth and Oauth
    * Integrating Twitter as auth provider

#### Week 8
* **Saturday** (4 hours)
*   [View Content](weeks/week8a.md "Week 8 - saturday")
    * Hack on individual projects
* **Wednesday** (2 hours)
*   [View Content](weeks/week8b.md "Week 8 - wednesday")
    * JavaScript
    * jQuery
    * Ajax
    * Adding ajax to application

#### Week 9
* **Saturday** (4 hours)
*   [View Content](weeks/week9a.md "Week 9 - saturday")
    * The Rails asset pipeline
    * Deploying to Heroku
    * Heroku commands
    * Working with configuration tokens/secrets
* **Wednesday** (2 hours)
    * More ActiveRecord goodness
    * Attribute delegation
    * ActiveRecord scopes
    * Adding business rules/logic
    * Transactions
    * Pagination

#### Week 10
* **Saturday** (4 hours)
    * Sending and receiving email
    * Unconventional forms/UI
    * More Ruby
    * Hashes and Arrays
    * Maps
    * Enumerators
* **Wednesday** (2 hours)
    * Timezones
    * Prettifying URLs
    * Integration with 3rd party services

#### Week 11
* **Saturday** (4 hours)
    * Rails Security
    * CSRF protection
    * XSS Protection
    * SQL Injection protection
    * Rails performance
    * Efficient Querying
    * N+1 Queries
    * Caching
    * Key/Value stores
* **Wednesday** (2 hours)
    * Words of advice
    * Where to go from here
    * Apps in the real-world



[Common Vocabulary]: resources/vocab.md
[Complimentary Tools]: resources/tools.md

[Install Rails]: http://installrails.com/
[Sublime Text]: http://www.sublimetext.com/
[Atom]: http://www.atom.io
[Postgresapp]: http://postgresapp.com/
[iTerm2]: http://www.iterm2.com/

[Blue1647]: http://www.blue1647.com/
[Code Chicago]: http://codechicago.com/
[@johnnycon]: http://www.twitter.com/johnnycon
