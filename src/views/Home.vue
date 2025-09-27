<script setup>
import { ref, onMounted } from "vue";
import axios from "axios";

const data = ref(null);
const loading = ref(true);
const isMenuOpen = ref(false);

// Form data
const formData = ref({
  fullName: '',
  email: '',
  phone: '',
  companyName: '',
  businessNeeds: ''
});

const isSubmitting = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const submitForm = async () => {
  isSubmitting.value = true;
  
  try {
    // Simulate form submission - replace with actual API call
    await new Promise(resolve => setTimeout(resolve, 2000));
    
    // Reset form after successful submission
    formData.value = {
      fullName: '',
      email: '',
      phone: '',
      companyName: '',
      businessNeeds: ''
    };
    
    alert('Terima kasih! Permintaan konsultasi Anda telah terkirim.');
    
  } catch (error) {
    alert('Terjadi kesalahan. Silakan coba lagi.');
    console.error('Form submission error:', error);
  } finally {
    isSubmitting.value = false;
  }
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
          Bisnis ingin maju, tapi sering terjebak masalah yang sama?
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

    <!-- Industri Section -->
    <section class="industry-solutions-section">
      <div class="industry-container">
        <!-- Section Header -->
        <div class="industry-header">
          <h2 class="industry-title text-3xl font-bold">
            Daftar Solusi Industri yang Telah Dirancang dan
            <span class="industry-highlight">Dilayani Oleh ALTiUS</span> di Indonesia
          </h2>
          <p class="industry-subtitle">
            Pengalaman lebih dari 25 tahun melayani berbagai sektor industri
          </p>
        </div>

        <!-- Industries Grid -->
        <div class="industry-grid">
          <!-- Distribusi -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-distribusi">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M3 6H21L19 16H5L3 6Z"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M3 6L2 2H1"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M16 11V8C16 6.89543 15.1046 6 14 6H10C8.89543 6 8 6.89543 8 8V11"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <circle cx="9" cy="20" r="1" stroke="currentColor" stroke-width="2" />
                  <circle cx="20" cy="20" r="1" stroke="currentColor" stroke-width="2" />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Distribusi</h3>
          </div>

          <!-- Manufaktur -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-manufaktur">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M3 21H21V8L12 3L3 8V21Z"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                  <path d="M9 21V12H15V21" stroke="currentColor" stroke-width="2" />
                  <path
                    d="M9 8H15"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M6 12H8"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M16 12H18"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Manufaktur</h3>
          </div>

          <!-- Ritel -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-ritel">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M3 7V21H21V7" stroke="currentColor" stroke-width="2" />
                  <path
                    d="M3 7L5 3H19L21 7"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M8 7V11C8 12.1046 8.89543 13 10 13C11.1046 13 12 12.1046 12 11V7"
                    stroke="currentColor"
                    stroke-width="2"
                  />
                  <path
                    d="M16 7V11C16 12.1046 16.8954 13 18 13C19.1046 13 20 12.1046 20 11V7"
                    stroke="currentColor"
                    stroke-width="2"
                  />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Ritel</h3>
          </div>

          <!-- Farmasi -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-farmasi">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12 2L12 22"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M2 12L22 12"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <circle cx="12" cy="12" r="9" stroke="currentColor" stroke-width="2" />
                  <path
                    d="M8 8L16 16"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M16 8L8 16"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Farmasi</h3>
          </div>

          <!-- Logistik -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-logistik">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M1 3H15L13 12H3L1 3Z"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M16 8H20L23 12V17H20"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M5.5 17C6.32843 17 7 16.3284 7 15.5C7 14.6716 6.32843 14 5.5 14C4.67157 14 4 14.6716 4 15.5C4 16.3284 4.67157 17 5.5 17Z"
                    stroke="currentColor"
                    stroke-width="2"
                  />
                  <path
                    d="M18.5 17C19.3284 17 20 16.3284 20 15.5C20 14.6716 19.3284 14 18.5 14C17.6716 14 17 14.6716 17 15.5C17 16.3284 17.6716 17 18.5 17Z"
                    stroke="currentColor"
                    stroke-width="2"
                  />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Logistik</h3>
          </div>

          <!-- Agribisnis -->
          <div class="industry-card">
            <div class="industry-icon-wrapper">
              <div class="industry-icon industry-icon-agribisnis">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                    d="M12 2C13.5 4 16 7 16 11C16 13.5 14.5 16 12 16C9.5 16 8 13.5 8 11C8 7 10.5 4 12 2Z"
                    stroke="currentColor"
                    stroke-width="2"
                  />
                  <path
                    d="M12 16V22"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M8 20H16"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M6 18C6 18 7 17 9 17"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                  <path
                    d="M18 18C18 18 17 17 15 17"
                    stroke="currentColor"
                    stroke-width="2"
                    stroke-linecap="round"
                  />
                </svg>
              </div>
            </div>
            <h3 class="industry-card-title">Agribisnis</h3>
          </div>
        </div>
      </div>
    </section>
    <!-- Industri Section -->

    <section class="erp-problems-section">
      <div class="erp-problems-container">
        <div class="erp-cta-section">
          <div class="erp-cta-content">
            <h2 class="erp-cta-title">
              Bergabunglah dengan ratusan perusahaan yang lebih efisien dengan ALTiUS ERP
            </h2>
            <p class="erp-cta-subtitle">
              Dari startup hingga enterprise, ALTiUS ERP telah membantu berbagai
              perusahaan mencapai efisiensi maksimal
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
          <!-- Amm Logo -->
          <div class="client-logo">
            <img src="../assets/amm.png" alt="Amm Logo" class="logo-img" />
          </div>
          <!-- BP Logo -->
          <div class="client-logo">
            <img src="../assets/bp.png" alt="BP Logo" class="logo-img" />
          </div>
          <!-- CCI Logo -->
          <div class="client-logo">
            <img src="../assets/cci.png" alt="CCI Logo" class="logo-img" />
          </div>
          <!-- Crystal Logo -->
          <div class="client-logo">
            <img src="../assets/crystal.jpg" alt="Crystal Logo" class="logo-img" />
          </div>
          <!-- Gading Murni Logo -->
          <div class="client-logo">
            <img
              src="../assets/gadingmurni.png"
              alt="GadingMurni Logo"
              class="logo-img"
            />
          </div>
          <!-- Jessindo Logo -->
          <div class="client-logo">
            <img src="../assets/jessindo.jpg" alt="Jessindo Logo" class="logo-img" />
          </div>
          <!-- Mojong Logo -->
          <div class="client-logo">
            <img src="../assets/mojong.jpeg" alt="Mojong Logo" class="logo-img" />
          </div>
          <!-- PMJ Logo -->
          <div class="client-logo">
            <img src="../assets/pmj.jpg" alt="PMJ Logo" class="logo-img" />
          </div>
          <!-- Subur Logo -->
          <div class="client-logo">
            <img src="../assets/subur.jpg" alt="Subur Logo" class="logo-img" />
          </div>
          <!-- SumberBaru Logo -->
          <div class="client-logo">
            <img src="../assets/sumberbaru.jpeg" alt="SumberBaru Logo" class="logo-img" />
          </div>
          <!-- Tripl3 Logo -->
          <div class="client-logo">
            <img src="../assets/triple.png" alt="Tripl3 Logo" class="logo-img" />
          </div>
          <!-- Yanno Logo -->
          <div class="client-logo">
            <img src="../assets/yanno.jpg" alt="Yanno Logo" class="logo-img" />
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

    <!-- Section About -->
    <section class="testimonials-section">
      <div class="testimonials-container">
        <!-- Section Header -->
        <div class="testimonials-header">
          <h2 class="testimonials-title">
            Kata Mereka Tentang <span class="testimonials-highlight">ALTiUS</span>
          </h2>
          <p class="testimonials-subtitle">
            Dengarkan pengalaman nyata dari para klien yang telah merasakan transformasi
            bisnis
          </p>
        </div>

        <!-- Testimonials Grid -->
        <div class="testimonials-grid" ref="testimonialsGrid">
          <!-- Testimonial Card 1 -->
          <div class="testimonial-card">
            <div class="testimonial-content">
              <!-- Client Info -->
              <div class="client-info">
                <div class="client-avatar">
                  <img src="../assets/1.jpg" alt="Andi Wijaya" class="avatar-img" />
                </div>
                <div class="client-details">
                  <h4 class="client-name">Fajar Achmadi</h4>
                  <p class="client-position">Operations Director</p>
                  <p class="client-company">PT. Indonesia Maju</p>
                </div>
              </div>
              <!-- Rating Stars -->
              <div class="rating-stars">
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
              </div>
              <!-- Testimonial Text -->
              <blockquote class="testimonial-text">
                "Sejak menggunakan ALTiUS ERP, kontrol stok di semua cabang jadi jauh
                lebih rapi. Kami bisa tahu posisi barang real-time tanpa harus tunggu
                laporan manual. Tim kami lebih efisien, dan biaya operasional berkurang
                signifikan."
              </blockquote>
            </div>
          </div>
          <!-- Testimonial Card 2 -->
          <div class="testimonial-card">
            <div class="testimonial-content">
              <div class="client-info">
                <div class="client-avatar">
                  <img src="../assets/2.jpg" alt="Sari Indrawati" class="avatar-img" />
                </div>
                <div class="client-details">
                  <h4 class="client-name">Sari Indrawati</h4>
                  <p class="client-position">Finance Manager</p>
                  <p class="client-company">CV. Karya Bersama</p>
                </div>
              </div>
              <div class="rating-stars">
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
              </div>
              <blockquote class="testimonial-text">
                "ALTiUS memberikan solusi terintegrasi yang kami butuhkan. Dari purchase
                hingga finance, semua terkoneksi dengan baik. Laporan keuangan otomatis
                dan akurat membuat decision making jadi lebih cepat dan tepat."
              </blockquote>
            </div>
          </div>
          <!-- Testimonial Card 3 -->
          <div class="testimonial-card">
            <div class="testimonial-content">
              <div class="client-info">
                <div class="client-avatar">
                  <img src="../assets/3.jpg" alt="Budi Santoso" class="avatar-img" />
                </div>
                <div class="client-details">
                  <h4 class="client-name">Budi Hartanto</h4>
                  <p class="client-position">IT Director</p>
                  <p class="client-company">PT. Teknologi Nusantara</p>
                </div>
              </div>
              <div class="rating-stars">
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
                <span class="star">★</span>
              </div>

              <blockquote class="testimonial-text">
                "Tim support ALTiUS sangat responsif dan profesional. Training yang
                diberikan mudah dipahami. Dalam 3 bulan, seluruh tim sudah mahir
                menggunakan sistem ini, jadi memudahkan untuk memakai ALTiUS"
              </blockquote>
            </div>
          </div>
        </div>
      </div>
    </section>
    <!-- Section About -->

    <!-- Section Contast Us -->
    <section class="contact-section">
    <div class="contact-container">
      
      <div class="contact-grid">
        
        <!-- Left Column - Contact Form -->
        <div class="contact-form-wrapper">
          <div class="form-card">
            <h2 class="form-title">Konsultasi Gratis</h2>
            
            <form @submit.prevent="submitForm" class="contact-form">
              
              <!-- Name and Email Row -->
              <div class="form-row">
                <div class="form-group">
                  <label for="fullName" class="form-label">Nama Lengkap</label>
                  <input 
                    type="text" 
                    id="fullName"
                    v-model="formData.fullName"
                    placeholder="Masukkan nama lengkap" 
                    class="form-input"
                    required
                  />
                </div>
                <div class="form-group">
                  <label for="email" class="form-label">Email</label>
                  <input 
                    type="email" 
                    id="email"
                    v-model="formData.email"
                    placeholder="email@perusahaan.com" 
                    class="form-input"
                    required
                  />
                </div>
              </div>

              <!-- Phone and Company Row -->
              <div class="form-row">
                <div class="form-group">
                  <label for="phone" class="form-label">Nomor Telepon</label>
                  <input 
                    type="tel" 
                    id="phone"
                    v-model="formData.phone"
                    placeholder="+62 xxx-xxxx-xxxx" 
                    class="form-input"
                    required
                  />
                </div>
                <div class="form-group">
                  <label for="companyName" class="form-label">Nama Perusahaan</label>
                  <input 
                    type="text" 
                    id="companyName"
                    v-model="formData.companyName"
                    placeholder="PT. Nama Perusahaan" 
                    class="form-input"
                    required
                  />
                </div>
              </div>

              <!-- Business Needs Textarea -->
              <div class="form-group">
                <label for="businessNeeds" class="form-label">Ceritakan Kebutuhan Bisnis Anda</label>
                <textarea 
                  id="businessNeeds"
                  v-model="formData.businessNeeds"
                  placeholder="Jelaskan tantangan bisnis yang sedang Anda hadapi..."
                  class="form-textarea"
                  rows="4"
                  required
                ></textarea>
              </div>

              <!-- Submit Button -->
              <button 
                type="submit" 
                class="submit-btn"
                :disabled="isSubmitting"
              >
                <svg v-if="!isSubmitting" class="btn-icon" viewBox="0 0 24 24" fill="none">
                  <path d="M22 2L11 13" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                  <path d="M22 2L15 22L11 13L2 9L22 2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <div v-else class="loading-spinner"></div>
                {{ isSubmitting ? 'Mengirim...' : 'Kirim Konsultasi' }}
              </button>

            </form>
          </div>
        </div>

        <!-- Right Column - Contact Info -->
        <div class="contact-info-wrapper">
          <div class="info-card">
            <h2 class="info-title">Hubungi Kami</h2>
            
            <!-- Contact Items -->
            <div class="contact-items">
              
              <!-- Phone -->
              <div class="contact-item">
                <div class="contact-icon phone-icon">
                  <svg viewBox="0 0 24 24" fill="none">
                    <path d="M3 5C3 3.89543 3.89543 3 5 3H8.27924C8.70967 3 9.09181 3.27543 9.22792 3.68377L10.7257 8.17721C10.8831 8.64932 10.6694 9.16531 10.2243 9.38787L7.96701 10.5165C9.06925 12.9612 11.0388 14.9308 13.4835 16.033L14.6121 13.7757C14.8347 13.3306 15.3507 13.1169 15.8228 13.2743L20.3162 14.7721C20.7246 14.9082 21 15.2903 21 15.7208V19C21 20.1046 20.1046 21 19 21H18C9.71573 21 3 14.2843 3 6V5Z" stroke="currentColor" stroke-width="2"/>
                  </svg>
                </div>
                <div class="contact-details">
                  <h3 class="contact-type">Telepon</h3>
                  <p class="contact-value">+62 21 1234 5678</p>
                </div>
              </div>

              <!-- Email -->
              <div class="contact-item">
                <div class="contact-icon email-icon">
                  <svg viewBox="0 0 24 24" fill="none">
                    <path d="M3 8L10.89 13.26C11.2187 13.4793 11.6049 13.5963 12 13.5963C12.3951 13.5963 12.7813 13.4793 13.11 13.26L21 8M5 19H19C20.1046 19 21 18.1046 21 17V7C21 5.89543 20.1046 5 19 5H5C3.89543 5 3 5.89543 3 7V17C3 18.1046 3.89543 19 5 19Z" stroke="currentColor" stroke-width="2"/>
                  </svg>
                </div>
                <div class="contact-details">
                  <h3 class="contact-type">Email</h3>
                  <p class="contact-value">info@altius.id</p>
                </div>
              </div>

              <!-- Address -->
              <div class="contact-item">
                <div class="contact-icon location-icon">
                  <svg viewBox="0 0 24 24" fill="none">
                    <path d="M21 10C21 17 12 23 12 23S3 17 3 10C3 5.02944 7.02944 1 12 1C16.9706 1 21 5.02944 21 10Z" stroke="currentColor" stroke-width="2"/>
                    <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
                  </svg>
                </div>
                <div class="contact-details">
                  <h3 class="contact-type">Alamat</h3>
                  <p class="contact-value">Jakarta, Indonesia</p>
                </div>
              </div>

            </div>

            <!-- Response Time Card -->
            <div class="response-card">
              <div class="response-icon">
                <svg viewBox="0 0 24 24" fill="none">
                  <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
                  <path d="M12 6V12L16 14" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <div class="response-content">
                <h3 class="response-title">Respon Cepat</h3>
                <p class="response-desc">Tim ahli ALTiUS akan merespons pertanyaan Anda dalam waktu maksimal 24 jam pada hari kerja.</p>
                <div class="response-features">
                  <div class="feature-item">
                    <svg class="feature-check" viewBox="0 0 24 24" fill="none">
                      <path d="M20 6L9 17L4 12" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                    <span>Konsultasi gratis & tanpa komitmen</span>
                  </div>
                </div>
              </div>
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>
    <!-- Section Contast Us -->

    <!-- Footer -->
    <footer class="altius-footer">
      <div class="altius-footer-overlay">
        <!-- Main Footer Content -->
        <div class="altius-footer-container">
          <!-- Top Section with CTA -->
          <div class="altius-footer-cta">
            <div class="altius-cta-content">
              <h3 class="altius-cta-title">Siap Tingkatkan Efisiensi Bisnis Anda?</h3>
              <p class="altius-cta-subtitle">
                Dapatkan konsultasi gratis dan demo personal dari tim expert ALTiUS
              </p>
              <div class="altius-cta-buttons">
                <button class="altius-btn-primary">
                  <svg class="altius-btn-icon" viewBox="0 0 24 24" fill="none">
                    <path
                      d="M3 5C3 3.89543 3.89543 3 5 3H8.27924C8.70967 3 9.09181 3.27543 9.22792 3.68377L10.7257 8.17721C10.8831 8.64932 10.6694 9.16531 10.2243 9.38787L7.96701 10.5165C9.06925 12.9612 11.0388 14.9308 13.4835 16.033L14.6121 13.7757C14.8347 13.3306 15.3507 13.1169 15.8228 13.2743L20.3162 14.7721C20.7246 14.9082 21 15.2903 21 15.7208V19C21 20.1046 20.1046 21 19 21H18C9.71573 21 3 14.2843 3 6V5Z"
                      stroke="currentColor"
                      stroke-width="2"
                    />
                  </svg>
                  Hubungi Sekarang
                </button>
                <button class="altius-btn-secondary">
                  <svg class="altius-btn-icon" viewBox="0 0 24 24" fill="none">
                    <path
                      d="M15 10L11 14L17 20L21 4L3 11L9 13V19L12 16"
                      stroke="currentColor"
                      stroke-width="2"
                      stroke-linejoin="round"
                    />
                  </svg>
                  Request Demo
                </button>
              </div>
            </div>
          </div>
          <!-- Links Section -->
          <div class="altius-footer-links">
            <!-- Company Info -->
            <div class="altius-footer-column altius-company-info">
              <div class="altius-logo-section">
                <span class="altius-logo-text">ALTiUS ERP</span>
              </div>
              <p class="altius-company-desc">
                Solusi ERP terdepan untuk bisnis distribusi & manufaktur. Trusted since
                1997 dengan teknologi AI terintegrasi.
              </p>
              <div class="altius-contact-info">
                <div class="altius-contact-item">
                  <svg class="altius-contact-icon" viewBox="0 0 24 24" fill="none">
                    <path
                      d="M3 8L10.89 13.26C11.2187 13.4793 11.6049 13.5963 12 13.5963C12.3951 13.5963 12.7813 13.4793 13.11 13.26L21 8M5 19H19C20.1046 19 21 18.1046 21 17V7C21 5.89543 20.1046 5 19 5H5C3.89543 5 3 5.89543 3 7V17C3 18.1046 3.89543 19 5 19Z"
                      stroke="currentColor"
                      stroke-width="2"
                    />
                  </svg>
                  <span>info@altius.id</span>
                </div>
                <div class="altius-contact-item">
                  <svg class="altius-contact-icon" viewBox="0 0 24 24" fill="none">
                    <path
                      d="M3 5C3 3.89543 3.89543 3 5 3H8.27924C8.70967 3 9.09181 3.27543 9.22792 3.68377L10.7257 8.17721C10.8831 8.64932 10.6694 9.16531 10.2243 9.38787L7.96701 10.5165C9.06925 12.9612 11.0388 14.9308 13.4835 16.033L14.6121 13.7757C14.8347 13.3306 15.3507 13.1169 15.8228 13.2743L20.3162 14.7721C20.7246 14.9082 21 15.2903 21 15.7208V19C21 20.1046 20.1046 21 19 21H18C9.71573 21 3 14.2843 3 6V5Z"
                      stroke="currentColor"
                      stroke-width="2"
                    />
                  </svg>
                  <span>+62 21 1234 5678</span>
                </div>
              </div>
            </div>
            <!-- Products -->
            <div class="altius-footer-column">
              <h4 class="altius-column-title">Produk</h4>
              <ul class="altius-link-list">
                <li><a href="#" class="altius-footer-link">Sales Management</a></li>
                <li><a href="#" class="altius-footer-link">Purchase Management</a></li>
                <li><a href="#" class="altius-footer-link">Inventory Management</a></li>
                <li><a href="#" class="altius-footer-link">Finance & Accounting</a></li>
              </ul>
            </div>
            <!-- Solutions -->
            <div class="altius-footer-column">
              <h4 class="altius-column-title">Solusi</h4>
              <ul class="altius-link-list">
                <li><a href="#" class="altius-footer-link">Distribusi & Trading</a></li>
                <li><a href="#" class="altius-footer-link">Manufaktur</a></li>
                <li><a href="#" class="altius-footer-link">Retail & FMCG</a></li>
                <li><a href="#" class="altius-footer-link">Automotive</a></li>
              </ul>
            </div>
            <!-- Support -->
            <div class="altius-footer-column">
              <h4 class="altius-column-title">Support</h4>
              <ul class="altius-link-list">
                <li><a href="#" class="altius-footer-link">Documentation</a></li>
                <li><a href="#" class="altius-footer-link">Video Tutorial</a></li>
                <li><a href="#" class="altius-footer-link">Training</a></li>
                <li><a href="#" class="altius-footer-link">Contact Support</a></li>
              </ul>
            </div>
            <!-- Company -->
            <div class="altius-footer-column">
              <h4 class="altius-column-title">Perusahaan</h4>
              <ul class="altius-link-list">
                <li><a href="#" class="altius-footer-link">Tentang Kami</a></li>
                <li><a href="#" class="altius-footer-link">Blog</a></li>
                <li><a href="#" class="altius-footer-link">Partnership</a></li>
                <li><a href="#" class="altius-footer-link">Awards</a></li>
              </ul>
            </div>
          </div>
          <!-- Bottom Section -->
          <div class="altius-footer-bottom">
            <div class="altius-bottom-left">
              <p class="altius-copyright">© 2024 ALTiUS ERP. All rights reserved.</p>
              <div class="altius-legal-links">
                <a href="#" class="altius-legal-link">Privacy Policy</a>
                <a href="#" class="altius-legal-link">Terms of Service</a>
                <a href="#" class="altius-legal-link">Cookie Policy</a>
              </div>
            </div>
            <div class="altius-social-links">
              <a href="#" class="altius-social-link" aria-label="Facebook">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                  />
                </svg>
              </a>
              <a href="#" class="altius-social-link" aria-label="LinkedIn">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
                  />
                </svg>
              </a>
              <a href="#" class="altius-social-link" aria-label="Twitter">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"
                  />
                </svg>
              </a>
              <a href="#" class="altius-social-link" aria-label="YouTube">
                <svg viewBox="0 0 24 24" fill="currentColor">
                  <path
                    d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"
                  />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
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
  background: linear-gradient(90deg, #003f5c, #00819b, #00bcd4);
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

/*Footer*/
.altius-footer {
  background: linear-gradient(135deg, #003f5c, #00819b, #00bcd4);
  position: relative;
  overflow: hidden;
}

.altius-footer-overlay {
  background: rgba(0, 0, 0, 0.1);
  position: relative;
}

.altius-footer::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")
    repeat;
  animation: altius-pattern-move 20s linear infinite;
}

@keyframes altius-pattern-move {
  0% {
    transform: translateX(0) translateY(0);
  }
  100% {
    transform: translateX(60px) translateY(60px);
  }
}

.altius-footer-container {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

/* CTA Section */
.altius-footer-cta {
  padding: 3rem 0;
  text-align: center;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  margin-bottom: 3rem;
}

.altius-cta-title {
  color: white;
  font-size: 2.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.altius-cta-subtitle {
  color: rgba(255, 255, 255, 0.9);
  font-size: 1.25rem;
  margin-bottom: 2rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.altius-cta-buttons {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.altius-btn-primary,
.altius-btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem 2rem;
  border-radius: 50px;
  font-weight: 600;
  font-size: 1rem;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  text-decoration: none;
}

.altius-btn-primary {
  background: rgba(255, 255, 255, 0.95);
  color: #003f5c;
}

.altius-btn-primary:hover {
  background: white;
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.altius-btn-secondary {
  background: transparent;
  color: white;
  border: 2px solid rgba(255, 255, 255, 0.5);
}

.altius-btn-secondary:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: white;
  transform: translateY(-2px);
}

.altius-btn-icon {
  width: 20px;
  height: 20px;
}

/* Links Section */
.altius-footer-links {
  display: grid;
  grid-template-columns: 2fr repeat(4, 1fr);
  gap: 3rem;
  margin-bottom: 3rem;
}

.altius-footer-column {
  color: white;
}

/* Company Info */
.altius-company-info .altius-logo-section {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
}

.altius-logo-icon {
  width: 40px;
  height: 40px;
  color: white;
}

.altius-logo-text {
  font-size: 2rem;
  font-weight: 700;
  color: white;
}

.altius-company-desc {
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.6;
  margin-bottom: 2rem;
}

.altius-contact-info {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.altius-contact-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: rgba(255, 255, 255, 0.9);
}

.altius-contact-icon {
  width: 20px;
  height: 20px;
  flex-shrink: 0;
}

/* Column Titles */
.altius-column-title {
  font-size: 1.125rem;
  font-weight: 600;
  color: white;
  margin-bottom: 1.5rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* Link Lists */
.altius-link-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.altius-link-list li {
  margin-bottom: 0.75rem;
}

.altius-footer-link {
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  transition: all 0.2s ease;
  position: relative;
}

.altius-footer-link:hover {
  color: white;
  padding-left: 0.5rem;
}

.altius-footer-link::before {
  content: "";
  position: absolute;
  left: -0.5rem;
  top: 50%;
  transform: translateY(-50%);
  width: 0;
  height: 2px;
  background: #00bcd4;
  transition: width 0.2s ease;
}

.altius-footer-link:hover::before {
  width: 0.25rem;
}

/* Bottom Section */
.altius-footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2rem 0;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.altius-bottom-left {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.altius-copyright {
  color: rgba(255, 255, 255, 0.7);
  margin: 0;
}

.altius-legal-links {
  display: flex;
  gap: 1.5rem;
}

.altius-legal-link {
  color: rgba(255, 255, 255, 0.6);
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.2s ease;
}

.altius-legal-link:hover {
  color: white;
}

/* Social Links */
.altius-social-links {
  display: flex;
  gap: 1rem;
}

.altius-social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  color: rgba(255, 255, 255, 0.7);
  text-decoration: none;
  transition: all 0.3s ease;
}

.altius-social-link svg {
  width: 20px;
  height: 20px;
}

.altius-social-link:hover {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  transform: translateY(-2px);
}

/* Responsive Design */
@media (max-width: 1024px) {
  .altius-footer-links {
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }

  .altius-company-info {
    grid-column: 1 / -1;
    margin-bottom: 2rem;
  }
}

@media (max-width: 768px) {
  .altius-footer-container {
    padding: 0 1rem;
  }

  .altius-cta-title {
    font-size: 2rem;
  }

  .altius-cta-subtitle {
    font-size: 1.125rem;
  }

  .altius-cta-buttons {
    flex-direction: column;
    align-items: center;
  }

  .altius-btn-primary,
  .altius-btn-secondary {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }

  .altius-footer-links {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.5rem;
  }

  .altius-footer-bottom {
    flex-direction: column;
    gap: 1.5rem;
    text-align: center;
  }

  .altius-legal-links {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .altius-footer-links {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .altius-cta-title {
    font-size: 1.75rem;
  }

  .altius-legal-links {
    flex-direction: column;
    gap: 0.5rem;
  }
}
/*Footer*/

/*Industri*/
.industry-solutions-section {
  background: linear-gradient(180deg, #f8f9fa 0%, #ffffff 100%);
  padding: 5rem 0;
  position: relative;
  overflow: hidden;
}

.industry-solutions-section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%2300819b' fill-opacity='0.02'%3E%3Cpath d='M30 30c0-6.6-5.4-12-12-12s-12 5.4-12 12 5.4 12 12 12 12-5.4 12-12zm12 0c0-6.6-5.4-12-12-12s-12 5.4-12 12 5.4 12 12 12 12-5.4 12-12z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")
    repeat;
  pointer-events: none;
}

.industry-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

/* Header Section */
.industry-header {
  text-align: center;
  margin-bottom: 4rem;
  max-width: 900px;
  margin-left: auto;
  margin-right: auto;
}

.industry-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #1f2937;
  line-height: 1.3;
  margin-bottom: 1.5rem;
}

.industry-highlight {
  color: #00819b;
  position: relative;
}

.industry-highlight::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #00819b, #4a9cb8);
  border-radius: 2px;
}

.industry-subtitle {
  font-size: 1.25rem;
  color: #6b7280;
  margin: 0;
  font-weight: 400;
}

/* Industries Grid */
.industry-grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: 1.5rem;
  justify-items: center;
}

/* Industry Cards */
.industry-card {
  background: white;
  border-radius: 20px;
  padding: 2rem 1rem;
  text-align: center;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.06);
  border: 1px solid #e5e7eb;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
  min-height: 180px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  width: 100%;
}

.industry-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(0, 129, 155, 0.1), transparent);
  transition: left 0.6s ease;
}

.industry-card:hover::before {
  left: 100%;
}

.industry-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 129, 155, 0.15);
  border-color: #00819b;
}

/* Icon Wrapper */
.industry-icon-wrapper {
  margin-bottom: 1.5rem;
  position: relative;
}

.industry-icon {
  width: 80px;
  height: 80px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto;
  transition: all 0.4s ease;
  position: relative;
  overflow: hidden;
}

.industry-icon svg {
  width: 36px;
  height: 36px;
  transition: all 0.3s ease;
  position: relative;
  z-index: 2;
}

.industry-card:hover .industry-icon {
  transform: scale(1.1) rotate(-5deg);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.industry-card:hover .industry-icon svg {
  transform: scale(1.1);
}

/* Icon Color Variants */
.industry-icon-distribusi {
  background: linear-gradient(135deg, #dbeafe 0%, #bfdbfe 100%);
  color: #1e40af;
}

.industry-icon-manufaktur {
  background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
  color: #d97706;
}

.industry-icon-ritel {
  background: linear-gradient(135deg, #f3e8ff 0%, #e9d5ff 100%);
  color: #7c3aed;
}

.industry-icon-farmasi {
  background: linear-gradient(135deg, #dcfce7 0%, #bbf7d0 100%);
  color: #16a34a;
}

.industry-icon-logistik {
  background: linear-gradient(135deg, #fee2e2 0%, #fecaca 100%);
  color: #dc2626;
}

.industry-icon-agribisnis {
  background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%);
  color: #059669;
}

/* Card Titles */
.industry-card-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #1f2937;
  margin: 0;
  transition: all 0.3s ease;
}

.industry-card:hover .industry-card-title {
  color: #00819b;
  transform: translateY(-2px);
}

/* Responsive Design */
@media (max-width: 1024px) {
  .industry-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }

  .industry-card {
    padding: 2rem 1.5rem;
  }

  .industry-icon {
    width: 70px;
    height: 70px;
  }

  .industry-icon svg {
    width: 32px;
    height: 32px;
  }
}

@media (max-width: 768px) {
  .industry-solutions-section {
    padding: 4rem 0;
  }

  .industry-container {
    padding: 0 1rem;
  }

  .industry-header {
    margin-bottom: 3rem;
  }

  .industry-title {
    font-size: 2rem;
  }

  .industry-subtitle {
    font-size: 1.125rem;
  }

  .industry-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1.25rem;
  }

  .industry-card {
    padding: 1.5rem 1rem;
    min-height: 180px;
  }

  .industry-icon {
    width: 60px;
    height: 60px;
  }

  .industry-icon svg {
    width: 28px;
    height: 28px;
  }

  .industry-card-title {
    font-size: 1.25rem;
  }
}

@media (max-width: 480px) {
  .industry-title {
    font-size: 1.75rem;
  }

  .industry-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }

  .industry-card {
    padding: 1.25rem 0.75rem;
    min-height: 160px;
  }

  .industry-icon {
    width: 50px;
    height: 50px;
  }

  .industry-icon svg {
    width: 24px;
    height: 24px;
  }

  .industry-card-title {
    font-size: 1.125rem;
  }
}

/* Special animation for page load */
@keyframes industry-fade-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.industry-card {
  animation: industry-fade-up 0.6s ease-out forwards;
}

.industry-card:nth-child(1) {
  animation-delay: 0.1s;
}
.industry-card:nth-child(2) {
  animation-delay: 0.2s;
}
.industry-card:nth-child(3) {
  animation-delay: 0.3s;
}
.industry-card:nth-child(4) {
  animation-delay: 0.4s;
}
.industry-card:nth-child(5) {
  animation-delay: 0.5s;
}
.industry-card:nth-child(6) {
  animation-delay: 0.6s;
}
/*Industri*/
/*About*/
.testimonials-section {
  background: linear-gradient(180deg, #ffffff 0%, #f8f9fa 50%, #ffffff 100%);
  padding: 5rem 0;
  position: relative;
  overflow: hidden;
}

.testimonials-section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='40' height='40' viewBox='0 0 40 40' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='%2300819b' fill-opacity='0.02'%3E%3Cpath d='M20 20c0-16 13-20 20-20v20c-6 0-20 6-20 20z'/%3E%3C/g%3E%3C/svg%3E")
    repeat;
  pointer-events: none;
}

.testimonials-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

/* Header Section */
.testimonials-header {
  text-align: center;
  margin-bottom: 4rem;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

.testimonials-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #1f2937;
  line-height: 1.3;
  margin-bottom: 1.5rem;
}

.testimonials-highlight {
  color: #00819b;
  position: relative;
}

.testimonials-highlight::after {
  content: "";
  position: absolute;
  bottom: -4px;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(90deg, #00819b, #4a9cb8);
  border-radius: 2px;
}

.testimonials-subtitle {
  font-size: 1.25rem;
  color: #6b7280;
  margin: 0;
  font-weight: 400;
}

/* Testimonials Grid */
.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

/* Testimonial Cards */
.testimonial-card {
  background: white;
  border-radius: 20px;
  padding: 2.5rem;
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.08);
  border: 1px solid #e5e7eb;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.testimonial-card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, #00819b, #4a9cb8);
  transform: scaleX(0);
  transition: transform 0.4s ease;
}

.testimonial-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 50px rgba(0, 129, 155, 0.15);
}

.testimonial-card:hover::before {
  transform: scaleX(1);
}

/* Testimonial Content */
.testimonial-content {
  margin-bottom: 2rem;
}

.quote-icon {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, #00819b, #4a9cb8);
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.quote-icon svg {
  width: 20px;
  height: 20px;
}

/* Rating Stars */
.rating-stars {
  display: flex;
  gap: 0.25rem;
  margin-bottom: 1.5rem;
}

.star {
  color: #fbbf24;
  font-size: 1.25rem;
  transition: all 0.2s ease;
}

.testimonial-card:hover .star {
  transform: scale(1.1);
}

/* Testimonial Text */
.testimonial-text {
  font-size: 1.125rem;
  line-height: 1.7;
  color: #374151;
  font-style: italic;
  margin: 0;
  position: relative;
}

.testimonial-text::before {
  content: '"';
  font-size: 4rem;
  color: #00819b;
  position: absolute;
  top: -1rem;
  left: -1rem;
  opacity: 0.2;
  font-family: serif;
}

/* Client Info */
.client-info {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding-top: 2rem;
  border-top: 1px solid #e5e7eb;
}

.client-avatar {
  flex-shrink: 0;
}

.avatar-img {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid #00819b;
  transition: all 0.3s ease;
}

.testimonial-card:hover .avatar-img {
  transform: scale(1.05);
  box-shadow: 0 4px 15px rgba(0, 129, 155, 0.3);
}

.client-details {
  flex: 1;
}

.client-name {
  font-size: 1.125rem;
  font-weight: 600;
  color: #1f2937;
  margin: 0 0 0.25rem 0;
}

.client-position {
  font-size: 1rem;
  font-weight: 500;
  color: #00819b;
  margin: 0 0 0.25rem 0;
}

.client-company {
  font-size: 0.9rem;
  color: #6b7280;
  margin: 0;
}

/* Navigation Dots */
.testimonial-dots {
  display: flex;
  justify-content: center;
  gap: 0.75rem;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  border: none;
  background: #d1d5db;
  cursor: pointer;
  transition: all 0.3s ease;
}

.dot.active {
  background: #00819b;
  transform: scale(1.2);
}

.dot:hover {
  background: #9ca3af;
}

/* Responsive Design */
@media (max-width: 768px) {
  .testimonials-section {
    padding: 4rem 0;
  }

  .testimonials-container {
    padding: 0 1rem;
  }

  .testimonials-header {
    margin-bottom: 3rem;
  }

  .testimonials-title {
    font-size: 2rem;
  }

  .testimonials-subtitle {
    font-size: 1.125rem;
  }

  .testimonials-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .testimonial-card {
    padding: 2rem;
  }

  .testimonial-text {
    font-size: 1rem;
  }

  .client-info {
    flex-direction: column;
    text-align: center;
    gap: 0.75rem;
  }

  .avatar-img {
    width: 50px;
    height: 50px;
  }
}

@media (max-width: 480px) {
  .testimonials-title {
    font-size: 1.75rem;
  }

  .testimonial-card {
    padding: 1.5rem;
  }

  .quote-icon {
    width: 35px;
    height: 35px;
  }

  .quote-icon svg {
    width: 18px;
    height: 18px;
  }

  .rating-stars {
    justify-content: center;
  }
}

/* Animation for page load */
@keyframes testimonial-fade-up {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.testimonial-card {
  animation: testimonial-fade-up 0.6s ease-out forwards;
}

.testimonial-card:nth-child(1) {
  animation-delay: 0.1s;
}
.testimonial-card:nth-child(2) {
  animation-delay: 0.2s;
}
.testimonial-card:nth-child(3) {
  animation-delay: 0.3s;
}
/*About*/

/*Contact Us*/
.contact-section {
  background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
  padding: 5rem 0;
  position: relative;
  overflow: hidden;
}

.contact-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%2300819b' fill-opacity='0.03'%3E%3Cpath d='M30 30c0-6.6-5.4-12-12-12s-12 5.4-12 12 5.4 12 12 12 12-5.4 12-12zm12-12c0-6.6-5.4-12-12-12s-12 5.4-12 12 5.4 12 12 12 12-5.4 12-12z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E") repeat;
  pointer-events: none;
}

.contact-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: start;
}

/* Form Card */
.form-card,
.info-card {
  background: white;
  border-radius: 20px;
  padding: 2.5rem;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.1);
  border: 1px solid #e2e8f0;
  height: fit-content;
}

/* Form Styling */
.form-title,
.info-title {
  font-size: 1.75rem;
  font-weight: 700;
  color: #1f2937;
  margin-bottom: 2rem;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-label {
  font-size: 0.9rem;
  font-weight: 500;
  color: #374151;
  margin-bottom: 0.5rem;
}

.form-input,
.form-textarea {
  padding: 0.875rem 1rem;
  border: 2px solid #e5e7eb;
  border-radius: 12px;
  font-size: 1rem;
  transition: all 0.3s ease;
  background: #f9fafb;
  color: #1f2937;
}

.form-input::placeholder,
.form-textarea::placeholder {
  color: #9ca3af;
}

.form-input:focus,
.form-textarea:focus {
  outline: none;
  border-color: #00819b;
  background: white;
  box-shadow: 0 0 0 3px rgba(0, 129, 155, 0.1);
}

.form-textarea {
  resize: vertical;
  min-height: 100px;
}

/* Submit Button */
.submit-btn {
  width: 100%;
  background: linear-gradient(135deg, #00819b, #4a9cb8);
  color: white;
  border: none;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 1rem;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 129, 155, 0.3);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.btn-icon {
  width: 20px;
  height: 20px;
}

.loading-spinner {
  width: 20px;
  height: 20px;
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-top: 2px solid white;
  border-radius: 50%;
  animation: contact-spin 1s linear infinite;
}

@keyframes contact-spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

/* Contact Info */
.contact-items {
  margin-bottom: 2rem;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding: 1rem;
  border-radius: 12px;
  background: #f8fafc;
  transition: all 0.3s ease;
}

.contact-item:hover {
  background: #e2e8f0;
  transform: translateX(5px);
}

.contact-icon {
  width: 50px;
  height: 50px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.contact-icon svg {
  width: 24px;
  height: 24px;
}

.phone-icon {
  background: linear-gradient(135deg, #dbeafe, #bfdbfe);
  color: #1e40af;
}

.email-icon {
  background: linear-gradient(135deg, #dcfce7, #bbf7d0);
  color: #16a34a;
}

.location-icon {
  background: linear-gradient(135deg, #f3e8ff, #e9d5ff);
  color: #7c3aed;
}

.contact-type {
  font-size: 1rem;
  font-weight: 600;
  color: #1f2937;
  margin: 0 0 0.25rem 0;
}

.contact-value {
  font-size: 0.95rem;
  color: #6b7280;
  margin: 0;
}

/* Response Card */
.response-card {
  background: linear-gradient(135deg, #00819b, #4a9cb8);
  color: white;
  padding: 1.5rem;
  border-radius: 16px;
  position: relative;
  overflow: hidden;
}

.response-card::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 50%);
  animation: contact-rotate 15s linear infinite;
}

@keyframes contact-rotate {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.response-content {
  position: relative;
  z-index: 2;
}

.response-icon {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.2);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
}

.response-icon svg {
  width: 20px;
  height: 20px;
}

.response-title {
  font-size: 1.25rem;
  font-weight: 600;
  margin: 0 0 0.5rem 0;
}

.response-desc {
  font-size: 0.95rem;
  margin: 0 0 1rem 0;
  opacity: 0.9;
  line-height: 1.5;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.9rem;
  opacity: 0.9;
}

.feature-check {
  width: 16px;
  height: 16px;
  flex-shrink: 0;
}

/* Responsive Design */
@media (max-width: 1024px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .form-row {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
}

@media (max-width: 768px) {
  .contact-section {
    padding: 4rem 0;
  }
  
  .contact-container {
    padding: 0 1rem;
  }
  
  .form-card,
  .info-card {
    padding: 2rem;
  }
  
  .form-title,
  .info-title {
    font-size: 1.5rem;
  }
  
  .contact-item {
    flex-direction: column;
    text-align: center;
    gap: 0.75rem;
  }
  
  .contact-item:hover {
    transform: none;
  }
}

@media (max-width: 480px) {
  .form-card,
  .info-card {
    padding: 1.5rem;
  }
  
  .response-card {
    padding: 1.25rem;
  }
}
/*Contact Us*/
</style>
