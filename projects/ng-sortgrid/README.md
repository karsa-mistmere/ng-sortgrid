[![Travis build badge](https://img.shields.io/travis/kreuzerk/ng-sortgrid.svg)](https://travis-ci.org/kreuzerk/ng-sortgrid)
[![codecov](https://codecov.io/gh/kreuzerk/ng-sortgrid/branch/master/graph/badge.svg)](https://codecov.io/gh/kreuzerk/ng-sortgrid)
[![angular7](https://img.shields.io/badge/angular%207%20ready-true-green.svg)]()

![Logo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/logo-new.png)

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/grid-demo.gif)

Read the README or just simply check out our demo at: https://kreuzerk.github.io/ng-sortgrid/ 

- [Getting started](#getting-started)
  - [Download the module](#download-the-module)
  - [Apply the directive](#apply-the-directive)
  - [React on changes](#react-on-changes)

# Getting started
## Download the module

```
npm i -s ng-sortgrid
```

Import the ```NgsgModule``` in your ```AppModule```.

```
  ...
  imports: [BrowserModule, NgsgModule],
  ...
```

## Apply the directive
Loop over your elements with *ngFor. 🛎️ the items needs to be an array. Alternate you can also use the async pipe to pass in your items.

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs1.png)

Apply the ngSortgridItem directive

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs2.png)

## React on changes
In most cases you are interested in the new sort order. Often you want to store them in local storage or even send them to the backend. To do so the following two steps are needed in addition to the "Getting started" step.

Pass your items to the directive via the ngSortGridItems input.

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs3.png)
React on the 'sorted' output events

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs4.png)

## Group sortgrids
In case you have more than one sortgriditem on the page you need to group the sortgriditems to avoid dropping drags from one group in another group.
Pass in a unique name to the ngSortGridGroup input

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs5.png)

## Use the async pipe
You can also use the async pipe to display items

![Grid demo](https://raw.githubusercontent.com/kreuzerk/ng-sortgrid/master/projects/ng-sortgrid-demo/src/assets/gs6.png)

# Style your items on different events
The ng-sortgrid adds different classes on different events to your items. You can either use those classes to style the appereance
of your items on certain events or you can include the build in CSS from the ng-sortgrid library.

## Integrate the build in CSS
To integrate the built in Stylesheet just import in in your angular.json.

```
    "styles": [
              "node_modules/ng-sortgrid/dist/lib/ngsg.css",
            ],
```

Alternative you can provide custom styles for the different classes listed bellow

| Class             | Description                                                                                                                                    |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| ng-sg-placeholder | This class is added to the placeholder item which previews where the item is inserted                                                          |
| ng-sg-dropped     | This class is added as soon after you drop an item. The class will be on the item for 500 milliseconds before it gets removed                  |
| ng-sg-selected    | This class is added when you press the CMD or the Ctrl Key and Click on an item. It indicates which items are selected for the multi drag&drop |