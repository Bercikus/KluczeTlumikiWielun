<template>
  <div>
    <header>
      <h1>{{ headerTitle }}</h1>
      <p>{{ headerSubtitle }}</p>
    </header>

    <nav>
      <ul>
        <li><a href="#services">Usługi</a></li>
        <li><a href="#pricing">Cennik</a></li>
        <li><a href="#about">O nas</a></li>
        <li><a href="#contact">Kontakt</a></li>
      </ul>
    </nav>

    <div class="hero">
      <h2>{{ heroTitle }}</h2>
      <p>{{ heroSubtitle }}</p>
      <a :href="heroCtaLink" class="cta">{{ heroCtaText }}</a>
    </div>

    <section id="services">
      <h2>{{ servicesTitle }}</h2>
      <div class="grid">
        <div class="card">
          <img src="https://via.placeholder.com/300x200" alt="Naprawa tłumików">
          <h3>{{ service1Title }}</h3>
          <p>{{ service1Description }}</p>
        </div>
        <div class="card">
          <img src="https://via.placeholder.com/300x200" alt="Dorabianie kluczy domowych">
          <h3>{{ service2Title }}</h3>
          <p>{{ service2Description }}</p>
        </div>
      </div>
    </section>

    <section id="pricing">
      <h2>{{ pricingTitle }}</h2>
      <table class="pricing-table">
        <thead>
          <tr>
            <th>Usługa</th>
            <th>Cena</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in prices" :key="index">
            <td>{{ item.service }}</td>
            <td>{{ item.price }}</td>
          </tr>
        </tbody>
      </table>
    </section>

    <section id="about">
      <h2>{{ aboutTitle }}</h2>
      <p>{{ aboutText }}</p>
    </section>

    <section id="contact">
      <h2>{{ contactTitle }}</h2>
      <p><strong>Telefon:</strong> {{ contactPhone }}</p>
      <p><strong>Email:</strong> {{ contactEmail }}</p>
    </section>

    <footer>
      <p>{{ footerCopyright }}</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Dane strony
const headerTitle = ref('Tłumiki & Dorabianie Kluczy');
const headerSubtitle = ref('Nowoczesna usługa dla Twoich potrzeb!');

const heroTitle = ref('Najlepsze rozwiązania w jednym miejscu');
const heroSubtitle = ref('Serwis tłumików, dorabianie kluczy i więcej!');
const heroCtaText = ref('Skontaktuj się z nami');
const heroCtaLink = ref('#contact');

const servicesTitle = ref('Nasze Usługi');
const service1Title = ref('Naprawa Tłumików');
const service1Description = ref('Profesjonalna regeneracja układów wydechowych.');
const service2Title = ref('Dorabianie Kluczy');
const service2Description = ref('Precyzyjne klucze do drzwi i zamków specjalistycznych.');

const pricingTitle = ref('Cennik Usług');
const prices = ref([
  { service: 'Naprawa tłumików', price: '250 PLN' },
  { service: 'Dorabianie kluczy', price: '80 PLN' }
]);

const aboutTitle = ref('O nas');
const aboutText = ref('Nasza firma oferuje szeroki zakres usług motoryzacyjnych i ślusarskich, ciesząc się zaufaniem klientów.');

const contactTitle = ref('Kontakt');
const contactPhone = ref('+48 123 456 789');
const contactEmail = ref('kontakt@tlumiki-klucze.pl');

const footerCopyright = ref('&copy; 2025 Tłumiki & Dorabianie Kluczy. Wszelkie prawa zastrzeżone.');
</script>

<style scoped>
/* Globalne style */
body {
  margin: 0;
  font-family: 'Segoe UI', Arial, sans-serif;
  background-color: #f3f5f7;
  color: #333;
  line-height: 1.6;
}

header {
  background: linear-gradient(135deg, #003366, #004080);
  color: white;
  padding: 40px 20px;
  text-align: center;
}

header h1 {
  font-size: 48px;
  margin: 0;
}

header p {
  font-size: 20px;
  margin: 10px 0;
}

nav {
  background: #00264d;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  position: sticky;
  top: 0;
  z-index: 1000;
}

nav ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 10px 20px;
  justify-content: center;
}

nav ul li {
  margin: 0 15px;
}

nav ul li a {
  text-decoration: none;
  color: white;
  font-weight: bold;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background 0.3s, color 0.3s;
}

nav ul li a:hover {
  background: #004080;
  color: #e0e0e0;
}

.hero {
  background: url('https://via.placeholder.com/1920x600') no-repeat center center/cover;
  color: white;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
  text-align: center;
  padding: 100px 20px;
}

.hero h2 {
  font-size: 40px;
  margin: 0;
}

.hero p {
  font-size: 20px;
  margin: 10px 0;
}

section {
  padding: 60px 20px;
  max-width: 1200px;
  margin: auto;
  border-radius: 10px;
  background: white;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

section h2 {
  font-size: 32px;
  color: #003366;
  text-align: center;
  margin-bottom: 30px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.card {
  background: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
}

.card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.card h3 {
  margin: 15px;
  color: #004080;
  font-size: 24px;
}

.card p {
  margin: 0 15px 15px;
  color: #555;
}

footer {
  background: #003366;
  color: white;
  text-align: center;
  padding: 20px 10px;
  margin-top: 40px;
}

.cta {
  display: inline-block;
  padding: 12px 25px;
  color: white;
  background: #004080;
  text-decoration: none;
  font-weight: bold;
  border-radius: 5px;
  transition: background 0.3s;
}

.cta:hover {
  background: #001f33;
}

.pricing-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

.pricing-table th,
.pricing-table td {
  padding: 15px;
  text-align: left;
  border: 1px solid #ddd;
}

.pricing-table th {
  background: #004080;
  color: white;
}

.pricing-table td:first-child {
  font-weight: bold;
}
</style>