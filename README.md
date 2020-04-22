# Angular Store

This example is from https://angular.io/start


## Getting Started
Here are exercises with hints

### Build the app
<details>
  <summary>Hint</summary>
  
  `npm install`
</details>


### Serve the file
<details>
  <summary>Hint</summary>
  
  `ng serve --open`
</details>


## Product Page Challenges

### List the products
<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>
  
  use `ngFor`
</details>

<details>
  <summary>Hint 2</summary>
  
  use `*ngFor="let product of products"`
</details>

<details>
  <summary>Hint 3</summary>

  ```
    <div *ngFor="let product of products">
        <h3>{{product.name}}</h3>
    </div>
  ```  
</details>

</details>

### Add product details as an aref title
<details>
  <summary>Hints</summary>

<details>
  <summary>Hint 1</summary>
  
  `<a [title]=...`
</details>

<details>
  <summary>Hint 2</summary>
  
  ```
    <a [title]="product.name + ' details'">
        {{ product.name }}
    </a>
  ```
</details>

</details>

### Product description as paragraph, if it exists
<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>
  
  `*ngIf`
</details>

<details>
  <summary>Hint 2</summary>
  
  `*ngIf='product.description`
</details>

<details>
  <summary>Hint 3</summary>
  
  ```
    <p *ngIf="product.description">
        Description: {{ product.description }}
    </p>

  ```
</details>

</details>


### Add a share button
<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>

  `(click)=`
</details>

<details>
  <summary>Hint 2</summary>
  
  ```
    <button (click)="share()">
        Share
    </button>
  ```
</details>

<details>
  <summary>Hint 3</summary>
  
  ```
    <p *ngIf="product.description">
        Description: {{ product.description }}
    </p>

  ```
</details>

</details>


### Review
<details>
  <summary>Interpolation</summary>
  
  ```{{ }}```
</details>

<details>
  <summary>Property Binding</summary>
  
  ```[ ]```
</details>

<details>
  <summary>Event Binding</summary>
  
  ```( )```
</details>


## Product Alert
"The next step is to create a new alert feature that takes a product as an input. The alert checks the product's price, and, if the price is greater than $700, displays a "Notify Me" button that lets users sign up for notifications when the product goes on sale."


### Create Component 'product-alerts'
Stub the basic module directory and 3 main files

<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>

  `src/app/product-alerts/product-alerts.component.[css/html/ts]`
</details>

<details>
  <summary>Hint 2</summary>
  
  In the product-alerts.component.ts file remember to fill in
  
  - import
  - @Component (selector, templateUrl, styleUrls)
  - export class with implements
  - constructor and ngOnInit

</details>

<details>
  <summary>Hint 3</summary>
  
  ```
    import { Component, OnInit } from '@angular/core';

    @Component({
      selector: 'app-product-alerts',
      templateUrl: './product-alerts.component.html',
      styleUrls: ['./product-alerts.component.css']
    })

    export class ProductAlertsComponent implements OnInit {

        constructor() {}

        ngOnInit() {}

    }

  ```
</details>

</details>



### Connect Component 'product-alerts'
Connect component to the application and display on product

<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>

  Add component to app.module.ts
</details>

<details>
  <summary>Hint 2</summary>
  
  Add `<app-product-alerts></app-product-alerts>` to product-list.component.html
</details>

</details>


### Pass information to Component 'product-alerts'
Pass the product information from product-list to product-alerts and make alert only show if price > 500

<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1</summary>

  add `import { Input } from '@angular/core';` to product-alerts
</details>

<details>
  <summary>Hint 2</summary>
  
  Add `@Input() product;` to ProductAlertsComponent class
</details>

<details>
  <summary>Hint 3</summary>
  
  Update product-list `<app-product-alerts [product]="product"> </app-product-alerts>`
</details>

<details>
  <summary>Hint 4</summary>
  
  Update product-list html
  ```
    <p *ngIf="product.price > 500">
      <button>Notify Me</button>
    </p>
  ```
</details>

</details>


### Make 'Notify Me' work

<details>
  <summary>Hints</summary>
  
<details>
  <summary>Hint 1 - import output</summary>

  ```
    import { Component } from '@angular/core';
    import { Input } from '@angular/core';
    import { Output, EventEmitter } from '@angular/core';
  ```
</details>

<details>
  <summary>Hint 2 - add output</summary>
  
  ```
    export class ProductAlertsComponent {
      @Input() product;
      @Output() notify = new EventEmitter();
    }
  ```
</details>

<details>
  <summary>Hint 3 - emit in html</summary>
  
  ```
    <p *ngIf="product.price > 500">
      <button (click)="notify.emit()">Notify Me</button>
    </p>
  ```
</details>

<details>
  <summary>Hint 4</summary>
  
  Add on notify to ProductListComponent
  ```
    onNotify() {
      window.alert('You will be notified when the product goes on sale');
    }
  ```
</details>
<details>
  <summary>Hint 5</summary>
  
  Add binding to product-list.component.html
  ```
    <app-product-alerts
      [product]="product" 
      (notify)="onNotify()">
    </app-product-alerts>
  ```
</details>

</details>


