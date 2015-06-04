Mock Data
============================
#### Mock data for sample apps, demos, and POCs

[![npm](http://img.shields.io/npm/v/@bigstickcarpet/mock-data.svg)](https://www.npmjs.com/package/@bigstickcarpet/mock-data)
[![License](https://img.shields.io/npm/l/@bigstickcarpet/mock-data.svg)](LICENSE)


Features
--------------------------
* No dependencies
* 100 mock employees, with names, addresses, phone numbers, etc.
* 100 mock projects, with names, dates, departments, employees assigned, etc.
* Full-size and thumbnail photos for each employee


Installation
--------------------------
Install via [NPM](https://docs.npmjs.com/getting-started/what-is-npm):

````bash
npm install @bigstickcarpet/mock-data
````


Usage
--------------------------
The mock data can be used as plain JSON files or as JavaScript arrays of objects.

```javascript
// Raw JSON data
var employeeJSON = require('mock-data/employees.json');
employeeJSON.forEach(function(employee) {
  console.log(employee.dob);    // string (in ISO 8601 zulu format)
});

// JavaScript objects
var mockData = require('mock-data');
mockData.employees.forEach(function(employee) {
  console.log(employee.dob);    // Date object
});
```


Employees
--------------------------
`mockData.employees` is an array of objects with the following properties:

| Property              | Data Type        | Description
|:----------------------|:-----------------|:----------------------------
| `username`            | string           | A alphanumeric username that is unique for each employee
| `password`            | string           | An alphanumeric password
| `name.first`          | string           | First name
| `name.last`           | string           | Last name
| `gender`              | string           | "male" or "female"
| `portrait`            | string           | The path of the full-size portrait photo
| `thumbnail`           | string           | The path of the thumbnail-size portrait photo
| `email`               | string           | Email address
| `address.street`      | string           | House number and street name
| `address.city`        | string           | City name
| `address.state`       | string           | U.S. state name (full name, not abbreviation)
| `address.zip`         | string           | U.S. zip code, in the format #####
| `phones`              | array of objects | Array of phone objects
| `phones[].type`       | string           | "home", "office", or "cell"
| `phones[].number`     | string           | Phone number, in the format ###-##-####
| `ssn`                 | string           | U.S. Social Security Number, in the format ###-##-####. Unique for each employee.
| `dob`                 | Date             | Date of birth
| `hiredOn`             | Date             | Date the employee was hired
| `terminatedOn`        | Date or null     | Date the employee was terminated, or `null` if still employed
| `department`          | string           | "Accounting", "Sales", "Human Resources", or "Marketing"
| `roles`               | array of strings | Array of roles, such as "employee", "consultant", "part time", etc.


Projects
--------------------------
`mockData.projects` is an array of objects with the following properties:

| Property              | Data Type        | Description
|:----------------------|:-----------------|:----------------------------
| `id`                  | string           | Numeric ID that is unique for each project
| `name`                | string           | Project name that is unique for each project. 55 characters max.
| `description`         | string           | Long project description. 2000 characters max
| `department`          | string           | "Accounting", "Sales", "Human Resources", or "Marketing"
| `startedOn`           | Date             | Date that the project started
| `endedOn`             | Date or null     | Date that the project ended, or `null` if still ongoing
| `assigned`            | array of strings | Array of usernames of employees who are assigned to the project. Projects will only have employees from the same department.


License
--------------------------
All JSON data is [MIT licensed](http://opensource.org/licenses/MIT) and can be used however you want.

All images (employee portraits) are licensed under [Creative Commons BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/2.0/deed.en) and have some limitations on their use.

See the [LICENSE file](LICENSE) for more details.
