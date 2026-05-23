<template>
  <div class="about-component">
    <!-- Hero Section -->
    <div class="about-hero">
      <div class="about-hero-content">
        <div class="hero-badge">
          <i class="fas fa-building"></i>
          <span>Registered Company</span>
        </div>
        <h2 class="about-title">About <span class="highlight">Kedesh Limited</span></h2>
        <p class="about-subtitle">Innovation & Excellence Since 2024</p>
      </div>
    </div>

    <div class="container">
      <!-- Company Overview - Premium Redesign -->
      <div class="company-overview">
        <div class="row g-4">
          <div class="col-lg-7">
            <div class="overview-card">
              <div class="overview-header">
                <div class="overview-icon">
                  <i class="fas fa-building"></i>
                </div>
                <h3 class="overview-title">Company Profile</h3>
              </div>
              <p class="overview-text">
                <strong>Kedesh Limited</strong> (Registration No. <span class="reg-number">178821040</span>) 
                is a legally registered company under the Companies Act, 2002 of Tanzania. Incorporated on 
                <strong class="date-highlight">15th October 2024</strong>, Kedesh Limited specializes in 
                digital marketing, video production, and intelligent system development. We serve clients 
                across East Africa and internationally, delivering cutting-edge solutions that drive business growth.
              </p>
              <div class="overview-features">
                <div class="feature-item">
                  <i class="fas fa-check-circle"></i>
                  <span>Fully Registered & Compliant</span>
                </div>
                <div class="feature-item">
                  <i class="fas fa-check-circle"></i>
                  <span>Expert Team of Professionals</span>
                </div>
                <div class="feature-item">
                  <i class="fas fa-check-circle"></i>
                  <span>Client-Focused Approach</span>
                </div>
              </div>
              <div class="license-badge">
                <i class="fas fa-certificate"></i>
                <span>Certificate of Incorporation No: 178821040</span>
              </div>
            </div>
          </div>
          <div class="col-lg-5">
            <div class="stats-card-modern">
              <div class="stats-header">
                <i class="fas fa-chart-line"></i>
                <span>Key Metrics</span>
              </div>
              <div class="stats-grid-modern">
                <div class="stat-item-modern" v-for="(stat, index) in companyStats" :key="index">
                  <div class="stat-ring">
                    <svg width="80" height="80" viewBox="0 0 120 120">
                      <circle cx="60" cy="60" r="50" fill="none" stroke="#e2e8f0" stroke-width="8"/>
                      <circle cx="60" cy="60" r="50" fill="none" :stroke="stat.color" stroke-width="8" 
                              :stroke-dasharray="circumference" 
                              :stroke-dashoffset="circumference - (stat.percentage / 100) * circumference"
                              stroke-linecap="round"
                              transform="rotate(-90 60 60)"/>
                    </svg>
                    <div class="stat-number-inner">{{ stat.value }}</div>
                  </div>
                  <div class="stat-info">
                    <h4>{{ stat.label }}</h4>
                    <p>{{ stat.description }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Vision & Mission -->
      <div class="vision-mission-section">
        <div class="row g-4">
          <div class="col-md-6">
            <div class="vision-card">
              <div class="card-icon">
                <i class="fas fa-eye"></i>
              </div>
              <h3>Our Vision</h3>
              <p>To become the leading digital transformation enabler in East Africa, empowering businesses through innovative technology and creative solutions.</p>
              <div class="card-footer-line"></div>
            </div>
          </div>
          <div class="col-md-6">
            <div class="mission-card">
              <div class="card-icon">
                <i class="fas fa-bullseye"></i>
              </div>
              <h3>Our Mission</h3>
              <p>To deliver exceptional digital solutions that combine creativity, technology, and strategic insight to help our clients achieve sustainable growth.</p>
              <div class="card-footer-line"></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Core Values -->
      <div class="values-section">
        <div class="section-header">
          <span class="section-badge">Core Principles</span>
          <h3>Our Core Values</h3>
          <p>The foundation of everything we do</p>
        </div>
        <div class="row g-4">
          <div class="col-md-3 col-sm-6" v-for="value in coreValues" :key="value.title">
            <div class="value-card">
              <div class="value-icon" :style="{ background: value.gradient }">
                <i :class="value.icon"></i>
              </div>
              <h4>{{ value.title }}</h4>
              <p>{{ value.description }}</p>
            </div>
          </div>
        </div>
      </div>

      <!-- CEO Section -->
      <div class="ceo-section">
        <div class="row align-items-center">
          <div class="col-lg-4">
            <div class="ceo-image-wrapper">
              <div class="ceo-image-frame">
                <img :src="ceoImage" alt="CEO - Israel Gilbert Salimu" class="ceo-image">
                <div class="ceo-glow"></div>
              </div>
              <div class="ceo-social">
                <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
              </div>
            </div>
          </div>
          <div class="col-lg-8">
            <div class="ceo-content">
              <div class="ceo-badge">
                <i class="fas fa-crown"></i>
                <span>Chief Executive Officer</span>
              </div>
              <h2 class="ceo-name">Israel Gilbert Salimu</h2>
              <div class="ceo-title-line"></div>
              <p class="ceo-message">
                "At Kedesh Limited, we believe in the power of innovation to transform businesses. 
                Our commitment to excellence drives us to deliver solutions that not only meet but 
                exceed our clients' expectations. We're building the future of digital business in Africa."
              </p>
              <div class="ceo-signature">
                <i class="fas fa-quote-right"></i>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Location & Map Section -->
      <div class="location-section">
        <div class="section-header">
          <span class="section-badge">Visit Us</span>
          <h3>Our Location</h3>
          <p>Find us at our headquarters in Dodoma, Tanzania</p>
        </div>
        <div class="row g-4">
          <div class="col-lg-5">
            <div class="location-card">
              <div class="location-icon">
                <i class="fas fa-map-marker-alt"></i>
              </div>
              <h4>Headquarters</h4>
              <p class="location-address">
                DODOMA, Dodoma Mjini<br>
                Ward - Kizota <br>
                Street - Sokoine<br>
                Tanzania, East Africa
              </p>
              <div class="contact-info">
                <div class="contact-item">
                  <i class="fas fa-phone-alt"></i>
                  <span>+255 752 128 096</span>
                </div>
                <div class="contact-item">
                  <i class="fas fa-envelope"></i>
                  <span>info@kedeshlimited.com</span>
                </div>
                <div class="contact-item">
                  <i class="fas fa-clock"></i>
                  <span>Mon - Sat: 8:00 AM - 6:00 PM</span>
                </div>
              </div>
              <div class="license-info">
                <i class="fas fa-file-certificate"></i>
                <div>
                  <strong>License Information:</strong><br>
                  Certificate No: 178821040<br>
                  Companies Act, 2002
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-7">
            <div class="map-card">
              <div class="map-wrapper">
                <iframe 
                  src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d126706.09445926883!2d35.701302!3d-6.162959!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x184d3b6c8b6b6b6b%3A0x6b6b6b6b6b6b6b6b!2sDodoma%2C%20Tanzania!5e0!3m2!1sen!2s!4v1700000000000!5m2!1sen!2s" 
                  width="100%" 
                  height="400" 
                  style="border:0; border-radius: 24px;" 
                  allowfullscreen="" 
                  loading="lazy" 
                  referrerpolicy="no-referrer-when-downgrade">
                </iframe>
              </div>
              <div class="map-note">
                <i class="fas fa-info-circle"></i>
                Located in the heart of Dodoma, near major business districts
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- License & Compliance Section -->
      <div class="compliance-section">
        <div class="row g-4">
          <div class="col-md-6">
            <div class="compliance-card">
              <i class="fas fa-gavel"></i>
              <h4>Regulatory Compliance</h4>
              <p>Fully compliant with the Companies Act, 2002 of Tanzania. Our license is conspicuously displayed at our place of business as required by law.</p>
              <div class="compliance-note">
                <i class="fas fa-check-circle"></i>
                Renewal applications submitted within 21 days of license expiry
              </div>
            </div>
          </div>
          <div class="col-md-6">
            <div class="compliance-card">
              <i class="fas fa-shield-alt"></i>
              <h4>Our Commitment</h4>
              <p>We operate with transparency, integrity, and full adherence to Tanzanian business regulations and international standards.</p>
              <div class="compliance-note">
                <i class="fas fa-check-circle"></i>
                Certificate of Incorporation No: 178821040
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ceoImage from '../assets/ceo-image.png'

export default {
  name: 'AboutComponent',
  data() {
    return {
      ceoImage: ceoImage,
      circumference: 2 * Math.PI * 50,
      companyStats: [
        { 
          value: '2024', 
          label: 'Year Established', 
          description: 'Founded with excellence',
          percentage: 100,
          color: '#2563eb'
        },
        { 
          value: '98%', 
          label: 'Client Satisfaction', 
          description: 'Happy clients worldwide',
          percentage: 98,
          color: '#7c3aed'
        },
        { 
          value: '150+', 
          label: 'Projects Done', 
          description: 'Successful deliveries',
          percentage: 85,
          color: '#f59e0b'
        }
      ],
      coreValues: [
        { 
          title: 'Integrity', 
          icon: 'fas fa-handshake',
          gradient: 'linear-gradient(135deg, #2563eb, #3b82f6)',
          description: 'We operate with honesty, transparency, and ethical practices in all our dealings.'
        },
        { 
          title: 'Innovation', 
          icon: 'fas fa-lightbulb',
          gradient: 'linear-gradient(135deg, #7c3aed, #8b5cf6)',
          description: 'Constantly pushing boundaries to deliver cutting-edge solutions.'
        },
        { 
          title: 'Excellence', 
          icon: 'fas fa-trophy',
          gradient: 'linear-gradient(135deg, #f59e0b, #fbbf24)',
          description: 'Committed to delivering nothing but the highest quality service.'
        },
        { 
          title: 'Client-Centric', 
          icon: 'fas fa-heart',
          gradient: 'linear-gradient(135deg, #ef4444, #f87171)',
          description: 'Your success is our success. We prioritize client satisfaction.'
        }
      ]
    }
  }
}
</script>

<style scoped>
.about-component {
  width: 100%;
  overflow-x: hidden;
}

/* Hero Section */
.about-hero {
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
  border-radius: 0 0 60px 60px;
  padding: 60px 20px 80px;
  margin-bottom: 60px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.about-hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 200 200"><path fill="rgba(37,99,235,0.05)" d="M0 0h200v200H0z"/><circle cx="100" cy="100" r="80" fill="none" stroke="rgba(37,99,235,0.1)" stroke-width="2"/></svg>') repeat;
  pointer-events: none;
}

.about-hero-content {
  position: relative;
  z-index: 2;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  padding: 8px 20px;
  border-radius: 50px;
  margin-bottom: 25px;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.hero-badge i, .hero-badge span {
  color: white;
  font-size: 0.85rem;
}

.about-title {
  font-size: 3rem;
  font-weight: 800;
  color: white;
  margin-bottom: 15px;
}

.about-title .highlight {
  background: linear-gradient(135deg, #60a5fa, #a78bfa);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.about-subtitle {
  font-size: 1.1rem;
  color: #94a3b8;
}

/* Company Overview - Premium Redesign */
.company-overview {
  margin-bottom: 60px;
}

.overview-card {
  background: white;
  border-radius: 32px;
  padding: 36px;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.08);
  height: 100%;
  transition: all 0.3s ease;
}

.overview-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 30px 50px -15px rgba(37, 99, 235, 0.15);
}

.overview-header {
  display: flex;
  align-items: center;
  gap: 15px;
  margin-bottom: 25px;
}

.overview-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.overview-icon i {
  font-size: 1.8rem;
  color: white;
}

.overview-title {
  font-size: 1.6rem;
  font-weight: 700;
  color: #0f172a;
  margin: 0;
}

.overview-text {
  font-size: 1rem;
  line-height: 1.7;
  color: #334155;
  margin-bottom: 25px;
}

.overview-features {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 25px;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 0.85rem;
  color: #475569;
}

.feature-item i {
  color: #10b981;
  font-size: 1rem;
}

.reg-number {
  font-family: monospace;
  background: #eef2ff;
  padding: 2px 8px;
  border-radius: 6px;
  font-weight: 600;
  color: #2563eb;
}

.date-highlight {
  color: #2563eb;
  font-weight: 600;
}

.license-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: linear-gradient(135deg, #fef3c7, #fffbeb);
  padding: 12px 20px;
  border-radius: 40px;
  font-size: 0.85rem;
  color: #d97706;
  border: 1px solid #fde68a;
}

/* Stats Card Modern */
.stats-card-modern {
  background: linear-gradient(135deg, #1e293b, #0f172a);
  border-radius: 32px;
  padding: 30px;
  height: 100%;
  color: white;
}

.stats-header {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 30px;
  padding-bottom: 15px;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.stats-header i {
  font-size: 1.2rem;
  color: #60a5fa;
}

.stats-header span {
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 1px;
}

.stats-grid-modern {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.stat-item-modern {
  display: flex;
  align-items: center;
  gap: 20px;
}

.stat-ring {
  position: relative;
  width: 80px;
  height: 80px;
  flex-shrink: 0;
}

.stat-number-inner {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1.1rem;
  font-weight: 700;
}

.stat-info h4 {
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 5px;
}

.stat-info p {
  font-size: 0.75rem;
  opacity: 0.7;
  margin: 0;
}

/* Vision & Mission */
.vision-mission-section {
  margin-bottom: 60px;
}

.vision-card, .mission-card {
  background: white;
  border-radius: 28px;
  padding: 35px;
  text-align: center;
  transition: all 0.3s ease;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
  position: relative;
  overflow: hidden;
}

.vision-card:hover, .mission-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 30px 45px -15px rgba(37, 99, 235, 0.2);
}

.card-icon {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, #eef2ff, #fff);
  border-radius: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
  font-size: 2rem;
  color: #2563eb;
}

.card-footer-line {
  width: 50px;
  height: 3px;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  margin: 20px auto 0;
  border-radius: 3px;
}

/* Values Section */
.values-section {
  margin-bottom: 60px;
}

.section-header {
  text-align: center;
  margin-bottom: 40px;
}

.section-badge {
  display: inline-block;
  background: linear-gradient(135deg, #2563eb20, #7c3aed20);
  padding: 6px 16px;
  border-radius: 30px;
  font-size: 0.8rem;
  font-weight: 600;
  color: #2563eb;
  margin-bottom: 15px;
}

.section-header h3 {
  font-size: 2rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 10px;
}

.section-header p {
  color: #64748b;
}

.value-card {
  text-align: center;
  padding: 30px 20px;
  background: white;
  border-radius: 24px;
  transition: all 0.3s ease;
  box-shadow: 0 10px 25px -8px rgba(0, 0, 0, 0.05);
  height: 100%;
}

.value-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.1);
}

.value-icon {
  width: 65px;
  height: 65px;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
  font-size: 1.8rem;
  color: white;
}

.value-card h4 {
  font-size: 1.2rem;
  margin-bottom: 12px;
  color: #0f172a;
}

.value-card p {
  font-size: 0.85rem;
  color: #64748b;
  line-height: 1.5;
}

/* CEO Section */
.ceo-section {
  background: linear-gradient(135deg, #f8fafc, #ffffff);
  border-radius: 40px;
  padding: 50px;
  margin-bottom: 60px;
}

.ceo-image-wrapper {
  position: relative;
  text-align: center;
}

.ceo-image-frame {
  position: relative;
  width: 280px;
  height: 280px;
  margin: 0 auto;
  border-radius: 50%;
  overflow: hidden;
  border: 4px solid white;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.2);
}

.ceo-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.ceo-glow {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: radial-gradient(circle at 30% 30%, rgba(37, 99, 235, 0.3), transparent);
  pointer-events: none;
}

.ceo-social {
  display: flex;
  gap: 12px;
  justify-content: center;
  margin-top: 20px;
}

.social-link {
  width: 40px;
  height: 40px;
  background: #eef2ff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #2563eb;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link:hover {
  background: #2563eb;
  color: white;
  transform: translateY(-3px);
}

.ceo-content {
  padding: 20px;
}

.ceo-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: linear-gradient(135deg, #2563eb15, #7c3aed15);
  padding: 6px 15px;
  border-radius: 30px;
  margin-bottom: 20px;
}

.ceo-badge i {
  color: #2563eb;
  font-size: 0.8rem;
}

.ceo-badge span {
  font-size: 0.8rem;
  font-weight: 600;
  color: #2563eb;
}

.ceo-name {
  font-size: 2rem;
  font-weight: 800;
  color: #0f172a;
  margin-bottom: 15px;
}

.ceo-title-line {
  width: 60px;
  height: 3px;
  background: linear-gradient(90deg, #2563eb, #7c3aed);
  border-radius: 3px;
  margin-bottom: 20px;
}

.ceo-message {
  font-size: 1rem;
  line-height: 1.7;
  color: #475569;
  font-style: italic;
  margin-bottom: 20px;
}

.ceo-signature {
  text-align: right;
  font-size: 2rem;
  color: #2563eb;
  opacity: 0.5;
}

/* Location Section */
.location-section {
  margin-bottom: 60px;
}

.location-card {
  background: white;
  border-radius: 28px;
  padding: 32px;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
  height: 100%;
}

.location-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.location-icon i {
  font-size: 1.8rem;
  color: white;
}

.location-card h4 {
  font-size: 1.3rem;
  margin-bottom: 15px;
  color: #0f172a;
}

.location-address {
  font-size: 0.95rem;
  line-height: 1.6;
  color: #475569;
  margin-bottom: 20px;
}

.contact-info {
  margin-bottom: 20px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
  font-size: 0.9rem;
  color: #475569;
}

.contact-item i {
  width: 25px;
  color: #2563eb;
}

.license-info {
  background: #f8fafc;
  padding: 15px;
  border-radius: 20px;
  display: flex;
  gap: 12px;
  font-size: 0.85rem;
  border-left: 3px solid #2563eb;
}

.license-info i {
  font-size: 1.2rem;
  color: #2563eb;
}

.map-card {
  background: white;
  border-radius: 28px;
  padding: 20px;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
  height: 100%;
}

.map-wrapper {
  border-radius: 24px;
  overflow: hidden;
}

.map-note {
  margin-top: 15px;
  font-size: 0.8rem;
  color: #64748b;
  text-align: center;
}

.map-note i {
  color: #2563eb;
  margin-right: 5px;
}

/* Compliance Section */
.compliance-section {
  margin-bottom: 40px;
}

.compliance-card {
  background: linear-gradient(135deg, #f8fafc, #ffffff);
  border-radius: 24px;
  padding: 30px;
  text-align: center;
  border: 1px solid #e2e8f0;
}

.compliance-card i {
  font-size: 2.5rem;
  color: #2563eb;
  margin-bottom: 15px;
}

.compliance-card h4 {
  font-size: 1.2rem;
  margin-bottom: 12px;
  color: #0f172a;
}

.compliance-card p {
  font-size: 0.9rem;
  color: #475569;
  margin-bottom: 15px;
}

.compliance-note {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: #eef2ff;
  padding: 8px 16px;
  border-radius: 30px;
  font-size: 0.8rem;
  color: #2563eb;
}

/* Responsive */
@media (max-width: 768px) {
  .about-title {
    font-size: 2rem;
  }
  
  .about-hero {
    padding: 40px 20px 60px;
  }
  
  .ceo-section {
    padding: 30px;
  }
  
  .ceo-name {
    font-size: 1.5rem;
  }
  
  .ceo-image-frame {
    width: 200px;
    height: 200px;
    margin-bottom: 20px;
  }
  
  .overview-header {
    flex-direction: column;
    text-align: center;
  }
  
  .overview-title {
    font-size: 1.3rem;
  }
  
  .stat-item-modern {
    flex-direction: column;
    text-align: center;
  }
}
</style>