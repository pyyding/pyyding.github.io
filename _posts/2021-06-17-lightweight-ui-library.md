---
layout: post
title: "Lightweight UI library MVP"
published: true
---
Say you're working with your app and you want to share UI components with another app. The correct solution is to extract and publish a UI library repository. 

While this is the right way to go, it isn't the most straight forward process. 
* You need to publish the repository as an npm module. 
* You want to set up a CI pipeline that publishes new versions. 
* To make the library development possible, you need playground tooling (something like Storybook). 

Putting in all the work for just sharing a folder is not worth the investment in early stage. 
And even if all that is done, coding has become more tedious than you could have imagined. 

Every time you want to make a change in UI components, you need to:
1. publish a new version
2. update the library version in the main app

Whenever you want to test the library components without publishing, you need to:
1. build the UI library
2. import UI library local build inside package json
3. run `npm install my-ui-library` to update the library in the main app

This whole process sucks big time.

This is why it's appealing to find a way around the "separate UI library repository" jargon.

### Solving this problem

I played around with a few ideas on how to tackle it: 

1. copy-paste components between apps
2. create a separate module and import it in package json by a relative local path
3. move components to a separate folder and import it where needed

Copy-pasting forces to keep every project in sync which is a stupid process, so we discard it. 

Creating a separate repository sounds like a half-decent idea. Initialize the library as npm module, install the dependencies. Have a relative import in package json like:
`"ui-lib": "file:./../ui-lib"`

In reality it forces us to do a lot of legwork. You would either have to 
a. rebuild the library and the app projects on every UI library change 

or

b. If you want to import a react library straight up, add a webpack rule to compile the code to javascript. 
Because Webpack understands only javascript or json. Additionally, adjust the main app's `run` and `build` commands to install library dependencies. 

Second idea has loads of steps, discard it. On with the third one!

We want to have a monorepo with a structure 
```
/my-repo/my-main-app
/my-repo/ui-lib
/my-repo/another-app-that-uses-ui-library
```

Importing the library from outside project's scope has a minor obstacle. It's not normally possible, Webpack gets angry and throws an error. 
To make it work we can use a symbolic link to fool Webpack. This means we are now hacking. At least it is clean(ish) and easy to refactor out later :) 

Symbolic link (also symlink or soft link) is a term for any file that contains a reference to another file or directory [1](
https://pubs.opengroup.org/onlinepubs/009695399/basedefs/xbd_chap04.html#tag_04_11)

Inside UI library folder, create an `index.js` file that exports all the components. This makes import paths nicer.

```
// index.js inside ui-lib
import Button from "./lib-components/Button" 

export default { Button }
```

Create a soft symlink. Inside `./my-app` folder run the following command.

```ln -s ../ui-lib ./components```

This creates a symlink that redirects to `ui-lib` folder.

Webpack doesn't accept symlinks by default. Modify Webpack configuration and set `resolve.symlinks = false`

With Next.js, you would implement the change in `next.config.js` like:

```
module.exports = {
  webpack: (config, options) => {
    config.resolve.symlinks = false
    return config
  },
}
```

Now you can import the library components like

```import { Button } from '../components/ui-lib'```

That should be it! If you can think of a nicer solution, please let me know on twitter @pyyding.
<br/>
[Example git repository](https://github.com/pyyding/ui-lib-example)
