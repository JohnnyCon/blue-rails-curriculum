Week 6 (Wednesday)
===================

## Overview
Last week we took a deeper look into ActiveRecord and added out events model. 

This week, we'll expand on our events model by building out it's UI. 


## Content

#### Events index page

Our final events index page should now include our four REST actions (show, new,
edit, destroy)

_/app/views/events/index.html.erb_
```html
<h2>All Events</h2>

<table>
  <thead>
    <tr>
      <td>Title</td>
      <td>Description</td>
      <td>Capacity</td>
      <td>Start</td>
      <td>End</td>
      <td></td>
      <td></td>
    </tr>
  </thead>
  <tbody>
    <% @events.each do |event| %>
      <tr>
        <td><%= link_to event.title, event_path(event) %></td>
        <td><%= event.description %></td>
        <td><%= event.capacity %></td>
        <td><%= event.start_at %></td>
        <td><%= event.end_at %></td>
        <td><%= link_to "edit", edit_event_url(event), class: "button tiny
round" %></td>
        <td><%= link_to "delete", event, method: :delete, class: "button tiny
alert round" %></td>
      </tr>
    <% end %>
  </tbody>
</table>



<br>

<%= link_to "Add new", new_event_path, class: "button radius" %>
```

#### Implementing remaining event pages
Implement the remaining event pages and controller actions. 


**Show**

Return an instance of the @event in the show action

_/app/controllers/events_controller.rb_
```ruby
def show
  @event = Event.find(params[:id])
end
```

Add the HTML markup for the show.html.erb page

_/app/views/events/show.html.erb_
```html
<h3>Event</h3>

<ul>
  <li>Title: <%= @event.title %></li>
  <li>Description: <%= @event.description %></li>
  <li>Capacity: <%= @event.capacity %></li>
  <li>Start: <%= @event.start_at %></li>
  <li>End: <%= @event.end_at %></li>
</ul>

```

**New/Create**

_Class to implement_

**Edit/Update**

_Class to implement_

**Destroy**

_Class to implement_


#### Making company industry a drop down with limited options

In some cases, we would rather limit the user to only specified options, rather
than allowing them to enter free-form data into the field.  The company industry
is one example where we might want to limit their options. 


_/app/views/events/show.html.erb_
```html
<ul>
<% @company.errors.full_messages.each do |msg| %>
  <li><%= msg %></li>
<% end %>
</ul>


<%= form_for(@company) do |f| %>

  <%= f.label :name %>
  <%= f.text_field :name %>
  <br>

  <%= f.label :industry %>
  <%= f.text_field :industry %>
  <br>

  <%= f.label :employee_count %>
  <%= f.text_field :employee_count %>
  <br>

  <%= f.label :join_date %>
  <%= f.date_select :join_date %>
  <br>

  <%= f.select :industry, options_for_select([["Choose...", ""], "finance",
"tech", "social", "non-profit", "other"]) %>
  <br>

  <%= f.submit class: "button radius" %>

<% end %>

```


#### Adding regular expression validation to member email

Writing regular expressions is an art few developer ever master.  There are many
tools available that help with writing regular expressions. 

When writing regular expressions for emails, you can use a super complex regular
expression and still miss a few edge cases (false-positives and
false-negatives), especially with the introduction of dozens of new TLD domain
extensions. I suggest using the simplest of regular expressions for validation
emails. 

```ruby
validates :email, format: {with: /@/ }
```

#### Adding uniqueness constraint to member email

Adding uniqueness to a model attribute is straight-forward. In this case, we
will simply add a new validation of uniqueness to members email attribute. 

```ruby
validates :email, uniqueness: true
```

You can put the three specific email validations on separate lines or combine
them into a single line. 

```ruby
validates :email, presence: true, uniqueness: true, format: {with: /@/ }
```

