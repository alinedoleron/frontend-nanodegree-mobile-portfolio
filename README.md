## Website Performance Optimization portfolio project

### Getting started

Some useful tips to help you get started:

1. Check out the repository
2. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
2. To make your local server accessible remotely run:

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```


### Optimizations made on the project

#### Part 1: PageSpeed Score 
The optimizations made to achieve a PageSpeed score of at least 90 for Mobile and Desktop were:

1. Put async attribute on google analytics script
2. Minify style.css and compress js files
3. Inlined css
3. Eliminate google fonts link
4. Put styles on the bottom of index.html
4. Convert .jpg pictures to .png format

I got 95 / 100 for Mobile and 98 / 100 for Desktop.

#### Part 2: Getting Rid of Jank

1. On views/js/main.js the following changes were made to render with a consistent frame-rate at 60fps when scrolling.:
  * On function updatePositions():
    1. document.documentElement.scrollTop query removed from the for loop
  * Into anonymous funtion on line 545:
    1. Create a variable "movingPizza" from document.querySelector("#movingPizzas1") query that was removed from from for loop 


2. On views/js/main.js the following changes were made to make time to resize pizzas less than 5 ms:
  * On function changePizzaSizes(size):   
    1. Create a variable "allPizza" for document.querySelectorAll(".randomPizzaContainer") query that was removed from the for loop
    2. Once all Pizzas have the same offsetwidth it's unnecessary do a loop over all pizzas to get the newWidth

  
 