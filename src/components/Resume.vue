<script setup>
const education = [
  {
    institution: "Universitas Semarang",
    gpa: 3.97,
    location: "Semarang, Jawa Tengah",
    degree: "Sarjana Komputer (S1)",
    duration: "2020 - 2024",
    thesis: "Menyelesaikan Tugas Akhir dengan judul 'Pembuatan Konten Berbasis Kecerdasan Buatan Menggunakan Integrasi React JS dan Node JS dengan Application Programming Interface GPT (API GPT)'",
    subjects: [
      "Mempelajari Perancangan Web",
      "Mempelajari MVC (Model View Controller)",
      "Mempelajari Basis Data"
    ]
  },
  {
    institution: "SMK Negeri 2 Purwodadi",
    location: "Grobogan, Jawa Tengah",
    major: "Jurusan Teknik Komputer Jaringan",
    duration: "2016 – 2019",
    subjects: [
      "Mempelajari Bahasa Pemrograman dasar",
      "Mempelajari komputer dan jaringan dasar",
      "Mempelajari administrasi infrastruktur jaringan"
    ]
  }
];
const workExperience = [
    {
    position: "IT / Webmaster",
    company: "Beritajateng.tv",
    location: "Semarang, Jawa Tengah",
    duration: "Juli 2025 - September 2025",
    tasks: [
      "Melakukan perbaikan dan pemeliharaan website.",
      "Melaksanakan migrasi integrasi antara Facebook dan WordPress.",
      "Mengembangkan plugin sederhana untuk kebutuhan website.",
      "Melakukan optimasi SEO untuk meningkatkan visibilitas di mesin pencari."
    ]
  },
{
    position: "Full Stack Developer",
    company: "BUDS (Software House)",
    location: "Semarang, Jawa Tengah",
    duration: "Maret 2024 - Maret 2025",
    tasks: [
      "Membangun dan mengembangkan software internal perusahaan.",
      "Melakukan perbaikan dan pemeliharaan website yang telah berjalan.",
      "Membuat REST API menggunakan CodeIgniter 3 untuk integrasi antar sistem.",
      "Mengembangkan frontend interaktif menggunakan Vue.js dan Vuetify.",
      "Membangun API dan tampilan modular dengan Laravel dan Vue.js.",
      "Mengerjakan ERP custom menggunakan CodeIgniter 3 dan Vue.js + Vuetify dengan MySQL.",
      "Berkolaborasi dengan tim untuk merancang dan menerapkan fitur baru."
    ]
  },
  {
    position: "Staff IT",
    company: "CV Katalis Indonesia",
    location: "Semarang, Jawa Tengah",
    duration: "Maret 2022 - Maret 2024",
    tasks: [
      "Membuat dan mengelola website menggunakan WordPress.",
      "Mengatur plugin, tema, dan layout sesuai kebutuhan klien.",
      "Membuat strategi iklan untuk meningkatkan trafik website.",
      "Membangun landing page yang menarik dan responsif.",
      "Membuat website generator konten dengan React.js dan Node.js.",
      "Mengoptimasi SEO: kata kunci, meta tag, kecepatan, dan struktur URL.",
      "Mengatur email hosting dan konfigurasi server."
    ]
  },
  {
    position: "IT Developer (Magang)",
    company: "Jatis Mobile",
    location: "Jakarta, DKI Jakarta",
    duration: "5 Oktober 2021 - 3 Februari 2022",
    tasks: [
      "Membuat chatbot menggunakan API dan Node.js.",
      "Membuat API dari Meta Developer.",
      "Mengelola database MySQL.",
      "Mempelajari ActiveMQ untuk sistem microservice."
    ]
  }
];

import SvgIcon from '@jamescoyle/vue-icon';
import { mdiSitemapOutline  } from '@mdi/js';

// Mendeklarasikan heading dan items
const heading = "RESUME";

</script>
<template>
    <div class="container"  id="About">
        <div class="row mb-4">
        <div class="col-12 text-center" data-aos="fade-up" data-aos-delay="0">
          <h2 class="heading">{{ heading }}</h2>
          <svg-icon type="mdi" :path="mdiSitemapOutline"></svg-icon>
        </div>
      </div>
    <div class="row">
        <div class="col-md-6">
            <h4 class="text-center">Pendidikan</h4>
            <div class="timeline">
    <div class="timeline-line"></div>
    <div v-for="(edu, index) in education" :key="index" class="timeline-item">
      <div class="card">
        <div class="card-body">
            <p class="card-text">{{ edu.institution }} - {{ edu.degree || edu.major }}</p>
            <P class="card-title">{{ edu.duration }}</P>
          <ul v-if="edu.subjects && edu.subjects.length > 0">
            <li v-for="(subject, sIndex) in edu.subjects" :key="sIndex">{{ subject }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
        </div>
        <div class="col-md-6">
            <h4 class="text-center">Pekerjaan</h4>
            <div class="timeline">
                <div class="timeline-line"></div>
      <div v-for="(work, index) in workExperience" :key="index" class="timeline-item">
        <div class="card">
          <div class="card-body">
            <h5 class="card-title">{{ work.duration }} - {{ work.location }}</h5>
            <p class="card-text">{{ work.position }} - {{ work.company }}</p>
            <p><strong>Deskripsi Pekerjaan:</strong></p>
            <ul>
              <li v-for="(task, tIndex) in work.tasks" :key="tIndex">{{ task }}</li>
            </ul>
          </div>
        </div>
      </div>
            </div>
        </div>
    </div>
</div>
</template>
