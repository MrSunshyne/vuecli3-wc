# vuecli3-wc

A simple project containing a demo of web components generated using vuecli3

`/website.html` is a standalone webpage

`/components` contain vue SFC files that are converted to Web Components using the command `vue build MyApp.vue --target wc`

This generates one js file that can be included in website.html along the html tag `<my-app></my-app>`, 
and that allows the web component to live & load inside the webpage! 

Tested on the following browsers so far : 

- Chrome / macOS High Sierra

