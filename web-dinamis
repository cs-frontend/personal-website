# Menambahkan Aksi Toggle Menu

### Buat folder js, kemudian buat file dengan nama script.js

### Masukan kode berikut di dalam script.js

```
const toggleMenu = document.getElementById("toggle-menu");
const navMenu = document.querySelector("nav>ul");

toggleMenu.addEventListener("click", () => {
  const isActive = navMenu.classList.contains("active");

  if (isActive) {
    navMenu.classList.remove("active");
  } else {
    navMenu.classList.toggle("active");
  }
});
```

### Menghubungkan script.js pada index.html

```
<body>
  ...
  
  <!-- JavaScript -->
  <script src="js/script.js" type="text/javascript"></script>

</body>
```

### Menambahkan css untuk menampilkan menu pada file responsive.css

```
header nav ul.active {
  display: flex;
  animation-name: fadeIn;
  animation-duration: 0.3s;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
```
