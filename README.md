# Ionic Angular SQLite

* App to store data using the [Ionic 5 framework](https://ionicframework.com/docs), [cordova SQLite database](https://ionicframework.com/docs/native/sqlite) & [SQLite Porter](https://ionicframework.com/docs/native/sqlite-porter) and [Capacitor](https://capacitor.ionicframework.com/).
* **Note:** to open web links in a new window use: _ctrl+click on link_

![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/ionic-angular-sqlite?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/ionic-angular-sqlite?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/ionic-angular-sqlite?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/ionic-angular-sqlite?style=plastic)

## Table of contents

* [Ionic Angular SQLite](#ionic-angular-sqlite)
  * [Table of contents](#table-of-contents)
  * [General info](#general-info)
  * [Screenshots](#screenshots)
  * [Technologies](#technologies)
  * [Setup](#setup)
  * [Code Examples](#code-examples)
  * [Features](#features)
  * [Status & To-do list](#status--to-do-list)
  * [Inspiration](#inspiration)
  * [Contact](#contact)

## General info

* App allows user to add details of developer and products.
* Initial seed data is a short list of developers and dev skills.

## Screenshots

![example screen print](./img/dev.screen.png)
![example screen print](./img/products-screen.png)

## Technologies

* [Ionic/angular v5](https://ionicframework.com/)
* [Ionic v5](https://ionicframework.com/docs/cli)
* [Angular 12](https://angular.io/)
* [cordova plugin SQLite database v5](https://ionicframework.com/docs/native/sqlite)
* [cordova SQLite Porter v5](https://ionicframework.com/docs/native/sqlite-porter)

## Setup

* Run `npm i` to install dependencies
* To start the server on _localhost://8100_ type: 'ionic serve'

## Code Examples

* `database.service.ts` function to get details of a developer from the database.

```typescript
getDeveloper(id): Promise<Dev> {
  return this.database.executeSql('SELECT * FROM developer WHERE id = ?', [id]).then(data => {
    let skills = [];
    if (data.rows.item[0].skills !== '') {
      skills = JSON.parse(data.rows.item[0].skills);
    }

    return {
      id: data.rows.item(0).is,
      name: data.rows.item(0).name,
      skills,
      img: data.rows.item[0].img
    };
  });
}
```

## Features

* storage of data in an SQL database.

## Status & To-do list

* Status: compiles and displays in a dev server. Build webpacks created. Needs implementing on an Android device or simulator to use database etc. Database side not tested.
* To-do: test database to see if it stores Dev and Product details.

## Inspiration

* [devdactic: How to Build an Ionic 4 App with SQLite Database & Queries (And Debug It!)](https://devdactic.com/ionic-4-sqlite-queries/).

## :file_folder: License

* This project is licensed under the terms of the MIT license.

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com
