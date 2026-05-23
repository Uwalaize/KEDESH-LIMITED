<template>
  <div class="home-container">
    <!-- Hero Section with Local Cover Image -->
    <div class="hero-section-wrapper">
      <div class="hero-overlay"></div>
      <div class="hero-background" :style="{ backgroundImage: `url(${coverImage})` }"></div>
      <div class="hero-content">
        <div class="hero-badge">
          <span class="badge-pulse"></span>
          Welcome to Kedesh Limited
        </div>
        <h1 class="hero-title">
          <span class="title-gradient">Innovate.</span>
          <span class="title-gradient">Create.</span>
          <span class="title-gradient">Elevate.</span>
        </h1>
        <div class="typed-text">
          <span class="typed-prefix">We deliver</span>
          <span class="typed-words">{{ typedWord }}</span>
        </div>
        <p class="hero-description">
          Kedesh Limited delivers cutting-edge digital marketing, cinematic video production, 
          and intelligent systems that redefine industries across East Africa.
        </p>
        <div class="hero-buttons">
          <button class="btn-primary-glow" @click="goToContact">
            Start a Project <i class="fas fa-arrow-right ms-2"></i>
          </button>
          <button class="btn-outline-light" @click="goToServices">
            Explore Services <i class="fas fa-play ms-2"></i>
          </button>
        </div>
        <div class="hero-stats">
          <div class="hero-stat">
            <i class="fas fa-smile"></i>
            <span>98% Client Satisfaction</span>
          </div>
          <div class="hero-stat">
            <i class="fas fa-clock"></i>
            <span>24/7 Support</span>
          </div>
          <div class="hero-stat">
            <i class="fas fa-globe"></i>
            <span>East Africa Wide</span>
          </div>
        </div>
      </div>
      <div class="hero-scroll-indicator">
        <div class="mouse"></div>
        <div class="arrow-down"></div>
      </div>
    </div>

    <!-- Floating Stats Section -->
    <div class="stats-section">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-card floating" v-for="(stat, index) in stats" :key="index" :style="{ animationDelay: `${index * 0.3}s`, animationDuration: '4s' }">
            <div class="stat-icon">
              <i :class="stat.icon"></i>
            </div>
            <div class="stat-number-wrapper">
              <span class="stat-number" :id="`statCounter${index}`">0</span>
              <span class="stat-suffix">{{ stat.suffix }}</span>
            </div>
            <p class="stat-label">{{ stat.label }}</p>
            <div class="stat-progress">
              <div class="progress-bar" :style="{ width: stat.progress }"></div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Services Section with Images -->
    <div class="services-section">
      <div class="container">
        <div class="section-header">
          <span class="section-subtitle">What We Do</span>
          <h2 class="section-title-glass">Our Core Services</h2>
          <p class="section-description">We provide innovative solutions that drive business growth</p>
        </div>
        <div class="services-grid">
          <div class="service-card-premium" v-for="(service, index) in services" :key="index">
            <div class="service-card-inner">
              <div class="service-front" :style="{ backgroundImage: `url(${service.image})`, backgroundSize: 'cover', backgroundPosition: 'center' }">
                <div class="service-overlay"></div>
                <div class="service-content">
                  <div class="service-icon-animated">
                    <i :class="service.icon"></i>
                    <div class="icon-pulse"></div>
                  </div>
                  <h3>{{ service.title }}</h3>
                  <p>{{ service.description }}</p>
                  <div class="service-hover-line"></div>
                </div>
              </div>
              <div class="service-back">
                <i :class="service.icon"></i>
                <h4>Learn More</h4>
                <p class="service-back-desc">{{ service.fullDescription }}</p>
                <!-- Explore button - navigates to services page -->
                <button class="btn-service" @click="goToServices">
                  Explore <i class="fas fa-arrow-right"></i>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- CEO Section - New Premium Section -->
    <div class="ceo-home-section">
      <div class="container">
        <div class="ceo-home-wrapper">
          <div class="row align-items-center">
            <div class="col-lg-4">
              <div class="ceo-home-image">
                <div class="ceo-image-circle">
                  <img :src="ceoImage" alt="CEO Israel Gilbert Salimu">
                  <div class="ceo-image-glow"></div>
                </div>
                <div class="ceo-badge-home">
                  <i class="fas fa-crown"></i>
                  CEO & Founder
                </div>
              </div>
            </div>
            <div class="col-lg-8">
              <div class="ceo-home-content">
                <div class="ceo-quote-icon">
                  <i class="fas fa-quote-left"></i>
                </div>
                <h3 class="ceo-home-name">Israel Gilbert Salimu</h3>
                <p class="ceo-home-title">Chief Executive Officer</p>
                <div class="ceo-divider"></div>
                <p class="ceo-home-message">
                  "At Kedesh Limited, we are committed to transforming businesses through innovative 
                  digital solutions. Our vision is to empower East African enterprises with cutting-edge 
                  technology, creative storytelling, and strategic marketing that delivers measurable results. 
                  We don't just provide services; we build lasting partnerships for success."
                </p>
                <div class="ceo-signature-line">
                  <span class="signature-name">Israel G. Salimu</span>
                  <span class="signature-title">CEO, Kedesh Limited</span>
                </div>
                <div class="ceo-stats-home">
                  <div class="ceo-stat-item">
                    <i class="fas fa-trophy"></i>
                    <span>10+ Years Experience</span>
                  </div>
                  <div class="ceo-stat-item">
                    <i class="fas fa-globe"></i>
                    <span>International Expertise</span>
                  </div>
                  <div class="ceo-stat-item">
                    <i class="fas fa-certificate"></i>
                    <span>Certified Professional</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- CTA Section -->
    <div class="cta-section">
      <div class="cta-particles"></div>
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Transform Your Business?</h2>
          <p>Let's work together to create something extraordinary</p>
          <button class="btn-cta" @click="goToContact">
            Get Free Consultation <i class="fas fa-calendar-alt ms-2"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// Import local cover image
import coverImage from '../assets/photo1.jpeg'
// Import CEO image
import ceoImage from '../assets/ceo-image.png'

export default {
  name: 'HomeComponent',
  data() {
    return {
      coverImage: coverImage,
      ceoImage: ceoImage,
      typedWord: '',
      typedIndex: 0,
      typedWords: ['Digital Marketing', 'Video Production', 'System Development', 'Creative Solutions'],
      stats: [
        { icon: 'fas fa-project-diagram', label: 'Projects Completed', suffix: '+', progress: '78%', target: 148 },
        { icon: 'fas fa-users', label: 'Happy Clients', suffix: '+', progress: '85%', target: 112 },
        { icon: 'fas fa-calendar-alt', label: 'Years of Excellence', suffix: '', progress: '92%', target: 3 }
      ],
      services: [
        { 
          icon: 'fas fa-chart-line', 
          title: 'Digital Marketing', 
          description: 'Data-driven strategies that maximize ROI',
          fullDescription: 'SEO, PPC, social media marketing, content strategy, and analytics that deliver measurable results.',
          image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=600&h=400&fit=crop'
        },
        { 
          icon: 'fas fa-video', 
          title: 'Video Production', 
          description: 'Cinematic storytelling that captures your brand',
          fullDescription: 'Commercials, explainer videos, corporate films, motion graphics, and drone footage.',
          image: 'https://images.unsplash.com/photo-1492691527719-9d1e07e534b4?w=600&h=400&fit=crop'
        },
        { 
          icon: 'fas fa-code', 
          title: 'System Development', 
          description: 'Custom software solutions tailored to your needs',
          fullDescription: 'Web applications, mobile apps, ERP systems, and cloud-based platforms.',
          image: 'https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=600&h=400&fit=crop'
        },
        { 
          icon: 'fas fa-paint-brush', 
          title: 'Creative Design', 
          description: 'Stunning visuals that leave lasting impressions',
          fullDescription: 'Brand identity, UI/UX design, logos, brochures, and marketing materials.',
          image: 'https://images.unsplash.com/photo-1561070791-2526d30994b5?w=600&h=400&fit=crop'
        },
        { 
          icon: 'fas fa-cloud-upload-alt', 
          title: 'Cloud Solutions', 
          description: 'Scalable cloud infrastructure for modern business',
          fullDescription: 'AWS/Azure deployment, cloud migration, DevOps, and managed hosting.',
          image: 'https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=600&h=400&fit=crop'
        },
        { 
          icon: 'fas fa-headset', 
          title: '24/7 Support', 
          description: 'Round-the-clock technical assistance',
          fullDescription: 'Technical support, maintenance, monitoring, and rapid response team.',
          image: 'https://images.unsplash.com/photo-1541746972996-4e0b0f43e02a?w=600&h=400&fit=crop'
        }
      ]
    }
  },
  mounted() {
    this.startTypingAnimation()
    this.observeStats()
    // Wait for DOM to be fully rendered before animating numbers
    this.$nextTick(() => {
      this.animateNumbers()
    })
  },
  methods: {
    animateNumbers() {
      for (let i = 0; i < this.stats.length; i++) {
        const counterElement = document.getElementById(`statCounter${i}`)
        if (counterElement) {
          let current = 0
          const target = this.stats[i].target
          const step = Math.ceil(target / 60)
          const interval = setInterval(() => {
            current += step
            if (current >= target) {
              counterElement.innerText = target
              clearInterval(interval)
            } else {
              counterElement.innerText = current
            }
          }, 35)
        }
      }
    },
    startTypingAnimation() {
      setInterval(() => {
        this.typedIndex = (this.typedIndex + 1) % this.typedWords.length
        this.typeWord()
      }, 4000)
      this.typeWord()
    },
    typeWord() {
      const word = this.typedWords[this.typedIndex]
      let i = 0
      this.typedWord = ''
      const interval = setInterval(() => {
        if (i < word.length) {
          this.typedWord += word[i]
          i++
        } else {
          clearInterval(interval)
        }
      }, 120)
    },
    observeStats() {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible')
          }
        })
      }, { threshold: 0.3 })
      
      const statCards = document.querySelectorAll('.stat-card')
      statCards.forEach(card => observer.observe(card))
    },
    // Navigation methods that work with the parent App component
    goToServices() {
      // Try multiple methods to ensure navigation works
      if (this.$parent && typeof this.$parent.navigate === 'function') {
        this.$parent.navigate('services')
        return
      }
      
      // Fallback: change hash directly
      window.location.hash = 'services'
      window.scrollTo({ top: 0, behavior: 'smooth' })
    },
    goToContact() {
      if (this.$parent && typeof this.$parent.navigate === 'function') {
        this.$parent.navigate('contact')
        return
      }
      window.location.hash = 'contact'
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
.home-container {
  overflow-x: hidden;
}

/* Hero Section with Cover Image */
.hero-section-wrapper {
  position: relative;
  min-height: 85vh;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  border-radius: 0 0 60px 60px;
  margin-bottom: 60px;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  transform: scale(1.05);
  transition: transform 12s cubic-bezier(0.4, 0, 0.2, 1);
}

.hero-section-wrapper:hover .hero-background {
  transform: scale(1.12);
}

.hero-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.85) 0%, rgba(37, 99, 235, 0.75) 100%);
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
  text-align: center;
  padding: 60px 20px;
  max-width: 900px;
  margin: 0 auto;
  animation: fadeInUp 1.2s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  padding: 8px 20px;
  border-radius: 50px;
  font-size: 0.85rem;
  font-weight: 500;
  color: white;
  margin-bottom: 30px;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.badge-pulse {
  width: 10px;
  height: 10px;
  background: #10b981;
  border-radius: 50%;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.4; transform: scale(1.3); }
}

.hero-title {
  font-size: 4rem;
  font-weight: 800;
  margin-bottom: 20px;
  line-height: 1.2;
}

.title-gradient {
  background: linear-gradient(135deg, #fff, #94a3b8, #2563eb);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  display: inline-block;
  animation: titleGlow 4s ease-in-out infinite;
}

@keyframes titleGlow {
  0%, 100% { text-shadow: 0 0 20px rgba(37, 99, 235, 0.3); }
  50% { text-shadow: 0 0 50px rgba(37, 99, 235, 0.7); }
}

.typed-text {
  font-size: 1.5rem;
  margin-bottom: 25px;
}

.typed-prefix {
  color: #cbd5e1;
}

.typed-words {
  color: #2563eb;
  font-weight: 700;
  border-right: 3px solid #2563eb;
  animation: blink 0.8s step-end infinite;
  margin-left: 10px;
}

@keyframes blink {
  from, to { border-color: transparent; }
  50% { border-color: #2563eb; }
}

.hero-description {
  font-size: 1.1rem;
  color: #e2e8f0;
  margin-bottom: 35px;
  line-height: 1.6;
}

.hero-buttons {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 50px;
  flex-wrap: wrap;
}

.btn-primary-glow {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 14px 32px;
  border-radius: 50px;
  font-weight: 600;
  color: white;
  transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
  box-shadow: 0 0 20px rgba(37, 99, 235, 0.4);
}

.btn-primary-glow:hover {
  transform: translateY(-4px);
  box-shadow: 0 0 35px rgba(37, 99, 235, 0.7);
}

.btn-outline-light {
  background: transparent;
  border: 2px solid white;
  padding: 14px 32px;
  border-radius: 50px;
  font-weight: 600;
  color: white;
  transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

.btn-outline-light:hover {
  background: white;
  color: #0f172a;
  transform: translateY(-4px);
}

.hero-stats {
  display: flex;
  gap: 40px;
  justify-content: center;
  flex-wrap: wrap;
}

.hero-stat {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #cbd5e1;
  font-size: 0.9rem;
}

.hero-stat i {
  color: #2563eb;
  font-size: 1.1rem;
}

.hero-scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  z-index: 3;
  animation: bounce 2.5s ease-in-out infinite;
}

@keyframes bounce {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(12px); }
}

.mouse {
  width: 26px;
  height: 42px;
  border: 2px solid white;
  border-radius: 20px;
  position: relative;
}

.mouse::after {
  content: '';
  width: 4px;
  height: 8px;
  background: white;
  position: absolute;
  top: 8px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 2px;
  animation: scroll 2s ease-in-out infinite;
}

@keyframes scroll {
  0% { opacity: 1; transform: translateX(-50%) translateY(0); }
  100% { opacity: 0; transform: translateX(-50%) translateY(18px); }
}

.arrow-down {
  width: 10px;
  height: 10px;
  border-right: 2px solid white;
  border-bottom: 2px solid white;
  transform: rotate(45deg);
}

/* Stats Section */
.stats-section {
  padding: 40px 0 80px;
  background: linear-gradient(180deg, #f8fafc 0%, #ffffff 100%);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 30px;
}

.stat-card {
  background: white;
  border-radius: 24px;
  padding: 30px;
  text-align: center;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
  position: relative;
  overflow: hidden;
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

.stat-card.visible {
  opacity: 1;
  transform: translateY(0);
}

.stat-card:hover {
  transform: translateY(-12px);
  box-shadow: 0 35px 50px -18px rgba(37, 99, 235, 0.2);
}

.stat-icon {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, #eef2ff, #fff);
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
  font-size: 2rem;
  color: #2563eb;
}

.stat-number-wrapper {
  display: flex;
  align-items: baseline;
  justify-content: center;
  gap: 5px;
  margin-bottom: 10px;
}

.stat-number {
  font-size: 3rem;
  font-weight: 800;
  color: #0f172a;
  line-height: 1;
}

.stat-suffix {
  font-size: 1.8rem;
  font-weight: 700;
  color: #2563eb;
}

.stat-label {
  font-size: 1rem;
  font-weight: 500;
  color: #64748b;
  margin-bottom: 15px;
}

.stat-progress {
  height: 4px;
  background: #e2e8f0;
  border-radius: 2px;
  overflow: hidden;
}

.progress-bar {
  height: 100%;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  border-radius: 2px;
  transition: width 1.5s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

/* Services Section */
.services-section {
  padding: 80px 0;
  background: #f8fafc;
}

.section-header {
  text-align: center;
  margin-bottom: 60px;
}

.section-subtitle {
  display: inline-block;
  background: linear-gradient(135deg, #2563eb20, #7c3aed20);
  padding: 6px 16px;
  border-radius: 30px;
  font-size: 0.8rem;
  font-weight: 600;
  color: #2563eb;
  margin-bottom: 15px;
}

.section-title-glass {
  font-size: 2.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, #0f172a, #2563eb);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  margin-bottom: 15px;
}

.section-description {
  color: #64748b;
  font-size: 1.1rem;
  max-width: 600px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 30px;
}

.service-card-premium {
  position: relative;
  width: 100%;
  height: 380px;
  cursor: pointer;
  perspective: 1500px;
}

.service-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.7s cubic-bezier(0.2, 0.9, 0.4, 1.2);
  transition-delay: 0.55s;
  transform-style: preserve-3d;
  border-radius: 28px;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.1);
}

.service-card-premium:hover .service-card-inner {
  transform: rotateY(180deg);
  transition-delay: 0s;
}

.service-front, .service-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  border-radius: 28px;
  overflow: hidden;
}

.service-front {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.service-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.75) 0%, rgba(37, 99, 235, 0.85) 100%);
  z-index: 1;
  transition: all 0.4s ease;
}

.service-card-premium:hover .service-overlay {
  background: linear-gradient(135deg, rgba(0, 0, 0, 0.85) 0%, rgba(37, 99, 235, 0.95) 100%);
}

.service-content {
  position: relative;
  z-index: 2;
  text-align: center;
  padding: 35px 25px;
  color: white;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.service-back {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  color: white;
  transform: rotateY(180deg);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 30px;
}

.service-back-desc {
  font-size: 0.85rem;
  margin: 15px 0;
  opacity: 0.9;
  line-height: 1.6;
}

.service-icon-animated {
  position: relative;
  width: 80px;
  height: 80px;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2.2rem;
  color: white;
  margin: 0 auto 20px;
  transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.2);
}

.service-card-premium:hover .service-icon-animated {
  animation: iconBounce 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.2);
  transform: scale(1.05);
}

@keyframes iconBounce {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.12); }
}

.icon-pulse {
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 30px;
  background: rgba(255, 255, 255, 0.3);
  animation: iconPulse 2.5s ease-in-out infinite;
}

@keyframes iconPulse {
  0% { transform: scale(1); opacity: 0.4; }
  100% { transform: scale(1.5); opacity: 0; }
}

.service-front h3 {
  font-size: 1.4rem;
  margin-bottom: 12px;
  font-weight: 700;
}

.service-front p {
  font-size: 0.9rem;
  opacity: 0.9;
  line-height: 1.5;
}

.service-hover-line {
  width: 0;
  height: 3px;
  background: white;
  border-radius: 3px;
  margin: 20px auto 0;
  transition: width 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
}

.service-card-premium:hover .service-hover-line {
  width: 60px;
}

.service-back i {
  font-size: 3rem;
  margin-bottom: 20px;
  animation: fadeInUp 0.5s ease;
}

.service-back h4 {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.btn-service {
  background: white;
  border: none;
  padding: 10px 28px;
  border-radius: 30px;
  font-weight: 600;
  color: #2563eb;
  transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.1);
  margin-top: 15px;
  cursor: pointer;
}

.btn-service:hover {
  transform: translateX(6px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

/* CEO Home Section - Premium */
.ceo-home-section {
  padding: 80px 0;
  background: linear-gradient(135deg, #f8fafc, #ffffff);
}

.ceo-home-wrapper {
  background: white;
  border-radius: 40px;
  padding: 50px;
  box-shadow: 0 25px 45px -12px rgba(0, 0, 0, 0.1);
  position: relative;
  overflow: hidden;
}

.ceo-home-wrapper::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -20%;
  width: 300px;
  height: 300px;
  background: radial-gradient(circle, rgba(37, 99, 235, 0.05), transparent);
  border-radius: 50%;
}

.ceo-home-image {
  text-align: center;
  position: relative;
}

.ceo-image-circle {
  width: 250px;
  height: 250px;
  margin: 0 auto;
  border-radius: 50%;
  overflow: hidden;
  border: 4px solid white;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.2);
  position: relative;
}

.ceo-image-circle img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.ceo-image-glow {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: radial-gradient(circle at 30% 30%, rgba(37, 99, 235, 0.3), transparent);
  pointer-events: none;
}

.ceo-badge-home {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  padding: 8px 20px;
  border-radius: 30px;
  margin-top: 20px;
  font-size: 0.85rem;
  font-weight: 600;
  color: white;
}

.ceo-home-content {
  position: relative;
  padding: 20px;
}

.ceo-quote-icon {
  font-size: 3rem;
  color: #2563eb;
  opacity: 0.2;
  margin-bottom: 10px;
}

.ceo-home-name {
  font-size: 2rem;
  font-weight: 800;
  color: #0f172a;
  margin-bottom: 5px;
}

.ceo-home-title {
  font-size: 1rem;
  color: #2563eb;
  font-weight: 600;
  margin-bottom: 20px;
}

.ceo-divider {
  width: 60px;
  height: 3px;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  border-radius: 3px;
  margin-bottom: 20px;
}

.ceo-home-message {
  font-size: 1rem;
  line-height: 1.7;
  color: #475569;
  margin-bottom: 25px;
  font-style: italic;
}

.ceo-signature-line {
  margin-bottom: 25px;
  padding-top: 10px;
  border-top: 1px solid #e2e8f0;
}

.signature-name {
  font-size: 1.1rem;
  font-weight: 700;
  color: #0f172a;
  display: block;
}

.signature-title {
  font-size: 0.8rem;
  color: #64748b;
}

.ceo-stats-home {
  display: flex;
  gap: 25px;
  flex-wrap: wrap;
}

.ceo-stat-item {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.85rem;
  color: #475569;
}

.ceo-stat-item i {
  color: #10b981;
}

/* CTA Section */
.cta-section {
  position: relative;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  margin: 0;
  padding: 80px 0;
  overflow: hidden;
}

.cta-particles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: radial-gradient(circle at 20% 50%, rgba(37, 99, 235, 0.15) 2px, transparent 2px);
  background-size: 35px 35px;
  animation: particleMove 25s linear infinite;
}

@keyframes particleMove {
  0% { background-position: 0 0; }
  100% { background-position: 70px 70px; }
}

.cta-content {
  text-align: center;
  position: relative;
  z-index: 2;
}

.cta-content h2 {
  font-size: 2.5rem;
  font-weight: 800;
  color: white;
  margin-bottom: 15px;
}

.cta-content p {
  font-size: 1.1rem;
  color: #cbd5e1;
  margin-bottom: 30px;
}

.btn-cta {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 16px 40px;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1rem;
  color: white;
  transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.1);
  box-shadow: 0 10px 30px rgba(37, 99, 235, 0.3);
}

.btn-cta:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 45px rgba(37, 99, 235, 0.5);
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.floating {
  animation: float 4s cubic-bezier(0.4, 0, 0.2, 1) infinite;
}

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-12px); }
}

/* Responsive */
@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }
  
  .typed-text {
    font-size: 1rem;
  }
  
  .hero-description {
    font-size: 0.9rem;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .section-title-glass {
    font-size: 1.8rem;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .cta-content h2 {
    font-size: 1.8rem;
  }
  
  .service-card-premium {
    height: 360px;
  }
  
  .ceo-home-wrapper {
    padding: 30px;
  }
  
  .ceo-home-name {
    font-size: 1.5rem;
  }
  
  .ceo-image-circle {
    width: 180px;
    height: 180px;
    margin-bottom: 20px;
  }
  
  .ceo-stats-home {
    justify-content: center;
  }
}
</style>