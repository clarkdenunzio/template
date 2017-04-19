---
layout: essay
type: essay
title: "Meteor Gotchas"
date: 2017-03-09
labels:
  - Software Engineering
  - Meteor
---

# Meteor Gotchas
## By: Clark DeNunzio

<img class="ui centered medium image" src="../images/meteor-logo.png">

-[Meteor](https://www.meteor.com/)

The meteor framework has been for the most part a joy to work with. For one exemplary reason, Meteor simply worked "out-of-the-box", which, for a hopeful Software Engineer, is a a blessing to say the least. Meteor has several intelligent, fault-tolerant features that I personally highly praise. I was sold once I saw the ability to completely destroy the app heirarchy and place static HTML, CSS, and JavaScript files back into the hierarchy, and still Meteor intuitively builds scaffoliding for the entire app!
<hr>
I will now highlight a pitfall that many readers may want to take note of because, with the intuitiveness of Meteor, the framework will also install it's own personal working directory of [NPM](https://www.npmjs.com/) which makes the use of .GitIgnore files absolutely essential when using Git with your workflow.

Without using a .GitIgnore file, I accidently commited over 7900 files into my project: Digits' repo!!! 

The following post, here: @[Stack OverFlow](http://stackoverflow.com/questions/10744305/how-to-create-gitignore-file) highlights the solution to this problem. The simple answer was:

```
echo "npm modules" > .gitignore
```

By using a simple command like this in your Git initialized directory will exclude Git Add, Git Commit, and Git Push commands from including what may be a robust YourMeteorApp/Npm_Modules directory. To continue adding exclusions, VI into your new .GitIgnore file and add directories onto new lines that you wish to exclude.

<hr>

Another pitfall that comes with a robust, powerful framework like Meteor is the large file structures behind the scenes, like the YourMeteorApp/Npm_Modules directory. As mentioned, it is absolutely essential to use .GitIgnore files. One problem I am encountering now is large startup times when prototyping my apps. For example, the command:

```
meteor --settings ../config/settings.development.json
```

Took over 90 minutes to complete on my command line interface when I first started building a Meteor app with EsLint, Semantic UI, and ECMAScript 6 integrations. If any advice is out there it is appreciated!
<hr>