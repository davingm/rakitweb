<script setup lang="ts">
interface Feature {
  title: string
  description: string
}

const features: Feature[] = [
  {
    title: 'Jadi Inovatif',
    description:
      'Berikan pelanggan Anda keamanan, kecepatan, kemampuan pemrograman, dan ketahanan Cloudflare.',
  },
  {
    title: 'Jadi Menguntungkan',
    description:
      'Tumbuhkan pendapatan dan berikan nilai lebih secara masif untuk mengembangkan bisnis Anda dengan cepat serta memperluas jangkauan.',
  },
  {
    title: 'Jadi Didukung',
    description:
      'Andalkan perusahaan yang mudah diajak bekerja sama dan berinvestasi dalam pertumbuhan penjualan, pemasaran, serta pengembangan kapabilitas Anda.',
  },
]

// ─── SEO & OpenGraph ───────────────────────────────────────────────
useSeoMeta({
  title: 'Percepat Pertumbuhan Bisnis Anda | Connectivity Cloud',
  description:
    'Tingkatkan profitabilitas dengan solusi pelanggan yang disesuaikan untuk layanan SASE, developer, jaringan, dan aplikasi. Bangun dengan Agents SDK untuk setiap kasus penggunaan.',
  keywords: [
    'connectivity cloud',
    'SASE',
    'agen AI',
    'Agents SDK',
    'mitra',
    'profitabilitas',
    'infrastruktur komposabel',
  ],
  ogTitle: 'Percepat Pertumbuhan Bisnis Anda | Connectivity Cloud',
  ogDescription:
    'Tingkatkan profitabilitas dengan solusi pelanggan yang disesuaikan untuk layanan SASE, developer, jaringan, dan aplikasi.',
  ogType: 'website',
  ogLocale: 'id_ID',
  ogSiteName: 'Connectivity Cloud',
  twitterCard: 'summary_large_image',
  twitterTitle: 'Percepat Pertumbuhan Bisnis Anda | Connectivity Cloud',
  twitterDescription:
    'Tingkatkan profitabilitas dengan solusi pelanggan yang disesuaikan untuk layanan SASE, developer, jaringan, dan aplikasi.',
  robots: 'index, follow',
})

useHead({
  link: [
    {
      rel: 'canonical',
      href: 'https://your-domain.com',
    },
  ],
  // Gambar OG — ganti URL ini dengan gambar yang sesuai
  meta: [
    {
      property: 'og:image',
      content: 'https://your-domain.com/og-image.png',
    },
    {
      property: 'og:image:width',
      content: '1200',
    },
    {
      property: 'og:image:height',
      content: '630',
    },
    {
      property: 'og:image:alt',
      content: 'Percepat pertumbuhan bisnis Anda dengan connectivity cloud',
    },
    {
      name: 'twitter:image',
      content: 'https://your-domain.com/og-image.png',
    },
    {
      name: 'twitter:image:alt',
      content: 'Percepat pertumbuhan bisnis Anda dengan connectivity cloud',
    },
    // Structured Data (JSON-LD) untuk organisasi / halaman
    {
      type: 'application/ld+json',
      innerHTML: JSON.stringify({
        '@context': 'https://schema.org',
        '@type': 'WebPage',
        name: 'Percepat Pertumbuhan Bisnis Anda',
        description:
          'Tingkatkan profitabilitas dengan solusi pelanggan yang disesuaikan untuk layanan SASE, developer, jaringan, dan aplikasi.',
        url: 'https://your-domain.com',
        inLanguage: 'id-ID',
      }),
    },
  ],
})
</script>

<template>
  <section class="relative bg-white dark:bg-black py-24 px-6 transition-colors duration-300">
    <!-- Hero copy: kolom bacaan yang lebih sempit -->
    <div class="mx-auto max-w-3xl text-center">
      <h1
        class="text-4xl sm:text-5xl md:text-6xl font-semibold tracking-tight leading-[1.1] text-neutral-900 dark:text-white"
      >
        Percepat pertumbuhan
        <br class="hidden sm:block" />
        dengan connectivity cloud kami
      </h1>

      <p
        class="mt-6 max-w-2xl mx-auto text-base sm:text-lg text-neutral-500 dark:text-neutral-400 leading-relaxed"
      >
        Tingkatkan profitabilitas dengan menciptakan solusi pelanggan yang disesuaikan untuk
        layanan SASE, developer, jaringan, dan aplikasi. Gabungkan infrastruktur kami yang
        komposabel dan terprogram dengan keahlian Anda untuk memecahkan tantangan paling
        kompleks pelanggan Anda.
      </p>

      <a
        href="https://login.partner.nlfts.dev"
        class="mt-10 inline-flex items-center gap-1 text-sm font-semibold text-neutral-900 dark:text-white transition-opacity hover:opacity-60"
      >
        Masuk portal mitra
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="none" class="h-3.5 w-3.5">
          <path
            d="M5 15L15 5M15 5H7M15 5V13"
            stroke="currentColor"
            stroke-width="1.6"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
      </a>
    </div>

    <!-- Baris fitur -->
    <div class="relative mt-24 -mx-6">
      <div
        class="grid grid-cols-1 sm:grid-cols-3 border-t border-b border-dashed border-neutral-300 dark:border-neutral-700"
      >
        <div
          v-for="(feature, index) in features"
          :key="feature.title"
          :class="[
            'relative px-6 sm:px-10 py-10',
            index < features.length - 1
              ? 'sm:border-r sm:border-dashed sm:border-neutral-300 dark:sm:border-neutral-700'
              : '',
            index > 0
              ? 'border-t sm:border-t-0 border-dashed border-neutral-300 dark:border-neutral-700'
              : '',
          ]"
        >
          <!-- Ikon -->
          <div class="text-neutral-900 dark:text-white">
            <svg
              v-if="index === 0"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              class="h-6 w-6"
            >
              <path
                d="M13 2L4 14h6l-1 8 9-12h-6l1-8z"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linejoin="round"
              />
            </svg>
            <svg
              v-else-if="index === 1"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="none"
              class="h-6 w-6"
            >
              <path
                d="M4 20V10M10 20V4M16 20v-7M22 20H2"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" class="h-6 w-6">
              <path
                d="M12 2l8 3v6c0 5-3.5 8.5-8 10-4.5-1.5-8-5-8-10V5l8-3z"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linejoin="round"
              />
              <path
                d="M12 8v8M8 12h8"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
              />
            </svg>
          </div>

          <h3 class="mt-4 text-sm font-semibold text-neutral-900 dark:text-white">
            {{ feature.title }}
          </h3>
          <p class="mt-2 text-sm leading-relaxed text-neutral-500 dark:text-neutral-400">
            {{ feature.description }}
          </p>
        </div>
      </div>

      <!-- Penanda sudut -->
      <span
        v-for="(marker, i) in [
          { pos: 'top-0 left-0', translate: '-translate-x-1/2 -translate-y-1/2' },
          { pos: 'top-0 left-1/3', translate: '-translate-x-1/2 -translate-y-1/2' },
          { pos: 'top-0 left-2/3', translate: '-translate-x-1/2 -translate-y-1/2' },
          { pos: 'top-0 right-0', translate: 'translate-x-1/2 -translate-y-1/2' },
          { pos: 'bottom-0 left-0', translate: '-translate-x-1/2 translate-y-1/2' },
          { pos: 'bottom-0 left-1/3', translate: '-translate-x-1/2 translate-y-1/2' },
          { pos: 'bottom-0 left-2/3', translate: '-translate-x-1/2 translate-y-1/2' },
          { pos: 'bottom-0 right-0', translate: 'translate-x-1/2 translate-y-1/2' },
        ]"
        :key="i"
        :class="[
          'hidden sm:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10',
          marker.pos,
          marker.translate,
        ]"
      />
    </div>
  </section>

  <section class="relative bg-white dark:bg-black py-20 md:py-20 px-6 transition-colors duration-300">
    <div class="mx-auto max-w-6xl">
      <div
        class="relative grid grid-cols-1 lg:grid-cols-3 lg:grid-rows-2 border border-neutral-200 dark:border-neutral-800"
      >
        <!-- ============ Panel kiri ============ -->
        <div
          class="lg:row-span-2 border-b lg:border-b-0 lg:border-r border-neutral-200 dark:border-neutral-800 p-8 md:p-10 flex flex-col justify-center"
        >
          <span
            class="inline-flex w-fit items-center gap-1.5 rounded-full border border-dashed border-orange-400/60 px-3 py-1 text-xs font-medium text-orange-500"
          >
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="h-3.5 w-3.5">
              <path
                d="M12 2l1.6 5.6L19 9l-5.4 1.4L12 16l-1.6-5.6L5 9l5.4-1.4L12 2zM19 15l.8 2.7L22.5 18l-2.7.8L19 21.5l-.8-2.7-2.7-.8 2.7-.8.8-2.7z"
              />
            </svg>
            Agen
          </span>

          <h2 class="mt-5 text-2xl md:text-3xl font-semibold tracking-tight leading-tight text-neutral-900 dark:text-white">
            Agen untuk setiap kasus penggunaan
          </h2>

          <p class="mt-4 text-sm text-neutral-500 dark:text-neutral-400">
            Bangun dengan Agents SDK:
          </p>

          <a
            href="#"
            class="mt-6 inline-flex w-fit items-center rounded-full border border-neutral-300 dark:border-neutral-700 px-5 py-2.5 text-sm font-medium text-neutral-900 dark:text-neutral-100 hover:bg-neutral-900 hover:text-white dark:hover:bg-white dark:hover:text-black transition-colors"
          >
            Lihat dokumentasi
          </a>
        </div>

        <!-- ============ Asisten proaktif ============ -->
        <div class="lg:border-r lg:border-b border-b border-neutral-200 dark:border-neutral-800 p-8 md:p-10">
          <h3 class="text-sm md:text-base font-semibold text-neutral-900 dark:text-white">
            Asisten proaktif
          </h3>
          <p class="mt-2 text-sm leading-relaxed text-neutral-500 dark:text-neutral-400">
            Agen yang mengirim email terjadwal, memantau sistem, dan mengambil tindakan tanpa
            menunggu perintah pengguna.
          </p>
        </div>

        <!-- ============ Kolaborasi realtime ============ -->
        <div class="lg:border-b border-b border-neutral-200 dark:border-neutral-800 p-8 md:p-10">
          <h3 class="text-sm md:text-base font-semibold text-neutral-900 dark:text-white">
            Kolaborasi realtime
          </h3>
          <p class="mt-2 text-sm leading-relaxed text-neutral-500 dark:text-neutral-400">
            Chat multipemain, pengeditan kolaboratif, atau sesi agen bersama di mana beberapa
            pengguna berinteraksi secara bersamaan.
          </p>
        </div>

        <!-- ============ Pesan dan notifikasi ============ -->
        <div class="lg:col-span-2 p-8 md:p-10">
          <h3 class="text-sm md:text-base font-semibold text-neutral-900 dark:text-white">
            Pesan dan notifikasi
          </h3>
          <p class="mt-2 text-sm leading-relaxed text-neutral-500 dark:text-neutral-400">
            Integrasikan dengan Slack, Discord, email, atau platform pesan apa pun. Agen dapat
            menerima dan mengirim pesan secara proaktif.
          </p>
        </div>

        <!-- ============ Penanda sudut — grid ============ -->
        <!-- Baris atas -->
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:1] [grid-column-start:1] self-start justify-self-start -translate-x-1/2 -translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:1] [grid-column-start:1] self-start justify-self-end translate-x-1/2 -translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:1] [grid-column-start:3] self-start justify-self-end translate-x-1/2 -translate-y-1/2" />

        <!-- Baris tengah (batas antara baris 1 dan 2) -->
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:1] self-start justify-self-end translate-x-1/2 -translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:3] self-start justify-self-start -translate-x-1/2 -translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:3] self-start justify-self-end translate-x-1/2 -translate-y-1/2" />

        <!-- Baris bawah -->
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:1] self-end justify-self-start -translate-x-1/2 translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:1] self-end justify-self-end translate-x-1/2 translate-y-1/2" />
        <span class="hidden lg:block absolute h-2 w-2 border border-neutral-300 dark:border-neutral-700 bg-white dark:bg-black z-10 [grid-row-start:2] [grid-column-start:3] self-end justify-self-end translate-x-1/2 translate-y-1/2" />
      </div>
    </div>
  </section>
</template>

<style scoped>
section {
  font-feature-settings: "cv11", "ss01", "cv01";
}

@media (max-width: 768px) {
  section {
    padding-top: 5rem;
    padding-bottom: 5rem;
  }
}
</style>