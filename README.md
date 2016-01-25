# Website Performance Optimization portfolio project

### How to run the application

Open index.html in a browser or visit http://theoberta.github.io/frontend-nanodegree-mobile-portfolio.

### Challenge
1. achieve PageSpeed score of 90 for index.html
2. ensure frame rate of 60fps when scrolling in pizza.html
3. optimize function so pizzas resize in less than 5ms


### Optimizations done

**1. index.html optimizations:**

* use of font loader: https://github.com/typekit/webfontloader
* ad `media:print` to stylesheet link
* add `async` to analytics link
* reduce image size
* inline CSS
* minify html, css, js

**2. optimize for 60fps:**

* rewrite function `updatePositions` - take out any unnecessary look ups (scrollTop) and calculations (phase) out of the for loop, take items array out of function
* use `transform` instead of `left`, so paint won't be triggered
* use `requestAnimationFrame`
* functionality added: screen height is checked and only number of background pizzas necessary to fill the screen are generated
* set `backface-visibility: hidden`, so background pizzas have own layer

**3. resize pizzas:**

* delete function `determineDx` - function does not do anything
* rewrite function `changePizzaSizes` - take out any unnecessary function calls or look ups out of for loop

**aditional optimizations**

* function `changeSliderLabel`: take out look up out of function and substitute querySelector by getElementById
* loop to append generated Pizzas: remove `pizzasDiv` from for loop to improve load performance
* change to anonymous function generating background pizzas: creation of elem moved outside of for loop; take out look up for movingPizzas out of function and substitute querySelector by getElementById