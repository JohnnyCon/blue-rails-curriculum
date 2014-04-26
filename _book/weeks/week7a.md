
Week 7 (Saturday)
===================

## Overview

Most applications need some kind of user authentication and authorization.  We
will be adding basic authentication functionality to our application using the
devise gem. 


## Authentication vs Authorization

Authentication verifies **WHO YOU ARE**

Authorization verifies **WHAT YOU CAN DO**

These are two separate concerns and responsibilities. 

In larger applications, the difference becomes increasingly clear. However, in
smaller applications, it's sometimes difficult to differentiate between
authentication and authorization. To further blur the line ...

## Alternate options

There are many options for using user authentication and authorization. The
defacto standard gems have changed through the years as well.  As of this
writing, the two gems I'd recommend for authentication are: 

*   Devise: for full featured authorization functionality
*   Clearance: for a slimmed-down version of doing the absolute basics in
  authentication

Many applications don't use a separate authorization gem due to the additionally
complexity it introduces.  No single authorization gem has become defacto in the
rails space.  The authorization space is fragmented with the following gems
among others: 

*   CanCan
*   Rolify
*   Pundit
*   TheRole


## Authentication

Authentication will allow you to know who a particular user is.  Additionally,
it will insure that any pages that you've protected can't be accessed by
anonymous users.


## Authorization

Authorization will allow you to partition your application and functions into
areas that are only accessible to users with a particular role or permission to
do so. 


## Sessions and Cookies

HTTP is a stateless protocol. This means that every request is made without the
understanding that it's tied to a specific user. As far as the server is
concerned, each request belongs to an anonymous user. 

Fortunately, the introduction of cookies to the web, gave application developers
a way to uniquely identify a specific user across multiple stateless http
requests. 

Rails has built functionality over cookies and provided a session mechanism in
order to give developers a way to manage and identify users for the duration of
that users interaction on the web application. 

#### What cookies are typically used for
Cookies are used in the industry for three primary concerns: 

*   Session Management
*   Personalization
*   Tracking

#### How it works
The browser will contain a cookie with a unique session id that will uniquely
identify that user for the duration of the session (these session typically
expire when the browser is closed, or at a pre-defined expiration time). When
each request is made to the server (rails), rails will create a new session (a
hash) that is stored on the server.  Now, each time a new request is made from
the browser (client), to rails (server), there is an existing session that is
uniquely identifying that this request is for the same person. 


## Learning authentication without a gem

It's a good idea to learn how to do authentication without the use of a gem in
order to understand how the pieces fit together. There are some good resources
online for learning authentication from scratch. 

*   Michael Hartl book
*   Ryan Bates podcast

## What is Devise

*   Built by Jose Valim of Plataformec
*   Heavily utilizes another authentication gem called Warden
*   Complete MVC solution to authentication
*   Can feel really big and overwhelming to new users
*   Composed of 10 modules
    * Database Authenticatable
    * OmniAuthable
    * Confirmable
    * Recoverable
    * Registerable
    * Trackable
    * Timeoutable
    * Validatable
    * Lockable


## Adding Devise to a brand new application
*   Create a new rails app
*   Add the devise gem
*   Run: bundle
*   Run: rails generate devise:install
    * This creates an initializer file
    * This creates a locale file

*   Run: rails generate devise user
*   Run: rake db:migrate
*   Naivate to: localhost:3000/users/sign\_in


add devise gem
run bundle
run generator: rails generate devise:install
create initializer file
creates locale file
run generator: rails generate devise user
run rake db:migrate


## Adding Devise to blue

The process for adding devise to blue will be identical. The difference is that
we have other existing resources in blue (company, members, events) and will be
able to start authorization and displaying content based on role

*   Make sure you're back in the root of blue
*   Add the devise gem
*   Run: bundle
*   Run: rails generate devise:install
    * This creates an initializer file
    * This creates a locale file

*   Run: rails generate devise user
*   Run: rake db:migrate
*   Naivate to: localhost:3000/users/sign\_in
*   

authorize using authenticate\_user!
modify scaffold to now show edit/create for anon users


## Authorization Actions

This can be accomplished using action filters

```ruby
before_action :authenticate_user!, only: [:new, :edit, :update, :destroy,
:create]
```



## Adding user controls to layout file

We'll want to display information about whether there is a current user
authenticated and sign\_in and sign\_out controls.  This can be accomplished by
using the devise helper method user\_signed\_in?

```html
<% if user_signed_in? %>
  Hello, <%= current_user.email %> <%= link_to "sign out",
destroy_user_session_path, method: :delete %>
<% else %>
  <%= link_to "sign in", new_user_session_path %>
<% end %>
```

## Adding Role

We'd like to restrict adding new companies and members to only administrators.
In order to do this, we'll add a role column to our User model.  This role
column will contain either "Administrator", "Member", or "Guest"

## Conditionally display UI by role

To insure that only administrators can create and modify companies and members,
we'll need to: 

*   Verify the role in proper actions
*   Conditionally display the UI elements for create, edit and destroy

```html
<% if user_signed_in? %>
  <td><%= link_to 'Edit', edit_company_path(company) %></td>
  <td><%= link_to 'Destroy', company, method: :delete, data: { confirm:
'Are you sure?' } %></td>
<% end %>
```

