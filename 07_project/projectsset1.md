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

## project 2 
