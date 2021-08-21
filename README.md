# angular-componentlinkedstyle

employee.ts

```js
export interface IEmployee {
  id: number;
  code: string;
  name: string;
  salary: number;
}
```

employee-component.component.ts

```js
import { Component, OnInit } from '@angular/core';
import { IEmployee } from './employee';

@Component({
  selector: 'app-employee-component',
  templateUrl: './employee-component.component.html',
  styleUrls: ['./employee-component.component.css']
})
export class EmployeeComponentComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
  employees: IEmployee[] = [
    {
      id: 1,
      code: 'VOD1410',
      name: 'Akshay Patel',
      salary: 3000
    },
    {
      id: 2,
      code: 'VOD1710',
      name: 'Panth Patel',
      salary: 1500
    }
  ];
}
```
employee-component.component.html

```html
<table>
  <thead>
    <td>Id</td>
    <td>Code</td>
    <td>Name</td>
    <td>Salary</td>
  </thead>
  <tr *ngFor="let employee of employees">
    <td>{{employee.id}}</td>
    <td>{{employee.code}}</td>
    <td>{{employee.name}}</td>
    <td>{{employee.salary}}</td>
  </tr>
</table>
```
employee-component.component.css

```css
thead {
  color: #337ab7;
}
```

app.module.ts

```js
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';

import { AppComponent } from './app.component';
import { EmployeeComponentComponent } from './employee-component/employee-component.component';

@NgModule({
  imports: [BrowserModule, FormsModule],
  declarations: [AppComponent, EmployeeComponentComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

app.component.html

```html
<app-employee-component></app-employee-component>
```


