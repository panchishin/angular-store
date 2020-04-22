# Angular Store



## Getting Started

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

### Product description as paragraph, if it exists
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


### Add a share button
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



