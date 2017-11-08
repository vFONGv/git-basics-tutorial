# A Tutorial on Git Basics

to be written...

## Files in Demonstration

To illustrate git in action, I pulled text files from a great book, [ThinkPython2](http://greenteapress.com/thinkpython2), using wget.

## Install git
in Terminal
```
brew install git
brew link git
```

## Get text files to manipulate
in Terminal
```
brew install wget
mkdir ThinkPython2
cd ThinkPython2
wget -r -np -k -nd http://greenteapress.com/thinkpython2/html/
```

## git init
in Terminal
```
git init
git add .
git commit -am 'initial commit'
```

## follow steps
in Terminal
```
git checkout -b move-images-into-a-folder
mkdir images
mv *.png images/
```

With Sublimetext installed, in Terminal
```
subl .
```

Use <kbd>⇧</kbd><kbd>⌘</kbd><kbd>f</kbd> call out find and replace panel.(In Windows use <kbd>Ctrl</kbd> <kbd>Shift<kbd><kbd>f<kbd>)

(Atom editor has an unsolved issue on finding and replacing with regex...)

> find:
> ```html
> img src="
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
> img src="images/
> ```

in Terminal
```
git status
git add .
git status
git commit -am 'move images into a folder'
git checkout master
git merge move-images-into-a-folder
git log
```

```
git checkout -b add-bootstrap
```

> find:
> ```html
> <link rel="stylesheet" type="text/css" href="thinkpython2.css">
> ```
> where:
> ```
> *.html
> ```
> replace
> ```html
> <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
> <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap-theme.min.css" integrity="sha384-fLW2N01lMqjakBkx3l/M9EahuwpSfeNvV63J5ezn3uZzapT0u7EYsXMjQV+0En5r" crossorigin="anonymous">
> <link rel="stylesheet" type="text/css" href="thinkpython2.css">
> ```

> find:
>
> ```html
> </html>
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
> <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min> .js"></script>
> <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js" integrity="sha384-0mSbJDEHialfmuBBQP6A4Qrprq5OVfW37PRR3j5ELqxss1yVq> OtnepnHVP9aJ7xS" crossorigin="anonymous"></script>
> </html>
> ```

with regex enabled
> find:
> ```
> <a href="(.*)"><img.*\s\Sa href="(.*)"><img.*\s\Sa href="(.*)"><img.*\s\Shr>
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
>   <nav class="navbar navbar-default navbar-fixed-top">
>     <div class="container-fluid">
>       <!-- Brand and toggle get grouped for better mobile display -->
>       <div class="navbar-header">
>         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
>           <span class="sr-only">Toggle navigation</span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>         </button>
>         <a class="navbar-brand" href="#"><strong>Think Python</strong> - How to Think like a Computer Scientist (2e) <em>by Allen B. Downey</em></a>
>       </div>
>       <div>
>         <ul class="nav navbar-nav navbar-right">
>           <li><a href="http://greenteapress.com/thinkpython2/html/index.html"><span class="glyphicon glyphicon glyphicon-book" aria-hidden="true"></span></a></li>
>           <li><a href="$1"><span class="glyphicon glyphicon glyphicon-menu-left" aria-hidden="true"></span></a></li>
>           <li><a href="index.html"><span class="glyphicon glyphicon glyphicon-home" aria-hidden="true"></span></a></li>
>           <li><a href="$3"><span class="glyphicon glyphicon glyphicon-menu-right" aria-hidden="true"></span></a></li>
>           <li><a href="http://amzn.to/1VUYQUU"><span class="glyphicon glyphicon glyphicon-shopping-cart" aria-hidden="true"></span></a></li>
>         </ul>
>       <div>
>     </div><!-- /.container-fluid -->
>   </nav>
> ```

>find:
>
>```
> <a href="index.html.1"><img src="images/up.png" ALT="Up"></a>
> <a href="thinkpython2002.html"><img src="images/next.png" ALT="Next"></a>
> <hr>
>```
> where:
> ```
> thinkpython2001.html
> ```
> replace:
> ```html
>   <nav class="navbar navbar-default navbar-fixed-top">
>     <div class="container-fluid">
>       <!-- Brand and toggle get grouped for better mobile display -->
>       <div class="navbar-header">
>         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
>           <span class="sr-only">Toggle navigation</span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>         </button>
>         <a class="navbar-brand" href="#"><strong>Think Python</strong> - How to Think like a Computer Scientist (2e) <em>by Allen B. Downey</em></a>
>       </div>
>       <div>
>         <ul class="nav navbar-nav navbar-right">
>           <li><a href="http://greenteapress.com/thinkpython2/html/index.html"><span class="glyphicon glyphicon glyphicon-book" aria-hidden="true"></span></a></li>
>           <li><a href="$1"><span class="glyphicon glyphicon glyphicon-menu-left" aria-hidden="true"></span></a></li>
>           <li><a href="index.html"><span class="glyphicon glyphicon glyphicon-home" aria-hidden="true"></span></a></li>
>           <li><a href="$3"><span class="glyphicon glyphicon glyphicon-menu-right" aria-hidden="true"></span></a></li>
>           <li><a href="http://amzn.to/1VUYQUU"><span class="glyphicon glyphicon glyphicon-shopping-cart" aria-hidden="true"></span></a></li>
>         </ul>
>       <div>
>     </div><!-- /.container-fluid -->
>   </nav>
> ```



> find:
>
> ```
> <a href="thinkpython2022.html"><img src="images/back.png" ALT="Previous"></a>
> <a href="index.html.1"><img src="images/up.png" ALT="Up"></a>
> <hr>
> ```
> where:
> ```
> thinkpython2023.html
> ```
> replace:
> ```html
>   <nav class="navbar navbar-default navbar-fixed-top">
>     <div class="container-fluid">
>       <!-- Brand and toggle get grouped for better mobile display -->
>       <div class="navbar-header">
>         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
>           <span class="sr-only">Toggle navigation</span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>         </button>
>         <a class="navbar-brand" href="#"><strong>Think Python</strong> - How to Think like a Computer Scientist (2e) <em>by Allen B. Downey</em></a>
>       </div>
>       <div>
>         <ul class="nav navbar-nav navbar-right">
>           <li><a href="http://greenteapress.com/thinkpython2/html/index.html"><span class="glyphicon glyphicon glyphicon-book" aria-hidden="true"></span></a></li>
>           <li><a href="thinkpython2022.html"><span class="glyphicon glyphicon glyphicon-menu-left" aria-hidden="true"></span></a></li>
>           <li><a href="index.html"><span class="glyphicon glyphicon glyphicon-home" aria-hidden="true"></span></a></li>
>           <li><a href="thinkpython2023.html"><span class="glyphicon glyphicon glyphicon-menu-right" aria-hidden="true"></span></a></li>
>           <li><a href="http://amzn.to/1VUYQUU"><span class="glyphicon glyphicon glyphicon-shopping-cart" aria-hidden="true"></span></a></li>
>         </ul>
>       <div>
>     </div><!-- /.container-fluid -->
>   </nav>
> ```

in index.html, insert before `<table>`
> ```html
>   <nav class="navbar navbar-default navbar-fixed-top">
>     <div class="container-fluid">
>       <!-- Brand and toggle get grouped for better mobile display -->
>       <div class="navbar-header">
>         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
>           <span class="sr-only">Toggle navigation</span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>           <span class="icon-bar"></span>
>         </button>
>         <a class="navbar-brand" href="#"><strong>Think Python</strong> - How to Think like a Computer Scientist (2e) <em>by Allen B. Downey</em></a>
>       </div>
>       <div>
>         <ul class="nav navbar-nav navbar-right">
>           <li><a href="http://greenteapress.com/thinkpython2/html/index.html"><span class="glyphicon glyphicon glyphicon-book" aria-hidden="true"></span></a></li>
>           <li><a href="index.html"><span class="glyphicon glyphicon glyphicon-menu-left" aria-hidden="true"></span></a></li>
>           <li><a href="index.html"><span class="glyphicon glyphicon glyphicon-home" aria-hidden="true"></span></a></li>
>           <li><a href="thinkpython2001.html"><span class="glyphicon glyphicon glyphicon-menu-right" aria-hidden="true"></span></a></li>
>           <li><a href="http://amzn.to/1VUYQUU"><span class="glyphicon glyphicon glyphicon-shopping-cart" aria-hidden="true"></span></a></li>
>         </ul>
>       <div>
>     </div><!-- /.container-fluid -->
>   </nav>
> ```

> find:
> ```
> <hr>\s\Sa href="(.*)"><img.*\s\Sa href="(.*)"><img.*\s\Sa href="(.*)"><img.*\s
> ```
> where:
> ```
> *.html
> ```
> replace with nothing:
> ```
>
> ```

> find:
> ```
> <hr>\s\Sa href="(.*)"><img.*\s\Sa href="(.*)"><img.*\s
> ```
> where:
> ```
> *.html
> ```
> replace with nothing:
> ```
>
> ```

> find:
> ```
> <a href="http://amzn.to/1VUYQUU">Buy this book at Amazon.com</a>
> ```
> where:
> ```
> *.html
> ```
> replace with nothing:
> ```
>
> ```

in Terminal
```
git add .
git commit -am 'menu added'
git checkout master
git merge add-bootstrap
git log
```

in Terminal
```
git checkout -b content
```

> find:
> ```
> <td valign="top" width="100" bgcolor="#b6459a">
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
> <td valign="top" width="100" bgcolor="#b6459a" id="col-left">
> ```

> find:
> ```
> <td width=130 valign="top">
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
> <td width=130 valign="top" id="col-right">
> ```

> find：
> ```
> <td valign="top" width="600" style="padding: 20px 20px;">
> ```
> where:
> ```
> *.html
> ```
> replace:
> ```html
> <td valign="top" id="content">
> ```

append `thinkpython2.css`

```css
td#col-left, td#col-right {
  display: none;
}
body{
    font-family: "Open Sans";
    font-size: 18px;
    padding-top: 60px;
    max-width: 800px;
    margin: 0 auto;
    margin-bottom:10em;
    background-color: #eee;

}

blockquote {
    border-left: 0px solid #eee;
}

pre.verbatim {
    font-family: "Courier New";
    margin: 10px auto;
    font-size: 16px;
}

table.c000 {
    margin: 12px auto;
}
```

in Terminal
```
git add .
git commit -am 'content cleaned'
git checkout master
git merge content
```
