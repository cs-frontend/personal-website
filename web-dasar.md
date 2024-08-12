# WEB Dasar

### Membuat Navigasi

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Personal Website</title>

  <!-- Font -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;900&display=swap" rel="stylesheet">

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

    <div class="profile-image">
      <img src="assets/images/profile.jpg" alt="profile image">
    </div>

    <div class="job-title">
      <h4>Hi, I am a</h4>
      <h1>Graphic Designer</h1>
    </div>
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
  scroll-behavior: smooth;
  font-family: "Poppins", sans-serif;
  color: #22223b;
}

header {
  height: 500px;
  position: relative;
  background-color: #22223b;
}

nav {
  position: fixed;
  left: 0px;
  top: 0px;
  z-index: 10;
  width: 100%;
  height: 100px;
  background-color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px 140px;
}

nav #toggle-menu {
  display: none;
}

nav a {
  text-decoration: none;
  font-size: 1.75rem;
  font-weight: 700;
}

nav ul {
  display: flex;
  list-style: none;
}

nav ul li {
  margin-left: 40px;
}

nav ul li a {
  font-size: 1.25rem;
  font-weight: 500;
  opacity: 0.75;

  /* transition */
  transition: all 0.3s ease;
}

nav ul li a:hover,
nav ul li a.active {
  opacity: 1;
}

.profile-image {
  position: absolute;
  left: 140px;
  bottom: -130px;
  width: 320px;
  height: 400px;
  z-index: 1;
}

.profile-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top center;
}

.job-title {
  position: absolute;
  bottom: 40px;
  left: calc(140px + 320px + 40px);
}

.job-title h4 {
  color: #ffffff;
  font-size: 1.75rem;
  font-weight: 600;
}

.job-title h1 {
  color: #ffffff;
  font-size: 3.5rem;
  font-weight: 700;
}
```
