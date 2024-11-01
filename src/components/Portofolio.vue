<template>
  <div class="untree_co-section" id="portfolio">
    <div class="container">
      <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading">{{ heading }}</h2>
        </div>
      </div>

      <div class="row justify-content-between">
        <div class="col-lg-5 order-lg-2 js-custom-dots">
          <a
            v-for="(project, index) in paginatedProjects"
            :key="index"
            :href="project.link"
            class="service link horizontal d-flex"
            data-aos="fade-left"
            :data-aos-delay="index * 100"
          >
            <div class="service-icon color-1 mb-4">
              <svg-icon type="mdi" :path="mdiProjector"></svg-icon>
            </div>
            <div class="service-contents">
              <h3>{{ project.name }}</h3>
              <p>{{ project.description }}</p>
            </div>
          </a>
        </div>

        <div class="col-lg-7">
          <div class="img-shadow">
            <div class="owl-single no-dots owl-carousel">
              <div class="item" v-for="(project, index) in paginatedProjects" :key="index">
                <img :src="project.image" alt="Image" class="img-fluid" />
                <div class="text-center mt-2" v-if="project.link !== '#'"> 
                  <a :href="project.link" target="_blank" class="btn btn-secondary btn-lg btn-block">Source Code</a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Pagination -->
      <div class="pagination mt-4 text-center">
        <span @click="prevPage" :class="{ disabled: currentPage.value === 1 }" class="page-number">«</span>
        <span
          v-for="page in totalPages"
          :key="page"
          @click="setPage(page)"
          :class="{ active: currentPage.value === page }"
          class="page-number"
        >
          {{ page }}
        </span>
        <span @click="nextPage" :class="{ disabled: currentPage.value === totalPages }" class="page-number">»</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import mainPhoto from "../assets/images/pendaftaran_kerja_api.png";
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiProjector } from '@mdi/js';
import spkImage from "../assets/images/spk.png";
import dimovieImage from "../assets/images/dimovie.png";
import datapasienImage from "../assets/images/datapasien.png";
import landingPageImage from "../assets/images/landing_page_company.jpeg";
import chatKatalisImage from "../assets/images/chatkatalismedia.png";
import pendaftaranImage from "../assets/images/pendaftaran_kerja_api.png";
import esensiaImage from "../assets/images/esensia.png";
import catatanPenjualanImage from "../assets/images/catatan_penjualan.png";

const heading = "PORTOFOLIO";
const projects = [
  {
    name: "Sistem Pendukung Keputusan",
    description: "SPK AHP SAW menggunakan CodeIgniter dan MySQL.",
    image: spkImage,
    link: "https://github.com/Prasdimas/SPK_Codeiginiter"
  },
  {
    name: "Movie Dim",
    description: "Website menggunakan API IMDB dengan React.",
    image: dimovieImage,
    link: "https://github.com/Prasdimas/dimovie"
  },
  {
    name: "Pembuatan API Laravel",
    description: "API rumah sakit sederhana dengan JWT.",
    image: datapasienImage,
    link: "https://github.com/Prasdimas/hospital-app"
  },
  {
    name: "Landing Page POS",
    description: "Tampilan menggunakan Vue dan Vuetify.",
    image: landingPageImage,
    link: "https://github.com/Prasdimas/company-profile_vue"
  },
  {
    name: "ChatKatalis",
    description: "Website dengan API ChatGPT menggunakan React dan Node.js.",
    image: chatKatalisImage,
    link: "https://github.com/Prasdimas/chatkatalis"
  },
  {
    name: "API Pembuatan Form Pendaftaran Kerja",
    description: "Pengalaman membuat API dengan Laravel dan MySQL.",
    image: pendaftaranImage,
    link: "https://github.com/Prasdimas/api-form-laravel"
  },
  {
    name: "Esensia",
    description: "Website company profile klinik dengan WordPress.",
    image: esensiaImage,
    link: "#"
  },
  {
    name: "Pembuatan Catatan Penjualan Rumah Sederhana",
    description: "Pembuatan jual beli menggunakan CodeIgniter dan MySQL.",
    image: catatanPenjualanImage,
    link: "https://github.com/Prasdimas/penjualan"
  },
];

const itemsPerPage = 4;
const currentPage = ref(1);
const totalPages = computed(() => Math.ceil(projects.length / itemsPerPage));

const paginatedProjects = computed(() => {
  const start = (currentPage.value - 1) * itemsPerPage;
  return projects.slice(start, start + itemsPerPage);
});

const nextPage = () => {
  if (currentPage.value < totalPages.value) {
    currentPage.value++;
  }
};

const prevPage = () => {
  if (currentPage.value > 1) {
    currentPage.value--;
  }
};

const setPage = (page) => {
  currentPage.value = page;
};
</script>

<style scoped>
.pagination {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}

.page-number {
  margin: 0 5px;
  cursor: pointer;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.page-number:hover {
  background-color: #f0f0f0;
}

.page-number.active {
  background-color: #007bff; /* Latar belakang biru untuk aktif */
  color: white; /* Warna teks putih */
}

.page-number.disabled {
  cursor: not-allowed;
  opacity: 0.5;
}
</style>
