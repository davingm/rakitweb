<script setup lang="ts">
import gsap from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const heroSection = ref<HTMLElement | null>(null)
const teamGrid = ref<HTMLElement | null>(null)
let heroCtx: gsap.Context | null = null

useSeoMeta({
  title: 'Tim Kami - RakitWeb',
  description: 'Kenali tim di balik RakitWeb — developer, designer, dan engineer yang membangun solusi digital terbaik untuk bisnis Anda.',
  ogTitle: 'Tim Kami - RakitWeb',
  ogDescription: 'Kenali tim di balik RakitWeb — developer, designer, dan engineer yang membangun solusi digital terbaik untuk bisnis Anda.',
  ogImage: '/rakitweb.jpeg'
})

const team = [
  {
    name: 'Kin You ( davingm )',
    role: 'Backend Enginner',
    experience: 'Never Say Never',
    avatar: 'https://avatars.githubusercontent.com/u/228851591?v=4',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Rakit+Dev&background=3b82f6&color=fff&size=200&bold=true',
    bio: 'Backend Engineer berpengalaman dalam membangun arsitektur sistem yang kokoh, efisien, dan berskala besar. Memiliki keahlian mendalam dalam pengembangan API, optimasi database, serta pengelolaan layanan berbasis cloud.',
    stacks: [
      { name: 'TypeScript', skill: 'ts' },
      { name: 'nestjs', skill: 'nestjs' },
      { name: 'rust', skill: 'rust' },
      { name: 'cloudfalre', skill: 'cloudflare' },
      { name: 'postgresql', skill: 'postgresql' }
      
    ]
  },
  {
    name: 'Chandra',
    role: 'Founder of RakitWeb',
    experience: '',
    avatar: '/blog/kucing.jpeg',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Web+Engineer&background=10b981&color=fff&size=200&bold=true',
    bio: 'Mengembangkan sistem backend dan frontend dengan fokus pada performa, stabilitas, dan pengalaman pengguna yang optimal.',
    stacks: [
      { name: 'dart', skill: 'dart' },
      { name: 'flutter', skill: 'flutter' },
      { name: 'TypeScript', skill: 'ts' },
    ]
  },
  {
    name: 'Silo Kusuma',
    role: 'Frontend Developer',
    experience: '',
    avatar: '/team/elaina.jpg',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Backend+Dev&background=8b5cf6&color=fff&size=200&bold=true',
    bio: 'Merancang arsitektur backend yang scalable dan reliable. Ahli dalam deployment dan optimasi server.',
    stacks: [
      { name: 'react', skill: 'react' },
      { name: 'Next.js', skill: 'nextjs' },
      { name: 'java', skill: 'java' },
      { name: 'TypeScript', skill: 'ts' },
      { name: 'Kotlin', skill: 'kotlin' }
    ]
  },
  {
    name: 'Agus',
    role: 'Cloud Engineer',
    experience: '2+ tahun pengalaman',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSIrZHGwxcayywMAO65J8sT9BrGLLfsnhPOPj6wzBN0PQ&s=10',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Rizal&background=ef4444&color=fff&size=200&bold=true',
    bio: 'Cloud Engineer yang berdedikasi untuk membantu perusahaan membangun infrastruktur digital yang aman, efisien, dan mudah dikembangkan. Berpengalaman dalam merancang arsitektur AWS/Azure/GCP yang berhasil memangkas biaya operasional hingga 80% sekaligus meningkatkan performa sistem..',
    stacks: [
      { name: 'aws', skill: 'aws' },
      { name: 'cloudflare', skill: 'cloudflare' },
      { name: 'docker', skill: 'docker' },
      { name: 'azure', skill: 'azure' },
      { name: 'ubuntu', skill: 'ubuntu' },

    ]
  },
  {
    name: 'Van You ( Wahyu )',
    role: 'Account Executive',
    experience: '2+ tahun pengalaman',
    avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQdVMnw-rehqaemLlChalcSTdnWQdUIAnlrcnov7D3umA&s=10',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Rizal&background=ef4444&color=fff&size=200&bold=true',
    bio: 'Menghubungkan tantangan bisnis klien dengan solusi teknologi yang tepat adalah keahlian saya. Sebagai seorang Account Executive, saya fokus mendengarkan kebutuhan mendasar dari calon mitra untuk memberikan nilai nyata (ROI) bagi bisnis mereka..',
    stacks: [
      { name: 'ASP.net', skill: 'dotnet' }
    ]
  }, 
  {
    name: 'Tokita ( Nafis )',
    role: 'UI/UX Designer',
    experience: '2+ tahun pengalaman',
    avatar: 'https://github.com/tokitakun.png',
    fallbackAvatar: 'https://ui-avatars.com/api/?name=Rizal&background=ef4444&color=fff&size=200&bold=true',
    bio: 'berfokus pada menjembatani kebutuhan pengguna dengan tujuan bisnis. Berpengalaman dalam mengubah masalah kompleks menjadi antarmuka digital yang intuitif, estetis, dan fungsional. Memiliki keahlian kuat dalam riset pengguna, pembuatan wireframe, hingga desain visual yang interaktif guna meningkatkan kepuasan dan retensi pengguna',
    stacks: [
      { name: 'astro', skill: 'astro' },
      { name: 'react', skill: 'react' },
      { name: 'nextjs', skill: 'nextjs' },
      { name: 'figma', skill: 'figma' },
      { name: 'Adobe XD', skill: 'adobe-xd' },
      { name: 'Photoshop', skill: 'photoshop' }
    ]
  },
]

const allStacks = [
  { name: 'TypeScript', skill: 'ts' },
  { name: 'JavaScript', skill: 'js' },
  { name: 'PHP', skill: 'php' },
  { name: 'Laravel', skill: 'laravel' },
  { name: 'Angular', skill: 'angular' },
  { name: 'Nuxt.js', skill: 'nuxt' },
  { name: 'Next.js', skill: 'nextjs' },
  { name: 'NestJS', skill: 'nestjs' },
  { name: 'Java', skill: 'java' },
  { name: 'Spring', skill: 'spring' },
  { name: 'Flutter', skill: 'flutter' },
  { name: 'React Native', skill: 'react' },
  { name: 'ASP.NET', skill: 'dotnet' },
  { name: 'Python', skill: 'python' }
]

const imgErrors = ref<Record<number, boolean>>({})
const onImgError = (idx: number) => { imgErrors.value[idx] = true }

onMounted(() => {
  heroCtx = gsap.context(() => {
    const badge = heroSection.value?.querySelector<HTMLElement>('.team-hero-badge')
    const headline = heroSection.value?.querySelectorAll<HTMLElement>('.team-hero-word')
    const copy = heroSection.value?.querySelector<HTMLElement>('.team-hero-copy')
    const orbs = heroSection.value?.querySelectorAll<HTMLElement>('.team-hero-orb')

    if (badge) {
      gsap.fromTo(badge,
        { opacity: 0, y: 20, filter: 'blur(10px)' },
        { opacity: 1, y: 0, filter: 'blur(0px)', duration: 0.7, ease: 'power3.out' }
      )
    }

    if (headline && headline.length) {
      gsap.fromTo(headline,
        { opacity: 0, y: 42, x: 18, rotateY: -18, filter: 'blur(10px)' },
        { opacity: 1, y: 0, x: 0, rotateY: 0, filter: 'blur(0px)', duration: 1, stagger: 0.08, ease: 'power3.out' }
      )
    }

    if (copy) {
      gsap.fromTo(copy,
        { opacity: 0, y: 22, filter: 'blur(8px)' },
        { opacity: 1, y: 0, filter: 'blur(0px)', duration: 0.9, delay: 0.18, ease: 'power3.out' }
      )
    }

    if (orbs && orbs.length) {
      gsap.to(orbs, {
        x: 'random(-30, 30)',
        y: 'random(-26, 26)',
        scale: 'random(0.9, 1.15)',
        duration: 'random(8, 12)',
        ease: 'sine.inOut',
        repeat: -1,
        yoyo: true,
        stagger: 1.2,
      })
    }

  }, heroSection.value || undefined)
})

onUnmounted(() => {
  heroCtx?.revert()
})
</script>

<template>
  <div class="min-h-screen bg-white text-zinc-900 antialiased dark:bg-black dark:text-zinc-50">

    <!-- HERO -->
    <section ref="heroSection" class="relative pt-32 pb-20 px-6 overflow-hidden">
      <div class="absolute inset-0 pointer-events-none">
        <div class="team-hero-orb absolute -top-10 left-10 h-56 w-56 rounded-full bg-zinc-200/70 blur-3xl dark:bg-zinc-700/40" />
        <div class="team-hero-orb absolute right-12 top-16 h-72 w-72 rounded-full bg-zinc-100/80 blur-3xl dark:bg-zinc-800/40" />
        <div class="team-hero-orb absolute bottom-0 left-1/3 h-60 w-60 rounded-full bg-zinc-300/40 blur-3xl dark:bg-zinc-700/30" />
      </div>

      <UContainer class="relative z-10">
        <div class="mx-auto max-w-3xl text-center">
          <p class="team-hero-badge font-mono text-xs text-zinc-400 dark:text-zinc-500 uppercase tracking-wider mb-6">Tim Kami</p>
          <h1 class="text-4xl md:text-6xl font-normal tracking-tighter text-black dark:text-white leading-[1.05] mb-6">
            <span class="team-hero-word block">Orang-orang di Balik</span>
            <span class="team-hero-word block">RakitWeb.</span>
          </h1>
          <p class="team-hero-copy mx-auto text-base text-zinc-500 dark:text-zinc-400 leading-relaxed max-w-xl">
            Kami adalah tim kecil yang bergerak cepat — developer, engineer, dan builder yang fokus membangun produk digital berkualitas tinggi.
          </p>
        </div>
      </UContainer>
    </section>

    <!-- DIVIDER -->
    <div class="border-t border-gray-100 dark:border-white/5" />

    <!-- TEAM GRID -->
    <section class="py-20 px-6">
      <UContainer>
        <div ref="teamGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-px bg-zinc-200 dark:bg-zinc-800 border border-zinc-200 dark:border-zinc-800 overflow-hidden">
          <div
            v-for="(member, idx) in team"
            :key="member.name"
            class="team-card bg-white dark:bg-black p-8 flex flex-col gap-6 hover:bg-zinc-50 dark:hover:bg-zinc-900/40 transition-colors duration-300"
          >
            <!-- Avatar + Info -->
            <div class="flex items-start gap-4">
              <div class="relative shrink-0">
                <img
                  :src="imgErrors[idx] ? member.fallbackAvatar : member.avatar"
                  :alt="member.name"
                  class="w-14 h-14 rounded-none object-cover bg-zinc-100 dark:bg-zinc-900"
                  @error="onImgError(idx)"
                />
              </div>
              <div class="flex-1 min-w-0">
                <h3 class="text-sm font-medium text-black dark:text-white truncate">{{ member.name }}</h3>
                <p class="text-xs text-zinc-500 dark:text-zinc-400 mt-0.5">{{ member.role }}</p>
                <p class="font-mono text-[10px] text-zinc-400 dark:text-zinc-500 uppercase tracking-wider mt-1">{{ member.experience }}</p>
              </div>
            </div>

            <!-- Bio -->
            <p class="text-xs text-zinc-500 dark:text-zinc-400 leading-relaxed">
              {{ member.bio }}
            </p>

            <!-- Divider -->
            <div class="border-t border-zinc-100 dark:border-zinc-800" />

            <!-- Stack -->
            <div class="space-y-3">
              <p class="font-mono text-[10px] text-zinc-400 dark:text-zinc-500 uppercase tracking-wider">Tech Stack</p>
              <div class="flex flex-wrap gap-2">
                <div
                  v-for="stack in member.stacks"
                  :key="stack.name"
                  class="group flex items-center gap-1.5 px-2.5 py-1.5 border border-zinc-200 dark:border-zinc-800 bg-zinc-50 dark:bg-zinc-900/40 hover:border-zinc-400 dark:hover:border-zinc-600 transition-all duration-200 cursor-default"
                  :title="stack.name"
                >
                  <img :src="`https://skillicons.dev/icons?i=${stack.skill}`" :alt="stack.name" class="w-3.5 h-3.5 shrink-0" />
                  <span class="text-[10px] font-medium text-zinc-600 dark:text-zinc-400 group-hover:text-zinc-900 dark:group-hover:text-white transition-colors">{{ stack.name }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- DIVIDER -->
    <div class="border-t border-gray-100 dark:border-white/5" />

    <!-- ALL STACKS SECTION -->
    <section class="py-20 px-6">
      <UContainer>
        <div class="max-w-4xl mx-auto">
          <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-12">
            <div>
              <p class="font-mono text-xs text-zinc-400 dark:text-zinc-500 uppercase tracking-wider mb-3">Teknologi</p>
              <h2 class="text-2xl md:text-3xl font-normal tracking-tighter text-black dark:text-white">
                Stack yang kami kuasai.
              </h2>
            </div>
            <p class="text-xs text-zinc-400 dark:text-zinc-500 max-w-xs leading-relaxed">
              Dari frontend hingga backend, mobile hingga cloud — kami memilih teknologi yang tepat untuk setiap kebutuhan.
            </p>
          </div>

          <div class="grid grid-cols-4 sm:grid-cols-7 gap-3">
            <div
              v-for="stack in allStacks"
              :key="stack.name"
              class="group flex flex-col items-center gap-2 p-3 border border-zinc-200 dark:border-zinc-800 bg-zinc-50 dark:bg-zinc-900/40 hover:border-zinc-400 dark:hover:border-zinc-600 hover:bg-white dark:hover:bg-zinc-900/60 transition-all duration-200 cursor-default"
              :title="stack.name"
            >
              <img :src="`https://skillicons.dev/icons?i=${stack.skill}`" :alt="stack.name" class="w-6 h-6 shrink-0 transition-transform duration-200 group-hover:scale-110" />
              <span class="text-[9px] font-medium text-zinc-500 dark:text-zinc-500 group-hover:text-zinc-700 dark:group-hover:text-zinc-300 transition-colors text-center leading-tight">{{ stack.name }}</span>
            </div>
          </div>
        </div>
      </UContainer>
    </section>

    <!-- CTA -->
    <section class="py-20 px-6 border-t border-zinc-200 dark:border-zinc-800">
      <UContainer>
        <div class="max-w-xl">
          <h2 class="text-2xl md:text-3xl font-normal tracking-tighter text-black dark:text-white mb-4">
            Tertarik bekerja sama?
          </h2>
          <p class="text-sm text-zinc-500 dark:text-zinc-400 mb-8 leading-relaxed">
            Kami selalu terbuka untuk proyek baru dan kolaborasi menarik. Hubungi kami dan ceritakan kebutuhan Anda.
          </p>
          <div class="flex items-center gap-4">
            <NuxtLink
              to="https://wa.me/6283160325595"
              target="_blank"
              class="inline-flex items-center gap-2 px-5 py-2.5 bg-zinc-950 dark:bg-zinc-50 text-white dark:text-zinc-950 text-sm font-medium rounded-md hover:opacity-90 transition-opacity"
            >
              <UIcon name="i-simple-icons-whatsapp" class="w-4 h-4" />
              Hubungi Kami
            </NuxtLink>
            <NuxtLink
              to="/pricing"
              class="inline-flex items-center gap-2 px-5 py-2.5 border border-zinc-200 dark:border-zinc-800 text-zinc-700 dark:text-zinc-300 text-sm font-medium rounded-md hover:border-zinc-400 dark:hover:border-zinc-600 transition-colors"
            >
              Lihat Harga
              <UIcon name="i-lucide-arrow-right" class="w-3.5 h-3.5" />
            </NuxtLink>
          </div>
        </div>
      </UContainer>
    </section>

  </div>
</template>
