
# Welcome

> Hi there, this is my NBA PHP website project

> Below you will find more information of the website

> Enjoy :eyes:


# NBA

[![NBA](https://i.imgur.com/1c3Bgzx.png)](height=1475)


> So, why NBA?

- I love basketball
- So many great players, so much excitement around the league :basketball:

---
## Table of Contents

> Click on one of the options:

- [Code](#code)
- [Features](#features)
- [Made](#made)
- [License](#license)
---

## Code

```php
//Calculating team win percentage

    $total_games = $team['win'] + $team['loss'];
    $percent = $team['win'] /  $total_games;
    $percent_friendly = number_format( $percent * 100, 1 ) . '%';

    echo $percent_friendly;

```
- A simple PHP calculation to find out each team's win percentage

:point_down:

![GIF](https://i.gyazo.com/becf287f8db0a0cabe5aa7dd955e904d.gif?_ga=2.234696856.745103909.1551221898-228063269.1547928545)


- Adding an image to a team
- To do this we must first set the target to which the image will be saved

```php
// This is the directory where images will be saved

    $target = "../images/";
    $target = $target . basename( $_FILES['image']['name']);

```

- Then, we add the image to the database as shown below :point_down:

```php

// Add the image to the database
    $query = "INSERT INTO categories (image) VALUES ('$image')";

// execute query
    mysqli_query($db, $sql);

    if (move_uploaded_file($_FILES['image']['tmp_name'], $target)) {
      $msg = "Image uploaded successfully";
    }else{
      $msg = "Failed to upload image";
    }
  }
    $result = mysqli_query($db, "SELECT * FROM images");

```

- Finally, we want to display it in the page

```html

// Displaying the image
    <form action="add_team.php" method="post" enctype="multipart/form-data" id="add_category_form">
        <input type="file" name="image" id="image" style="padding-top:20px">
        <input id="add_category_button" type="submit" value="Add">
    </form>

```




---

## Features

> Adding **new** player and editing **existing** player

![GIF](https://i.gyazo.com/e6cb5e59acc322184de98e07189b8c63.gif?_ga=2.264340428.2127822680.1551223246-228063269.1547928545)

![GIF](https://i.gyazo.com/92527c80c4f23ae548580941c5593cb8.gif?_ga=2.193676142.2127822680.1551223246-228063269.1547928545)

- **Is that all?**
    - Of course not, users can also add or delete a team and view the current standings!

---

## Made

> By:

| <a href="http://www.google.com" target="_blank">**Renzo W**</a>
| :---: |
| [![renwid](https://i.imgur.com/8mkpIBh.jpg)](http://google.com)
| <a href="http://github.com/renwid" target="_blank">`github.com/renwid`</a> |

- With :atom:
- and the help ***google***

---

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
- Copyright 2019 © <a href="http://nba.com" target="_blank">NBA</a>.
