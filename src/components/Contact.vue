<template>
  <div class="untree_co-section" id="contact">
    <div class="container">
      <div class="row mb-4" data-aos="fade-up" data-aos-delay="0">
        <div class="col-12 text-center">
          <h2 class="heading">{{ heading }}</h2>
          <p>{{ subHeading }}</p>
        </div>
        <div class="col-12 text-center">
          <ul class="list-unstyled social">
            <li class="social-item" v-for="(item, index) in socialItems" :key="index">
              <a :href="item.link" target="_blank">
                <span :class="item.icon"></span>
              </a>
            </li>
          </ul>
          <div class="cta-primary">
                  <a 
    href="https://drive.google.com/uc?id=1lzMUboX1w-v53iM8GcbRMpyyTVhbvVP1&export=download" class="btn btn-primary" 
    download>
    HIRE ME
  </a>
                </div>
        </div>
      </div>
      <div class="row justify-content-center">
        <div class="col-lg-8">
          <form class="contact-form" @submit.prevent="sendEmail" data-aos="fade-up" data-aos-delay="100">
            <div class="row mb-4">
              <div class="col-md-6">
                <div class="form-group">
                  <label for="fname">{{ labels.firstName }}</label>
                  <input type="text" v-model="formData.fname" class="form-control form-control-lg" id="fname" required />
                </div>
              </div>
              <div class="col-md-6">
                <div class="form-group">
                  <label for="lname">{{ labels.lastName }}</label>
                  <input type="text" v-model="formData.lname" class="form-control form-control-lg" id="lname" required />
                </div>
              </div>
            </div>
            <div class="form-group mb-4">
              <label for="email">{{ labels.email }}</label>
              <input type="email" v-model="formData.email" class="form-control form-control-lg" id="email" required />
            </div>
            <div class="form-group mb-4">
              <label for="message">{{ labels.message }}</label>
              <textarea v-model="formData.message" class="form-control form-control-lg" id="message" cols="30" rows="5" required></textarea>
            </div>
            <div class="text-right">
              <button type="submit" class="btn btn-primary btn-lg">KIRIM</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

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

const heading = "CONTACT";
const subHeading = "Hubungi Bisa lewat Form dibawah ini";
const labels = {
  firstName: "First Name",
  lastName: "Last Name",
  email: "Email Address",
  message: "Message",
};

const formData = ref({
  fname: '',
  lname: '',
  email: '',
  message: ''
});

const sendEmail = () => {
  const { fname, lname, email, message } = formData.value;
  const subject = `New message from ${fname} ${lname}`;
  const body = `Email: ${email}\nMessage: ${message}`;
  
  window.location.href = `mailto:prasdimasetyo@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
};
</script>

<style>
.contact-form {
  padding: 20px;
  border-radius: 8px;
}

.social {
  display: flex;
  justify-content: center; /* Centering the social media icons */
  padding: 0; /* Reset padding */
}

.social-item {
  margin: 0 10px; /* Spacing between icons */
}
</style>
