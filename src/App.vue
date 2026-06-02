<script setup>
import avatar from './assets/ganza.jpeg'
import project1 from './assets/download (17).jpg'
import project2 from './assets/Simplify Your Shopify Store in 2025 — One-Page Design That Converts.jpg'
import project3 from './assets/What Is the Best Laptop for Multitasking in 2025.jpg'
const projects = [
    {
      title: 'Design system for product launch',
      description: 'Built a polished interface with Vue 3, animations, and responsive UI patterns for a modern brand.',
      tag: 'UI / UX',
      link: 'http://ganza-khalid.netlify.app',
      linkLabel: 'View project',
      image: project1,
    },
  {
    title: 'E-commerce performance refresh',
    description: 'Improved load time and conversion with optimized assets, accessibility updates, and seamless navigation.',
    tag: 'Performance',
    link: 'http://ganza-khalid.netlify.app',
    linkLabel: 'View project',
    image: project2,
  },
  {
    title: 'Best 14-inch laptops 2026',
    description: 'Curated review for productivity, portability, and long battery life.',
    tag: 'Hardware Review',
    link: 'http://ganza-khalid.netlify.app',
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

import { onMounted } from 'vue'

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
    <main class="layout">
      <section class="hero-section hero-dark">
        <div class="profile-card">
          <div class="avatar-wrap">
            <img :src="avatar" alt="avatar" class="avatar" />
          </div>
          <h3 class="profile-name"> GANZA AL-KHALID </h3>
          <p class="profile-role">Fullstack Web Developer</p>
          <p class="profile-location">Kigali, Rwanda</p> 
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
            <a class="button button-primary" href="#contact">Let's Talk</a>
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
            <a :href="`#${c.id}`" class="case-link">Read case study</a>
          </article>
        </div>
      </section>

      <section class="section skills">
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
        <p>Want a stronger online presence? Send a message, and I’ll help shape your next digital project.</p>
        <a class="button button-primary" href="mailto:ganzaalkhalid@gmail.com">ganzaalkhalid@gmail.com</a>
      </section>
      
    </main>
  </div>
</template>
