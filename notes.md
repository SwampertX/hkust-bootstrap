# Chapter 1 - container, row, columns, imports

## Imports
General HTML structure
- DOCTYPE - HTML tag - HEAD - BODY
### To initialize
Put inside **head**. First thing.
```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,
    initial-scale=1, shrink-to-fit=no">
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
### To import CSS/JS for bootstrap 4
Put **inside head, just before title**
```html
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css">
    <link href="css/styles.css" rel="stylesheet">
```
Javascript files usually take longer to load, so **put at the end of body**.
```html
<!-- jQuery first, then Popper.js, then Bootstrap JS. -->
    <script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
    <script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
    <script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
```
## Use of containers
- Containers
```
jumbotron # usually used for header bars
container # just about everything
```
- Formatting
```
rows rows-header rows-content 
col col-<number> col-<screen-size>-<number>
align-items-<center> justify-items-<center>
```
Each row is divided into 12 columns, and the number represent the columns you want to use for that particular element.

There are 4 default screen sizes, small (*sm*), medium (*md*), large(*lg*), extra-large (*xl*), and extra-small (leave that blank).

Bootstrap uses a upward inheritance (*as I call it*), a setting is "broadcasted" to the screens of at least that size.

For example:
```html
<div class="col col-12 col-sm-6 col-lg-10">
    <!-- items -->
</div>
```
Will give:
- 12 columns to extra-small
- 6 columns to small and medium
- 10 columns to large and extra-large
screens respectively.

# Chapter 2: Navigation
## Navigation
### Navbar
Idea: A very top row containing:
- For extra small screens: Logo/Company name plus a toggler for contents
- For small onwards: Logo/Company plus main directories
Hence the design is:
- nav
    - button
    - logo
    - div
        - ul
            - items

```html
<nav class="navbar navbar-dark bg-primary navbar-expand-sm fixed-top">
        <!-- Just one container -->
        <div class="container">
            <!-- Containing button, -->
            <button class="navbar-toggler" type="button"
                data-toggle="collapse" data-target="#Navbar">
                    <span class="navbar-toggler-icon"></span> 
            </button>
            <!-- brand -->
            <a class="navbar-brand" href="#">
                Ristorante Con Fusion
            </a>
            <!-- rest of the items, wrapped in ul, then wrapped in div
                (for collapsing)-->
            <div class="collapse navbar-collapse" id="Navbar">
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item active">
                        <a class="nav-link" href="#">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="./aboutus.html">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Menu</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#">Contact</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
```
### Breadcrumbs
Usually implemented as 
- div
    - link
    - link
    - ...
    - active
```html
<div class="col-12 breadcrumb">
    <li class="breadcrumb-item">
        <a href="./index.html">Home</a>
    </li>
    <li class="breadcrumb-item active">About Us</li>
</div>
```
### Font-icons
We use the ```font-awesome``` and ```bootstrap-social``` libraries.
Font-awesome provides the icons while Bootstrap-social, the background.
```html
<!-- a home icon -->
<span class="fa fa-home fa-lg"></span>
<!-- a social media icon -->
<a class="btn btn-social-icon btn-facebook" 
    href="http://www.facebook.com/profile.php?id=">
        <i class="fa fa-facebook fa-lg"></i></a>
```
### Button-groups
- div (button group)
    - a tag surrounding icons and texts (buttons)
    - ...
- available classes (for color)
    - btn btn-primary (Deep blue)
    - btn btn-info (Light blue)
    - btn btn-success (Green)
```html
<div class="btn-group" role="group">
    <a role="button" class="btn btn-primary" href="tel:+85212345678">
        <i class="fa fa-phone"></i> Call</a>
    <a role="button" class="btn btn-info">
        <i class="fa fa-skype"></i> Skype</a>
    <a role="button" class="btn btn-success" href="mailto:confusion@food.net">
        <i class="fa fa-envelope-o"></i> Email</a>
</div>
```

### Forms
- div-wrapped-form (to prevent overextension of textboxes on big screens)
    - div-wrapped-entry-rows ```class="form-group rows"```, for ex: 
    - textboxes
        - label (can give 2 columns on bigger screens for uniformity)
        ```class="col-md-2 col-form-label"```
        - div-wrapped input (distribute up the remaining space)
        ```class="form-control"```
    - checkbox (i will *throw* the example here)
        ```html
        <div class="form-group row">
            <div class="col-md-6 offset-md-2">
                <div class="form-check">
                    <input type="checkbox" class="form-check-input" name="approve" id="approve" value="">
                    <label class="form-check-label" for="approve">
                        <strong>May we contact you?</strong>
                    </label>
                </div>
            </div>
            <div class="col-md-3 offset-md-1">
                <select class="form-control">
                    <option>Tel.</option>
                    <option>Email</option>
                </select>
            </div>
        </div>
        ```
    - textarea
        - similar to textboxes, just change input tag to textarea tag
    - submit button
        - a div-wrapped button tag
        ```html
            <div class="offset-md-2 col-md-10">
                <button type="submit" class="btn btn-primary">Send Feedback</button>
            </div>
        ```
### Tables and Cards
Tables:
- div (class="table-responsive")
    - table (class="table table-striped")
        - thead (class="thead-dark")
            - tr
                - th or td
                - th or td
                - ...
        - tbody
            - tr
                - th or td
                - th or td 
                - ...

Cards: Facts
- div (class="col-*")
    - div (class="card")
        - header (class="card-header bg-primary text-white)
        - div (class="card-body")
        - dl (class="row")
            - dt (class="col-6")
            - dd (class="col-6")
            - dt (class="col-6")
            - dd (class="col-6")
            - ...

Cards: Quote
- div (class="col-*")
    - div (class="card card-body bg-light")
        - blockquote (class="blockquote")
            - p (class="mb-0")
              quote goes here...
            - footer (class=blockquote-footer)
              author goes here
                - cite
                  source goes here


