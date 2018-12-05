# Chapter 1 - container, row, columns, imports

## Imports
General HTML structure
- DOCTYPE - HTML tag - HEAD - BODY
### To initialize
Put inside **head**. First thing.
```
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,
    initial-scale=1, shrink-to-fit=no">
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
### To import CSS/JS for bootstrap 4
Put **inside head, just before title**
```
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css">
    <link href="css/styles.css" rel="stylesheet">
```
Javascript files usually take longer to load, so **put at the end of body**.
```
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
```
<div class="col col-12 col-sm-6 col-lg-10"><div>
```
Will give:
- 12 columns to extra-small
- 6 columns to small and medium
- 10 columns to large and extra-large
screens respectively.

