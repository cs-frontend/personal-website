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
      <img src="images/profile.jpg" alt="profile image">
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
  height: 400px;
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
  width: 240px;
  height: 300px;
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
  left: calc(140px + 240px + 40px);
}

.job-title h4 {
  color: #ffffff;
  font-size: 1.75rem;
  font-weight: 600;
}

.job-title h1 {
  color: #ffffff;
  font-size: 3rem;
  font-weight: 700;
}
```

# Membuat Section Bio, Education & Portofolio

### HTML Bio Code

```
<body>
  ...

  <main>
    <p class="bio">
      Passionate graphic designer seeking remote opportunities to bring creative visions to life.
      Let's collaborate and create something extraordinary! 🎨✨ #GraphicDesigner #RemoteWork #CreativityUnleashed
    </p>

  </main>

</body>
```

### CSS Bio Code

```
main {
  padding-top: 170px;
  padding-left: 140px;
  padding-right: 140px;
}

main p {
  font-size: 1.25rem;
  font-weight: 400;
}
```

### HTML Education Code

```
<main>
  ...

    <section id="education">
      <h2>Education</h2>

      <article>
        <div class="logo">
          <img src="assets/images/binus.jpeg" alt="binus">
        </div>

        <div class="content">
          <h3>Graduated as Graphic Designer</h3>
          <h4>Binus University</h4>
          <p>20 July 2019 - 20 July 2024</p>
        </div>
      </article>

      <article>
        <div class="logo">
          <img src="assets/images/smk-yaj.jpeg" alt="smk yaj">
        </div>

        <div class="content">
          <h3>Graduated as Software Engineer</h3>
          <h4>YAJ Vocational High School</h4>
          <p>20 June 2017 - 20 June 2019</p>
        </div>
      </article>
    </section>

  ...
</main>
```

### CSS Education Code

```
main h2 {
  font-size: 2rem;
  font-weight: 600;
}

section h2 {
  margin-bottom: 40px;
}

section#education {
  margin-top: 60px;
  margin-bottom: 60px;
}

section#education article {
  display: flex;
  justify-content: start;
  align-items: start;
  margin-bottom: 40px;
}

section#education article .logo {
  width: 100px;
  height: 100px;
  margin-right: 20px;
  border: 1px solid #C9C9C9;
}

section#education article .logo img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

section#education article .content {
  padding-left: 20px;
}

section#education article .content h3 {
  font-size: 1.5rem;
  font-weight: 600;
}

section#education article .content h4 {
  font-size: 1.25rem;
  font-weight: 500;
  margin-top: 5px;
}

section#education article .content p {
  font-size: 1rem;
  font-weight: 400;
  margin-top: 5px;
}
```

### HTML Portofolio Code

```
<main>
  ...

  <section id="portofolio">
      <h2>Portofolio</h2>

      <div class="list-portofolio">
        <article>
          <div class="image-portofolio">
            <img src="assets/images/portofolio-1.jpg" alt="portofolio">
          </div>

          <div class="content-portofolio">
            <h3>UI Design Personal Website</h3>
            <h4>Role as Graphic Designer</h4>
            <p>Create a design system and prototype personal website project using Figma.</p>

            <button>View</button>
          </div>
        </article>
        <article>
          <div class="image-portofolio">
            <img src="assets/images/portofolio-2.png" alt="portofolio">
          </div>

          <div class="content-portofolio">
            <h3>Template Personal Website</h3>
            <h4>Role as Front End Web Developer</h4>
            <p>Create a template project personal website using HTML, CSS & JavaScript.</p>

            <button>View</button>
          </div>
        </article>
        <article>
          <div class="image-portofolio">
            <img src="assets/images/portofolio-3.png" alt="portofolio">
          </div>

          <div class="content-portofolio">
            <h3>REST API Personal Website</h3>
            <h4>Role as Backend Developer</h4>
            <p>Create a REST API project for manage data personal website.</p>

            <button>View</button>
          </div>
        </article>
      </div>
    </section>
  
  ...
</main>
```

### CSS Portofolio Code

```
section#portofolio .list-portofolio {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  margin-bottom: 60px;
}

.list-portofolio article .image-portofolio {
  width: 100%;
  height: 300px;
}

.list-portofolio article .image-portofolio img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.list-portofolio article .content-portofolio {
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  text-align: center;
}

.list-portofolio article .content-portofolio h3 {
  font-size: 1.5rem;
  font-weight: 600;
}

.list-portofolio article .content-portofolio h4 {
  font-size: 1.25rem;
  font-weight: 500;
  margin-top: 5px;
}

.list-portofolio article .content-portofolio p {
  font-size: 1rem;
  font-weight: 400;
  margin-top: 5px;
}

.list-portofolio article .content-portofolio button {
  color: #ffffff;
  font-size: 1rem;
  font-weight: 500;
  background-color: #22223b;
  border: none;
  padding: 10px 20px;
  margin-top: 20px;
  cursor: pointer;
  box-shadow: 0px 3px 3px rgba(0, 0, 0, 0.25);
  transition: all 0.3s ease;
}

.list-portofolio article .content-portofolio button:hover {
  opacity: 0.5;
}
```


# Membuat Section Contact, Feedback & Footer

### HTML Contact Code

```
<main>
  ...

    <section id="contact">
      <h2>Contact us</h2>

      <div class="list-contact">
        <a href="https://api.whatsapp.com/send?phone=6281234567890">
          <div class="icon">
            <img src="assets/icons/whatsapp.png" alt="whatsapp">
          </div>
        </a>
        <a href="https://www.linkedin.com/in/angelica-stephanie">
          <div class="icon">
            <img src="assets/icons/linkedin.png" alt="linkedin">
          </div>
        </a>
        <a href="https://github.com/angelica-stephanie">
          <div class="icon">
            <img src="assets/icons/github.png" alt="github">
          </div>
        </a>
        <a href="mailto:Uw9j3@example.com">
          <div class="icon">
            <img src="assets/icons/email.png" alt="email">
          </div>
        </a>
      </div>
    </section>
  
  ...
</main>
```

### CSS Contact Code

```
section#contact .list-contact {
  display: flex;
  justify-content: start;
  align-items: center;
  margin-bottom: 60px;
}

section#contact .list-contact .icon {
  width: 60px;
  height: 60px;
  border-radius: 9999px;
  margin-right: 20px;
  background-color: #22223b;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease;
}

section#contact .list-contact .icon img {
  width: 36px;
  height: 36px;
  object-fit: contain;
  object-position: center;
}

section#contact .list-contact .icon:hover {
  opacity: 0.5;
}
```

### HTML Feedback Code

```
<main>
  ...

    <section id="feedback">
      <h2>Give your feedback about me!</h2>

      <form action="/">
        <div class="input-group">
          <div class="input-text">
            <label for="name">Your name</label>
            <input type="text" name="name" id="name">
          </div>
  
          <div class="input-text">
            <label for="email">Your email address</label>
            <input type="email" name="email" id="email">
          </div>
        </div>

        <div class="input-text">
          <label for="message">Message</label>
          <textarea name="message" id="message" cols="30" rows="10"></textarea>
        </div>
        
        <button type="submit">Submit</button>
      </form>
    </section>
  
  ...
</main>
```

### CSS Feedback Code

```
section#feedback {
  margin-bottom: 60px;
}

section#feedback form .input-group {
  width: 100%;
  display: flex;
  justify-content: start;
  align-items: center;
  gap: 20px;
  margin-bottom: 20px;
}

section#feedback form .input-text {
  display: flex;
  flex: 1;
  flex-direction: column;
}

section#feedback form .input-text label {
  font-size: 1rem;
  font-weight: 500;
  margin-bottom: 5px;
}

section#feedback form .input-text input {
  font-size: 1rem;
  font-weight: 400;
  padding: 10px;
  border: 1px solid #22223B;
}

section#feedback form .input-text textarea {
  font-size: 1rem;
  font-weight: 400;
  padding: 10px;
  border: 1px solid #22223B;
}

section#feedback form button {
  color: #FFFFFF;
  font-size: 1rem;
  font-weight: 500;
  background-color: #22223B;
  border: none;
  padding: 10px 20px;
  margin-top: 20px;
  cursor: pointer;
  box-shadow: 0px 3px 3px rgba(0, 0, 0, 0.25);
  transition: all 0.3s ease;
}

section#feedback form button:hover {
  opacity: 0.5;
}
```

### HTML Footer Code

```
<body>
  ...

  <footer>
    <p>Copyright ©2024 <strong>Angelica Stephanie</strong>. All rights reserved.</p>
  </footer>
</body>
```

### CSS Footer Code

```
footer {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #22223B;
  height: 60px;
}

footer p,
footer strong {
  font-size: 1rem;
  font-weight: 400;
  text-align: center;
  color: #FFFFFF;
}

footer strong {
  font-weight: 600;
}
```

# Responsive Code

### HTML

```
<head>
  ...

  <!-- Responsive -->
  <link rel="stylesheet" href="assets/css/responsive.css">
</head>

<body>

  <header
    <nav>
      ...

      <!-- Toggle -->
      <div id="toggle-menu">
        <div></div>
        <div></div>
        <div></div>
      </div>
    </nav>
  </header>
</body>
```

### CSS

```
@media screen and (max-width: 768px) {
  body {
    overflow-x: hidden;
  }

  header {
    height: 260px;
  }

  header nav {
    height: auto;
    padding: 0px;
    height: 60px;
  }

  header #toggle-menu {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    width: 32px;
    height: 32px;
    margin-right: 20px;
  }

  header #toggle-menu div {
    font-size: 1.5rem;
    width: 100%;
    height: 4px;
    background-color: #22223b;
    margin: 2px auto;
  }

  header nav a {
    font-size: 1rem;
    padding: 5px 20px;
  }

  header nav ul {
    position: fixed;
    top: 60px;
    left: 0;
    right: 0;
    width: 100%;
    flex-direction: column;
    align-items: start;
    background-color: #fff;
    display: none;
  }

  header nav ul li {
    width: 100%;
    margin-left: 0px;
    padding: 5px 0px;
    border-top: 1px solid #c9c9c9;
  }

  header nav ul li a {
    font-size: 1rem;
  }

  header .profile-image {
    width: 150px;
    height: 150px;
    left: 20px;
    bottom: -75px;
  }

  header .job-title {
    left: 20px;
    right: 20px;
    bottom: 100px;
  }

  header .job-title h4 {
    font-size: 1rem;
  }

  header .job-title h1 {
    font-size: 2rem;
  }

  main {
    padding-left: 20px;
    padding-right: 20px;
    padding-top: 100px;
  }

  main p {
    font-size: 1rem;
  }

  main h2 {
    font-size: 1.25rem;
  }

  section#education article .content h3,
  .list-portofolio article .content-portofolio h3 {
    font-size: 1.125rem;
  }

  section#education article .content h4,
  .list-portofolio article .content-portofolio h4 {
    font-size: 1rem;
  }

  section#education article .content p,
  .list-portofolio article .content-portofolio p {
    font-size: 0.875rem;
  }

  section#contact .list-contact .icon {
    width: 40px;
    height: 40px;
    margin-right: 10px;
  }
  
  section#contact .list-contact .icon img {
    width: 24px;
    height: 24px;
  }

  section#education article .logo {
    width: 80px;
    height: 80px;
    flex-shrink: 0;
    margin-right: 10px;
  }

  section#portofolio .list-portofolio {
    grid-template-columns: repeat(1, 1fr);
  }

  .list-portofolio article {
    margin-bottom: 10px;
  }

  section#feedback form .input-group {
    flex-direction: column;
    align-items: start;
  }

  section#feedback form .input-group .input-text {
    width: 100%;
  }

  footer p,
  footer strong {
    font-size: 0.875rem;
  }
}
```

