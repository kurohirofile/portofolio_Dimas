<script setup>
import { themeColor, siteName } from "../data/items";
import { ref } from "vue";

const isDarkMode = ref(false);

const switchTheme = () => {
  const body = document.body;
  if (isDarkMode.value) {
    body.classList.remove('dark-mode');
    localStorage.setItem('theme', 'light');
  } else {
    body.classList.add('dark-mode');
    localStorage.setItem('theme', 'dark');
  }
  isDarkMode.value = !isDarkMode.value;
};

// Memuat tema yang dipilih pengguna dari localStorage saat halaman dimuat
const loadTheme = () => {
  const savedTheme = localStorage.getItem('theme');
  if (savedTheme === 'dark') {
    document.body.classList.add('dark-mode');
    isDarkMode.value = true;
  } else {
    document.body.classList.remove('dark-mode');
    isDarkMode.value = false;
  }
};

// Memanggil loadTheme saat komponen dimuat
loadTheme();
</script>

<template>
  <nav class="site-nav js-site-navbar mb-5 site-navbar-target" >
    <div class="container">
      <div class="site-navigation">
        <a href="" class="logo m-0 float-left" :style="{ color: isDarkMode ? 'white' : 'black' }">
  {{ siteName }}<span class="text-primary">.</span>
</a>

        <ul class="js-clone-nav d-none d-lg-inline-block site-menu float-left" >
          <li class="active">
            <a href="#About" class="nav-link" :style="{ color: isDarkMode ? 'white' : 'black' }">ABOUT</a>
          </li>
          <li class="active">
            <a href="#skills" class="nav-link" :style="{ color: isDarkMode ? 'white' : 'black' }">SKILL</a>
          </li>
          <li class="active">
            <a href="#contact" class="nav-link" :style="{ color: isDarkMode ? 'white' : 'black' }">CONTACT</a>
          </li>
          <li class="active">
            <a href="#portfolio" class="nav-link" :style="{ color: isDarkMode ? 'white' : 'black' }">PORTFOLIO</a>
          </li>
        </ul>
        <ul class="js-clone-nav  mt-1 d-lg-inline-block site-menu float-right">
          <li class="cta-primary d-none d-lg-block d-md-block">
  <a 
    href="https://drive.google.com/uc?id=1lzMUboX1w-v53iM8GcbRMpyyTVhbvVP1&export=download" 
    :style="[{ backgroundColor: themeColor, marginLeft: '10px' }]" 
    download>
    HIRE ME
  </a>
</li>


<li class="cta-secondary"   >
  <a href="#" @click="switchTheme">
    <i v-if="!isDarkMode" class="fas fa-sun" style="color: black; font-size: 18px;"></i> 
    <i v-if="isDarkMode" class="fas fa-moon" style="color: white; font-size: 18px;"></i>
  </a>
</li>

        </ul>
        <!-- <a href="#" class="burger ml-auto float-right site-menu-toggle js-menu-toggle d-inline-block dark d-lg-none" data-toggle="collapse" data-target="#main-navbar">
          <span></span>
        </a> -->
      </div>
    </div>
  </nav>
</template>

<style>
/* Mengubah tema default ke dark */
.dark-mode {
  background-color: #121212;
  color: white;
}
.nav-link{
  color:red;
}
.dark-mode .site-nav {
  background-color: #333;
}

.dark-mode .logo  {
  color: #ffffff;
}
.dark-mode .nav-link {
  color: #f0f0f0;
}

.dark-mode .cta-primary a {
  background-color: #ff8c00;
  color: #000000;
}

.dark-mode .burger span {
  background-color: #fff;
}
.dark-mode .burger {
  /* background-color: #fff; */
  color: #f0f0f0;
}


.dark-mode .btn-outline-light {
  color: white;
  border-color: white;
}

.dark-mode .btn-outline-light i {
  color: white;
}

/* Pengaturan untuk mode light */
body {
  background-color: #f5f5f5;
  color: #333;
}

.site-nav {
  background-color: #fff;
}

.site-nav .logo {
  color: #333;
}

.site-nav .nav-link {
  color: #333;
}

.site-nav .cta-primary a {
  background-color: #ff8c00;
  color: #fff;
}

.site-nav .burger span {
  background-color: #333;
}

.site-nav .site-menu li.active a {
  color: #ff8c00;
}

.btn-outline-light {
  color: #333;
  border-color: #333;
}

.btn-outline-light i {
  color: #333;
}

</style>

