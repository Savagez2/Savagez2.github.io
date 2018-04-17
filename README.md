## How to run
1. Extract files
2. Run locally (review how to set up local server below)

##Part 1: Optimized PageSpeed Insights score for index.html with fixes below:
1.  The images in both img and views/images were large and needed reduced per google pagespeed.  I reduced these    
    images with paint (img - profilepic: 75% of original; views/images - pizzeriaEdited: 1% of original).
2.  I removed the online google fonts as it didn't seem to have much impact on the look of the site
3.  Moved the scripting resources that were not required to load the page to after and made them deferred
4.  Minified the HTML and the CSS. I also in lined the styles CSS

## Part 2: Optimized PageSpeed Insights score for pizza.html with fixes below:
1. replaced the querySelector with getElementById within the changeSliderLabel function
2. In the function updatePositions, I moved the var initialization out of the loop for scrollTop and also initialized the num variable with the items.length
3. In the event listener which creates the moving pizzas, I shrank the number generated from 200 to 20 and it didnt seem to effect the look of the site. I also created a var for the moving pizza element out of the loop, so it doesnt need to query more than it needs to.
4. In the function changePizzaSizes, I removed the determineDX function and just had the function return the percent size based on what the slider was. I took out all the DOM lookups out of the loop and assigned them variables before the loop. The size gets assigned directly at the end of the loop instead of on the fly for each one.

## How to run local server to test page speed
Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)
