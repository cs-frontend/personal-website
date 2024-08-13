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

# Menampilkan data dari server

### Menambahkan attribut id pada elemen html yang akan diubah menjadi data dinamis

#### Nama
```
<a href="#" id="user-fullname">Angelica Stephanie</a>
```

#### Profile Image
```
<img src="images/profile.jpg" alt="profile image" id="user-profile-image">
```

#### Job Title
```
<div class="job-title">
  <h4>Hi, I am a</h4>
  <h1 id="user-job-title">Graphic Designer</h1>
</div>
```

#### Bio
```
<p class="bio" id="user-bio">
  Passionate graphic designer seeking remote opportunities to bring creative visions to life.
  Let's collaborate and create something extraordinary! 🎨✨ #GraphicDesigner #RemoteWork #CreativityUnleashed
</p>
```

#### Contact
```
<div class="list-contact">
  <a href="https://api.whatsapp.com/send?phone=6281234567890" id="whatsapp">
    <div class="icon">
      <img src="icons/whatsapp.png" alt="whatsapp">
    </div>
  </a>
  <a href="https://www.linkedin.com/in/angelica-stephanie" id="linkedin">
    <div class="icon">
      <img src="icons/linkedin.png" alt="linkedin">
    </div>
  </a>
  <a href="https://github.com/angelica-stephanie" id="github">
    <div class="icon">
      <img src="icons/github.png" alt="github">
    </div>
  </a>
  <a href="mailto:Uw9j3@example.com" id="email">
    <div class="icon">
      <img src="icons/email.png" alt="email">
    </div>
  </a>
</div>
```

### Membuat fungsi untuk mengambil data dari server, modifikasi script.js menjadi seperti berikut
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

// Fungsi untuk mengambil data dari server
function fetchData() {
  var xhr = new XMLHttpRequest();

  const apiUrl =
    "https://personal-website-api-mauve.vercel.app/users/clzqbt2um0000120uiy6cnjku";

  xhr.open("GET", apiUrl, true);

  const loadingEl = document.getElementById("loading");

  xhr.onload = function () {
    if (xhr.status === 200) {
      var data = JSON.parse(xhr.responseText);

      displayData(data.user);
    } else {
      console.error("Failed to fetch data");
    }

    // Menyembunyikan loading
    loadingEl.style.display = "none";
  };

  xhr.onerror = function () {
    console.error("Request error");

    // Menyembunyikan loading
    loadingEl.style.display = "none";
  };

  xhr.send();
}

// Fungsi untuk membuat format tanggal DD MMM YYYY
function formatDate(date) {
  const options = { year: "numeric", month: "long", day: "numeric" };
  return new Date(date).toLocaleDateString("id-ID", options);
}

// Fungsi untuk menampilkan data
function displayData(userData) {
  // Menampilkan data nama user
  const elName = document.getElementById("user-fullname");
  elName.textContent = userData.name;

  // Menampilkan data pekerjaan user
  const elJobTitle = document.getElementById("user-job-title");
  elJobTitle.textContent = userData.job_title;

  // Menampilkan data profil user
  const elProfileImage = document.getElementById("user-profile-image");
  elProfileImage.src = userData.image;

  // Menampilkan data bio user
  const elBio = document.getElementById("user-bio");
  elBio.textContent = userData.bio;

  // Menampilkan data pendidikan user
  const elEducation = document.getElementById("education");
  elEducation.innerHTML = "";
  userData.educations.forEach((item) => {
    const period = formatDate(item.start_at) + " - " + formatDate(item.end_at);
    
    const educationItem = `
      <article>
        <div class="logo">
          <img src="${item.image}" alt="logo">
        </div>

        <div class="content">
          <h3>${item.major}</h3>
          <h4>${item.name}</h4>
          <p>${period}</p>
        </div>
      </article>
    `;
    elEducation.innerHTML += educationItem;
  });

  // Menampilkan data portofolio user
  const elPortofolio = document.getElementById("portofolio");
  elPortofolio.lastElementChild.innerHTML = "";

  userData.portofolios.forEach((item) => {
    const portofolioItem = `
      <article>
        <div class="image-portofolio">
          <img src="${item.image}" alt="portofolio">
        </div>

        <div class="content-portofolio">
          <h3>${item.name}</h3>
          <h4>Role as ${item.role}</h4>
          <p>${item.description}</p>

          <button onclick="window.open('${item.url}')">View</button>
        </div>
      </article>
    `;
    elPortofolio.lastElementChild.innerHTML += portofolioItem;
  });

  // Menampilkan data kontak whatsapp user
  const elWhatsapp = document.getElementById("whatsapp");
  elWhatsapp.setAttribute("href", `https://api.whatsapp.com/send?phone=${userData.whatsapp}`);

  // Menampilkan data kontak linkedin user
  const elLinkedin = document.getElementById("linkedin");
  elLinkedin.setAttribute("href", userData.linkedin);

  // Menampilkan data kontak github user
  const elGithub = document.getElementById("github");
  elGithub.setAttribute("href", userData.github);

  // Menampilkan data kontak email user
  const elEmail = document.getElementById("email");
  elEmail.setAttribute("href", `mailto:${userData.email}`);

  // Mengubah nama di footer sesuai data user
  const elFooter = document.querySelector("footer strong");
  elFooter.textContent = userData.name;
}

document.addEventListener("DOMContentLoaded", () => {
  fetchData();
});
```

