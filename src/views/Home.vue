<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

const data = ref(null);
const loading = ref(true);
const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

onMounted(() => {
  // Your existing mounted logic here
});
</script>

<template>
  <div
    class="leading-normal tracking-normal text-white"
    style="font-family: 'Source Sans Pro', sans-serif"
  >
    <!-- Navigation -->
    <nav id="header" class="fixed w-full z-30 top-0 text-white">
      <div
        class="w-full container mx-auto flex flex-wrap items-center justify-between mt-0 py-2"
      >
        <div class="pl-4 flex items-center">
          <a
            class="toggleColour text-white no-underline hover:no-underline font-bold text-2xl lg:text-4xl"
            href="#"
          >
            ALTiUS ERP
          </a>
        </div>
        <div class="block lg:hidden pr-4">
          <button
            @click="toggleMenu"
            class="flex items-center p-1 text-pink-800 hover:text-gray-900 focus:outline-none focus:shadow-outline transform transition hover:scale-105 duration-300 ease-in-out"
          >
            <svg
              class="fill-current h-6 w-6"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Menu</title>
              <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
            </svg>
          </button>
        </div>
        <div
          :class="[
            'w-full flex-grow lg:flex lg:items-center lg:w-auto mt-2 lg:mt-0 bg-white lg:bg-transparent text-black p-4 lg:p-0 z-20',
            { hidden: !isMenuOpen },
          ]"
        >
          <ul class="list-reset lg:flex justify-end flex-1 items-center">
            <li class="mr-3">
              <a class="inline-block py-2 px-4 text-black font-bold no-underline" href="#"
                >Active</a
              >
            </li>
            <li class="mr-3">
              <a
                class="inline-block text-black no-underline hover:text-gray-800 hover:text-underline py-2 px-4"
                href="#"
                >link</a
              >
            </li>
            <li class="mr-3">
              <a
                class="inline-block text-black no-underline hover:text-gray-800 hover:text-underline py-2 px-4"
                href="#"
                >link</a
              >
            </li>
          </ul>
          <button
            class="mx-auto lg:mx-0 hover:underline bg-white text-gray-800 font-bold rounded-full mt-4 lg:mt-0 py-4 px-8 shadow opacity-75 focus:outline-none focus:shadow-outline transform transition hover:scale-105 duration-300 ease-in-out"
          >
            Action
          </button>
        </div>
      </div>
      <hr class="border-b border-gray-100 opacity-25 my-0 py-0" />
    </nav>

    <!-- Hero Section -->
    <div class="hero-gradient pt-24">
      <div
        class="container px-3 mx-auto flex flex-wrap flex-col md:flex-row items-center"
      >
        <!-- Left Column -->
        <div
          class="flex flex-col w-full md:w-2/5 justify-center items-start text-center md:text-left"
        >
          <p class="uppercase tracking-loose w-full">Bisnis apa yang anda miliki?</p>
          <h1 class="my-4 text-5xl font-bold leading-tight">
            Solusi ERP terpercaya untuk Bisnis Distribusi & Manufaktur
          </h1>
          <p class="leading-normal text-xl mb-8">
            Cloud-ERP lengkap dengan fitur canggih dan AI terintegrasi sejak 1997. Pantau
            operasional, inventori, dan keuangan secara real-time, dari mana saja, untuk
            hasil lebih cepat dan risiko minimal.
          </p>
          <button
            class="mx-auto lg:mx-0 hover:underline bg-white text-gray-800 font-bold rounded-full my-6 py-4 px-8 shadow-lg focus:outline-none focus:shadow-outline transform transition hover:scale-105 duration-300 ease-in-out"
          >
            Konsultasi dengan tim ALTiUS →
          </button>
        </div>
        <!-- Right Column -->
        <div class="w-full md:w-3/5 py-6 text-center">
          <img class="w-full md:w-4/5 z-50" src="../assets/hero.png" alt="Hero Image" />
        </div>
      </div>
    </div>

    <!-- Problem Section -->
    <section class="erp-problems-section">
      <div class="erp-problems-container">
        <h2
          class="w-full my-2 text-3xl font-bold leading-tight text-center text-gray-800"
        >
          Setiap bisnis ingin berkembang, tapi sering terjebak dengan kendala klasik yang
          berulang
        </h2>
        <div class="w-full mb-4">
          <div
            class="h-1 mx-auto custom-gradient w-64 opacity-25 my-0 py-0 rounded-t"
          ></div>
        </div>
        <!-- Problems Grid -->
        <div class="erp-problems-grid mt-5">
          <!-- Problem Card 1 -->
          <div class="erp-problem-card">
            <div class="erp-problem-icon erp-icon-database">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M12 3C16.97 3 21 4.79 21 7V17C21 19.21 16.97 21 12 21C7.03 21 3 19.21 3 17V7C3 4.79 7.03 3 12 3Z"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path
                  d="M21 12C21 14.21 16.97 16 12 16C7.03 16 3 14.21 3 12"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path
                  d="M21 7C21 9.21 16.97 11 12 11C7.03 11 3 9.21 3 7"
                  stroke="currentColor"
                  stroke-width="2"
                />
              </svg>
            </div>
            <p class="erp-problem-text">
              Data tersebar di banyak sistem sehingga sulit dikendalikan
            </p>
          </div>
          <!-- Problem Card 2 -->
          <div class="erp-problem-card">
            <div class="erp-problem-icon erp-icon-report">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M14 2H6C4.9 2 4 2.9 4 4V20C4 21.1 4.89 22 5.99 22H18C19.1 22 20 21.1 20 20V8L14 2Z"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path d="M14 2V8H20" stroke="currentColor" stroke-width="2" />
                <path d="M16 13H8" stroke="currentColor" stroke-width="2" />
                <path d="M16 17H8" stroke="currentColor" stroke-width="2" />
                <path d="M10 9H9H8" stroke="currentColor" stroke-width="2" />
              </svg>
            </div>
            <p class="erp-problem-text">
              Laporan keuangan lambat & rawan error karena masih manual
            </p>
          </div>
          <!-- Problem Card 3 -->
          <div class="erp-problem-card">
            <div class="erp-problem-icon erp-icon-inventory">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M21 16V8C20.9996 7.64928 20.9071 7.30481 20.7315 7.00116C20.556 6.69751 20.3037 6.44536 20 6.27L13 2.27C12.696 2.09446 12.3511 2.00205 12 2.00205C11.6489 2.00205 11.304 2.09446 11 2.27L4 6.27C3.69626 6.44536 3.44398 6.69751 3.26846 7.00116C3.09294 7.30481 3.00036 7.64928 3 8V16C3.00036 16.3507 3.09294 16.6952 3.26846 16.9988C3.44398 17.3025 3.69626 17.5546 4 17.73L11 21.73C11.304 21.9055 11.6489 21.9979 12 21.9979C12.3511 21.9979 12.696 21.9055 13 21.73L20 17.73C20.3037 17.5546 20.556 17.3025 20.7315 16.9988C20.9071 16.6952 20.9996 16.3507 21 16Z"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path
                  d="M7.5 4.21L12 6.81L16.5 4.21"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path d="M7.5 19.79V14.6L3 12" stroke="currentColor" stroke-width="2" />
                <path d="M21 12L16.5 14.6V19.79" stroke="currentColor" stroke-width="2" />
                <path d="M12 22V12.81" stroke="currentColor" stroke-width="2" />
              </svg>
            </div>
            <p class="erp-problem-text">
              Stok tidak akurat antar gudang, menyebabkan overstock atau kekurangan barang
            </p>
          </div>
          <!-- Problem Card 4 -->
          <div class="erp-problem-card">
            <div class="erp-problem-icon erp-icon-delivery">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M16 3H5C3.9 3 3 3.9 3 5V19C3 20.1 3.9 21 5 21H16C17.1 21 18 20.1 18 19V5C18 3.9 17.1 3 16 3Z"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path
                  d="M21 7V17C21 18.1 20.1 19 19 19H18"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <circle cx="7" cy="17" r="2" stroke="currentColor" stroke-width="2" />
                <circle cx="15" cy="17" r="2" stroke="currentColor" stroke-width="2" />
              </svg>
            </div>
            <p class="erp-problem-text">
              Penjualan dan pengiriman tidak terintegrasi, memperlambat pelayanan
              pelanggan
            </p>
          </div>
          <!-- Problem Card 5 -->
          <div class="erp-problem-card">
            <div class="erp-problem-icon erp-icon-time">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2" />
                <path d="M12 6V12L16 14" stroke="currentColor" stroke-width="2" />
              </svg>
            </div>
            <p class="erp-problem-text">
              Manajemen kesulitan mengambil keputusan cepat karena data tidak real-time
            </p>
          </div>
        </div>

        <!-- Call to Action Section -->
        <div class="erp-cta-section">
          <div class="erp-cta-content">
            <h2 class="erp-cta-title">
              Masalah ini membuat biaya membengkak dan peluang bisnis terbuang sia-sia.
            </h2>
            <p class="erp-cta-subtitle">
              Inilah alasan ALTiUS ERP hadir: memberikan jawaban nyata atas masalah
              sehari-hari yang menghambat pertumbuhan perusahaan.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Problem Section -->

    <!-- Section Client -->
    <section class="sectionclient">
      <div class="containerclient">
        <!-- Section Title -->
        <h2
          class="w-full my-2 text-3xl font-bold leading-tight text-center text-gray-800"
        >
          Client Kita
        </h2>
        <div class="w-full mb-4">
          <div
            class="h-1 mx-auto custom-gradient w-64 opacity-25 my-0 py-0 rounded-t"
          ></div>
        </div>
        <!-- Clients Grid -->
        <div class="gridclient">
          <!-- P&G Logo -->
          <div class="client-logo">
            <img src="../assets/pandg.png" alt="P&G Logo" class="logo-img" />
          </div>

          <!-- Acer Logo -->
          <div class="client-logo">
            <img src="../assets/acer.png" alt="Acer Logo" class="logo-img" />
          </div>

          <!-- Ando Logo -->
          <div class="client-logo">
            <img src="../assets/ando.png" alt="Ando Logo" class="logo-img" />
          </div>

          <!-- Suzuki Logo -->
          <div class="client-logo">
            <img src="../assets/suzuki.png" alt="Suzuki Logo" class="logo-img" />
          </div>

          <!-- Holcim Logo -->
          <div class="client-logo">
            <img src="../assets/holcim.png" alt="Holcim Logo" class="logo-img" />
          </div>

          <!-- HP Logo -->
          <div class="client-logo">
            <img src="../assets/hp.png" alt="HP Logo" class="logo-img" />
          </div>

          <!-- Toyota Logo -->
          <div class="client-logo">
            <img src="../assets/toyota.png" alt="Toyota Logo" class="logo-img" />
          </div>
        </div>

        <!-- Optional: Add more description -->
        <div class="text-centerclient">
          <p class="descriptionclient">
            Dipercaya oleh berbagai perusahaan kelas dunia yang telah mempercayai solusi
            ERP kami untuk mengoptimalkan operasional bisnis mereka.
          </p>
        </div>
      </div>
    </section>
    <!-- Section Client -->

    <!-- First Content Section -->
    <section class="bg-white border-b py-8">
      <div class="container max-w-5xl mx-auto m-8">
        <h2
          class="w-full my-2 text-3xl font-bold leading-tight text-center text-gray-800"
        >
          Fitur Utama Untuk Hasil Nyata
        </h2>
        <div class="w-full mb-4">
          <div
            class="h-1 mx-auto custom-gradient w-64 opacity-25 my-0 py-0 rounded-t"
          ></div>
        </div>
        <div class="flex flex-wrap mt-5">
          <div class="w-5/6 sm:w-1/2 p-6">
            <h3 class="text-3xl text-gray-800 font-bold leading-none mb-3">
              Sales Management
            </h3>
            <p class="text-gray-600 mb-8">
              "Sales Management lebih cepat & transparan — mulai dari forecasting, order,
              dan delivery hingga mobile sales force, semuanya terintegrasi dalam satu
              sistem untuk mendukung keputusan yang lebih tepat dan pertumbuhan penjualan
              yang lebih tinggi."
            </p>
          </div>
          <div class="w-full sm:w-1/2 p-6">
            <img
              src="../assets/salesmanagement.jpg"
              alt="Sales Management Illustration"
              class="w-full sm:h-64 mx-auto object-contain rounded"
            />
          </div>
        </div>

        <!-- Second row with reversed order -->
        <div class="flex flex-wrap flex-col-reverse sm:flex-row">
          <div class="w-full sm:w-1/2 p-6 mt-6">
            <img
              src="../assets/purchasemanagement.jpg"
              alt="Purchase Management Illustration"
              class="w-5/6 sm:h-64 mx-auto object-contain rounded"
            />
          </div>
          <div class="w-full sm:w-1/2 p-6 mt-5">
            <div class="align-middle">
              <h3 class="text-3xl text-gray-800 font-bold leading-none mb-3">
                Purchase Management
              </h3>
              <p class="text-gray-600 mb-8">
                "Purchase Management lebih efisien dan terkendali — kelola seluruh proses
                pembelian dengan approval otomatis, pantau histori harga secara
                transparan, dan pastikan setiap pengeluaran tetap terkontrol untuk menjaga
                stabilitas biaya dan meningkatkan profitabilitas."
              </p>
            </div>
          </div>
        </div>

        <div class="flex flex-wrap mt-5">
          <div class="w-5/6 sm:w-1/2 p-6">
            <h3 class="text-3xl text-gray-800 font-bold leading-none mb-3">
              Inventory Management
            </h3>
            <p class="text-gray-600 mb-8">
              "Inventory Management terintegrasi untuk akurasi stok yang selalu terjamin —
              dukung multi gudang, batch/IMEI tracking, serta transfer stok yang mudah,
              sehingga operasional lebih efisien dan risiko kehilangan dapat
              diminimalkan."
            </p>
          </div>
          <div class="w-full sm:w-1/2 p-6">
            <img
              src="../assets/inventorymanagement.jpg"
              alt="Inventory Management Illustration"
              class="w-full sm:h-64 mx-auto object-contain rounded"
            />
          </div>
        </div>
      </div>
    </section>

    <section class="erp-problems-section">
      <div class="erp-problems-container">
        <div class="erp-cta-section">
          <div class="erp-cta-content">
            <h2 class="erp-cta-title">
              Bergabunglah dengan ratusan perusahaan yang lebih efisien dengan ALTiUS ERP
            </h2>
            <p class="erp-cta-subtitle">
              Dari startup hingga enterprise, ALTiUS ERP telah membantu berbagai perusahaan mencapai efisiensi maksimal
            </p>
          </div>
          <div class="grid grid-cols-3 gap-1 max-w-xl mx-auto mt-4">
            <div class="p-1">
              <div class="text-2xl md:text-3xl font-bold text-white">50+</div>
              <div class="text-xs text-white/80">Perusahaan</div>
            </div>
            <div class="p-1">
              <div class="text-2xl md:text-3xl font-bold text-white">20+</div>
              <div class="text-xs text-white/80">Tahun</div>
            </div>
            <div class="p-1">
              <div class="text-2xl md:text-3xl font-bold text-white">99.9%</div>
              <div class="text-xs text-white/80">Uptime</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="bg-white">
      <div class="container mx-auto px-8">
        <div class="w-full flex flex-col md:flex-row py-6">
          <div class="flex-1 mb-6 text-black">
            <a
              class="text-pink-600 no-underline hover:no-underline font-bold text-2xl lg:text-4xl"
              href="#"
            >
              <svg
                class="h-8 fill-current inline"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 512.005 512.005"
              >
                <rect
                  fill="#2a2a31"
                  x="16.539"
                  y="425.626"
                  width="479.767"
                  height="50.502"
                  transform="matrix(1,0,0,1,0,0)"
                />
                <path
                  class="plane-take-off"
                  d=" M 510.7 189.151 C 505.271 168.95 484.565 156.956 464.365 162.385 L 330.156 198.367 L 155.924 35.878 L 107.19 49.008 L 211.729 230.183 L 86.232 263.767 L 36.614 224.754 L 0 234.603 L 45.957 314.27 L 65.274 347.727 L 105.802 336.869 L 240.011 300.886 L 349.726 271.469 L 483.935 235.486 C 504.134 230.057 516.129 209.352 510.7 189.151 Z "
                />
              </svg>
              ALTiUS
            </a>
          </div>
          <div class="flex-1">
            <p class="uppercase text-gray-500 md:mb-6">Links</p>
            <ul class="list-reset mb-6">
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >FAQ</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Help</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Support</a
                >
              </li>
            </ul>
          </div>
          <div class="flex-1">
            <p class="uppercase text-gray-500 md:mb-6">Legal</p>
            <ul class="list-reset mb-6">
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Terms</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Privacy</a
                >
              </li>
            </ul>
          </div>
          <div class="flex-1">
            <p class="uppercase text-gray-500 md:mb-6">Social</p>
            <ul class="list-reset mb-6">
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Facebook</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Linkedin</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Twitter</a
                >
              </li>
            </ul>
          </div>
          <div class="flex-1">
            <p class="uppercase text-gray-500 md:mb-6">Company</p>
            <ul class="list-reset mb-6">
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Official Blog</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >About Us</a
                >
              </li>
              <li class="mt-2 inline-block mr-2 md:block md:mr-0">
                <a
                  href="#"
                  class="no-underline hover:underline text-gray-800 hover:text-pink-500"
                  >Contact</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
      <a
        href="https://www.freepik.com/free-photos-vectors/background"
        class="text-gray-500"
        >Background vector created by freepik - www.freepik.com</a
      >
    </footer>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Source+Sans+Pro:400,700");

.hero-gradient {
  background: linear-gradient(135deg, #003f5c, #00819b, #00bcd4);
}

.custom-gradient {
  background: linear-gradient(90deg, #00819b 0%, #ffc8dd 100%);
}
.blue-gradient {
  background: linear-gradient(90deg, #00819b 0%, #4a9cb8 100%);
}
@media (max-width: 1024px) {
  .lg\\:hidden + div {
    transition: all 0.3s ease-in-out;
  }
}
.containercall {
  border-radius: 16px;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
}
.stat-item {
  padding: 20px;
  transition: transform 0.3s ease;
}
.stat-item:hover {
  transform: translateY(-5px);
}
button,
a {
  transition: all 0.3s ease-in-out;
}
button {
  border-radius: 10px;
  cursor: pointer;
}
.wave-top {
  display: block;
  width: 100%;
  height: auto;
}

body {
  font-family: "Source Sans Pro", sans-serif;
}
.containercall {
  border-radius: 10px;
}
.sectionclient {
  background-color: #f9fafb;
  padding: 4rem 0;
}
.containerclient {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}
.text-centerclient {
  text-align: center;
}
.h2 {
  font-size: 1.875rem;
  font-weight: 600;
  color: #6b7280;
  margin-bottom: 2rem;
}

.gridclient {
  display: flex;
  overflow-x: auto;
  gap: 3rem;
  align-items: center;
  padding: 1rem 0;
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}
.gridclient::-webkit-scrollbar {
  height: 6px;
}

.gridclient::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 3px;
}
.gridclient::-webkit-scrollbar-thumb {
  background: #c1c1c1;
  border-radius: 3px;
}
.gridclient::-webkit-scrollbar-thumb:hover {
  background: #a8a8a8;
}
.client-logo {
  padding: 1rem;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  min-width: 120px;
}
.logo-img {
  width: 100px;
  height: 50px;
  object-fit: contain;
  transition: transform 0.3s ease-in-out;
  filter: grayscale(100%);
  opacity: 0.7;
}
.client-logo:hover .logo-img {
  transform: scale(1.1);
  filter: grayscale(0%);
  opacity: 1;
}
.descriptionclient {
  color: #6b7280;
  max-width: 42rem;
  margin: 3rem auto 0;
  text-align: center;
}
@media (max-width: 768px) {
  .client-logo {
    padding: 0.75rem;
    min-width: 100px;
  }
  .logo-img {
    width: 80px;
    height: 40px;
  }
  .sectionclient {
    padding: 3rem 0;
  }

  .gridclient {
    gap: 2rem;
  }
}
@media (max-width: 480px) {
  .logo-img {
    width: 70px;
    height: 35px;
  }
  .h2client {
    font-size: 1.5rem;
  }
  .gridclient {
    gap: 1.5rem;
  }
  .client-logo {
    min-width: 90px;
  }
}
.logo-img {
  image-rendering: -webkit-optimize-contrast;
  image-rendering: crisp-edges;
}

/*Problem Section*/
.erp-problems-section {
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  padding: 4rem 0;
  position: relative;
  overflow: hidden;
}

.erp-problems-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

/* Problems Grid */
.erp-problems-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

/* Problem Card */
.erp-problem-card {
  background: white;
  border-radius: 16px;
  padding: 2rem;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
  border: 1px solid #e9ecef;
  transition: all 0.3s ease;
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  position: relative;
  overflow: hidden;
}

.erp-problem-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #dc3545, #fd7e14);
  transform: scaleX(0);
  transition: transform 0.3s ease;
}

.erp-problem-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.12);
}

.erp-problem-card:hover::before {
  transform: scaleX(1);
}

/* Problem Icons */
.erp-problem-icon {
  flex-shrink: 0;
  width: 48px;
  height: 48px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.erp-problem-icon svg {
  width: 24px;
  height: 24px;
}

/* Icon Color Variants */
.erp-icon-database {
  background: #fee2e2;
  color: #dc2626;
}

.erp-icon-report {
  background: #fef3c7;
  color: #d97706;
}

.erp-icon-inventory {
  background: #f3e8ff;
  color: #7c3aed;
}

.erp-icon-delivery {
  background: #dbeafe;
  color: #2563eb;
}

.erp-icon-time {
  background: #ecfdf5;
  color: #059669;
}

.erp-problem-card:hover .erp-problem-icon {
  transform: scale(1.1);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}

/* Problem Text */
.erp-problem-text {
  color: #374151;
  font-size: 1rem;
  line-height: 1.6;
  margin: 0;
  font-weight: 500;
}

/* Call to Action Section */
.erp-cta-section {
  background: linear-gradient(135deg, #003f5c, #00819b, #00bcd4);
  border-radius: 20px;
  padding: 3rem;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.erp-cta-section::before {
  content: "";
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.1) 0%, transparent 50%);
  animation: erp-rotate 20s linear infinite;
}

@keyframes erp-rotate {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.erp-cta-content {
  position: relative;
  z-index: 2;
}

.erp-cta-title {
  color: white;
  font-size: 1.5rem;
  font-weight: 600;
  line-height: 1.3;
  margin-bottom: 1rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.erp-cta-subtitle {
  color: rgba(255, 255, 255, 0.95);
  font-size: 12pt;
  line-height: 1.6;
  margin: 0;
  max-width: 800px;
  margin: 0 auto;
}
/* Responsive Design */
@media (max-width: 768px) {
  .erp-problems-section {
    padding: 3rem 0;
  }
  .erp-problems-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
    margin-bottom: 3rem;
  }
  .erp-problem-card {
    padding: 1.5rem;
    flex-direction: row;
    gap: 1rem;
  }
  .erp-problem-icon {
    width: 40px;
    height: 40px;
  }
  .erp-problem-icon svg {
    width: 20px;
    height: 20px;
  }
  .erp-problem-text {
    font-size: 0.95rem;
  }
  .erp-cta-section {
    padding: 2rem;
    border-radius: 16px;
  }
  .erp-cta-title {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }
  .erp-cta-subtitle {
    font-size: 1rem;
  }
}

@media (max-width: 480px) {
  .erp-problems-container {
    padding: 0 0.75rem;
  }
  .erp-problem-card {
    padding: 1.25rem;
  }
  .erp-cta-section {
    padding: 1.5rem;
  }
  .erp-cta-title {
    font-size: 1.25rem;
  }
  .erp-cta-subtitle {
    font-size: 0.95rem;
  }
}
/* Grid adjustment for better layout */
@media (min-width: 769px) and (max-width: 1023px) {
  .erp-problems-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (min-width: 1024px) {
  .erp-problems-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  .erp-problem-card:last-child {
    grid-column: 1 / -1;
    max-width: 600px;
    margin: 0 auto;
  }
}
</style>
