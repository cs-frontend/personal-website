# WEB Dasar

### Membuat Navigasi

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personal Website</title>

  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  
  <header>
    <nav>
      <a href="#">Angelica Stephanie</a>

      <ul>
        <li><a href="#">Education</a></li>
        <li><a href="#">Portofolio</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

</body>
</html>
```

### CSS 

```
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: #ddd;
}

nav {
  width: 100%;
  height: 80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #ffffff;
  padding: 0px 140px;
}

nav a {
  color: #000000;
  text-decoration: none;
  font-weight: bold;
  font-size: 18px;
}

nav ul {
  display: flex;
  list-style: none;
}

nav ul li {
  margin-right: 20px;
}
```
