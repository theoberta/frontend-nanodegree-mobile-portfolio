# Website Performance Optimization portfolio project

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
* reduce number of background pizzas, reduce number of columns and adjust position of pizzas so they still fill screen
* set `backface-visibility: hidden`, so background pizzas have own layer

**3. resize pizzas:**

* delete function `determineDx` - function does not do anything
* rewrite function `changePizzaSizes` - take out any unnecessary function calls or look ups out of for loop