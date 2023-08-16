---
layout: default
title: Site
parent: Commands
nav_order: 4
---

## **Site Command**
Site command is how you do CRUD operations on sites

```markdown
   dotCMS site find
```
Gets you a list of all the published sites

```
name: [default] id: [8a7d5e23-da1e-420a-b4f0-471e7da8ea2d] inode: [1b407535-67e3-4f21-ad00-8ef5ef492d64] live:[yes] default: [yes] archived: [no]
name: [demo2.dotcms.com] id: [28c9ce6b2147e0f4763ee2ee5628faeb] inode: [b81879e0-5f81-4cf9-9cc3-86a048f1203c] live:[no] default: [no] archived: [no]
```

From the list of sites pick the one that interests you and to get more details do
```markdown
   dotCMS site pull demo2.dotcms.com
```
This command gets you a representation of the site info in json format. Saving it immediately as file using as name the site-name itself.

```markdown
   dotCMS site push "./site-descriptor.json" 
```
or 

```markdown
   dotCMS site push "./site-descriptor.yml"  --format=YML 
```

There's another useful command that can be used to quickly kick off a site  by simply providing a name 

```markdown
   dotCMS site create "my.cool.bikes.site.com" 
```
Once a site has been created you need to start it or stop it. and that can be accomplished with the two following examples respectively

```markdown
   dotCMS site start "my.cool.bikes.site.com" 
```
And 

```markdown
   dotCMS site stop "my.cool.bikes.site.com" 
```

And finally here's how you remove sites

First you need to archive the site 

```markdown
   dotCMS site archive "my.cool.bikes.site.com" 
```

And then

```markdown
   dotCMS site remove "my.cool.bikes.site.com" 
```

