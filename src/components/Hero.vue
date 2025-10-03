<script setup>
import mainPhoto from "../assets/images/profile.png";
import { themeColor } from "../data/items";

const heroHeading = "Halo,";
const buttonSeeFeature = "See Features";
const buttonPricing = "Pricing";
const socialItems = [
  {
    link: "https://www.instagram.com/prasdimas10",
    icon: "icon-instagram",
  },
  {
    link: "https://www.facebook.com/people/Dimas-P/",
    icon: "icon-facebook",
  },
  {
    link: "https://www.linkedin.com/in/dimas-prasetyo0163",
    icon: "icon-linkedin",
  },
  {
    link: "https://github.com/Prasdimas",
    icon: "icon-github",
  },
];
</script>

<template>
  <div class="untree_co-hero">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-12">
          <div class="dots" style="margin-left: -40px;"></div>
          <div class="row align-items-center">
            <div
              class="col-lg-5 ml-auto order-lg-2"
              data-aos="fade-right"
              data-aos-delay="400"
            >
              <img :src="mainPhoto" alt="Image" class="img-fluid" />
              <ul class="list-unstyled social">
                <li class="social-item">
    <a :href="socialItems[1].link">
      <span :class="socialItems[1].icon"></span>
    </a>
  </li>
                <li class="social-item">
    <a :href="socialItems[0].link">
      <span :class="socialItems[0].icon"></span>
    </a>
  </li>
  <li class="social-item">
    <a :href="socialItems[2].link">
      <span :class="socialItems[2].icon"></span>
    </a>
  </li>
  <li class="social-item">
    <a :href="socialItems[3].link">
      <span :class="socialItems[3].icon"></span>
    </a>
  </li>
</ul>
            </div>
            <div class="col-lg-7">
              <h2 class="heading text-primary">
                {{ heroHeading }}
              </h2>
              <div class="excerpt" data-aos="fade-up" data-aos-delay="100">
                <p>
                 Lulusan Teknik Informatika Universitas Semarang dengan pengalaman lebih dari 2 tahun di bidang pengembangan perangkat lunak. Pernah bekerja sebagai Staff IT di CV Katalis Indonesia dan Full Stack Programmer, saya memiliki kemampuan dalam membangun dan mengelola website menggunakan teknologi seperti Vue.js, React.js, Node.js, Laravel, dan CodeIgniter.
                  <br> Selain itu, saya juga berpengalaman dalam pembuatan website berbasis WordPress, pengelolaan iklan digital, dan pengembangan aplikasi sederhana menggunakan Flutter. Saya antusias mempelajari teknologi baru, mampu bekerja dalam tim, dan berorientasi pada solusi.
                </p>
                <div class="cta-primary">
                  <a 
    href="https://drive.google.com/file/d/1OKRS5BQqXi5U4vwNit6lXBdvbIgjy96A/view?usp=sharing" class="btn btn-primary" 
    download>
    HIRE ME
  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-lg-12">
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.social {
  display: flex; /* Use flexbox for alignment */
  margin-bottom: 20px; /* Space below the icons */
}

.social-item {
  margin-right: 10px; /* Space between icons */
}

.social-item:last-child {
  margin-right: 0; /* Remove margin from the last item */
}

</style>
