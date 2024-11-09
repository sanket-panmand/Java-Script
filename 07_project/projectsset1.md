# Project related to DOM

## project code link
[Click here](https://github.com/sanket-panmand/Java-Script/blob/main/07_project/projectsset1.md)
.......[Refrence link](https://stackblitz.com/edit/dom-project-chaiaurcode?file=index.html)


# Solution code
```css
//common css file
* {
    box-sizing: border-box;
  }
  
  body {
    margin: 0;
    font-family: system-ui, sans-serif;
    color: black;
    background-color: white;
  }
  
  nav {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    padding: 0.5rem;
    gap: 0.5rem;
    border-bottom: solid 1px #aaa;
    background-color: #eee;
  }
  
  nav a {
    display: inline-block;
    min-width: 9rem;
    padding: 0.5rem;
    border-radius: 0.2rem;
    border: solid 1px rgb(22, 22, 22);
    text-align: center;
    text-decoration: none;
    color: #1b1b1b;
  }
  
  nav a[aria-current='page'] {
    color: #000;
    background-color: #d4d4d4;
  }
  
  main {
    padding: 1rem;
  }
  
  h1 {
    font-weight: bold;
    font-size: 1.5rem;
  }
  
  .projects {
    display: flex;
    flex-direction: column;
  }
  
  .project-link {
    background-color: #fff;
    padding: 10px 30px;
    border-radius: 8px;
    color: #212121;
    text-decoration: none;
    border: 2px solid #212121;
    margin-top: 5px;
  }
  
```
## project 1 Background Color Switcher
```html
// html code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="../styles.css">
    
    <title>JavaScript Background Colour Changer</title>
</head>
<body>
    
    <nav>

        <a href="/" aria-current="page">Home</a>

        <a target="_blank" href="">About Project</a>

    </nav>

    <div class="canvas">

        <h1>Color Scheme Switcher</h1>

        <span class="button" id="grey"></span>
        <span class="button" id="white"></span>
        <span class="button" id="blue"></span>
        <span class="button" id="yellow"></span>

        <h2>Try clicking on one of the colors above</h2>

        <span>to change the background color of this page !</span>

    </div>

    <script src="logic.js"></script>

</body>
</html>
```
``` javascript
//javascript code

const buttons = document.querySelectorAll('.button');
const body = document.querySelector('body');

buttons.forEach(function (button) {
  console.log(button);
  button.addEventListener('click', function (e) {
    console.log(e);
    console.log(e.target);
    if (e.target.id === 'grey') {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id == 'white') {
      body.style.backgroundColor = e.target.id;
    }
    if (e.target.id =='blue'){
        body.style.backgroundColor = e.target.id;
    }
    if (e.target.id =='yellow'){
        body.style.backgroundColor = e.target.id;
    }
    
  });
});



```
```css
//css code
html {
    margin: 0;
}

span {
    display: block;
}

.canvas {
    margin: 100px auto 100px;
    width: 80%;
    text-align: center;
  }
  
  .button {
    width: 100px;
    height: 100px;
    border: solid black 2px;
    display: inline-block;
  }
  
  #grey {
    background: grey;
  }
  
  #white {
    background: white;
  }
  #blue {
    background: blue;
  }
  #yellow {
    background: yellow;
  }
  
```

## project 2 BMI Calculator 
```html
//html code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="../styles.css" />
 
    <title>BMI Calculator</title>
</head>
<body>
    <nav>
        <a href="/" aria-current="page">Home</a>
        <a target="_blank" href="/"
          >project code</a
        >
      </nav>
    
      <div class="container">
    <h1>BMI Calculator</h1>
    <form>
        <p>
            <label>Height in CM</label> 
            <input type="text" id="height">
        </p>
        <p>
            <label>Weight in KG</label> 
            <input type="text" id="weight">
        </p>

        <button>Calculate</button>

        <div id="results"></div>

        <div id="weight-guide">
            <h3>BMI Weight Guide</h3>
            <p>Under Weight = Less than 18.6</p>
            <p>Normal Range = 18.6 and 24.9</p>
            <p>Overweight = Greater than 24.9</p>
          </div>
    </form>
</div>
</body>
<script src="logic.js"></script>
</html>
```
```javascript
//javascript code
const form = document.querySelector('form');
// this usecase will give you empty
// const height = parseInt(document.querySelector('#height').value)

form.addEventListener('submit', function (e) {
  e.preventDefault();

  const height = parseInt(document.querySelector('#height').value);
  const weight = parseInt(document.querySelector('#weight').value);
  const results = document.querySelector('#results');

  if (height === '' || height < 0 || isNaN(height)) {
    results.innerHTML = `Please give a valid height ${height}`;
  } else if (weight === '' || weight < 0 || isNaN(weight)) {
    results.innerHTML = `Please give a valid weight ${weight}`;
  } else {
    const bmi = (weight / ((height * height) / 10000)).toFixed(2);
    //show the result
    results.innerHTML = `<span>${bmi}</span>`;
  }
});


```
```css
//css code
.container {
    width: 650px;
    height: 825px;
  
    background-color: #b0c0a6;
    padding-left: 200px;
  }
  #height,
  #weight {
    width: 150px;
    height: 25px;
    margin-top: 30px;

  }
  
  #weight-guide {
    margin-left: 75px;
    margin-top: 25px;
  }
  
  #results {
    font-size: 35px;
    margin-left: 90px;
    margin-top: 20px;
    color: rgb(241, 241, 241);
  }
  
  button {
    width: 150px;
    height: 35px;
    margin-left: 90px;
    margin-top: 25px;
    background-color: #fff;
    padding: 1px 30px;
    border-radius: 8px;
    color: #212121;
    text-decoration: none;
    border: 2px solid #212121;
  
    font-size: 25px;

   
  }
  
  h1 {
    padding-left: 15px;
    padding-top: 25px;
    
  }
  
```
## project 3 Digital Clock
```javascript
const clock = document.getElementById('clock');
// const clock = document.querySelector('#clock')

setInterval(function () {
  let date = new Date();
  // console.log(date.toLocaleTimeString());
  clock.innerHTML = date.toLocaleTimeString();
}, 1000);


```
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" type="text/css" href="../styles.css" />
    <title>Your Local Time</title>
    <style>
      body {
        background-color: #212121;
        color: #fff;
      }
      .center {
        display: flex;
        height: 100vh;
        justify-content: center;
        align-items: center;
        flex-direction: column;
      }
      #clock {
        font-size: 40px;
        background-color: orange;
        padding: 20px 50px;
        margin-top: 10px;
        border-radius: 10px;
      }
    </style>
  </head>
  <body>
    <div class="center">
      <div id="banner"><span>Your local time</span></div>
      <div id="clock"></div>
    </div>
    <script src="logic.js"></script>
  </body>
</html>

```