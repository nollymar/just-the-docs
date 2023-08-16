---
layout: default
title: Instance
parent: Commands
nav_order: 3
---

## **Instance Command**

Instance allows the activation of a dotCMS instance profile
to get a list with all available profiles do:
```markdown
   dotCMS instance  
```

```
Available registered dotCMS servers.
 Profile [default], Uri [http://localhost:8080/api], active [yes].
 Profile [demo], Uri [https://demo.dotcms.com/api], active [no].
```

From the list of available instances select one and then activate it using the activate option like this
```markdown
instance --activate demo
```

Once you have activated the new instance you want to see what your current status again is.