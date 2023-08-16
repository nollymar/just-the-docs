---
layout: default
title: "Content Type"
parent: Commands
nav_order: 5
---

## **Content-Type Command**

Content-Type command is how you do CRUD operations on CTs

**Find Content-type**
```markdown
   dotCMS content-types find 
```
Gets you a complete list of the available Content-types. By Default, they are shown in batches of 10.
But you can also get an entire list at one by specifying  --interactive=false 

Find Sites
```markdown
   dotCMS content-types find --interactive=false 
```

For a name like type of search do as follows 
```markdown
   dotCMS content-types --name="File" --page=0 --pageSize=10
```
This should bring back all content-types matching the name "File"

**Pull Content-type**
```markdown
   dotCMS content-types pull FileAsset 
```
This will get you a descriptor of the solicited content-type in this case "FileAsset" 
Saving it as a file using the content-type variable name as file name. 
  
All content info is presented by default in json format.
However. this is a preference that can be modified by specifying the attribute format
Like this 

**Pull Content-type**
```markdown
   dotCMS content-types pull "FileAsset" --format=YML 
```

**Push Content-type**
The next command is Push which allows you to create a new content-type by sending the CT definition using a file as follows

```markdown
   dotCMS content-types push "./content-type.json" 
```

Again here we can change the format of the input file by using the option --format like this:

```markdown
   dotCMS content-types push "./content-type.yml" --format=YML 
```
