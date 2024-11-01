<script setup>
import { themeColor } from "../data/items";
const heading = "PELATIHAN";
const subHeading = "BEBERAPA PELATIHAN BERSERTIFIKAT";
// const buttonLearnMore = "Learn More";
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
        <div class="service-icon color-1 mb-4">
          <svg
            class="bi bi-award"
            width="1em"
            height="1em"
            viewBox="0 0 16 16"
            fill="currentColor"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M9.669 2.864a1.2 1.2 0 1 1-1.338 0l-.668 1.332a1.2 1.2 0 0 1-.676.676l-1.332.668a1.2 1.2 0 0 1 0 1.338l.668 1.332a1.2 1.2 0 0 1 .676.676l1.332.668a1.2 1.2 0 1 1 0 1.338l-.668 1.332a1.2 1.2 0 0 1 1.338 0l1.332-.668a1.2 1.2 0 0 1 .676-.676l.668-1.332a1.2 1.2 0 0 1 0-1.338l-1.332-.668a1.2 1.2 0 0 1-.676-.676l-.668-1.332zM8 0c-1.654 0-3 1.346-3 3 0 .69.227 1.332.615 1.847A3.973 3.973 0 0 0 5 3a3 3 0 1 1 6 0c0 .003-.002.006-.002.009A3.973 3.973 0 0 0 12 3c.183 0 .36.019.533.054A2.993 2.993 0 0 0 16 3c0-1.654-1.346-3-3-3h-5z"/>
          </svg>
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