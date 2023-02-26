# Kraut

**Kraut** is a simple router for [Karax](https://github.com/karaxnim/karax) frontend framework.

```
# app.nim

import karax/[karax, karaxdsl, vdom]
import kraut

import pages/[index, users, user]


const routes = {
. "/": index.render,
. "/users/": users.render,
. "/users/{userId}/": user.render
}

setRenderer(render(routes))
```

```
# user.nim

import karax/[karax, karaxdsl, vdom]
import kraut/context

proc render*(context: Context): VNode =
. buildHtml(tdiv):
.   h1: text "User id" & context.params["userId"]
```
