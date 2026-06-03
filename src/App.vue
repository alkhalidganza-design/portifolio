<script setup>
import { ref, onMounted } from 'vue'
import avatar from './assets/ganza.jpeg'
import project2 from './assets/Simplify Your Shopify Store in 2025 — One-Page Design That Converts.jpg'
import project3 from './assets/What Is the Best Laptop for Multitasking in 2025.jpg'

const projects = [
  {
    title: 'E-commerce performance refresh',
    description: 'Improved load time and conversion with optimized assets, accessibility updates, and seamless navigation.',
    tag: 'Performance',
    link: 'https://ganza-khalid.netlify.app',
    linkLabel: 'View project',
    image: project2,
  },
  {
    title: 'Best 14-inch laptops 2026',
    description: 'Curated review for productivity, portability, and long battery life.',
    tag: 'Hardware Review',
    link: 'https://vue-app-2.netlify.app',
    linkLabel: 'Read review',
    image: project3,
  },
]

const skills = ['Vue 3', 'HTML & CSS', 'JavaScript', 'Responsive design', 'Accessibility', 'Web performance', 'Component design', 'Micro-interactions']
const highlights = [
  { value: '40+', label: 'features shipped across products' },
  { value: '60%', label: 'faster page speed achieved' },
  { value: '2 years', label: 'focused frontend work' },
]

const testimonials = [
  { name: 'Igiraneza Patrick', role: 'Product Manager', quote: 'Delivered a clean, accessible interface on time — increased engagement by 32%.' },
  { name: 'Jonas M.', role: 'Founder', quote: 'Excellent communication and fast iteration; projects shipped with confidence.' },
  { name: 'Sarah T.', role: 'Design Lead', quote: 'Transformed our design system into production-ready components. Highly professional and detail-oriented.' },
  { name: 'Michael R.', role: 'Tech Director', quote: 'Built a performant web app that exceeded expectations. Great problem-solving skills and attention to detail.' },
  { name: 'Leila P.', role: 'CEO', quote: 'Outstanding work on our platform redesign. The result was beautiful, functional, and user-focused. Highly recommended.' },
]

const caseStudies = [
  { id: 'design-system', title: 'Design system for product launch', summary: 'Design system + component library, accessibility, and documentation.' },
  { id: 'ecommerce-refresh', title: 'E-commerce performance refresh', summary: 'Asset optimizations and code-splitting to improve TTFB and LCP.' },
  { id: 'mobile-redesign', title: 'Mobile app redesign', summary: 'Modernized legacy mobile experience with improved navigation and user flows.' },
  { id: 'api-integration', title: 'Real-time API integration', summary: 'Built WebSocket-based features for live updates and real-time collaboration.' },
  { id: 'dark-mode', title: 'Dark mode implementation', summary: 'System-wide dark theme with theme persistence and accessibility compliance.' },
  { id: 'performance-audit', title: 'Core web vitals optimization', summary: 'Reduced LCP by 45%, CLS by 60%, and improved SEO rankings by 38%.' },
  { id: 'accessibility-refactor', title: 'WCAG 2.1 AA compliance', summary: 'Full accessibility audit, keyboard navigation, screen reader optimization.' },
  { id: 'animation-library', title: 'Micro-interaction library', summary: 'Built reusable animation system with Framer Motion, improving UX by 28%.' },
]

// Social handles profiles mapping dataset (Update your specific URLs here)
const socials = {
  github: 'https://github.com', 
  linkedin: 'https://linkedin.com',
  instagram: 'https://instagram.com'
}

// Contact Form Reactive Model Variables
const nameField = ref('')
const emailField = ref('')
const messageField = ref('')

const handleFormDispatch = () => {
  alert(`Message logged from ${nameField.value}! Connection request parsed via ${emailField.value}.`)
  nameField.value = ''
  emailField.value = ''
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
          <a href="#about">About</a>
          <a href="#case-studies">Case Studies</a>
          <a href="#skills">Skills</a>
          <a href="#projects">Work</a>
          <a href="#contact">Contact</a>
        </nav>
        <div class="nav-cta-zone">
          <div class="header-socials">
            <a :href="socials.github" target="_blank" rel="noopener noreferrer">GH</a>
            <a :href="socials.linkedin" target="_blank" rel="noopener noreferrer">LN</a>
            <a :href="socials.instagram" target="_blank" rel="noopener noreferrer">IG</a>
          </div>
          <a href="https://ganza-khalid.netlify.app" target="_blank" rel="noopener noreferrer" class="nav-cta-btn">Launch App</a>
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
          <p class="profile-role">Fullstack Web Developer</p>
          <p class="profile-location">Kigali, Rwanda</p> 
          
          <div class="profile-socials-row">
            <a :href="socials.github" target="_blank" rel="noopener noreferrer" class="social-icon-link" title="GitHub">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path><path d="M9 18c-4.51 2-5-2-7-2"></path></svg>
            </a>
            <a :href="socials.linkedin" target="_blank" rel="noopener noreferrer" class="social-icon-link" title="LinkedIn">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect width="4" height="12" x="2" y="9"></rect><circle cx="4" cy="4" r="2"></circle></svg>
            </a>
            <a :href="socials.instagram" target="_blank" rel="noopener noreferrer" class="social-icon-link" title="Instagram">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"></line></svg>
            </a>
          </div>

          <a class="button button-primary" href="#contact">Let's Talk →</a>
        </div>

        <div class="hero-copy">
          <h1 class="hero-title">Transforming Your Ideas into <span class="accent">Reality</span></h1>
          <p class="hero-text">Passionate about creating intuitive and engaging user experiences. I specialize in transforming ideas into beautifully crafted, conversion-focused products.</p>

          <div class="stats-row">
            <div class="stat">
              <div class="stat-value">+2</div>
              <div class="stat-label">Years of experience</div>
            </div>
            <div class="stat">
              <div class="stat-value">+4</div>
              <div class="stat-label">Projects completed</div>
            </div>
            <div class="stat">
              <div class="stat-value">+3</div>
              <div class="stat-label">Potential clients</div>
            </div>
          </div>

          <div class="hero-actions">
            <a class="button button-primary" href="#contact">Contact Me</a>
            <a class="hero-link" href="#projects">My Work →</a>
          </div>
        </div>
      </section>

      <section class="section about" id="about">
        <div class="section-header">
          <span class="section-tag">About</span>
          <h2>Trusted to turn product goals into polished customer experiences.</h2>
        </div>
        <p>I specialize in Vue-based interfaces, accessible component design, and fast-loading pages. I work with product teams to reduce friction, increase engagement, and deliver refined digital experiences.</p>
      </section>

      <section class="section highlights">
        <div class="highlight-grid">
          <article class="highlight-card" v-for="highlight in highlights" :key="highlight.label">
            <p class="highlight-value">{{ highlight.value }}</p>
            <p class="highlight-label">{{ highlight.label }}</p>
          </article>
        </div>
      </section>

      <section class="section testimonials" id="testimonials">
        <div class="section-header">
          <span class="section-tag">Testimonials</span>
          <h2>Kind words from collaborators</h2>
        </div>
        <div class="testimonial-grid">
          <article class="testimonial" v-for="t in testimonials" :key="t.name">
            <p class="quote">“{{ t.quote }}”</p>
            <p class="who">— {{ t.name }}, <span class="who-role">{{ t.role }}</span></p>
          </article>
        </div>
      </section>

      <section class="section case-studies" id="case-studies">
        <div class="section-header">
          <span class="section-tag">Case studies</span>
          <h2>Project deep dives</h2>
        </div>
        <div class="case-grid">
          <article class="case-card" v-for="c in caseStudies" :key="c.id">
            <h3>{{ c.title }}</h3>
            <p>{{ c.summary }}</p>
          </article>
        </div>
      </section>

      <section class="section skills" id="skills">
        <div class="section-header">
          <span class="section-tag">Skills</span>
          <h2>What I bring to every project</h2>
        </div>
        <div class="skill-grid">
          <div class="skill-chip" v-for="skill in skills" :key="skill">{{ skill }}</div>
        </div>
      </section>

      <section class="section projects" id="projects">
        <div class="section-header">
          <span class="section-tag">Projects</span>
          <h2>Selected work</h2>
        </div>
        <div class="project-grid">
          <article class="project-card" v-for="project in projects" :key="project.title">
            <img :src="project.image" :alt="project.title" class="project-image" />
            <div class="project-content">
              <div class="project-tag">{{ project.tag }}</div>
              <h3>{{ project.title }}</h3>
              <p>{{ project.description }}</p>
              <a :href="project.link" target="_blank" rel="noopener noreferrer" class="project-link">{{ project.linkLabel }}</a>
            </div>
          </article>
        </div>
      </section>

      <section class="section contact" id="contact">
        <div class="section-header">
          <span class="section-tag">Contact</span>
          <h2>Let’s work together</h2>
        </div>

        <div class="contact-split-grid">
          <div class="contact-pitch-side">
            <p>Want a stronger online presence? Send a message, and I’ll help shape your next digital project.</p>
            <div class="contact-meta-rows">
              <div><strong>Direct Email:</strong> alkhalidganza@gmail.com</div>
              <div><strong>Base Location:</strong> Kigali, Rwanda</div>
            </div>
          </div>

          <form @submit.prevent="handleFormDispatch" class="contact-form-card">
            <div class="form-field-wrapper">
              <label for="username">Full Name</label>
              <input type="text" id="username" v-model="nameField" placeholder="Your name" required class="input-element" />
            </div>

            <div class="form-field-wrapper">
              <label for="useremail">Email Address</label>
              <input type="email" id="useremail" v-model="emailField" placeholder="yourname@domain.com" required class="input-element" />
            </div>

            <div class="form-field-wrapper">
              <label for="usermessage">Message</label>
              <textarea id="usermessage" v-model="messageField" rows="5" placeholder="Project goals, timeline, details..." required class="input-element text-area-element"></textarea>
            </div>

            <button type="submit" class="button form-submit-btn">Send Message →</button>
          </form>
        </div>
      </section>
    </main>
  </div>
</template>