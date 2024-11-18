<script setup>
import { ref } from "vue";

const profileImageUrl = ref("https://github.com/rafatuba.png");
const name = ref("Rafael de Oliveira Silva");
const occupation = ref("Desenvolvedor Front-End");
const contact = ref("Contato: (67) 98134-7898");
const email = ref("rafaolly1@gmail.com");
const socialLinks = ref([
  { platform: "LinkedIn", link: "https://www.linkedin.com/in/rafatubadev" },
  { platform: "GitHub", link: "https://github.com/rafatuba" },
  { platform: "Instagram", link: "https://instagram.com/rafaolly1" },
]);
</script>

<template>
  <div class="card">
    <img :src="profileImageUrl" alt="Foto de perfil" class="profile-image" />
    <h1>{{ name }}</h1>
    <p>{{ occupation }}</p>
    <p>{{ contact }}</p>
    <p>{{ email }}</p>
    <div class="socials">
      <a
        v-for="social in socialLinks"
        :key="social.platform"
        :href="social.link"
        target="_blank"
      >
        {{ social.platform }}
      </a>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: #fff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
  width: 300px;
  margin: 20px auto;
  transition: 300ms;
}

.card:hover {
  box-shadow: -5px 5px 10px #007bff;
  transition: 300ms;
  transform: rotate(1deg);
}

.profile-image {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 10px;
}

.card h1 {
  margin: 0 0 10px;
}

.card p {
  margin: 5px 0;
}

.socials a {
  display: inline-block;
  margin: 5px;
  color: #007bff;
  text-decoration: none;
}

.socials a:hover {
  text-decoration: underline;
}
</style>
