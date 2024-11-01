<template>
  <div class="untree_co-section">
    <div class="container">
      <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading">{{ heading }}</h2>
        </div>
      </div>
      <div class="row">
        <div
          v-for="(item, index) in items"
          :key="index"
          class="col-md-6 mb-4 mb-lg-0 col-lg-3"
          data-aos="fade-up"
          :data-aos-delay="index * 100"
        >
          <div class="service">
            <div class="service-icon mb-4" :style="[item.iconBg]">
              
              <svg-icon type="mdi" :path="item.icon"></svg-icon>
            </div>
            <div class="service-contents">
              <h3><strong>{{ item.title }}</strong></h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiReact, mdiVuejs , mdiVuetify,mdiGithub , mdiTailwind, mdiLanguageJavascript,mdiLaravel,mdiFireCircle,mdiDolphin,mdiNodejs,mdiAlphaF,mdiLanguagePhp,mdiWordpress   } from '@mdi/js';

// Mendeklarasikan heading dan items
const heading = "SKILLS";

const items = [
  {
    iconBg: "background-color: #61DBFB", // Warna biru untuk React
    icon: mdiReact,
    title: "React",
    description: "Pustaka JavaScript untuk membangun antarmuka pengguna.",
  },
  {
    iconBg: "background-color: #42b883", // Warna hijau untuk Vue
    icon: mdiVuejs,
    title: "Vue",
    description: "Framework JavaScript progresif untuk UI.",
  },
  {
    iconBg: "background-color: #1867C0", // Warna biru untuk Vuetify
    icon: mdiVuetify,
    title: "Vuetify",
    description: "Framework Material Design untuk Vue.js.",
  },
  {
    iconBg: "background-color: #1996d4", // Warna teal untuk Tailwind
    icon: mdiTailwind,
    title: "Tailwind",
    description: "Framework CSS utility-first untuk desain cepat.",
  },
  {
    iconBg: "background-color: #0b1321", // Warna merah untuk Figma
    icon: mdiAlphaF,
    title: "Figma",
    description: "Alat desain kolaboratif berbasis web.",
  },
  {
    iconBg: "background-color: #F7DF1E", // Warna kuning untuk JavaScript
    icon: mdiLanguageJavascript,
    title: "Javascript",
    description: "Bahasa pemrograman untuk interaksi web.",
  },
  {
    iconBg: "background-color: #8CC84B", // Warna hijau untuk Node.js
    icon: mdiNodejs,
    title: "Node JS",
    description: "Runtime JavaScript untuk pengembangan server.",
  },
  {
    iconBg: "background-color: #0b1321", // Warna hijau untuk Express.js
    icon: mdiLanguageJavascript,
    title: "Express JS",
    description: "Framework minimalis untuk aplikasi Node.js.",
  },
  {
    iconBg: "background-color: #4F5B93", // Warna ungu untuk PHP
    icon: mdiLanguagePhp,
    title: "PHP",
    description: "Bahasa pemrograman untuk pengembangan web.",
  },
  {
    iconBg: "background-color: #d41919", // Warna kuning untuk CodeIgniter
    icon: mdiFireCircle,
    title: "Codeigniter",
    description: "Framework PHP yang cepat dan ringan.",
  },
  {
    iconBg: "background-color: #d90b0b", // Warna biru untuk Wordpress
    icon: mdiLaravel,
    title: "Laravel",
    description: "Framework PHP yang kuat untuk pengembangan aplikasi web.",
},
{
    iconBg: "background-color: #00758F", // Warna biru untuk MySQL
    icon: mdiDolphin,
    title: "MySQL",
    description: "Sistem manajemen basis data open-source yang populer.",
},
{
    iconBg: "background-color: #21759B", // Warna biru untuk Wordpress
    icon: mdiWordpress,
    title: "WordPress",
    description: "Sistem manajemen konten (CMS) yang populer untuk membuat situs web.",
},
{
    iconBg: "background-color: #181717", // Warna hitam untuk GitHub
    icon: mdiGithub,
    title: "GitHub",
    description: "Platform untuk pengembangan perangkat lunak dan kolaborasi berbasis git.",
},

];

</script>

<style scoped>
/* Tambahkan gaya CSS sesuai kebutuhan */
.service {
  text-align: center;
}
.service-icon {
  width: 60px; /* Sesuaikan ukuran ikon */
  height: 60px; /* Sesuaikan ukuran ikon */
  margin: 0 auto;
}
</style>
