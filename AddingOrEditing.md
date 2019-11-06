---
title: "Adding or editing a docs page"
redirect_from: "/docs"
layout: docsPage
sections: ["Adding a page", "Editing a page"]
---

## Adding a page
To add a new page to the documentation, you must first have this Github repository cloned. Create a new .md file in the root directory of the repository, and add what is 
referred to as 'front matter' to the top of the file. Front matter is just a block of YAML that defines several variables for Jekyll. 
Front matter is denoted by three hyphens (`---`) on the top and bottom.
 The front matter for this page, for example, is:
```
---
title: "Adding or editing a docs page"
redirect_from: "/docs"
layout: docsPage
sections: ["Adding a page", "Editing a page"]
---
```

There are three necessary things for the front matter. First off, the title. This page will show up as whatever you put in the front matter title, regardless of the file name. 
Second, the `layout: docsPage` is necessary to make sure the new page shows up in the docs. 
The last necessary item is the `sections` item. In this variable, you should define the sections that you would like to have links to on the table of contents to the left.
Make sure to type section names as they are in the markup. Because I have defined `sections: ["Adding a page", "Editing a page"]` in the front matter of this page and
have two sections in the markup (`## Adding a page`, `## Editing a page`),
you will see two links in the table of contents to the left that link to the two corresponding sections on this page.

## Editing a page
Editing a page is as easy as changing the markup file (.md) found in the root directory of the Github repository and pushing all of the changes that occur.
