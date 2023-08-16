---
layout: default
title: Status
parent: Commands
nav_order: 1
---

## **Status Command**

Status is how you determine what dotCMS instance you are connected to
Also tells you if your currently logged in that selected instance

```shell script
   dotCMS status  
```

```
2023-02-22 11:25:29,499 INFO  [com.dot.api.cli.HybridServiceManagerImpl] (Quarkus Main Thread) Service [default] is missing credentials.
2023-02-22 11:25:29,500 INFO  [com.dot.api.cli.HybridServiceManagerImpl] (Quarkus Main Thread) Service [demo] is missing credentials.
Active instance is [demo] API is [https://demo.dotcms.com/api] No active user Use login Command.
```
Please note that the output of the status command says **demo** is the selected  instance

These instances or dotCMS profiles are loaded from file located under user home user a hidden folder named .dotCMS
The file is dot-service.yml and the contents looks more or less like this:

```
---
- name: "default"
- name: "demo"
  active: true
```

### **Important:** This file is where new instances should be registered.