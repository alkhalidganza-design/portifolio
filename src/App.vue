<script setup>
import { ref, computed, onMounted } from 'vue'
import avatar from './assets/ganza.jpeg'
import project2 from './assets/Simplify Your Shopify Store in 2025 — One-Page Design That Converts.jpg'
import project3 from './assets/What Is the Best Laptop for Multitasking in 2025.jpg'

// Projects dataset with customized links and button targets
const projects = [
  {
    title: 'E-commerce performance refresh',
    description: 'Improved load time and conversion with optimized assets, accessibility updates, and seamless navigation.',
    tag: 'Performance',
    projectLink: 'https://ganza-khalid.netlify.app',
    codeLink: 'https://github.com/alkhalidganza-design',
    image: project2,
  },
  {
    title: 'Best 14-inch laptops 2026',
    description: 'Curated review for productivity, portability, and long battery life.',
    tag: 'Hardware Review',
    projectLink: 'https://vue-app-2.netlify.app',
    codeLink: 'https://github.com/alkhalidganza-design',
    image: project3,
  },
]

const skills = ['Vue 3', 'HTML & CSS', 'JavaScript', 'Responsive design', 'Accessibility', 'Web performance', 'Component design', 'Micro-interactions']
const highlights = [
  { value: '40+', label: 'features shipped across products' },
  { value: '60%', label: 'faster page speed achieved' },
  { value: '2 years', label: 'focused frontend work' },
]

const socials = {
  github: 'https://github.com/alkhalidganza-design', 
  linkedin: 'https://linkedin.com',
  instagram: 'https://instagram.com'
}

// Language Switcher Setup
const currentLang = ref('en')

const toggleLanguage = () => {
  currentLang.value = currentLang.value === 'en' ? 'rw' : 'en'
}

// Translations Dictionary Database
const t = computed(() => {
  return {
    en: {
      about: 'About',
      roiCalc: 'ROI Calculator',
      skillsNav: 'Skills',
      work: 'Work',
      contact: 'Contact',
      launchApp: 'Launch App',
      talk: "Let's Talk →",
      contactMe: 'Contact Me',
      myWork: 'My Work →',
      role: 'Fullstack Web Developer',
      location: 'Kigali, Rwanda',
      heroTitle: 'Transforming Your Ideas into',
      heroAccent: 'Reality',
      heroText: 'Passionate about creating intuitive and engaging user experiences. I specialize in transforming ideas into beautifully crafted, conversion-focused products.',
      expYears: 'Years of experience',
      projDone: 'Projects completed',
      potentialClients: 'Potential clients',
      trustedTitle: 'Trusted to turn product goals into polished customer experiences.',
      aboutText: 'I specialize in Vue-based interfaces, accessible component design, and fast-loading pages. I work with product teams to reduce friction, increase engagement, and deliver refined digital experiences.',
      skillsTitle: 'What I bring to every project',
      selectedWork: 'Selected work',
      valueGen: 'Value Generator',
      badPerf: 'See what bad performance is costing you',
      currentTraffic: 'Your Current Monthly Traffic:',
      visitors: 'visitors',
      dragSlider: 'Drag the slider to match your estimated monthly traffic metrics.',
      estRevenue: 'Estimated Monthly Revenue Increase',
      calcDesc: 'By optimizing Core Web Vitals, page speed metrics, and fixing conversion drop-offs, we can typically reclaim this hidden value.',
      auditBtn: 'Secure Your Growth Audit',
      
      // Action Labels
      viewCode: 'View Code',
      viewProject: 'View Project',
      
      // Contact Section Translations
      letsConnect: "Let's Connect",
      pitch: "I'm always interested in new opportunities and collaborations. Whether you have a project in mind or just want to chat about technology, feel free to reach out!",
      baseLoc: 'Kigali, Nyarugenge, Rwanda',
      sendAMessage: 'Send a Message',
      subPitch: "I'll get back to you within 24 hours",
      firstName: 'First Name *',
      lastName: 'Last Name *',
      emailAddress: 'Email Address *',
      subject: 'Subject *',
      message: 'Message *',
      placeholderFirstName: 'Ganza',
      placeholderLastName: 'Al-khalid',
      placeholderSubject: 'Project Collaboration',
      placeholderMsg: 'Tell me about your project or how we can work together...',
      sendBtn: 'Send Message',
      alertSuccess: 'Thank you! Your message has been captured.'
    },
    rw: {
      about: 'Aba muntu',
      roiCalc: 'Kubara Inyungu',
      skillsNav: 'Ubumenyi',
      work: 'Ibikorwa',
      contact: 'Twandikire',
      launchApp: 'Yifashishe',
      talk: 'Tuganire →',
      contactMe: 'Twandikire',
      myWork: 'Ibikorwa Byanjye →',
      role: 'Umuhanzi w’Imbuga za Internet',
      location: 'Kigali, Rwanda',
      heroTitle: 'Guhindura Ibitekerezo Byanyu Mo',
      heroAccent: 'Kuri',
      heroText: 'Niyeguriye gukora imbuga zizana umubano mwiza n’abazisura. Nshinzwe guhindura ibitekerezo byanyu ibikorwa bishimishije kandi byinjiza inyungu.',
      expYears: 'Imyaka y’ubushakashatsi',
      projDone: 'Imishinga yarangiye',
      potentialClients: 'Abakiriya bategerejwe',
      trustedTitle: 'Nizewe guhindura intego z’ibicuruzwa ibikorwa bishimishije ku bakiriya.',
      aboutText: 'Nizera gukoresha Vue, gukora ibice byoroshye gukoreshwa, n’imbuga zihuta. Nkora n’amakipe y’ibicuruzwa kugira ngo tugabanye ingorane, twongere ubwiyongere, kandi dutange imbuga zisobanutse.',
      skillsTitle: 'Ibyo nzanira buri mushinga',
      selectedWork: 'Imishinga yatoranyijwe',
      valueGen: 'Gushakisha Agaciro',
      badPerf: 'Reba icyo gutinda kw’urubuga kuguhombya',
      currentTraffic: 'Abasura Urubuga Rwawe Ku Kwezi:',
      visitors: 'abasuzi',
      dragSlider: 'Kurura aka kamenyetso ujyanishe n’abasuzi b’urubuga rwawe.',
      estRevenue: 'Inyungu Ngira Ku Kwezi Yiyongereye',
      calcDesc: 'Mu gukuraho ibibazo by’umuvuduko w’urubuga, dushobora kugarura aya mafaranga aba yahombye.',
      auditBtn: 'Saba Isuzuma Ry’Urubuga Rwawe',
      
      // Action Labels Kinyarwanda
      viewCode: 'Reba Kode',
      viewProject: 'Reba Umushinga',
      
      // Contact Section Kinyarwanda
      letsConnect: 'Tunyuzemo Ubutumwa',
      pitch: 'Nshishikajwe buri gihe n’amahirwe mashya ndetse n’ubushakashatsi bw’imishinga. Niba ufite umushinga uteganya cyangwa ushaka ko tuganira ku bumenyi ngiro, twandikire!',
      baseLoc: 'Kigali, Nyarugenge, Rwanda',
      sendAMessage: 'Yandika Ubutumwa',
      subPitch: 'Ndakubita igisubizo mu masaha 24',
      firstName: 'Izina Ryambere *',
      lastName: 'Izina rya Kabiri *',
      emailAddress: 'Imeyili Yandikwa *',
      subject: 'Icyo mwandikira *',
      message: 'Ubutumwa Bwawe *',
      placeholderFirstName: 'Ganza',
      placeholderLastName: 'Al-khalid',
      placeholderSubject: 'Gukorana Umushinga',
      placeholderMsg: 'Bwira ibijyanye n’umushinga wawe cyangwa uburyo twakorana...',
      sendBtn: 'Yohereza Ubutumwa',
      alertSuccess: 'Murakoze! Ubutumwa bwanyu bwakiriwe neza.'
    }
  }[currentLang.value]
})

// Calculator logic
const monthlyTraffic = ref(10000)
const estimatedAOV = 50 
const revenueGain = computed(() => {
  return Math.round(monthlyTraffic.value * 0.012) * estimatedAOV
})

// Contact Form variables
const firstNameField = ref('')
const lastNameField = ref('')
const emailField = ref('')
const subjectField = ref('')
const messageField = ref('')

const handleFormDispatch = () => {
  alert(`${t.value.alertSuccess} (${firstNameField.value})`)
  firstNameField.value = ''
  lastNameField.value = ''
  emailField.value = ''
  subjectField.value = ''
  messageField.value = ''
}

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('in-view')
          observer.unobserve(entry.target)
        }
      })
    },
    { threshold: 0.12 }
  )
  document.querySelectorAll('.fade-up').forEach((el) => observer.observe(el))
})
</script>

<template>
  <div id="app">
    <header class="app-navbar">
      <div class="navbar-inner">
        <a href="#" class="nav-brand">GANZA.DEV</a>
        <nav class="nav-links">
          <a href="#about">{{ t.about }}</a>
          <a href="#roi-estimator">{{ t.roiCalc }}</a>
          <a href="#skills">{{ t.skillsNav }}</a>
          <a href="#projects">{{ t.work }}</a>
          <a href="#contact">{{ t.contact }}</a>
        </nav>
        
        <div class="nav-cta-zone">
          <button @click="toggleLanguage" class="lang-switcher-btn" :title="currentLang === 'en' ? 'Hindura mu Kinyarwanda' : 'Switch to English'">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><line x1="2" y1="12" x2="22" y2="12"></line><path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1 4-10z"></path></svg>
            <span>{{ currentLang === 'en' ? 'RW' : 'EN' }}</span>
          </button>

          <div class="header-socials-icons">
            <a :href="socials.github" target="_blank" rel="noopener noreferrer" class="nav-social-box">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path></svg>
            </a>
            <a :href="socials.linkedin" target="_blank" rel="noopener noreferrer" class="nav-social-box">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect width="4" height="12" x="2" y="9"></rect></svg>
            </a>
          </div>
          <a href="https://ganza-khalid.netlify.app" target="_blank" rel="noopener noreferrer" class="nav-cta-btn">{{ t.launchApp }}</a>
        </div>
      </div>
    </header>

    <main class="layout content-container-shift">
      <section class="hero-section hero-dark">
        <div class="profile-card">
          <div class="avatar-wrap">
            <img :src="avatar" alt="avatar" class="avatar" />
          </div>
          <h3 class="profile-name"> GANZA AL-KHALID </h3>
          <p class="profile-role">{{ t.role }}</p>
          <p class="profile-location">{{ t.location }}</p> 
          <div class="profile-socials-row">
            <a :href="socials.github" target="_blank" rel="noopener noreferrer" class="social-icon-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path></svg>
            </a>
            <a :href="socials.linkedin" target="_blank" rel="noopener noreferrer" class="social-icon-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect width="4" height="12" x="2" y="9"></rect></svg>
            </a>
          </div>
          <a class="button button-primary" href="#contact">{{ t.talk }}</a>
        </div>

        <div class="hero-copy">
          <h1 class="hero-title">{{ t.heroTitle }} <span class="accent">{{ t.heroAccent }}</span></h1>
          <p class="hero-text">{{ t.heroText }}</p>
          <div class="stats-row">
            <div class="stat"><div class="stat-value">+2</div><div class="stat-label">{{ t.expYears }}</div></div>
            <div class="stat"><div class="stat-value">+4</div><div class="stat-label">{{ t.projDone }}</div></div>
          </div>
          <div class="hero-actions">
            <a class="button button-primary" href="#contact">{{ t.contactMe }}</a>
            <a class="hero-link" href="#projects">{{ t.myWork }}</a>
          </div>
        </div>
      </section>

      <section class="section about" id="about">
        <div class="section-header">
          <span class="section-tag">{{ t.about }}</span>
          <h2>{{ t.trustedTitle }}</h2>
        </div>
        <p>{{ t.aboutText }}</p>
      </section>

      <section class="section highlights">
        <div class="highlight-grid">
          <article class="highlight-card" v-for="highlight in highlights" :key="highlight.label">
            <p class="highlight-value">{{ highlight.value }}</p>
            <p class="highlight-label">{{ highlight.label }}</p>
          </article>
        </div>
      </section>

      <section class="section roi-estimator" id="roi-estimator">
        <div class="section-header">
          <span class="section-tag">{{ t.valueGen }}</span>
          <h2>{{ t.badPerf }}</h2>
        </div>
        <div class="estimator-container">
          <div class="estimator-controls">
            <label for="traffic-slider">{{ t.currentTraffic }} <strong>{{ monthlyTraffic.toLocaleString() }} {{ t.visitors }}</strong></label>
            <input id="traffic-slider" type="range" min="2000" max="100000" step="1000" v-model.number="monthlyTraffic" class="slider-element" />
          </div>
          <div class="estimator-result-card">
            <span class="result-label">{{ t.estRevenue }}</span>
            <h3>+${{ revenueGain.toLocaleString() }}/mo</h3>
            <p>{{ t.calcDesc }}</p>
          </div>
        </div>
      </section>

      <section class="section skills" id="skills">
        <div class="section-header">
          <span class="section-tag">{{ t.skillsNav }}</span>
          <h2>{{ t.skillsTitle }}</h2>
        </div>
        <div class="skill-grid">
          <div class="skill-chip" v-for="skill in skills" :key="skill">{{ skill }}</div>
        </div>
      </section>

      <section class="section projects" id="projects">
        <div class="section-header">
          <span class="section-tag">{{ t.work }}</span>
          <h2>{{ t.selectedWork }}</h2>
        </div>
        <div class="project-grid">
          <article class="project-card" v-for="project in projects" :key="project.title">
            <img :src="project.image" :alt="project.title" class="project-image" />
            <div class="project-content">
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
              
              <div class="project-actions-row">
                <a :href="project.codeLink" target="_blank" rel="noopener noreferrer" class="action-btn link-code-btn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path></svg>
                  <span>{{ t.viewCode }}</span>
                </a>
                <a :href="project.projectLink" target="_blank" rel="noopener noreferrer" class="action-btn link-live-btn">
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path><polyline points="15 3 21 3 21 9"></polyline><line x1="10" y1="14" x2="21" y2="3"></line></svg>
                  <span>{{ t.viewProject }}</span>
                </a>
              </div>
            </div>
          </article>
        </div>
      </section>

      <section class="section contact-section-dark" id="contact">
        <div class="contact-split-layout">
          
          <div class="contact-info-panel">
            <h2>{{ t.letsConnect }}</h2>
            <p class="panel-pitch-text">{{ t.pitch }}</p>
            
            <div class="contact-meta-channels">
              <div class="meta-channel-row">
                <div class="icon-avatar-shell">
                  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#10b981" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
                </div>
                <span class="channel-data-text">ikundabayoplacide500@gmail.com</span>
              </div>
              
              <div class="meta-channel-row">
                <div class="icon-avatar-shell">
                  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#10b981" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>
                </div>
                <span class="channel-data-text">+250 789 897 235</span>
              </div>
              
              <div class="meta-channel-row">
                <div class="icon-avatar-shell">
                  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#10b981" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
                </div>
                <span class="channel-data-text">github.com/alkhalidganza-design</span>
              </div>
              
              <div class="meta-channel-row">
                <div class="icon-avatar-shell">
                  <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="#10b981" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
                </div>
                <span class="channel-data-text">{{ t.baseLoc }}</span>
              </div>
            </div>
          </div>

          <form @submit.prevent="handleFormDispatch" class="premium-form-shell">
            <h3 class="form-panel-title">{{ t.sendAMessage }}</h3>
            <p class="form-panel-subtitle">{{ t.subPitch }}</p>

            <div class="form-inputs-dual-row">
              <div class="form-input-block">
                <label for="first-name">{{ t.firstName }}</label>
                <input type="text" id="first-name" v-model="firstNameField" :placeholder="t.placeholderFirstName" required class="premium-input" />
              </div>
              <div class="form-input-block">
                <label for="last-name">{{ t.lastName }}</label>
                <input type="text" id="last-name" v-model="lastNameField" :placeholder="t.placeholderLastName" required class="premium-input" />
              </div>
            </div>

            <div class="form-input-block">
              <label for="email-addr">{{ t.emailAddress }}</label>
              <input type="email" id="email-addr" v-model="emailField" placeholder="alkhalidganza@gmail.com" required class="premium-input" />
            </div>

            <div class="form-input-block">
              <label for="msg-subject">{{ t.subject }}</label>
              <input type="text" id="msg-subject" v-model="subjectField" :placeholder="t.placeholderSubject" required class="premium-input" />
            </div>

            <div class="form-input-block">
              <label for="msg-body">{{ t.message }}</label>
              <textarea id="msg-body" v-model="messageField" rows="4" :placeholder="t.placeholderMsg" required class="premium-input content-textarea"></textarea>
            </div>

            <button type="submit" class="premium-emerald-submit-btn">
              <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>
              {{ t.sendBtn }}
            </button>
          </form>

        </div>
      </section>
    </main>
  </div>
</template> 