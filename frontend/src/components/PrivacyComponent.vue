<template>
  <div class="privacy-component">
    <!-- Hero Section -->
    <div class="privacy-hero">
      <div class="privacy-hero-content">
        <div class="hero-badge">
          <i class="fas fa-shield-alt"></i>
          <span>Legal & Compliance</span>
        </div>
        <h1 class="privacy-title">Privacy <span class="highlight">Policy</span></h1>
        <p class="privacy-subtitle">Sera ya Faragha ya Kedesh Limited</p>
        <div class="hero-meta">
          <div class="meta-item">
            <i class="fas fa-calendar-alt"></i>
            <span>Effective Date: <strong>{{ effectiveDate }}</strong></span>
          </div>
          <div class="meta-item">
            <i class="fas fa-sync-alt"></i>
            <span>Last Updated: <strong>{{ lastUpdated }}</strong></span>
          </div>
          <div class="meta-item">
            <i class="fas fa-building"></i>
            <span>Kedesh Limited</span>
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <!-- Table of Contents -->
      <div class="toc-card">
        <div class="toc-header">
          <i class="fas fa-list-ul"></i>
          <h3>Table of Contents</h3>
        </div>
        <div class="toc-links">
          <a href="#section1" @click.prevent="scrollTo('section1')" class="toc-link">
            <span>01</span> Information We Collect
          </a>
          <a href="#section2" @click.prevent="scrollTo('section2')" class="toc-link">
            <span>02</span> How We Use Your Information
          </a>
          <a href="#section3" @click.prevent="scrollTo('section3')" class="toc-link">
            <span>03</span> Meta Pixel & Advertising
          </a>
          <a href="#section4" @click.prevent="scrollTo('section4')" class="toc-link">
            <span>04</span> Data Security
          </a>
          <a href="#section5" @click.prevent="scrollTo('section5')" class="toc-link">
            <span>05</span> Your Rights
          </a>
          <a href="#section6" @click.prevent="scrollTo('section6')" class="toc-link">
            <span>06</span> Contact Us
          </a>
        </div>
      </div>

      <!-- Introduction -->
      <div class="intro-card">
        <div class="intro-icon">
          <i class="fas fa-info-circle"></i>
        </div>
        <div class="intro-content">
          <h3>Introduction</h3>
          <p>
            <strong>Kedesh Limited</strong> ("Kampuni", "sisi", "yetu") tunachukulia usalama wa data yako kwa uzito. 
            Sera hii inaeleza jinsi tunavyokusanya, kutumia na kulinda taarifa za kibinafsi unapotumia tovuti yetu 
            na kutumia huduma zetu. Tunajitahidi kuhakikisha kwamba taarifa zako zinalindwa kwa viwango vya juu zaidi.
          </p>
        </div>
      </div>

      <!-- Section 1 -->
      <div id="section1" class="policy-section">
        <div class="section-number">01</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fas fa-database"></i>
            </div>
            <h2>Information We Collect</h2>
            <p>Taarifa tunazokusanya</p>
          </div>
          <div class="section-body">
            <p>Katika kuwasiliana nasi au kutumia huduma zetu, tunaweza kukusanya aina zifuatazo za taarifa:</p>
            <ul class="info-list">
              <li>
                <i class="fas fa-user-check"></i>
                <div>
                  <strong>Taarifa za Kitambulisho</strong>
                  <span>Majina yako kamili, nafasi yako kazini, na maelezo ya kampuni yako</span>
                </div>
              </li>
              <li>
                <i class="fas fa-envelope"></i>
                <div>
                  <strong>Taarifa za Mawasiliano</strong>
                  <span>Anwani za barua pepe, namba za simu, na anwani ya posta</span>
                </div>
              </li>
              <li>
                <i class="fas fa-chart-line"></i>
                <div>
                  <strong>Taarifa za Matumizi ya Tovuti</strong>
                  <span>Data kuhusu jinsi unavyotumia tovuti yetu, ikiwemo cookies na teknolojia za kufuatilia</span>
                </div>
              </li>
              <li>
                <i class="fas fa-comment-dots"></i>
                <div>
                  <strong>Mawasiliano na Maswali</strong>
                  <span>Ujumbe unaotutumia kupitia fomu za mawasiliano, barua pepe, au njia nyingine</span>
                </div>
              </li>
            </ul>
            <div class="info-note">
              <i class="fas fa-info-circle"></i>
              <span>Tunatumia cookies ili kuboresha matumizi yako kwenye tovuti yetu. Unaweza kudhibiti mipangilio ya cookies kwenye browser yako.</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Section 2 -->
      <div id="section2" class="policy-section">
        <div class="section-number">02</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fas fa-chart-pie"></i>
            </div>
            <h2>How We Use Your Information</h2>
            <p>Matumizi ya taarifa</p>
          </div>
          <div class="section-body">
            <p>Taarifa tunazokusanya hutumiwa kwa madhumuni yafuatayo:</p>
            <div class="usage-grid">
              <div class="usage-card">
                <i class="fas fa-reply-all"></i>
                <h4>Kujibu Maswali</h4>
                <p>Kukujibu maswali yako na kutoa taarifa ulizoomba</p>
              </div>
              <div class="usage-card">
                <i class="fas fa-cogs"></i>
                <h4>Kutoa Huduma</h4>
                <p>Kutoa huduma ulizoomba na kuboresha matumizi yako</p>
              </div>
              <div class="usage-card">
                <i class="fas fa-bullhorn"></i>
                <h4>Mawasiliano</h4>
                <p>Kutuma taarifa muhimu kuhusu huduma zetu na matangazo</p>
              </div>
              <div class="usage-card">
                <i class="fas fa-chart-line"></i>
                <h4>Uchambuzi na Uboreshaji</h4>
                <p>Kuchambua matumizi ya tovuti na kuboresha huduma zetu</p>
              </div>
            </div>
            <div class="important-note">
              <i class="fas fa-ban"></i>
              <strong>Hatutauzi kamwe taarifa zako kwa wahusika wengine.</strong>
              <span>Taarifa zako zinalindwa na siuzwi kwa watu au kampuni nyingine.</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Section 3 -->
      <div id="section3" class="policy-section">
        <div class="section-number">03</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fab fa-facebook"></i>
            </div>
            <h2>Meta Pixel & Advertising</h2>
            <p>Meta Pixel na Utangazaji</p>
          </div>
          <div class="section-body">
            <p>
              Tunaweza kutumia Meta Pixel (inayojulikana pia kama Facebook Pixel) kwa ajili ya kuboresha kampeni 
              zetu za matangazo kwenye mitandao ya Meta (Facebook na Instagram). Hii inatusaidia:
            </p>
            <ul class="feature-list">
              <li><i class="fas fa-chart-line"></i> Kupima ufanisi wa matangazo yetu</li>
              <li><i class="fas fa-users"></i> Kuunda hadhira maalum kwa ajili ya matangazo</li>
              <li><i class="fas fa-sync-alt"></i> Kufuatilia matukio na mabadiliko kwenye tovuti yetu</li>
              <li><i class="fas fa-adjust"></i> Kuboresha uzoefu wa mtumiaji kwenye matangazo</li>
            </ul>
            <div class="cookie-settings">
              <div class="cookie-info">
                <i class="fas fa-cookie-bite"></i>
                <span>Unaweza kudhibiti mipangilio ya utumiaji wa kuki kwenye browser yako au kukataa kupitia mipangilio ya Meta.</span>
              </div>
              <button class="btn-cookie" @click="showCookieSettings">
                <i class="fas fa-sliders-h"></i>
                Cookie Settings
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Section 4 -->
      <div id="section4" class="policy-section">
        <div class="section-number">04</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fas fa-shield-alt"></i>
            </div>
            <h2>Data Security</h2>
            <p>Usalama wa Data</p>
          </div>
          <div class="section-body">
            <div class="security-grid">
              <div class="security-item">
                <i class="fas fa-lock"></i>
                <div>
                  <h4>Encryption</h4>
                  <p>Data yako inasimbwa kwa kutumia teknolojia za kisasa za usimbaji fiche</p>
                </div>
              </div>
              <div class="security-item">
                <i class="fas fa-server"></i>
                <div>
                  <h4>Secure Servers</h4>
                  <p>Tunatumia seva salama na firewalls za kiwango cha juu</p>
                </div>
              </div>
              <div class="security-item">
                <i class="fas fa-user-shield"></i>
                <div>
                  <h4>Access Control</h4>
                  <p>Wafanyakazi wetu wanafikia data kwa misingi ya haja tu</p>
                </div>
              </div>
            </div>
            <div class="disclaimer-note">
              <i class="fas fa-exclamation-triangle"></i>
              <span>Kumbuka: Hakuna njia ya kuhakikisha usalama 100% mtandaoni. Tunafanya kila tuwezalo kulinda data yako, lakini hatuwezi kuthibitisha usalama kamili.</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Section 5 -->
      <div id="section5" class="policy-section">
        <div class="section-number">05</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fas fa-gavel"></i>
            </div>
            <h2>Your Rights</h2>
            <p>Haki zako</p>
          </div>
          <div class="section-body">
            <p>Kwa mujibu wa sheria za ulinzi wa data, una haki zifuatazo:</p>
            <div class="rights-grid">
              <div class="right-card">
                <i class="fas fa-eye"></i>
                <h4>Right to Access</h4>
                <p>Haki ya kuomba kuona taarifa zetu tunazozihifadhi</p>
              </div>
              <div class="right-card">
                <i class="fas fa-edit"></i>
                <h4>Right to Rectification</h4>
                <p>Haki ya kuomba kusahihisha taarifa zisizo sahihi</p>
              </div>
              <div class="right-card">
                <i class="fas fa-trash-alt"></i>
                <h4>Right to Erasure</h4>
                <p>Haki ya kuomba kufutwa kwa taarifa zako</p>
              </div>
              <div class="right-card">
                <i class="fas fa-ban"></i>
                <h4>Right to Object</h4>
                <p>Haki ya kupinga usindikaji wa taarifa zako</p>
              </div>
            </div>
            <div class="contact-action">
              <p>Ili kutumia haki zako, tafadhali wasiliana nasi kwa:</p>
              <div class="contact-buttons">
                <a href="mailto:info@kedesh.co.tz" class="contact-btn email">
                  <i class="fas fa-envelope"></i> info@kedesh.co.tz
                </a>
                <button class="contact-btn phone" @click="$parent.navigate('contact')">
                  <i class="fas fa-phone-alt"></i> Contact Form
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Section 6: Contact -->
      <div id="section6" class="policy-section contact-section">
        <div class="section-number">06</div>
        <div class="section-content">
          <div class="section-header">
            <div class="section-icon">
              <i class="fas fa-phone-alt"></i>
            </div>
            <h2>Contact Us</h2>
            <p>Wasiliana nasi</p>
          </div>
          <div class="section-body">
            <div class="contact-card-full">
              <div class="contact-row">
                <i class="fas fa-map-marker-alt"></i>
                <div>
                  <strong>Data Protection Officer</strong>
                  <span>Kedesh Limited, Plot No. 123 Kikuyu Street, P.O. Box 456, Dodoma, Tanzania</span>
                </div>
              </div>
              <div class="contact-row">
                <i class="fas fa-envelope"></i>
                <div>
                  <strong>Email</strong>
                  <span>info@kedesh.co.tz</span>
                </div>
              </div>
              <div class="contact-row">
                <i class="fas fa-phone-alt"></i>
                <div>
                  <strong>Phone</strong>
                  <span>+255 752 128 096</span>
                </div>
              </div>
              <div class="contact-row">
                <i class="fas fa-clock"></i>
                <div>
                  <strong>Business Hours</strong>
                  <span>Monday - Friday: 8:30 AM - 5:30 PM</span>
                </div>
              </div>
            </div>
            <div class="gdpr-note">
              <i class="fas fa-check-circle"></i>
              <div>
                <strong>GDPR Compliant</strong>
                <span>Kedesh Limited inafuata kanuni za kimataifa za ulinzi wa data na taarifa za kibinafsi.</span>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Footer Note -->
      <div class="policy-footer">
        <i class="fas fa-file-contract"></i>
        <p>Sera hii inaweza kubadilishwa mara kwa mara. Tafadhali tembelea ukurasa huu kwa ajili ya updates za hivi karibuni.</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PrivacyComponent',
  data() {
    return {
      effectiveDate: 'January 1, 2025',
      lastUpdated: new Date().toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'long',
        day: 'numeric'
      })
    }
  },
  methods: {
    scrollTo(sectionId) {
      const element = document.getElementById(sectionId)
      if (element) {
        const offset = 100
        const elementPosition = element.offsetTop - offset
        window.scrollTo({
          top: elementPosition,
          behavior: 'smooth'
        })
      }
    },
    showCookieSettings() {
      alert('Cookie settings would open here.\n\nYou can manage cookie preferences in your browser settings.\n\nFor Meta Pixel, you can manage ad preferences in your Facebook settings.')
    }
  }
}
</script>

<style scoped>
.privacy-component {
  width: 100%;
  overflow-x: hidden;
  padding-bottom: 60px;
}

/* Hero Section */
.privacy-hero {
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
  border-radius: 0 0 60px 60px;
  padding: 60px 20px 80px;
  margin-bottom: 60px;
  text-align: center;
  position: relative;
  overflow: hidden;
}

.privacy-hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 20% 30%, rgba(37, 99, 235, 0.1), transparent);
  pointer-events: none;
}

.privacy-hero-content {
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
}

.hero-badge i, .hero-badge span {
  color: white;
  font-size: 0.85rem;
}

.privacy-title {
  font-size: 3rem;
  font-weight: 800;
  color: white;
  margin-bottom: 15px;
}

.privacy-title .highlight {
  background: linear-gradient(135deg, #60a5fa, #a78bfa);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.privacy-subtitle {
  font-size: 1.1rem;
  color: #94a3b8;
  margin-bottom: 30px;
}

.hero-meta {
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
  margin-top: 20px;
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.85rem;
  color: #cbd5e1;
}

.meta-item i {
  color: #60a5fa;
}

/* Table of Contents */
.toc-card {
  background: white;
  border-radius: 28px;
  padding: 30px;
  margin-bottom: 40px;
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
}

.toc-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 25px;
  padding-bottom: 15px;
  border-bottom: 2px solid #e2e8f0;
}

.toc-header i {
  font-size: 1.5rem;
  color: #2563eb;
}

.toc-header h3 {
  font-size: 1.2rem;
  font-weight: 700;
  color: #0f172a;
  margin: 0;
}

.toc-links {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}

.toc-link {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px 18px;
  background: #f8fafc;
  border-radius: 40px;
  text-decoration: none;
  transition: all 0.3s ease;
  font-size: 0.85rem;
  font-weight: 500;
  color: #475569;
}

.toc-link:hover {
  background: #2563eb;
  color: white;
  transform: translateY(-2px);
}

.toc-link span {
  font-weight: 700;
  color: #2563eb;
}

.toc-link:hover span {
  color: white;
}

/* Introduction Card */
.intro-card {
  background: linear-gradient(135deg, #eef2ff, #ffffff);
  border-radius: 28px;
  padding: 30px;
  margin-bottom: 40px;
  display: flex;
  gap: 25px;
  border: 1px solid rgba(37, 99, 235, 0.2);
}

.intro-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.intro-icon i {
  font-size: 1.8rem;
  color: white;
}

.intro-content h3 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 10px;
}

.intro-content p {
  font-size: 1rem;
  line-height: 1.6;
  color: #475569;
  margin: 0;
}

/* Policy Sections */
.policy-section {
  display: flex;
  gap: 30px;
  margin-bottom: 50px;
  position: relative;
}

.section-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 800;
  color: white;
  flex-shrink: 0;
}

.section-content {
  flex: 1;
  background: white;
  border-radius: 28px;
  padding: 30px;
  box-shadow: 0 10px 25px -8px rgba(0, 0, 0, 0.05);
}

.section-header {
  margin-bottom: 25px;
  padding-bottom: 15px;
  border-bottom: 2px solid #e2e8f0;
}

.section-icon {
  width: 50px;
  height: 50px;
  background: #eef2ff;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.section-icon i {
  font-size: 1.5rem;
  color: #2563eb;
}

.section-header h2 {
  font-size: 1.6rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 8px;
}

.section-header p {
  font-size: 0.9rem;
  color: #64748b;
  margin: 0;
}

.section-body p {
  font-size: 0.95rem;
  line-height: 1.6;
  color: #475569;
  margin-bottom: 20px;
}

/* Info List */
.info-list {
  list-style: none;
  padding: 0;
  margin: 20px 0;
}

.info-list li {
  display: flex;
  gap: 15px;
  margin-bottom: 20px;
  padding: 15px;
  background: #f8fafc;
  border-radius: 16px;
  transition: all 0.3s ease;
}

.info-list li:hover {
  background: #eef2ff;
  transform: translateX(5px);
}

.info-list li i {
  font-size: 1.2rem;
  color: #2563eb;
  margin-top: 2px;
}

.info-list li div {
  flex: 1;
}

.info-list li strong {
  display: block;
  font-size: 0.9rem;
  color: #0f172a;
  margin-bottom: 5px;
}

.info-list li span {
  font-size: 0.85rem;
  color: #64748b;
}

.info-note {
  background: #fef3c7;
  padding: 15px 20px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  margin-top: 20px;
}

.info-note i {
  font-size: 1.2rem;
  color: #d97706;
}

.info-note span {
  font-size: 0.85rem;
  color: #92400e;
}

/* Usage Grid */
.usage-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin: 20px 0;
}

.usage-card {
  background: #f8fafc;
  padding: 20px;
  border-radius: 20px;
  text-align: center;
  transition: all 0.3s ease;
}

.usage-card:hover {
  transform: translateY(-5px);
  background: #eef2ff;
}

.usage-card i {
  font-size: 2rem;
  color: #2563eb;
  margin-bottom: 12px;
}

.usage-card h4 {
  font-size: 1rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 8px;
}

.usage-card p {
  font-size: 0.8rem;
  color: #64748b;
  margin: 0;
}

.important-note {
  background: linear-gradient(135deg, #dcfce7, #f0fdf4);
  padding: 20px;
  border-radius: 20px;
  border-left: 4px solid #10b981;
  margin-top: 20px;
}

.important-note i {
  font-size: 1.2rem;
  color: #10b981;
  margin-right: 10px;
}

.important-note strong {
  display: inline-block;
  margin-bottom: 5px;
  color: #0f172a;
}

.important-note span {
  display: block;
  font-size: 0.85rem;
  color: #475569;
}

/* Feature List */
.feature-list {
  list-style: none;
  padding: 0;
  margin: 20px 0;
}

.feature-list li {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 12px;
  padding: 10px;
}

.feature-list li i {
  width: 25px;
  color: #2563eb;
}

.cookie-settings {
  background: #f8fafc;
  padding: 20px;
  border-radius: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 15px;
  margin-top: 20px;
}

.cookie-info {
  display: flex;
  align-items: center;
  gap: 10px;
}

.cookie-info i {
  font-size: 1.2rem;
  color: #2563eb;
}

.cookie-info span {
  font-size: 0.85rem;
  color: #475569;
}

.btn-cookie {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 10px 24px;
  border-radius: 30px;
  font-size: 0.85rem;
  font-weight: 600;
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-cookie:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3);
}

/* Security Grid */
.security-grid {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin: 20px 0;
}

.security-item {
  display: flex;
  gap: 15px;
  padding: 20px;
  background: #f8fafc;
  border-radius: 20px;
  transition: all 0.3s ease;
}

.security-item:hover {
  background: #eef2ff;
  transform: translateX(5px);
}

.security-item i {
  font-size: 1.8rem;
  color: #2563eb;
}

.security-item h4 {
  font-size: 1rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 5px;
}

.security-item p {
  font-size: 0.85rem;
  color: #64748b;
  margin: 0;
}

.disclaimer-note {
  background: #fef2f2;
  padding: 15px 20px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  margin-top: 20px;
}

.disclaimer-note i {
  font-size: 1.2rem;
  color: #ef4444;
}

.disclaimer-note span {
  font-size: 0.85rem;
  color: #991b1b;
}

/* Rights Grid */
.rights-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin: 20px 0;
}

.right-card {
  background: #f8fafc;
  padding: 20px;
  border-radius: 20px;
  text-align: center;
  transition: all 0.3s ease;
}

.right-card:hover {
  transform: translateY(-5px);
  background: #eef2ff;
}

.right-card i {
  font-size: 2rem;
  color: #2563eb;
  margin-bottom: 12px;
}

.right-card h4 {
  font-size: 1rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 8px;
}

.right-card p {
  font-size: 0.8rem;
  color: #64748b;
  margin: 0;
}

.contact-action {
  margin-top: 25px;
  padding: 20px;
  background: #f8fafc;
  border-radius: 20px;
}

.contact-action p {
  margin-bottom: 15px;
}

.contact-buttons {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.contact-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 12px 24px;
  border-radius: 40px;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  cursor: pointer;
  border: none;
}

.contact-btn.email {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  color: white;
}

.contact-btn.phone {
  background: #e2e8f0;
  color: #2563eb;
}

.contact-btn:hover {
  transform: translateY(-2px);
}

/* Contact Section Full */
.contact-card-full {
  background: #f8fafc;
  border-radius: 20px;
  padding: 25px;
  margin-bottom: 20px;
}

.contact-row {
  display: flex;
  gap: 15px;
  margin-bottom: 20px;
  padding: 10px;
  border-radius: 16px;
  transition: all 0.3s ease;
}

.contact-row:hover {
  background: white;
}

.contact-row i {
  width: 40px;
  height: 40px;
  background: #eef2ff;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #2563eb;
  font-size: 1.1rem;
}

.contact-row div strong {
  display: block;
  font-size: 0.85rem;
  color: #0f172a;
  margin-bottom: 5px;
}

.contact-row div span {
  font-size: 0.9rem;
  color: #475569;
}

.gdpr-note {
  background: linear-gradient(135deg, #dcfce7, #f0fdf4);
  padding: 20px;
  border-radius: 20px;
  display: flex;
  gap: 15px;
  align-items: center;
}

.gdpr-note i {
  font-size: 2rem;
  color: #10b981;
}

.gdpr-note strong {
  display: block;
  font-size: 0.9rem;
  color: #0f172a;
  margin-bottom: 5px;
}

.gdpr-note span {
  font-size: 0.85rem;
  color: #475569;
}

/* Policy Footer */
.policy-footer {
  text-align: center;
  padding: 30px;
  margin-top: 40px;
  background: #f8fafc;
  border-radius: 28px;
}

.policy-footer i {
  font-size: 2rem;
  color: #2563eb;
  margin-bottom: 15px;
}

.policy-footer p {
  font-size: 0.85rem;
  color: #64748b;
  margin: 0;
}

/* Responsive */
@media (max-width: 768px) {
  .privacy-title {
    font-size: 2rem;
  }
  
  .policy-section {
    flex-direction: column;
  }
  
  .section-number {
    width: 50px;
    height: 50px;
    font-size: 1.2rem;
  }
  
  .intro-card {
    flex-direction: column;
    text-align: center;
  }
  
  .intro-icon {
    margin: 0 auto;
  }
  
  .usage-grid, .rights-grid {
    grid-template-columns: 1fr;
  }
  
  .cookie-settings {
    flex-direction: column;
    text-align: center;
  }
  
  .hero-meta {
    flex-direction: column;
    gap: 10px;
    align-items: center;
  }
  
  .toc-links {
    justify-content: center;
  }
}
</style>