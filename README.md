# Vue 3 + esbuild Plugin Sample

A starter project for creating Figma plugins using Vue 3, built on top of esbuild and modeled after (stolen from) [esbuild-react](https://github.com/figma/plugin-samples/tree/master/esbuild-react).

---

## Contents

  * [Intro](#intro)
  * [Getting started](#getting-started)
  * [Recommendations](#recommendations)
  * [Available scripts](#available-scripts)

---

## Intro
While, surprisingly, creating a Figma plugin, I realized that there were no updated boilerplates for creating plugins using Vue 3.

I've created this project to, hopefully, help someone that rather spends time working on their plugin idea instead of setting up stuff (and prefers working with Vue).

If you have any feedback regarding the project, or simply want to share a plugin you've created using the boilerplate, feel free to open an issue or reach out to me directly on [Linkedin](https://www.linkedin.com/in/carlldreyer/).

Happy coding!

---

## Getting started
Before you start, make sure that you have updated versions of [node](https://nodejs.org/en/) and [npm](https://www.npmjs.com/), it's recommended to use the current LTS versions.

### Step 1
Clone the repo using:

`git clone https://github.com/CarlLDreyer/figma-plugin-sample-vue3.git <YOUR PROJECT NAME>`

or using your favorite Git GUI such as [Sourcetree](https://www.sourcetreeapp.com/) or [Gitkraken](https://www.gitkraken.com/).

### Step 2
Move to the appropriate directory:

`cd <YOUR PROJECT NAME>`

### Step 3
Install the dependencies using:

`npm install`

### Step 4
Run the project using:

`npm run dev`

Simply put, this will build your code into the `dist` folder and watch for any changes you make, once a change has been discovered the project will be rebuilt, meaning you can make use of your latest changes inside the Figma client.

### Step 5
Inside the Figma client, go to **Plugins / Development / Import plugin from manifest**.

Choose the **manifest.json** file located in the root of your newly created directory, commonly referred to as `<YOUR PROJECT NAME>`.

You can then run your plugin by hovering over the list item and selecting **Run**.

At any point, you can find your plugin under **Plugins / Development**.

### Build for Figma publication
Once you're ready to publish your plugin in Figma, you'll need a minified version, this can be generated using:

`npm run build`

---

## Recommendations
I did not want to enforce my personal code conventions in this project, although, prettier might be on the verge of doing so.

When using this starter project to create a Figma plugin, I'd start by adding [ESLint](https://eslint.org/), or even more precise [eslint-plugin-vue](https://eslint.vuejs.org/), to ensure that the code is consistent (in your preferred way :)).

I haven't added **Sass** to the project (it should probably be out of the box right?) but that would probably be my second point of action.

---

## Available scripts
The following scripts are available to use in the project:

### Build

`npm run build`

Builds a minified version ready to be published.

### Build (Only plugin)

`npm run build:plugin`

Only builds the code.ts file located in **plugin**.

### Build (Only UI)

`npm run build:ui`

Only builds the Vue UI.

### Build (And watch changes)

`npm run build:watch`

Builds the plugin+UI and watches for changes.

### Development

`npm run dev`

Launches "development mode" where the project is built and changes are being watched.

### Format

`npm run format`

Runs [prettier](https://prettier.io/) to format the files of the project, prettier can be configured using the **.prettierrc.js** file.

### "Test"

`npm run test`

Performs a Typescript compilation and builds the project, any errors that occur are outputted for your pleasure.

### Compile Typescript

`npm run tsc`

Performs a Typescript compilation without generating any output.

### Compile Typescript (And watch for changes)

`npm run tsc:watch`

Performs a Typescript compilation and watches for changes.
