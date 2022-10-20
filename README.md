# THINGS IN HERE

## GEMS

```
gem "sassc-rails"
gem 'devise'
```
- devise set for turbo, rails 7
- from: https://dev.to/efocoder/how-to-use-devise-with-turbo-in-rails-7-9n9

## MODELS
- devise user
- user has many posts
- posts have many comments, comments not linked with user

## OTHER
- custom styling with sidebar
- used current page

```
<div id="header">
  <% if current_page?(root_path) %>
    <p>Post Feed</p>
  <% elsif current_page?(about_path) %>
    <p>My Site</p>
  <% else %>
    <%= link_to "Back to Post Feed", root_path %>
  <% end %>
  <% if user_signed_in? %>
    <div class="buttons">
      <button class="button"><%= link_to "Make Post", new_post_path %></button>
      <button class="button"><%= button_to "Sign Out", destroy_user_session_path, method: :delete %></button>
    </div>
  <% end %>
```

- validations

```
	validates :title, presence: true, length: { minimum: 5 }
	validates :body, presence: true
end
```