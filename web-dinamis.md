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

# Menambahkan Loading

### Masukan kode berikut pada index.html setelah tag </footer>

```
<!-- Loading -->
<div id="loading">
  <div class="loading-indicator"></div>
</div>
```

### Tambahkan kode css berikut pada file style.css

```
#loading {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #22223b9e;
  z-index: 99;
  display: flex;
  justify-content: center;
  align-items: center;
}

.loading-indicator {
  width: 50px;
  height: 50px;
  border-radius: 9999px;
  border: 4px solid #ffffff;
  border-top-color: transparent;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
```

### Menambahkan fungsi untuk menghilangkan loading setelah 2 detik, tambahkan kode berikut pada script.js

```
document.addEventListener("DOMContentLoaded", () => {
  const loadingEl = document.getElementById("loading");

  setTimeout(() => {
    loadingEl.style.display = "none";
  }, 2000);
});
```

