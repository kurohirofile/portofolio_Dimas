<script setup>
import { themeColor } from "../data/items";
const heading = "PELATIHAN";
const subHeading = "BEBERAPA PELATIHAN BERSERTIFIKAT";
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiCertificate   } from '@mdi/js';

const certificates = [
        {
          name: "Dicoding - Belajar Membuat Aplikasi Back-End untuk Pemula",
          description: "Pelatihan dasar untuk memahami dan membuat aplikasi backend menggunakan berbagai teknologi."
        },
        {
          name: "Cloud Practitioner Essentials (Belajar Dasar AWS Cloud)",
          description: "Pelatihan mengenai konsep dasar cloud computing dengan fokus pada layanan AWS."
        },
        {
          name: "Belajar Membuat Aplikasi Web dengan React",
          description: "Pelatihan untuk mengembangkan aplikasi web modern menggunakan React."
        },
        {
          name: "Belajar Membuat Front-End Web untuk Pemula",
          description: "Dasar-dasar pengembangan front-end web, termasuk HTML, CSS, dan JavaScript."
        },
        {
          name: "Belajar Dasar Pemrograman Web",
          description: "Pelatihan mengenai konsep dasar pemrograman web dan pengembangan aplikasi."
        },
        {
          name: "Belajar Dasar Pemrograman JavaScript",
          description: "Pengantar pemrograman menggunakan JavaScript untuk pemula."
        },
        {
          name: "Digitalent (Kominfo x Google) - Google IT Support Professional Certificate",
          description: "Sertifikasi profesional di bidang IT Support dari Google."
        },
        {
          name: "Fresh Graduate Academy Digitalent Scholarship 2023 - Pelatihan UX Google",
          description: "Pelatihan mengenai pengalaman pengguna (UX) yang disediakan oleh Google."
        },
        {
          name: "CARIILMU - Pelatihan Pembuatan Website dan SEO",
          description: "Pelatihan tentang pembuatan website dan teknik optimasi mesin pencari (SEO)."
        }
      ];
</script>

<template>
  <div class="untree_co-section" id="skills">
    <div class="container">
      <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2>{{ heading }}</h2>
          <span class="description">{{ subHeading }}</span>
        </div>
      </div>
      <div class="row">
        <div v-for="(cert, index) in certificates" :key="index" class="col-lg-6 mb-4" data-aos="fade-up" data-aos-delay="100">
      <div class="service horizontal d-flex">
        <div class="service-icon color-2 mb-4">
          <svg-icon type="mdi" :path="mdiCertificate"></svg-icon>
        </div>
        <div class="service-contents">
          <h3>{{ cert.name }}</h3>
          <p class="description">{{ cert.description }}</p>
        </div>
      </div>
    </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.description{
  font-size: 14px;
}
</style>