# Bootstrap Tutorial for TIY Houston

###0. Some Prelims:
Sites I've built w bootstrap
http://t3patterson.github.io/Portfolio/
http://lingerie-x.herokuapp.com/
http://t3patterson.github.io/LaCondesa/
http://t3patterson.github.io/furniture-dealer/

We will build sth off this site
[bootstrap-template](http://ironsummitmedia.github.io/startbootstrap-agency/)

###1. Setup new project `bootstrap-walkthru` with your build
    run the npm install with your `package.json` file and any setup/linkups


###2. Install bootstrap with npm and import it into your css file
    1. `npm install bootstrap`
    2. At the top of your `style.css` file in you will need to import the bootstrap styles. 

      Line 1 will look something something like: `@import ../node_modules/bootstrap/dist/css/bootstrap.css`


###3. Bootstrap On the Page Sanity Check
    1. start your local server and go to your `index.html`
    2. change the name of the `<div class="container">` to have a class of `wrapper`
      - we do this because 'container' is a style-class in bootstrap

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
    1. Copy and paste code for hero unit -- bootstrap calls it 'jumbotron': http://getbootstrap.com/components/#jumbotron

    **Tip**
    Being a nazi is not cool, but in your code being an indentation nazis are okay. Make sure your html is indented right

###7. Navbar
    1. http://getbootstrap.com/components/#navbar
    2. We could copy and paste straight from the docs like we did for the jumbotron BUT....we don't want all that stuff
    3. Lets be crafty....and take it from the page source i.e. c+p from Inspect Element: http://getbootstrap.com/components/#navbar-fixed-top

###8. Responsive Content Columns




### Cleanup
1. Hero-div: 
  - text-align center for the hero-div:
    http://getbootstrap.com/css/#type-alignment 
  - bg image
  - padding problem--- solve w/ padding-top on `.wrapper`

2. Navbar
  - let's align the nav-elements to the right
    http://getbootstrap.com/components/#navbar-component-alignment

3. Grid it

