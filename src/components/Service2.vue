<script setup>
import { ref, computed } from 'vue';
import mainPhoto from "../assets/images/service2.jpg";

const heading = "PORTOFOLIO";
const projects = [
  {
    name: "Sistem Pendukung Keputusan",
    description: "SPK AHP SAW menggunakan CodeIgniter dan MySQL.",
    image: "link_to_image_sistem_pendukung_keputusan.jpg",
    link: "link_to_project_sistem_pendukung_keputusan"
  },
  {
    name: "Movie Dim",
    description: "Website menggunakan API IMDB dengan React.",
    image: "link_to_image_movie_dim.jpg",
    link: "link_to_project_movie_dim"
  },
  {
    name: "Pembuatan API Laravel",
    description: "API rumah sakit sederhana dengan JWT.",
    image: "link_to_image_api_laravel.jpg",
    link: "link_to_project_api_laravel"
  },
  {
    name: "Landing Page POS",
    description: "Tampilan menggunakan Vue dan Vuetify.",
    image: "link_to_image_landing_page_pos.jpg",
    link: "link_to_project_landing_page_pos"
  },
  {
    name: "ChatKatalis",
    description: "Website dengan API ChatGPT menggunakan React dan Node.js.",
    image: "link_to_image_chatkatalis.jpg",
    link: "link_to_project_chatkatalis"
  },
  {
    name: "CRUD Pembuatan Laravel",
    description: "Pengalaman membuat API dengan Laravel dan MySQL.",
    image: "link_to_image_crud_laravel.jpg",
    link: "link_to_project_crud_laravel"
  },
  {
    name: "Esensia",
    description: "Website company profile klinik dengan WordPress.",
    image: "link_to_image_esensia.jpg",
    link: "link_to_project_esensia"
  },
  {
    name: "Pembuatan Jual Beli Rumah Sederhana",
    description: "Pembuatan jual beli menggunakan CodeIgniter dan MySQL.",
    image: "link_to_image_jual_beli_rumah.jpg",
    link: "link_to_project_jual_beli_rumah"
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
              <h3>{{ project.name }}</h3>
              <p>{{ project.description }}</p>
            </div>
          </a>
        </div>

        <div class="col-lg-7">
          <div class="img-shadow">
            <div class="owl-single no-dots owl-carousel">
              <div class="item" v-for="(project, index) in paginatedProjects" :key="index">
                <span class="number">{{ (currentPage.value - 1) * itemsPerPage + index + 1 }}/{{ projects.length }}</span>
                <img :src="project.image" alt="Image" class="img-fluid" />
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
