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


###2. Configure bootstap and font awesome
1. Install bootstrap thru npm: `npm install bootstrap`  

2. At line 1 of your `style.css` file in you will need to import the bootstrap styles from the node_modules     
  ```
  @import ../node_modules/bootstrap/dist/css/bootstrap.css
  ```

3. Get **[font awesome](https://fortawesome.github.io/Font-Awesome/get-started/)** set up...in the `<head>` on your `index.html` page:
```
   <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css"> 
```

4. Set `<div class="container">` to have a class of `wrapper` instead -- `container` is a bootstrap style


###3. Bootstrap On the Page Sanity Check
1. start your local server and go to your `index.html`  

2. change the name of the `<div class="container">` to have a class of `wrapper`
  * we do this because 'container' is a style-class in bootstrap  

3. make sure in your `index.html` file that the font is showing helvetica
`<h1>Hi bootstrap</h1>`

### -- Cool dev trick! --
I use this `outline` css property to show the positioning of elements when i'm in dev phase. You can also hover and increase pxls to demonstrate the box of the element. Makes me feel like a samaurai warrior. 
```
*,
*:before,
*:after {
    box-sizing: border-box;
    outline: 1px solid rgba(200,0,0,.15);
    tranition: all .1s;
}

*:hover{
  outline: 2px solid rgba(200,0,0,.15);
}
```

###4. Hero Div -- w/ bootstrap's *jumbotron*
1. Copy and paste code for hero unit -- bootstrap calls it [jumbotron] (http://getbootstrap.com/components/#jumbotron)

**Tip**
Being a nazi is not cool, but in your code being an indentation nazis are okay. Make sure your html is indented right

###5. Navbar
1. Let's checkout the docs on Bootstrap's [Navbar](http://getbootstrap.com/components/#navbar)
2. We could copy and paste straight from the docs like we did for the jumbotron BUT....we don't want all that stuff
3. Lets be crafty....and take it from the page source i.e. c+p from Inspect Element: http://getbootstrap.com/components/#navbar-fixed-top

###6. Sevices Section - Responsive Content Columns W/ Icons
1. `.container-fluid` > `.row` > `.col-«size»-«x/12»` >  |your html|
  * this order of nesting is very important due to bootstraps margin/padding setting

2. First do it with `col-xs-12` * 3  
  
3. Then add the `col-sm-4` to see the effect  

   **Tip**
Think mobile first. It's easier to go from simple and build up to complex rather than the other way around

###7. Portfolio Section - Responsive Columns W/ Thumbnails
   1. Same as before: start with good div structure `.container-fluid` > `.row` > `.col-xs-12` and make 6 of them  
      
     *i.e*. `<div class="col-xs-12"> </div>` * 6
 
   2.  Grab the [thumbnail component](http://getbootstrap.com/components/#thumbnails-default) from the bs docs
   ```
   <a href="#" class="thumbnail">
      <img src="..." alt="...">
   </a>
   ```
 
   3. Populate the img-tag's  `src` attribute with random images from [lorempixel.com](http://lorempixel.com/)
*e.g.* http://lorempixel.com/300/200/business/5

###8. Contact-us : responsive form & form group
1. Same as it always was:
  `.container-fluid` > `.row` > `.col-«size»-«x/12»`

2. we will need to use the [bootstrap forms](http://getbootstrap.com/css/#forms-example)...for now let's keep it simple with form types
  - important thing about forms in bootstrap
    1. outer div needs to have a class of `form-group`
    2. `<input>` needs to have a class of `form-control`

3. notice that the form changes layout when viewport widens...how should we do this any ideas?
  **Answer:** 
  ```
  <div col-xs-12 col-xs-6> 
     ## Name Input 
     ## Email Input
  </div>
  <div col-xs-12 col-xs-6>
    ## Tell Me More textarea
  </div>

  ```

4. For the big text area we will need [bootstrap's text area component](http://getbootstrap.com/css/#textarea)

5. Let's checkout how the bootstrap button syntax `class= "btn btn-«type»`  note the many [button styles](http://getbootstrap.com/css/#buttons-options)





### Polishing Up With CSS
this is when css skills become important
1. Add your own classes to major divs for your own styles...   
  *it's a bad idea to style the bootstrap classes (e.g. `jumbotron`, `input-group`, `col-xs-12`, etc... ) in your CSS*  

  - Example: `<div class="jumbotron hero-splash">` (+ `hero-splash`)
    
  - major divs to add:   
    - `my-nav`
    - `hero-splah`
    - `services`
    - `portfolio`
    - `contact`
  
2. Margin/Padding
  - set padding/margins on `h2` elements and on major `div`
  ```
    .services h2,
    .portfolio h2,
    .contact-us h2 {
        margin: 0;
        margin-bottom: 25px;
    }

    .portfolio, 
    .services, 
    .contact-us{
        padding-top: 25px;
        padding-bottom: 25px

    }
  ```

3. Navbar
  + let's align the nav-elements to the right with bootstrap's
    [navbar component alignment](http://getbootstrap.com/components/#navbar-component-alignment)
  + let's make it black: add the class `navbar-inverse` on `<nav>` element

4. Hero-div:
  1. cool full-width background cover trick. on `.hero-splash` in `style.scss`
  ```
  background: url(http://lorempixel.com/900/600/nature/1/) 100% 100% no-repeat;
  background-size: cover;
  ```
   
  2. **problem**: navbar cuts into the herodiv
    + **solution**: padding-top on wrapper div that is the same height of navbar

5. Big Icons Centered in Circle - so hot right now!!!
  1. The HTML  
  ```
  <div class="big-icon">
    <i class="fa fa-shopping-cart"></i>
  </div>
  ```

  2. The CSS
  *line-height* will vertically center the icon :)
  ```
    display: block;
    margin: 0 auto;

    line-height: 150px; width: 150px;
    border-radius: 50%;

    background: #f1c40f;
    color: #fff;
    font-size: 80px;
    text-align: center;
  ```

6. Outer bg-color, narrow inner-content w/ bootstrap container classes
```
<div class="container-fluid">
   <div class="container">
     ## your HTML here
   </div>
</div>

```
  

### Don't Be Basic
Bootstrap resources and addons
- [bootbundle](http://www.bootbundle.com/)
  - **spectacular** resource for:
    + additional components
    + code snippets for common ui features
    + themes
    + flat icons
    + stock images and photos
    + mockups
    + patterns/textures

- [bootswatch](https://bootswatch.com/)
  + aditional 'skins' for bootstrap
    + changes default css styles for
      + color schemes
      + button styles
      + typography 
      + form groups & tables
      + navs & dropdowns
      + and more
      + 

