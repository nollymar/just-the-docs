---
layout: page
title: "dotCMS CLI"
nav_order: 1
---

# dotCMS CLI 

Welcome to the cli readme   
Here I'll explain how the tool can be used

The CLI is a quarkus/pico-cli project that depends on module api-data-module for which that dependency should have been built already see top level read-me for more details on how to build this entire project.  
Assuming the that api-data-module has been built already    

```markdown
# from top level to build all
../mvnw clean install
```

To run cli. 

First Start a dotCMS instance locally. The CLI is a client program designed to simplify access to dotCMS content services. So we're going to need a running instance of dotCMS to point our client to  

## Running The CLI in dev mode

```markdown
# from top level to build all
cd cli
# command is same as the following to run the quarkus build plugin
# ../mvnw quarkus:dev 
quarkus dev
```
By executing the command described above we launch the cli within Quarkus dev environment 
Meaning we can perform changes to our sources and see them reflected live. So be mindful about it.
This is the only quarkus module within our project so any attempt to run mvnw quarkus:dev 
in any other module is going to result in failure and that is expected

Once the cli is launched in dev mode it'll print out a list of available commands.

followed by 

```markdown
--
Tests paused
Press [space] to restart, [e] to edit command line args (currently ''), [r] to resume testing, [o] Toggle test output, [:] for the terminal, [h] for more options>
```
These are quarkus offered options. 
Now in order to see the CLI in action you need to edit the command line arguments and introduce the cli command and arguments of choice. for example.

```markdown
--
Tests paused
status
```
Which provides you with a quick summary of your status as user. 

or

```markdown
--
Tests paused
login --user=admin@dotCMS.com --password=admin
```
Which allows you to login against an environment. 

Now you're probably asking your self how do I instruct the cli what instance of dotCMS I'm running against.

```markdown
--
Tests paused
instance --list
```
Which allows you to list and select the dotCMS instance we want to run against

in order to see all available command options simply introduce the command name followed by --help
a list of all available commands will appear upon executing the cli with no arguments 

We can also instruct Quarkus dev mode to launch our cli using a preconfigured param by doing 

```markdown
mvn quarkus:dev -Dquarkus.args=status
```
This will launch the cli passing directly into it the arguments that tell them to execute the command status

## Running The CLI as a jar

In order to generate the cli as a jar packed with all necessary dependencies you need to do

```markdown
./mvnw clean install package
```
all the commands used above can be applied directly to the generated jar which can be found under 

```markdown
./cli/target/quarkus-app/
```
Like this 

```markdown
java -jar ./cli/target/quarkus-app/quarkus-run.jar status
```