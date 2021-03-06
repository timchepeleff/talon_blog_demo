# TalonBlogDemo

A Blog project using the [Talon](https://github.com/talonframework/talon) Framework.

## Installation

```bash
git clone https://github.com/talonframework/talon_blog_demo.git
cd talon_blog_demo
mix deps.get && cd assets && npm install && cd .. && mix ecto.setup && mix phx.server
```

Visit `http://localhost:4000/talon/blogs` in your browser.

## Steps Taken to Create this Project

1. `mix phx.new talon_blog_demo`
2. `cd talon_blog_demo`
3. `mix ecto.create`
4. `mix phx.gen.context Accounts User users first_name last_name username email active:boolean`
5. `mix phx.gen.context Blogs Blog blogs name description:text active:boolean user_id:references:accounts_users`
  * Add the `belongs_to` and `has_many` to the `Blog` and `User` schemas
6. `mix phx.gen.context Blog as Post posts title body:text published:boolean views:integer blog_id:references:blogs_blog`
  * Add the `belongs_to` and `has_many` to the `Post` and `Blog` schemas
7. Fill out the `seeds.exs` file
8. `mix run priv/repo/seeds.exs`
9. Edit the `mix.exs` file. Add `talon` and `faker` deps
10. `mix deps.get`
11. `mix talon.new`
12. Follow the instructions printed
  * Add the pagination to `repo.ex`
  * Add the talon routes to `router.ex`
  * Edited the `brunch-config.js` file. Copied the boilerplate sections, pasted, and uncommented.
13. `mix talon.gen.resource Accounts.User`
14. `mix talon.gen.resource Blogs.Blog`
15. `mix talon.gen.resource Blogs.Post`
16. Edit the `config/talon.exs` file and add the resources per instructions
