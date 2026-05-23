<template>
  <div>
    <!-- Navigation Bar - Professional & Modern -->
    <nav class="navbar navbar-expand-lg sticky-top glass-nav">
      <div class="container">
        <!-- Logo Area with Circular Image -->
        <a class="navbar-brand" href="#" @click.prevent="navigate('home')">
          <div class="logo-wrapper">
            <div class="logo-circle">
              <img :src="logoPath" alt="Kedesh Logo" class="logo-image" @error="handleImageError">
            </div>
            <div class="logo-text">
              <span class="logo-main">KEDESH</span>
              <span class="logo-sub">LIMITED</span>
            </div>
          </div>
        </a>
        
        <button class="navbar-toggler custom-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mainNavbar">
          <span class="navbar-toggler-icon"></span>
        </button>
        
        <div class="collapse navbar-collapse" id="mainNavbar">
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item" v-for="item in navItems" :key="item.page">
              <a 
                class="nav-link" 
                :class="{ active: currentPage === item.page }" 
                href="#" 
                @click.prevent="navigate(item.page)"
              >
                <span class="nav-link-text">{{ item.label }}</span>
                <span class="nav-link-indicator"></span>
              </a>
            </li>
            <li class="nav-item ms-lg-2">
              <button class="btn-consultation" @click.prevent="navigate('contact')">
                Get Consultation <i class="fas fa-arrow-right ms-2"></i>
              </button>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Main Content with Transition -->
    <main class="main-content">
      <div class="container py-5">
        <transition name="fade" mode="out-in">
          <component :is="currentComponent" :key="currentPage" />
        </transition>
      </div>
    </main>

    <!-- Footer - Premium Design -->
    <footer class="footer premium-footer">
      <div class="footer-wave">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 120">
          <path fill="#0f1729" fill-opacity="1" d="M0,64L80,69.3C160,75,320,85,480,80C640,75,800,53,960,48C1120,43,1280,53,1360,58.7L1440,64L1440,120L1360,120C1280,120,1120,120,960,120C800,120,640,120,480,120C320,120,160,120,80,120L0,120Z"></path>
        </svg>
      </div>
      <div class="footer-main">
        <div class="container">
          <div class="row g-5">
            <!-- Company Info with Circular Logo -->
            <div class="col-lg-4 col-md-6">
              <div class="footer-brand">
                <div class="footer-logo">
                  <div class="footer-logo-circle">
                    <img :src="logoPath" alt="Kedesh Logo" class="footer-logo-image" @error="handleImageError">
                  </div>
                  <div>
                    <div class="footer-logo-text">KEDESH LIMITED</div>
                    <div class="footer-tagline">Innovation & Excellence</div>
                  </div>
                </div>
                <p class="footer-description">
                  Kedesh Limited ni kampuni inayoongoza katika kutoa huduma za digital marketing, 
                  uzalishaji wa video, na utengenezaji wa mifumo ya kisasa. Tunawawezesha biashara 
                  kufikia upeo wao wa ukuaji.
                </p>
                <div class="footer-cert">
                  <i class="fas fa-check-circle"></i> Registered No. 789012345
                </div>
              </div>
            </div>

            <!-- Quick Links -->
            <div class="col-lg-2 col-md-6">
              <h5 class="footer-title">Quick Links</h5>
              <ul class="footer-links">
                <li><a href="#" @click.prevent="navigate('home')"><i class="fas fa-chevron-right"></i> Home</a></li>
                <li><a href="#" @click.prevent="navigate('services')"><i class="fas fa-chevron-right"></i> Our Services</a></li>
                <li><a href="#" @click.prevent="navigate('about')"><i class="fas fa-chevron-right"></i> About Us</a></li>
                <li><a href="#" @click.prevent="navigate('contact')"><i class="fas fa-chevron-right"></i> Contact</a></li>
                <li><a href="#" @click.prevent="navigate('privacy')"><i class="fas fa-chevron-right"></i> Privacy Policy</a></li>
              </ul>
            </div>

            <!-- Contact Info -->
            <div class="col-lg-3 col-md-6">
              <h5 class="footer-title">Contact Info</h5>
              <ul class="footer-contact-list">
                <li>
                  <i class="fas fa-map-marker-alt"></i>
                  <span>Plot No. 123, Kikuyu Street<br>P.O. Box 456, Dodoma, Tanzania</span>
                </li>
                <li>
                  <i class="fas fa-phone-alt"></i>
                  <span>+255 752 128 096</span>
                </li>
                <li>
                  <i class="fas fa-envelope"></i>
                  <span>info@kedesh.co.tz</span>
                </li>
                <li>
                  <i class="fas fa-clock"></i>
                  <span>Mon - Fri: 8:30 AM - 5:30 PM</span>
                </li>
              </ul>
            </div>

            <!-- Newsletter & Social -->
            <div class="col-lg-3 col-md-6">
              <h5 class="footer-title">Stay Connected</h5>
              <p class="newsletter-text">Subscribe to get latest updates and offers</p>
              <div class="newsletter-form">
                <div class="input-group">
                  <input type="email" class="form-control" placeholder="Your email address" v-model="newsletterEmail">
                  <button class="btn-subscribe" @click="subscribeNewsletter">
                    <i class="fas fa-paper-plane"></i>
                  </button>
                </div>
              </div>
              <div class="social-section">
                <h5 class="footer-title mt-4">Follow Us</h5>
                <div class="social-icons">
                  <a href="#" class="social-icon" v-for="social in socialLinks" :key="social.name" :style="{ background: social.color }">
                    <i :class="social.icon"></i>
                  </a>
                </div>
              </div>
            </div>
          </div>

          <hr class="footer-divider">

          <div class="footer-bottom">
            <div class="row align-items-center">
              <div class="col-md-6">
                <p class="copyright">
                  &copy; {{ currentYear }} Kedesh Limited. All rights reserved. 
                  <span class="separator">|</span> 
                  <a href="#" @click.prevent="navigate('privacy')">Privacy Policy</a>
                </p>
              </div>
              <div class="col-md-6 text-md-end">
                <p class="credits">
                  Designed with <i class="fas fa-heart text-danger"></i> by CodeMotion co.ltd
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue'
import ServicesComponent from './components/ServicesComponent.vue'
import AboutComponent from './components/AboutComponent.vue'
import ContactComponent from './components/ContactComponent.vue'
import PrivacyComponent from './components/PrivacyComponent.vue'

// Option 1: Import logo (Recommended)
import logoImage from './assets/logo.png'

export default {
  name: 'App',
  components: {
    HomeComponent,
    ServicesComponent,
    AboutComponent,
    ContactComponent,
    PrivacyComponent
  },
  data() {
    return {
      currentPage: 'home',
      newsletterEmail: '',
      currentYear: new Date().getFullYear(),
      // Option 1: Use imported logo
      logoPath: logoImage,
      // Option 2: If logo not working, uncomment below and comment Option 1
      // logoPath: '/logo.png',
      // Option 3: Use online placeholder (temporary)
      // logoPath: 'https://ui-avatars.com/api/?background=2563eb&color=fff&size=100&rounded=true&bold=true&name=K',
      navItems: [
        { page: 'home', label: 'Home' },
        { page: 'services', label: 'Services' },
        { page: 'about', label: 'About' },
        { page: 'contact', label: 'Contact' }
      ],
      socialLinks: [
        { name: 'Facebook', icon: 'fab fa-facebook-f', color: '#1877f2' },
        { name: 'Twitter', icon: 'fab fa-twitter', color: '#1da1f2' },
        { name: 'LinkedIn', icon: 'fab fa-linkedin-in', color: '#0077b5' },
        { name: 'Instagram', icon: 'fab fa-instagram', color: '#e4405f' },
        { name: 'YouTube', icon: 'fab fa-youtube', color: '#ff0000' }
      ]
    }
  },
  computed: {
    currentComponent() {
      const components = {
        home: HomeComponent,
        services: ServicesComponent,
        about: AboutComponent,
        contact: ContactComponent,
        privacy: PrivacyComponent
      }
      return components[this.currentPage] || HomeComponent
    }
  },
  methods: {
    navigate(page) {
      this.currentPage = page
      window.location.hash = page
      window.scrollTo({ top: 0, behavior: 'smooth' })
    },
    handleHashChange() {
      const hash = window.location.hash.slice(1)
      if (['home', 'services', 'about', 'contact', 'privacy'].includes(hash)) {
        this.currentPage = hash
      } else {
        this.currentPage = 'home'
      }
    },
    subscribeNewsletter() {
      if (this.newsletterEmail && this.newsletterEmail.includes('@')) {
        alert(`Thank you for subscribing! We'll send updates to ${this.newsletterEmail}`)
        this.newsletterEmail = ''
      } else {
        alert('Please enter a valid email address')
      }
    },
    handleImageError(e) {
      // If logo fails to load, show fallback
      e.target.src = 'https://ui-avatars.com/api/?background=2563eb&color=fff&size=100&rounded=true&bold=true&name=K'
    }
  },
  mounted() {
    window.addEventListener('hashchange', this.handleHashChange)
    this.handleHashChange()
  },
  beforeUnmount() {
    window.removeEventListener('hashchange', this.handleHashChange)
  }
}
</script>

<style scoped>
.main-content {
  min-height: 70vh;
}

/* Modern Navigation Styles */
.glass-nav {
  background: rgba(15, 23, 42, 0.98);
  backdrop-filter: blur(12px);
  padding: 0.8rem 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  transition: all 0.3s ease;
}

/* Circular Logo Styles - Header */
.logo-wrapper {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 8px 20px rgba(37, 99, 235, 0.3);
  transition: all 0.3s ease;
  overflow: hidden;
  border: 2px solid rgba(255, 255, 255, 0.2);
}

.logo-circle:hover {
  transform: scale(1.05) rotate(5deg);
  box-shadow: 0 12px 30px rgba(37, 99, 235, 0.5);
  border-color: rgba(255, 255, 255, 0.5);
}

.logo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
}

.logo-text {
  display: flex;
  flex-direction: column;
  line-height: 1.2;
}

.logo-main {
  font-size: 1.4rem;
  font-weight: 800;
  letter-spacing: -0.5px;
  background: linear-gradient(135deg, #ffffff, #94a3b8);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.logo-sub {
  font-size: 0.65rem;
  font-weight: 500;
  letter-spacing: 1.5px;
  color: #94a3b8;
}

.nav-item {
  margin: 0 4px;
}

.nav-link {
  position: relative;
  padding: 8px 16px !important;
  font-weight: 600;
  font-size: 0.95rem;
  color: #e2e8f0;
  transition: all 0.3s ease;
}

.nav-link .nav-link-text {
  position: relative;
  z-index: 1;
}

.nav-link .nav-link-indicator {
  position: absolute;
  bottom: -2px;
  left: 50%;
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  border-radius: 3px;
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover {
  color: white;
}

.nav-link:hover .nav-link-indicator {
  width: 70%;
}

.nav-link.active {
  color: white;
}

.nav-link.active .nav-link-indicator {
  width: 70%;
}

.btn-consultation {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 8px 24px;
  border-radius: 30px;
  font-weight: 600;
  font-size: 0.9rem;
  color: white;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
}

.btn-consultation:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(37, 99, 235, 0.4);
}

.custom-toggler {
  border: none;
  background: rgba(255, 255, 255, 0.1);
}

.custom-toggler:focus {
  box-shadow: none;
}

/* Premium Footer Styles */
.premium-footer {
  margin-top: 60px;
  background: #0f1729;
  color: #e2e8f0;
  position: relative;
}

.footer-wave {
  position: absolute;
  top: -60px;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.footer-main {
  padding-top: 60px;
  padding-bottom: 30px;
  position: relative;
}

.footer-brand {
  margin-bottom: 20px;
}

/* Circular Logo Styles - Footer */
.footer-logo {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 20px;
}

.footer-logo-circle {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  border: 2px solid rgba(37, 99, 235, 0.5);
  transition: all 0.3s ease;
}

.footer-logo-circle:hover {
  transform: scale(1.05);
  border-color: #2563eb;
  box-shadow: 0 0 20px rgba(37, 99, 235, 0.4);
}

.footer-logo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.footer-logo-text {
  font-size: 1.3rem;
  font-weight: 800;
  letter-spacing: -0.5px;
  background: linear-gradient(135deg, #ffffff, #94a3b8);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.footer-tagline {
  font-size: 0.7rem;
  color: #94a3b8;
  letter-spacing: 1px;
}

.footer-description {
  font-size: 0.85rem;
  line-height: 1.6;
  color: #94a3b8;
  margin-bottom: 15px;
}

.footer-cert {
  font-size: 0.75rem;
  color: #2563eb;
  padding: 5px 12px;
  background: rgba(37, 99, 235, 0.1);
  border-radius: 20px;
  display: inline-block;
}

.footer-title {
  font-size: 1.1rem;
  font-weight: 700;
  margin-bottom: 20px;
  position: relative;
  padding-bottom: 10px;
}

.footer-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 40px;
  height: 3px;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  border-radius: 3px;
}

.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin-bottom: 12px;
}

.footer-links li a {
  color: #94a3b8;
  text-decoration: none;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.9rem;
}

.footer-links li a i {
  font-size: 0.7rem;
  transition: transform 0.3s ease;
}

.footer-links li a:hover {
  color: white;
  transform: translateX(5px);
}

.footer-links li a:hover i {
  transform: translateX(3px);
}

.footer-contact-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-contact-list li {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  margin-bottom: 15px;
  font-size: 0.85rem;
  color: #94a3b8;
}

.footer-contact-list li i {
  margin-top: 3px;
  color: #2563eb;
  font-size: 1rem;
}

.newsletter-text {
  font-size: 0.8rem;
  color: #94a3b8;
  margin-bottom: 15px;
}

.newsletter-form .input-group {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 30px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.newsletter-form .form-control {
  background: transparent;
  border: none;
  color: white;
  padding: 12px 18px;
}

.newsletter-form .form-control::placeholder {
  color: #64748b;
}

.newsletter-form .form-control:focus {
  box-shadow: none;
  background: transparent;
}

.btn-subscribe {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 0 20px;
  color: white;
  transition: all 0.3s ease;
}

.btn-subscribe:hover {
  opacity: 0.9;
}

.social-icons {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.social-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  text-decoration: none;
  transition: all 0.3s ease;
  font-size: 1.1rem;
}

.social-icon:hover {
  transform: translateY(-5px);
  filter: brightness(1.1);
}

.footer-divider {
  margin: 40px 0 30px;
  border-color: rgba(255, 255, 255, 0.05);
}

.footer-bottom {
  padding-top: 10px;
}

.copyright {
  font-size: 0.8rem;
  color: #64748b;
  margin: 0;
}

.copyright a {
  color: #64748b;
  text-decoration: none;
  transition: color 0.3s ease;
}

.copyright a:hover {
  color: #2563eb;
}

.separator {
  margin: 0 8px;
}

.credits {
  font-size: 0.8rem;
  color: #64748b;
  margin: 0;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .glass-nav {
    padding: 0.5rem 0;
  }
  
  .logo-main {
    font-size: 1.1rem;
  }
  
  .logo-circle {
    width: 40px;
    height: 40px;
  }
  
  .btn-consultation {
    margin-top: 10px;
    width: 100%;
    text-align: center;
  }
  
  .footer-wave {
    top: -40px;
  }
  
  .footer-main {
    padding-top: 40px;
  }
  
  .footer-bottom {
    text-align: center;
  }
  
  .credits {
    text-align: center;
    margin-top: 10px;
  }
  
  .footer-logo-circle {
    width: 50px;
    height: 50px;
  }
}
</style>