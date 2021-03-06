<template>
  <main>
    <section id="home" class="mx-auto container grid grid-cols-12 pt-5 mb-20 items-center">
      <div class=" col-span-2 grid place-items-center md:col-span-1">
        <div class=" space-y-4">
          <a v-for="btn in socials" :key="btn.icon" class=" block text-primary" :href="btn.link" target="_blank"
            rel="noopener noreferrer">
            <i class='bx text-3xl' :class="btn.icon"></i>
          </a>
        </div>
      </div>
      <div class=" col-span-10 md:col-span-5 md:order-2">
        <svg class=" fill-primary" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
          <mask fill="" id="mask0" mask-type="alpha">
            <path
              d="M62.1,-57.5C77.1,-47,83.7,-23.5,83.6,-0.1C83.5,23.2,76.6,46.4,61.5,58.2C46.4,69.9,23.2,70.2,3.2,66.9C-16.7,63.7,-33.5,56.9,-47.5,45.2C-61.6,33.5,-72.9,16.7,-75.6,-2.7C-78.3,-22.2,-72.4,-44.4,-58.4,-54.9C-44.4,-65.4,-22.2,-64.3,0.7,-65C23.5,-65.6,47,-68.1,62.1,-57.5Z"
              transform="translate(100 100)" />
          </mask>
          <g mask="url(#mask0)">
            <path
              d="M62.1,-57.5C77.1,-47,83.7,-23.5,83.6,-0.1C83.5,23.2,76.6,46.4,61.5,58.2C46.4,69.9,23.2,70.2,3.2,66.9C-16.7,63.7,-33.5,56.9,-47.5,45.2C-61.6,33.5,-72.9,16.7,-75.6,-2.7C-78.3,-22.2,-72.4,-44.4,-58.4,-54.9C-44.4,-65.4,-22.2,-64.3,0.7,-65C23.5,-65.6,47,-68.1,62.1,-57.5Z"
              transform="translate(100 100)" />
            <image class=" w-36" x="30" y="30" xlink:href="../assets/backup/section2.png" />
          </g>
        </svg>
      </div>
      <div class=" col-start-2 col-span-10 md:col-span-5">
        <h1 class=" text-4xl font-bold leading-loose">Hi! I'am&nbsp;Chambers</h1>
        <p class=" text-gray-500 md:leading-loose mb-5">Frontend developer</p>
        <p class="text-gray-500 md:leading-relaxed mb-10">High Level experience in web development knowledge, producing
          quality work.</p>
        <a class="hover:opacity-80 transition bg-primary p-4 rounded-xl text-white" href="#contact">
          Contact Me <i class='bx bx-send'></i>
        </a>
      </div>
    </section>

    <section class="mb-20 py-10">
      <h2 id="about" class="lg:scroll-m-16 text-center text-2xl font-bold leading-loose">About me</h2>
      <p class="text-gray-500 text-center mb-10">My introduction</p>
      <div
        class=" max-w-5xl w-4/5 mx-auto space-y-10 md:space-x-10 flex items-center justify-center flex-col md:flex-row">
        <figure class="md:w-1/2">
          <img tg-name="hero-size" tg-to="1.7" tg-from=".3" style="transform: scale(min(var(--hero-size), 1));" class="rounded-2xl object-fill max-w-xs mx-auto" loading="lazy" src="../assets/hero.jpeg" alt="hero">
        </figure>
        <div class="md:w-1/2 space-y-10">
          <p class="text-gray-500 dark:text-gray-300">Web developer, with extensive knowledge and years of experience, working in web
            technologies and delivering quality work.</p>
          <ul class="w-full flex items-center justify-center">
            <li class=" text-center w-1/3" v-for="(item, i) in experience" :key="i">
              <p class=" text-2xl font-bold leading-relaxed">{{ item.number }}+</p>
              <p class=" text-gray-500 dark:text-gray-300">{{ item.content }}</p>
              <p class=" text-gray-500 dark:text-gray-300">{{ item.last }}</p>
            </li>
          </ul>
          <button class="hover:opacity-80 bg-primary p-4 rounded-xl text-white">
            Download CV <i class='bx bxs-contact'></i>
          </button>
        </div>
      </div>

    </section>
    <SkillsSection/>
    <section class="mb-20 py-10">
      <h2 id="services" class="lg:scroll-m-16 text-center text-2xl font-bold leading-loose">Services</h2>
      <p class="text-gray-500 text-center mb-10">What I offer</p>
      <ul class=" w-5/6 mx-auto max-w-3xl grid grid-cols-2 grid-rows-1 gap-6">
        <ServiceSection  v-for="item in services" :key="item.icon"
          :title="item.title"
          :icon="item.icon"
          :description="item.description"
        />
      </ul>
    </section>
    <section class="mb-20 py-10">
      <h2 id="portfolio" class="lg:scroll-m-16 text-center text-2xl font-bold leading-loose">Portfolio</h2>
      <p class="text-gray-500 text-center mb-10">Most recent work</p>
      <div class="mx-auto relative max-w-4xl px-10">
        <div v-for="item in portfolio" :key="item.link" class="p-5 lg:pb-20 lg:flex lg:justify-between items-center group">
          <a class=" group-even:order-1 relative group-even:md:bottom-10 group-even:md:right-10 group-odd:md:top-10 group-odd:md:left-10 lg:w-5/12" :href="item.link">
            <img class="object-cover shadow-lg rounded-lg group-even:md:shadow-[.5rem_.5rem_.9rem_#a3a3a3] group-odd:md:shadow-[-.5rem_.5rem_.9rem_#a3a3a3]" :src="item.img" alt="image1">
          </a>
          <div class=" lg:w-6/12 p-4">
            <h3 class=" text-primary leading-loose font-bold text-2xl">{{ item.title }}</h3>
            <p class=" text-gray-500 mb-5">{{ item.subtitle }}</p>
            <p>
              <a :href="item.link" target="_blank" rel="noopener noreferrer" class="hover:opacity-80 transition bg-primary py-2 px-3 rounded-xl text-white inline-block leading-8 mx-2">
                Demo
              </a>
              <a :href="item.github" target="_blank" rel="noopener noreferrer" class="hover:opacity-80 transition bg-primary py-2 px-3 rounded-xl text-white inline-block leading-8 mx-2">
                <i class='bx bxl-github text-2xl align-middle'></i>
              </a>
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="mb-20 py-10 lg:scroll-m-16">
      <div class=" max-w-4xl w-5/6 rounded-3xl mx-auto bg-gradient-to-r from-primary to-primary/70 p-10 lg:flex dark:bg-black dark:bg-none  transition">
        <div class=" lg:w-4/6 mb-5 lg:mb-0">
          <h2 class="text-2xl font-bold leading-loose tracking-tighter text-white">You have a new project</h2>
          <p class="text-white mb-10 tracking-tighter">Contact me now and get a 10% discount on your new project</p>
          <a class="p-4 rounded-xl text-primary bg-white" href="https://forms.gle/foySUptVKdx9hjFS9" target="_blank" rel="noopener noreferrer">
            Contact Me <i class='bx bx-send'></i>
          </a>
        </div>
        <div class="lg:w-2/6 bg-[url('/s4.png')] py-40 lg:p-30  lg:ml-0 -lg:mt-10 -mb-10 -mx-10 bg-no-repeat bg-contain bg-bottom" ></div>
      </div>
    </section>
    <ContactSection />
  </main>
</template>

<script setup>
import ServiceSection from '../components/serviceSection.vue'
import SkillsSection from '../components/skillsSection.vue'
import ContactSection from '../components/contactSection.vue'

const portfolio = [
  {
    link: 'https://shopee.nosegates.com/',
    title: '蝦英雄',
    subtitle: '本專案提供使用者貼入蝦皮網址後產生出蝦皮專用短網址,自行撰寫NodeJS後端串接蝦皮官方提供的GraphQL API,前端使用Vue框架撰寫',
    github: 'https://github.com/connectshark/shopee-short-link',
    img: '/portfolio/img1.png'
  },
  {
    link: 'https://line.me/R/ti/p/@848gsxak',
    title: 'line機器人-超極巨皮卡丘',
    subtitle: '藉由串接line官方提供SDK的方式應用製作line機器人,主要功能與蝦英雄一樣可以縮短任意蝦皮網址(串接相同後端程式),添加基礎機器人回應訊息,傳入貼圖回應貼圖,傳入"/how"回應基礎使用方式,傳入蝦皮連結回應縮短後蝦皮連結',
    github: 'https://github.com/connectshark/line-bot-pika',
    img: '/portfolio/bot-pika.png'
  },
  {
    link: 'https://express-with-linepay.onrender.com/',
    title: 'linePay付款技術串接',
    subtitle: '使用express後端框架串接測試linePay付款流程全記錄,為全後端技術專案,專案內扣款為測試環境不會扣真實賬戶,初次開啟需稍等機器啟動',
    github: 'https://github.com/connectshark/express-with-linepay',
    img: '/portfolio/express-linepay.png'
  },
  {
    link: 'https://connectshark.github.io/command-palette-tailwindcss/#/',
    title: '台灣縣市搜尋器',
    subtitle: '本專案專注於客製搜尋器,於頁面中使用按鍵 ctrl or control + "k"即可開啟面板搜尋器,輸入英文中文皆可進入搜尋',
    github: 'https://github.com/connectshark/command-palette-tailwindcss',
    img: '/portfolio/search.png'
  }
]

const services = [
  {
    icon: 'bx-code-alt',
    title: 'Frontend Developer',
    description: ['Web page development', 'Build responsive sites', 'I develop the user interface']
  },
  {
    icon: 'bx-data',
    title: 'Full-Stack Developer',
    description: ['Web API development', 'OAuth 2.0 login', 'JWT access token']
  }
]

const experience = [
  {
    number: '04',
    content: 'Years',
    last: 'experience'
  },
  {
    number: '20',
    content: 'Completed',
    last: 'projects'
  },
  {
    number: '03',
    content: 'Companies',
    last: 'worked'
  }
]
const socials = [
  {
    link: 'https://github.com/connectshark',
    icon: 'bxl-github'
  },
  {
    link: 'https://www.linkedin.com/in/%E6%81%A9%E9%A8%B0-%E8%91%89-935867189/',
    icon: 'bxl-linkedin'
  }
]
</script>