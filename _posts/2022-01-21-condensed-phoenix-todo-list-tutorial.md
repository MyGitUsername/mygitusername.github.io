---
layout: post
title:  "Condensed Phoenix Todo List Tutorial"
date:   2022-01-21
---

0. Install the required software: phoenix, elixir, and postgres
1. `mix phx.new todo_list`
2. `cd todo_list `
3. `mix phx.gen.html TaskList Item items description:string complete:boolean`
4. Add the resource to your browser scope in `lib/todo_list_web/router.ex`

    ```
        ...
        get "/", PageController, :index
    +   resources "/items", ItemController
    ```

5. `mix ecto.migrate` 
6. `mix phx.server` and navigate to `http://localhost:4000/items`  

[View the Code] [github-repo]

[github-repo]: https://github.com/MyGitUsername/todo_list
