<!-- eslint-disable vue/require-v-for-key -->
<script>
import emailjs from 'emailjs-com'
import { register } from 'swiper/element/bundle'
  const currentLang = ref("en");

 const translations = {
  en: {
    nav: {
      home: "Home",
      story: "Our Story",
      bustard: "Meet the Bustards",
      work: "Our Work",
      center: "Our Center",
    },
    hero: {
      slogan: "Protecting the Houbara Bustard for Future Generations",
    },
    story: {
      title: "Our Story",
      who: "Who We Are",
      text: `Under the leadership and vision of His Highness Sheikh Tamim bin Hamad Al Thani, 
      the Houbara Foundation was established to preserve one of the most iconic desert species. 
      This initiative reflects a deep commitment to biodiversity, sustainability, and future generations.`,
    },
    bustard: {
      title: "Meet the Bustards",
      text: `The bustard birds make up the Otididae family and are large-bodied birds with long legs and slender necks. 
      Members of the bustard family include the great bustard, Arabian bustard, great Indian bustard, lesser florican, 
      Bengal florican, kori bustard, black-bellied bustard, Australian bustard, and the houbara bustard.`,
    },
    work: {
      title: "Our Work",
      block1: {
        title: "Conserving Bustards",
        text: "Protecting the natural habitats of the Houbara Bustard and ensuring long-term sustainability through research and conservation programs."
      },
      block2: {
        title: "Breeding And Release",
        text: "Our breeding programs focus on increasing population numbers and safely reintroducing birds into their native ecosystems."
      },
      block3: {
        title: "Nest Protection",
        text: "Safeguarding nests from predators and environmental challenges to ensure the survival of new generations."
      },
      block4: {
        title: "Incubation",
        text: "Scientific incubation techniques improve hatching success rates and strengthen our conservation efforts."
      }
    },
    center: {
      title: "Our Center",
      subtitle: "International Foundation for Ecological Research (IFER)",
      text: `At our center, the International Foundation for Ecological Research (IFER) leads innovative projects to protect biodiversity and ecosystems. 
      One of our key missions is the conservation of the houbara bustard. Through breeding programs, habitat protection, and community engagement, 
      we work to restore wild populations and ensure this emblematic bird thrives for generations to come.`
    },
    footer: "2025 IFER All Rights Reserved",
  },

  ar: {
    nav: {
      home: "الرئيسية",
      story: "قصتنا",
      bustard: "تعرف على الحباري",
      work: "عملنا",
      center: "مركزنا",
    },
    hero: {
      slogan: "حماية طائر الحبارى من أجل الأجيال القادمة",
    },
    story: {
      title: "قصتنا",
      who: "من نحن",
      text: `تحت القيادة والرؤية السامية لصاحب السمو الشيخ تميم بن حمد آل ثاني، 
      تأسست مؤسسة الحبارى للحفاظ على واحد من أكثر الطيور الصحراوية رمزية. 
      هذه المبادرة تجسد التزاماً عميقاً بالتنوع البيولوجي والاستدامة والأجيال القادمة.`,
    },
    bustard: {
      title: "تعرف على طيور الحباري",
      text: `تنتمي طيور الحباري إلى عائلة "الـ Otididae"، وهي طيور كبيرة الحجم ذات أرجل طويلة وأعناق رشيقة. 
      وتشمل هذه العائلة الحباري الكبير، الحبارى العربي، الحبارى الهندي الكبير، الفلوركان الأصغر، الفلوركان البنغالي، 
      الكوري، ذو البطن السوداء، الحبارى الأسترالي، والحبارى العربي (الحبارى الآسيوي).`,
    },
    work: {
      title: "عملنا",
      block1: {
        title: "حماية طيور الحبارى",
        text: "حماية المواطن الطبيعية لطائر الحبارى وضمان الاستدامة طويلة المدى من خلال برامج البحث والحفاظ."
      },
      block2: {
        title: "التربية والإطلاق",
        text: "تركز برامج التربية لدينا على زيادة أعداد الطيور وإعادة إطلاقها بأمان في أنظمتها البيئية الأصلية."
      },
      block3: {
        title: "حماية الأعشاش",
        text: "حماية الأعشاش من الحيوانات المفترسة والتحديات البيئية لضمان بقاء الأجيال الجديدة."
      },
      block4: {
        title: "الحضانة",
        text: "تعمل تقنيات الحضانة العلمية على تحسين معدلات الفقس وتعزيز جهودنا في الحفاظ على الطيور."
      }
    },
    center: {
      title: "مركزنا",
      subtitle: "المؤسسة الدولية للأبحاث البيئية (IFER)",
      text: `في مركزنا، تقود المؤسسة الدولية للأبحاث البيئية (IFER) مشاريع مبتكرة لحماية التنوع البيولوجي والأنظمة البيئية. 
      ومن بين مهامنا الأساسية الحفاظ على طائر الحبارى. من خلال برامج التربية، حماية المواطن، والمشاركة المجتمعية، 
      نعمل على استعادة أعداد الطيور في البرية وضمان استمرار هذا الطائر الرمزي عبر الأجيال القادمة.`
    },
    footer: "2025 IFER جميع الحقوق محفوظة",
  }
};

    function setLanguage(lang) {
      currentLang.value = lang;
      document.documentElement.setAttribute("dir", lang === "ar" ? "rtl" : "ltr");
      if (lang === "ar") {
        document.body.classList.add("arabic");
      } else {
        document.body.classList.remove("arabic");
      }
    }
register()
import Cursor from './components/AppCursor.vue'
import Loader from './components/AppLoading.vue'
import ScrollToTop from './components/ScrollToTop.vue'
import SwitchTheme from './components/SwitchTheme.vue'
import FacebookIcon from './components/icons/FacebookIcon.vue'
import LinkedinIcon from './components/icons/LinkedincIcon.vue'
import GithubIcon from './components/icons/GithubIcon.vue'
import EmailIcon from './components/icons/EmailIcon.vue'
import ArrowRightIcon from './components/icons/ArrowRightIcon.vue'
import BootstrapIcon from './components/icons/skills/BootstrapIcon.vue'
import CssIcon from './components/icons/skills/CssIcon.vue'
import HtmlIcon from './components/icons/skills/HtmlIcon.vue'
import JiraIcon from './components/icons/skills/JiraIcon.vue'
import JsIcon from './components/icons/skills/JsIcon.vue'
import TailwindcssIcon from './components/icons/skills/TailwindcssIcon.vue'
import UxIcon from './components/icons/skills/UxIcon.vue'
import VueIcon from './components/icons/skills/VueIcon.vue'
import StarIcon from './components/icons/StarIcon.vue'
// import CopyrightIcon from './components/icons/CopyrightIcon.vue'
import MenuIcon from './components/icons/MenuIcon.vue'
import LogoIcon from './components/icons/LogoIcon.vue'
  export default {
  name: 'App',
  components: {
    Cursor,
    Loader,
    ScrollToTop,
    SwitchTheme,
    FacebookIcon,
    LinkedinIcon,
    GithubIcon,
    EmailIcon,
    ArrowRightIcon,
    BootstrapIcon,
    CssIcon,
    HtmlIcon,
    JiraIcon,
    JsIcon,
    TailwindcssIcon,
    UxIcon,
    VueIcon,
    StarIcon,
    MenuIcon,
    LogoIcon
  },
  data() {
  
  return {
      experiences: [
        {
          period: '11/24 - Present',
          company: 'Neven Eyewear',
          role: 'Front-End Engineer',
          link: 'https://neveneyewear.com/'
        },
        {
          period: '04/21 - 11/24',
          company: 'Protect',
          role: 'Front-End Engineer',
          link: 'https://protect.inc'
        },
        {
          period: '04/21 - 11/24',
          company: 'Le ventures',
          role: 'Front-End Engineer',
          link: 'https://leventures.com'
        },
        {
          period: '08/18 - 04/21',
          company: '[ NEXTMEDIA, YOUCAN, COD NETWEORK ]',
          role: 'Front-End Engineer',
          link: 'https://youcan.shop/en'
        },
        {
          period: '03/17 - 08/18',
          company: 'Webdevia',
          role: 'Front-End Developer',
          link: 'https://themeforest.net/user/mymoun/portfolio'
        }
      ],
      skills: [
          {
            title: 'VueJs',
            icon: 'VueIcon',
            progress: 95
          },
          {
            title: 'Ux Design',
            icon: 'UxIcon',
            progress: 95
          },
          {
            title: 'Javascript',
            icon: 'JsIcon',
            progress: 95
          },
          {
            title: 'TailwindCss',
            icon: 'TailwindcssIcon',
            progress: 90
          },
          {
            title: 'HTML5',
            icon: 'HtmlIcon',
            progress: 100
          },
          {
            title: 'CSS3',
            icon: 'CssIcon',
            progress: 100
          },
          {
            title: 'Bootstrap',
            icon: 'BootstrapIcon',
            progress: 95
          },
          {
            title: 'Jira',
            icon: 'JiraIcon',
            progress: 90
          }
        ],
      services: [
        {
          letter: 'W',
          title: 'Web Development',
          description: 'Visual elements and interactive features of your website. Translate design mockups and wireframes into actual code using HTML, CSS, and JavaScript.'
        },
        {
          letter: 'R',
          title: 'Responsive Design',
          description: 'Ensuring that your website look and function well on different devices and screen sizes. Use techniques like media queries and flexible layouts to achieve responsive design.'
        },
        {
          letter: 'U',
          title: 'User Experience',
          description: 'Collaborate with UX designers to create a seamless and intuitive user experience. Implement interactive elements, animations, and transitions to enhance the user journey.'
        },
        {
          letter: 'C',
          title: 'Cross-Browser Compatibility',
          description: 'Ensure that your websites work consistently across different web browsers, addressing any compatibility issues that may arise.'
        },
        {
          letter: 'P',
          title: 'Performance Optimization',
          description: 'Optimizing the performance of your website to deliver a fast and smooth user experience. Optimize code, images, and assets to improve loading times and overall performance.'
        },
        {
          letter: 'F',
          title: 'Front-End Frameworks',
          description: 'Work with frameworks like React, and Vue.js to streamline development, manage state, and build interactive user interfaces.'
        },
        {
          letter: 'I',
          title: 'Integration With Back End',
          description: 'Work closely with back-end developers to integrate front-end code with back-end systems, APIs, and databases.'
        },
        {
          letter: 'T',
          title: 'Testing And Debugging',
          description: 'Use browser developer tools and testing frameworks to identify and resolve issues.'
        }
      ],
      projects: [
        {
          image: 'bio.webp',
          skills:['Shopify'],
          name:'BioPro',
          link: 'https://5rnifb-x6.myshopify.com/'
        },
        {
          image: 'protect.webp',
          skills: ['VueJs', 'TailwindCss'],
          name: 'Protect',
          link: 'https://protect.inc'
        },
        {
          image: 'lapermanence.webp',
          skills:['Bootstrap 4', 'HTML5-CSS3-Javascript'],
          name:'La permanence',
          link: 'https://la-permanence.com'
        },
        {
          image: 'codnetwork.webp',
          skills:['Bootstrap 4', 'HTML5-CSS3-Javascript'],
          name:'COD Network',
          link: 'https://cod.network/'
        },
        {
          image: 'apocalypsecoffee.webp',
          skills:['Shopify'],
          name:'Apocalypse Coffee',
          link: 'https://apocalypsecoffee.com/'
        },
        {
          image: 'goodshirts.webp',
          skills:['Shopify'],
          name:'GoodShirts',
          link: 'https://thegoodshirts.com/'
        },
        {
          image: 'neven.webp',
          skills:['Shopify'],
          name:'Neven Eyewear',
          link: 'https://neveneyewear.com/'
        },
        {
          image: 'freestyle.webp',
          skills:['Shopify'],
          name:'Freestyle',
          link: 'https://www.freestyleusa.com/'
        },
        {
          image: 'inkedshop.webp',
          skills:['shopify'],
          name:'InkedShop',
          link: 'https://inkedshop.com/'
        }
      ],
      testimonials: [
        {
          author: {
            name: 'Mohamed El Ghaissani',
            title: 'CEO & Founder, YouCan Inc.',
            image: 'elghissani-mohamed.webp'
          },
          quote: "I had the pleasure of working with Tarik as a Front-End Developer, and I can confidently say he is an exceptional asset to any development team. Throughout his time with us, Tarik consistently demonstrated a deep understanding of modern web technologies, particularly Vue.js, Tailwind CSS, and responsive design principles.What sets Tarik apart is not only his technical skills but also his dedication to delivering high-quality work on time. He approaches each project with creativity, problem-solving ability, and attention to detail, ensuring that the final product is polished and user-friendly. His collaborative nature made him a great team player, always open to feedback and eager to contribute new ideas.Tarik's passion for learning and staying updated with the latest trends in front-end development makes him stand out as a developer. I highly recommend him for any role that requires a skilled, motivated, and innovative Front-End Developer.",
          reviews: 5
        },
        {
          author: {
            name: 'Zouhir Bahij',
            title: 'CEO & Founder, YouCan Inc.',
            image: 'zouhir-bahij.webp'
          },
          quote: "Crafting captivating user experiences through code is not just a job for Tarik, it's a passion. With an expert command over front-end technologies, Tarik brings life to designs and transforms ideas into interactive digital realities. Creating seamless journeys for users. As a Front-End Engineer, Tarik illuminates the path where creativity and technology converge.",
          reviews: 5
        },
        // {
        //   author: {
        //     name: 'Khoi Le',
        //     title: 'CEO & Founder, Protect Inc.',
        //     image: 'khoi-le.webp'
        //   },
        //   quote: "We've had the pleasure of working with Tarik, and he's truly transformed our digital presence. his coding skills bring our designs to life, resulting in beautiful and user-friendly websites. Tarik is reliable, efficient, and pays attention to detail, ensuring our projects are completed to perfection. his creative problem-solving abilities have been invaluable to our team.",
        //   reviews: 5
        // },
        {
          author: {
            name: 'Anass Ezzouine',
            title: 'CEO & Founder, Tekency.',
            image: 'anas-ezzouine.webp'
          },
          quote: "Tarik is a person who possesses all the skills needed to manage a team and be productive during intense crunch periods. Furthermore, he has a unique ability to keep the team organized and on schedule. Besides, Tarik also supported and helped us to reach our full potential, and he never hesitated to lend a helping hand.",
          reviews: 5
        },
        {
          author: {
            name: 'Mohamed El-Ghorfi',
            title: 'CEO & Founder, Tekency.',
            image: 'mohamed-el-ghourfi.webp'
          },
          quote: "Tarik is an essential asset to any development team. During my collaboration with him, I consistently marveled at his strong work ethic and unwavering determination to complete any assigned task. Whether it was debugging functions in templates, constructing intricate sales systems for rapidly expanding clients, or providing comprehensive guidance to newer team members finding their way in the industry. Tarik has repeatedly demonstrated his readiness to take on challenges. I am genuinely honored to have had the opportunity to work alongside Tarik, and without reservation, I affirm that he deserves every chance to progress and thrive in the field.",
          reviews: 5
        }
      ],
      form: {
        to_name: 'Tarik Bouich',
        name: '',
        from_name: '',
        subject: '',
        message: ''
      },   
      sended: false,
      sending: false,
      emailResponse: {
        status: false,
        message: '',
        type: 'success'
      },
      isMenuCollapsed: false
    }
    
  },
  mounted() {
  },
  methods: {
    scrollToSection(sectionId) {
      const targetSection = document.querySelector(sectionId)
      window.scrollTo({
        top: sectionId !== '#home' ? targetSection.offsetTop - 80 : targetSection.offsetTop,
        behavior: 'smooth'
      })
      this.isMenuCollapsed = false
    },
    scrollToTop () {
      window.scroll({
        top: 0,
        behavior: 'smooth'
      })
    },
  }
};
</script>

<template>
<div>
  <Cursor />
    <Loader :class="{ 'slide-out': !loading }" />
    <ScrollToTop />
    <!-- <SwitchTheme /> -->
  
  <main>
    <header
        class="sticky w-full top-0 left-0 py-1 md:border-b md:border-dark-75 dark:md:border-dark-75 md:border-opacity-50 dark:md:border-opacity-10 z-50 bg-white"
      >
      <div class="container">
        <div class="flex items-center justify-between relative text-white">
          <div class="flex items-center justify-between md:w-full">
            <a
              href="/"
              class="flex items-center w-auto -ml-2 outline-none md:w-[auto] text-white dark:text-white"
            >
              <img src="@/assets/logoifer.jpeg" alt="Houbara" class="w-[auto] h-[75px]" />
            </a>
            <div
              @click="isMenuCollapsed = !isMenuCollapsed"
              class="dark:text-white text-black hidden md:block header__body-burger bg-brown-100"
              :class="{'header__body-burger--active': isMenuCollapsed}"
            >
              <MenuIcon :class="{'header__body-burger-icon': isMenuCollapsed, 'w-10 h-10': true}" />
            </div>
          </div>
          <ul class="flex items-center justify-center gap-10 flex-1 md:hidden lgx:gap-5 text-dark-100">
             <li>
                <a @click.prevent="scrollToTop()" class="text-xs uppercase tracking-widest cursor-pointer">
                  {{ translations[currentLang].nav.home }}
                </a>
              </li>
              <li>
                <a @click.prevent="scrollToSection('#story')" href="#story" class="text-xs uppercase tracking-widest">
                  {{ translations[currentLang].nav.story }}
                </a>
              </li>
              <li>
                <a @click.prevent="scrollToSection('#bustard')" href="#bustard" class="text-xs uppercase tracking-widest">
                  {{ translations[currentLang].nav.bustard }}
                </a>
              </li>
              <li>
                <a @click.prevent="scrollToSection('#work')" href="#work" class="text-xs uppercase tracking-widest">
                  {{ translations[currentLang].nav.work }}
                </a>
              </li>
              <li>
                <a @click.prevent="scrollToSection('#center')" href="#center" class="text-xs uppercase tracking-widest">
                  {{ translations[currentLang].nav.center }}
                </a>
              </li>
            <li>
              <button 
                @click="setLanguage('en')" 
                :class="{'font-bold underline': currentLang === 'en'}"
                class="uppercase text-xs tracking-widest"
              >
                EN
              </button>
            </li>
            <li>
              <button 
                @click="setLanguage('ar')" 
                :class="{'font-bold underline': currentLang === 'ar'}"
                class="uppercase text-xs tracking-widest"
              >
                AR
              </button>
            </li>
          </ul>
          <ul
            v-if="isMenuCollapsed"
              class="hidden md:absolute md:top-full md:grid md:justify-normal md:z-10 md:0 bg-brown-100 dark:md:bg-dark-header md:gap-0 md:-mx-4 md:w-header"
            >

            <li>
              <a 
              @click.prevent="scrollToTop()"
                href="#home"
              class="text-sm uppercase tracking-widest md:block md:w-full md:p-4">
                 {{ translations[currentLang].nav.home }}
              </a>
            </li>
            <li>
              <a
                @click.prevent="scrollToSection('#about')"
                href="#about"
                class="text-sm uppercase tracking-widest md:block md:w-full md:p-4"
              >
                 {{ translations[currentLang].nav.story }}
              </a>
            </li>
            <li>
              <a
                @click.prevent="scrollToSection('#services')"
                href="#services"
                class="text-sm uppercase tracking-widest md:block md:w-full md:p-4"
              >
               {{ translations[currentLang].nav.bustard }}
              </a>
            </li>
            <li>
              <a
                @click.prevent="scrollToSection('#portfolio')"
                href="#portfolio"
                class="text-sm uppercase tracking-widest md:block md:w-full md:p-4"
              >
                {{ translations[currentLang].nav.work }}
              </a>
            </li>
            <li>
              <a
                @click.prevent="scrollToSection('#contact')"
                href="#contact"
                class="text-sm uppercase tracking-widest md:block md:w-full md:p-4"
              >
                {{ translations[currentLang].nav.center }}
              </a>
            </li>
              <li class="flex items-center gap-2  md:p-4">
              <button 
                @click="setLanguage('en')" 
                :class="{'font-bold underline': currentLang === 'en'}"
                class="uppercase text-xs tracking-widest"
              >
                EN
              </button>
               <button 
                @click="setLanguage('ar')" 
                :class="{'font-bold underline': currentLang === 'ar'}"
                class="uppercase text-xs tracking-widest"
              >
                AR
              </button>
            </li>
          </ul>
        </div>
      </div>
    </header>
  <section class="pb-0 md:pt-0 sm:pt-0" id="home"> 
    <div class="p-0">
      <!-- :style="{ backgroundImage: `url(${bgHoubara})` }" -->
      <div class="flex items-center justify-center gap-24 bg-banner md:flex-col lgx:gap-10" >
        <video src="@/assets/clip1.mp4" type="video/mp4" class="video-background w-full h-full object-cover" loop="" muted=""></video>
        <div class="absolute z-10  top-1/2 left-4 transform  -translate-y-1/2 font-bold md:hidden lgx:hidden">
              <h1 class="pl-5 text-5xl text-white leading-normal md:text-3xl md:leading-normal md:text-center sm:text-2xl">
              <!-- Protect the Desert’s Secret Bird -->
                <!-- <span v-html="displayText"></span>
                <span class="blinking-cursor">|</span> -->
            </h1>
        </div>
      
      </div>
    </div>
    <a
    @click.prevent="scrollToSection('#story')"
    href="#story"
    class="text-xs uppercase tracking-widest "
    >
    <span class="absolute bottom-5 left-1/2 transform -translate-x-1/2 translate-y-1/2 w-10 h-10 cursor-pointer">
      <svg class="w-6 h-6 animate-bounce" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" fill="#fff" version="1.1" id="Capa_1" width="40px" height="40px" viewBox="0 0 30.727 30.727" xml:space="preserve">
        <g>
          <path d="M29.994,10.183L15.363,24.812L0.733,10.184c-0.977-0.978-0.977-2.561,0-3.536c0.977-0.977,2.559-0.976,3.536,0   l11.095,11.093L26.461,6.647c0.977-0.976,2.559-0.976,3.535,0C30.971,7.624,30.971,9.206,29.994,10.183z"/>
        </g>
      </svg>
    </span>
    </a>

  </section>
  <section class="mx-auto bg-land-50" id="story">
    <div class="container">
      <!-- Title -->
      <h2 class="text-4xl pt-8 font-bold text-center text-brown-100 mb-8">{{ translations[currentLang].story.title }}</h2>
      <div class="relative grid grid-cols-2 sm:grid-cols-1 gap-4 pb-8">
          <div class="relative flex items-center justify-center w-[600px] h-[600px] sm:w-[100%] sm:h-[auto] mx-auto">
            <img
              src="@/assets/tamim.jpg"
              alt="Vision & Mission"
              class="w-full h-full object-cover"
            />
          </div>
          <div class="relative flex items-center justify-center mr-auto">
            <div class="p-6 flex flex-col justify-center flex-1">
              <h3 class="text-4xl font-bold mb-3 text-brown-100 capitalize">{{ translations[currentLang].story.who }}</h3>
              <p class="text-lg leading-relaxed mb-4 text-brown-100">
                {{ translations[currentLang].story.text }}
              </p>
            </div>
          </div>
      </div>
      
    </div>
  </section>
  <section class="mx-auto" id="bustard">
    <!-- bg-[url('@/assets/h1.png')] -->
    <div class=" bg-cover bg-center h-screen flex items-center relative  py-4">
      <video src="@/assets/clip2.mp4" type="video/mp4" class="video-background w-full h-full object-cover w-full h-full absolute inset-0" loop="" muted=""></video>
      <div class="w-full h-full absolute inset-0 bg-black bg-opacity-40 z-2"></div>
      <div class="container z-10">
        <div class="py-16 px-6 bg-black/50 text-white text-center w-1/2 sm:w-full sm:bg-transparent">
          <h2 class="text-3xl font-bold mb-4">{{ translations[currentLang].bustard.title }}</h2>
          <p class="mb-6">
            {{ translations[currentLang].bustard.text }}
          </p>
        </div>
      </div>
    </div>
  </section>
  <section class="mx-auto bg-land-50" id="work">
    <div class="container">
      <!-- Title -->
      <h2 class="text-3xl pt-8 font-bold text-center text-brown-100 mb-12">
        {{ translations[currentLang].work.title }}
      </h2>

      <!-- Block 1 -->
      <div class="grid grid-cols-2 items-center">
        <img
          src="@/assets/houbara_fly.png"
          alt="Conserving Bustards"
          class="h-[400px] w-full object-cover shadow-lg ml-auto mr-0"
        />
        <div class="p-6">
          <h3 class="text-2xl font-bold text-brown-100 mb-4">{{ translations[currentLang].work.block1.title }}</h3>
          <p class="text-gray-700">
            {{ translations[currentLang].work.block1.text }}
          </p>
        </div>
      </div>

      <!-- Block 2 (reversed) -->
      <div class="grid grid-cols-2 items-center">
        <div class="p-6">
          <h3 class="text-2xl font-bold text-brown-100 mb-4">{{ translations[currentLang].work.block2.title }}</h3>
          <p class="text-gray-700">
            {{ translations[currentLang].work.block2.text }}
          </p>
        </div>
        <img
          src="@/assets/release.jpg"
          alt="Breeding And Release"
          class="w-full h-[400px] md:h-full object-cover shadow-lg"
        />
      </div>

      <!-- Block 3 -->
      <div class="grid grid-cols-2 items-center">
        <img
          src="@/assets/nestProtection.webp"
          alt="Nest Protection"
          class="w-full h-[400px] md:h-full object-cover shadow-lg"
        />
        <div class="p-6">
          <h3 class="text-2xl font-bold text-brown-100 mb-4">{{ translations[currentLang].work.block3.title }}</h3>
          <p class="text-gray-700">
            {{ translations[currentLang].work.block3.text }}
          </p>
        </div>
      </div>

      <!-- Block 4 (reversed) -->
      <div class="grid grid-cols-2 items-center">
        <div class="p-6">
          <h3 class="text-2xl font-bold text-brown-100 mb-4">{{ translations[currentLang].work.block4.title }}</h3>
          <p class="text-gray-700">
            {{ translations[currentLang].work.block4.text }}
          </p>
        </div>
        <img
          src="@/assets/incubation.png"
          alt="Incubation"
          class="w-full h-[400px]  object-cover mr-auto ml-0 shadow-lg"
        />
      </div>
    </div>
  </section>
  <section class="mx-auto bg-white" id="center">
    <div class="container">
      <!-- Title -->
      <h2 class="text-4xl pt-8 font-bold text-center text-brown-100 mb-8">{{ translations[currentLang].center.title }}</h2>
      <div class="relative grid grid-cols-2 sm:grid-cols-1 gap-4 pb-8">
          <div class="relative flex items-center justify-center w-[600px] h-[600px] sm:w-[100%] sm:h-[auto] mx-auto">
            <img
              src="@/assets/img_air.png"
              alt="Vision & Mission"
              class="w-full h-full object-cover"
            />
          </div>
          <div class="relative flex items-center justify-center mr-auto">
            <div class="p-6 flex flex-col justify-center flex-1">
              <h3 class="text-3xl font-bold mb-3 text-brown-100 capitalize text-center leading-normal">{{ translations[currentLang].center.subtitle }}</h3>
              <p class="text-lg leading-relaxed mb-4 text-brown-100">
                {{ translations[currentLang].center.text }}
              </p>
            </div>
          </div>
      </div>
      
    </div>
  </section>
  <footer class="border-t border-paragraph dark:border-white dark:border-opacity-10 border-opacity-10 py-7 md:py-5 bg-land-100">
  <div class="container">
    <span class="leading-none flex items-center justify-center text-center gap-1 text-white dark:text-dark-75">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" fill="currentColor" class="w-3.5 h-3.5 md:w-3 md:h-3">
        <path d="M256 48a208 208 0 1 1 0 416 208 208 0 1 1 0-416zm0 464A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM199.4 312.6c-31.2-31.2-31.2-81.9 0-113.1s81.9-31.2 113.1 0c9.4 9.4 24.6 9.4 33.9 0s9.4-24.6 0-33.9c-50-50-131-50-181 0s-50 131 0 181s131 50 181 0c9.4-9.4 9.4-24.6 0-33.9s-24.6-9.4-33.9 0c-31.2 31.2-81.9 31.2-113.1 0z"></path>
      </svg>
      <span class="font-extralight text-sm md:text-xs md:text-center text-white">{{ translations[currentLang].footer }}</span>
    </span>
  </div>
  </footer>
  </main>

</div>
</template>
<script setup>
import { ref, onMounted } from "vue";
import bgHoubara from '@/assets/bg_houbara_2.jpg'
const texts = [
  "Protecting the <br/> Houbara Bustard",
  "For Future Genarations",
  "A symbol of the desert",
  "Conservation for the future",
  "Preserve biodiversity",
  "Guardians of the ecosystem",
  "Saving the Houbara, saving ourselves"
];

const displayText = ref("");
let index = 0;
let charIndex = 0;
let isDeleting = false;

function type() {
  const currentText = texts[index];

  if (!isDeleting && charIndex <= currentText.length) {
    // typing forward
    displayText.value = currentText.substring(0, charIndex++);
  } else if (isDeleting && charIndex >= 0) {
    // deleting backward
    displayText.value = currentText.substring(0, charIndex--);
  }

  if (!isDeleting && charIndex === currentText.length + 1) {
    // finished typing full word
    isDeleting = true;
    setTimeout(type, 1500); // pause before deleting
    return;
  }

  if (isDeleting && charIndex === -1) {
    // finished deleting
    isDeleting = false;
    index = (index + 1) % texts.length;
    charIndex = 0;
  }

  setTimeout(type, isDeleting ? 60 : 120);
}

onMounted(() => {
  type();
});
</script>

<style scoped>
.blinking-cursor {
  font-weight: 100;
  font-size: 1.5rem;
  color: white;
  animation: blink 0.8s step-end infinite;
}
@keyframes blink {
  from,
  to {
    color: transparent;
  }
  50% {
    color: white;
  }
}
</style>