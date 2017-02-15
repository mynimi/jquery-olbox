# Olbox a minimal, yet powerful Lightbox Plugin for jQuery
A super simple responsive lightbox plugin that opens images and iframes including navigators

## What does it do?
The Plugin will read for a data-attribute, check if it's a link or an iframe tag, decide whether to use an image or iframe tag and open up. It comes with a navigator.

Iframes and Images can be mixed. You can have multiple lightboxes across a page. So a separate navigator for each category as an examples.

## Basic Use
Check out the minimal example below:

``` html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <title>Your Page</title>
            <!-- Olbox CSS -->
            <link href="css/olbox.min.css" rel="stylesheet">
        </head>
        <body>
            <!-- header -->
            <header>
                <h1>My awesome header</h1>
            </header>

            <!-- whatever other code you use -->

            <span data-olbox="<iframe src='http://halfapx.com/' width='100%' height='500px'></iframe>">Toggles Iframe Container</span>
            <span data-olbox="https://www.youtube.com/embed/nIhLQ8E9c1s?">Toggles Responsive Iframe</span>
            <span data-olbox="http://halfapx.com/img/posts/collection.jpg">Toggles Image</span>

            <!-- whatever other code you use -->

            <!-- jQuery -->
            <script src="js/jquery.min.js"></script>
            <!-- jQuery Olbox -->
            <script src="js/jquery.olbox.min.js"></script>
            <!-- initiate sticky nav -->
            <script>
                $('span').olbox();
            </script>
        </body>
    </html>
```

## Types of Media
As you can see there are 3 different ways to use olbox.

### Image
This is the most common way, just add the link to your image and your all set, it will be added and be responsive.

### Iframe Container
You can add full iframe Tags withn the data attribute. Just make sure to use other quotes within. The added Lightbox will be responsive, however the height of the iframe will not be adjusted, I do not recommend this method, but there are cases where it might be desired.

### Iframe Link
The Other Method is iFrame Link. Add the link to the site you want to open in an iframe. Using the paddinghack, the iframe will be placed responsively with a fixed aspect ratio. By default the ratio is set to be 16:9 which should work amongst most types of iframes, like video or websites.

## Options
Here are all of the Options with the defaults.

``` js
    $(selector).olbox({
        iframeRatioWidth : 16, // used for responsive iframe aspectRatio
        iframeRatioHeight:  9, // used for responsive iframe aspectRatio
        includeVisualNavigator: true, // include arrow buttons to navigate
        includeKeyNavigator: true, // include option to navigate with arrow keys
        dataAttribute: 'olbox', // set custom data-attribute (for example if multiple separate lightboxes will be needed)
        debug: false // setting to true will add console.logs after some of the steps
    });
```

## Having multiple lightboxes
If you want to have different navigations, you'll have to set different data-attributes for each set.
Example set `data-olbox-video` for all of your videos and `data-olbox-image` for all the images. Then toggle like so:

``` js
    $('span[data-olbox-video]').olbox({dataAttribute: 'olbox-video'});
    $('span[data-olbox-image]').olbox({dataAttribute: 'olbox-image'});
```

## CSS
The Plugin comes with a stylesheet. There is a Sass file with Variables for easy overwriting. Make sure to use Autoprefixer when compiling or add the needed prefixes for it to work across the board.

## Questions, Problems, Enhancements etc.
Just open an issue and let me know.
