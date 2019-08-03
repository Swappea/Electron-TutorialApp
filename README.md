# Angular 8 Cascading Dropdown

Angular 8 Cascading Dropdown Component for web applications. Dynamic and easy to use.

## Table of Contents

- [Getting Started](#gettingstarted)
- [Installation](#installation)
- [Usage](#usage)
- [Settings](#settings)
- [Events](#events)
- [Run locally](#runlocally)

## Getting Started

### Installation

- The Cascading Dropdown Dropdown package is published on the [npm](https://www.npmjs.com/package/ng-cascading-dropdown-lib) Registry.
- Install the package :
  `npm install ng-cascading-dropdown-lib`

### Demo Url
https://swappea.github.io/ng-cascading-dropdown-lib/

### Usage

Import `NgCascadingDropdownLibModule` into `NgModule` in `app.module.ts`. Angular's `FormsModule` is also required.

```js
import { NgCascadingDropdownLibModule } from 'ng-cascading-dropdown-lib';
import { FormsModule } from '@angular/forms';

@NgModule({
  // ...
  imports: [
    NgCascadingDropdownLibModule,
    FormsModule
  ]
  // ...
})

```

Declare the component data variables and default options in your component where you want to consume the dropdown component.

```js
import { Component, OnInit } from "@angular/core";

export class AppComponent implements OnInit {
  defaultTestData = [];
  defaultDropdownData = [];

  ngOnInit() {
    this.defaultTestData = [
      {
        id: 1,
        grpName: "Asia",
        parentGroupID: null
      },
      {
        id: 2,
        grpName: "North America",
        parentGroupID: null
      },
      {
        id: 3,
        grpName: "Europe",
        parentGroupID: null
      },
      {
        id: 4,
        grpName: "India",
        parentGroupID: 1
      },
      {
        id: 5,
        grpName: "Pakistan",
        parentGroupID: 1
      },
      {
        id: 6,
        grpName: "China",
        parentGroupID: 1
      },
      {
        id: 7,
        grpName: "USA",
        parentGroupID: 2
      },
      {
        id: 8,
        grpName: "Germany",
        parentGroupID: 3
      },
      {
        id: 9,
        grpName: "Maharashtra",
        parentGroupID: 4
      },
      {
        id: 10,
        grpName: "Texas",
        parentGroupID: 7
      },
      {
        id: 11,
        grpName: "Bayern",
        parentGroupID: 8
      },
      {
        id: 12,
        grpName: "Mumbai",
        parentGroupID: 9
      },
      {
        id: 13,
        grpName: "Dallas",
        parentGroupID: 10
      },
      {
        id: 14,
        grpName: "Munich",
        parentGroupID: 11
      }
    ];

    defaultDropdownData = [
      "Select Continent",
      "Select Country",
      "Select State",
      "Select City"
    ];
  }
  notifyFinalDropDownValue(event) {
    console.log("FINAL VALUE", event);
  }

  notifyDropDownValue(event) {
    console.log("ALL SELECTIONS", event);
  }
}
```

Add the following component tag in you template

```html
<ng-cascading-dropdown
  [inputCascadingData]="defaultTestData"
  [defaultSelectionData]="defaultDropdownData"
  [showDefaultSelection]="true"
  (notifyDropDownValue)="notifyDropDownValue($event)"
  (notifyFinalDropDownValue)="notifyFinalDropDownValue($event)"
>
</ng-cascading-dropdown>
```

### Settings

The following list of settings are supported by the component. Configure the settings to meet your requirement.

| Setting              | Type    | Description                                                  | Default Value |
| :------------------- | :------ | :----------------------------------------------------------- | :------------ |
| inputCascadingData   | Array   | Input Data for cascading dropdown                            | [ ]           |
| defaultSelectionData | Array   | Text to be show in the dropdown, when no items are selected. | [ ]           |
| showDefaultSelection | Boolean | Show the default text for Dropdown                           | false         |
| disableDropdown      | Boolean | Disable the Cascading Dropdown                               | false         |

### Events

- `notifyDropDownValue` - Returns all the selections for all dropdown
  Example : (notifyDropDownValue)="notifyDropDownValue(\$event)"
- `notifyFinalDropDownValue` - Return the final selected item
  Example : (notifyFinalDropDownValue)="notifyFinalDropDownValue(\$event)"

## Run locally

- Clone the repository or downlod the .zip,.tar files.
- Run `npm install`
- Run `ng serve` for a dev server
- Navigate to `http://localhost:4200/`
  The app will automatically reload if you change any of the source files.
