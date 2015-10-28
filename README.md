# Bootstrap Tutorial for TIY Houston

###0. Some Prelims:
Some mockups I've built w bootstrap
- [Example 1](http://t3patterson.github.io/Portfolio/)
- [Example 2](http://lingerie-x.herokuapp.com/)
- [Example 3](http://t3patterson.github.io/LaCondesa/)
- [Example 4](http://t3patterson.github.io/furniture-dealer/)

We will build sth based on and similar to this template 
- [bootstrap-template](http://ironsummitmedia.github.io/startbootstrap-agency/)

###1. Setup new project `bootstrap-walkthru` with your build
run the npm install with your `package.json` file and any setup/linkups


###2. Install bootstrap with npm and import it into your css file
1. `npm install bootstrap`  

2. At line 1 of your `style.css` file in you will need to import the bootstrap styles from the node_modules     
  ```
  @import ../node_modules/bootstrap/dist/css/bootstrap.css
  ```

3. Get glyphicons set up -- we need to change the `url` font-file-path on the `@font-face` rule to `..node_modules/bootstrap/dist/fonts/«font-type»`
```
    @font-face {
      font-family: 'Glyphicons Halflings';
      src: url('../node_modules/bootstrap/dist/fonts/glyphicons-halflings-regular.eot');
      src: url('../node_modules/bootstrap/dist/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), 
          url('../node_modules/bootstrap/dist//fonts/glyphicons-halflings-regular.woff2') format('woff2'), 
          url('../node_modules/bootstrap/dist/fonts/glyphicons-halflings-regular.woff') format('woff'), 
          url('../node_modules/bootstrap/dist/fonts/glyphicons-halflings-regular.ttf') format('truetype'), 
          url('../node_modules/bootstrap/dist/fonts/glyphicons-halflings- regular.svg#glyphicons_halflingsregular') format('svg');
    }
```


###3. Bootstrap On the Page Sanity Check
1. start your local server and go to your `index.html`  

2. change the name of the `<div class="container">` to have a class of `wrapper`
  * we do this because 'container' is a style-class in bootstrap  

3. make sure in your `index.html` file that the font is showing helvetica
`<h1>Hi bootstrap</h1>`

### -- Cool dev trick! --
I use this `outline` css property to show the positioning of elements when i'm in dev phase. Makes me feel like a samaurai warrior. 
```
*,
*:before,
*:after {
    box-sizing: border-box;
    outline: 1px solid rgba(200,0,0,.15);
}
```

###6. Hero Div -- w/ bootstrap's *jumbotron*
1. Copy and paste code for hero unit -- bootstrap calls it [jumbotron] (http://getbootstrap.com/components/#jumbotron)

**Tip**
Being a nazi is not cool, but in your code being an indentation nazis are okay. Make sure your html is indented right

###7. Navbar
1. Let's checkout the docs on Bootstrap's [Navbar](http://getbootstrap.com/components/#navbar)
2. We could copy and paste straight from the docs like we did for the jumbotron BUT....we don't want all that stuff
3. Lets be crafty....and take it from the page source i.e. c+p from Inspect Element: http://getbootstrap.com/components/#navbar-fixed-top

###8. Grid It 1 - Responsive Content Columns
1. `.container-fluid` > `.row` > `.col-«size»-«x/12»` >  |your html|
  * this order of nesting is very important due to bootstraps margin/padding setting

2. First do it with `col-xs-12` * 3  
  
3. Then add the `col-sm-4` to see the effect  

   **Tip**
Think mobile first. It's easier to go from simple and build up to complex rather than the other way around

###9. Grid It 2 - Responsive Image Columns
   1. Same as before: start with good div structure `.container-fluid` > `.row` > `.col-xs-12` and make 6 of them  
  
*i.e*. `<div class="col-xs-12">` * 6
 
   2.  Grab the [thumbnail component](http://getbootstrap.com/components/#thumbnails-default) from the bs docs
   ```
   <a href="#" class="thumbnail">
  <img src="..." alt="...">
</a>
<p>Deesigin</p>
   ```
 
   3. Populate the img-tag's  `src` attribute with random images from [lorempixel.com](http://lorempixel.com/)
*e.g.* http://lorempixel.com/300/200/business/5

###10. Footer w/ a form
1. Same as it always was:
  `.container-fluid` > `.row` > `.col-«size»-«x/12»`

2. we will need to use the [bootstrap forms](http://getbootstrap.com/css/#forms-example)...for now let's keep it simple with form types

3. notice that the form changes layout when viewport widens...how should we do this any ideas?
  **Answer:** `<form>` wraps around `col-xs-12` > `email, `  and  `col-xs-6`

4. For the big fat text area we will need [bootstrap's text area component](http://getbootstrap.com/css/#textarea)

5. Let's checkout how the bootstrap button syntax `class= "btn btn-«type»`  note the many [button styles](http://getbootstrap.com/css/#buttons-options)





### Cleanup
1. Hero-div: 
  - [text-align center](http://getbootstrap.com/css/#type-alignment) for the hero-div:
     
  - bg image
  - padding problem--- solve w/ padding-top on `.wrapper`

2. Navbar
  - let's align the nav-elements to the right with bootstrap's
    [navbar component alignment](http://getbootstrap.com/components/#navbar-component-alignment)

3. Grid it w/ icons & text
   *icons*

4. Grid it w/ icons & thumbnails

