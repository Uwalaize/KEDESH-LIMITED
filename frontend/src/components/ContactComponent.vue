<template>
  <div class="contact-component">
    <div class="container">
      <!-- Hero Section -->
      <div class="contact-hero">
        <div class="contact-hero-content">
          <div class="hero-badge">
            <i class="fas fa-comments"></i>
            <span>Get In Touch</span>
          </div>
          <h2 class="contact-title">Let's <span class="highlight">Connect</span></h2>
          <p class="contact-subtitle">We're here to help and answer any questions you might have</p>
        </div>
      </div>

      <div class="row g-5">
        <!-- Contact Information Column - Full Width Now -->
        <div class="col-lg-12">
          <div class="contact-info-card">
            <div class="info-header">
              <div class="info-icon">
                <i class="fas fa-building"></i>
              </div>
              <h3>Contact Information</h3>
              <p>Reach out to us through any of these channels</p>
            </div>

            <div class="info-details">
              <div class="detail-item">
                <div class="detail-icon">
                  <i class="fas fa-map-marker-alt"></i>
                </div>
                <div class="detail-content">
                  <h4>Office Location</h4>
                  <p>Kizota, Sokoine Street<br>Dodoma, Tanzania</p>
                </div>
              </div>

              <div class="detail-item">
                <div class="detail-icon">
                  <i class="fas fa-phone-alt"></i>
                </div>
                <div class="detail-content">
                  <h4>Phone Number</h4>
                  <p>+255 752 128 096</p>
                  <p class="small">Mon - Sat, 8:00 AM - 6:00 PM</p>
                </div>
              </div>

              <div class="detail-item">
                <div class="detail-icon">
                  <i class="fas fa-envelope"></i>
                </div>
                <div class="detail-content">
                  <h4>Email Address</h4>
                  <p>info@kedeshlimited.com</p>
                  <p class="small">Support & Inquiries</p>
                </div>
              </div>

              <div class="detail-item">
                <div class="detail-icon">
                  <i class="fas fa-clock"></i>
                </div>
                <div class="detail-content">
                  <h4>Business Hours</h4>
                  <p>Monday - Friday: 8:30 AM - 5:30 PM<br>Saturday: 9:00 AM - 1:00 PM<br>Sunday: Closed</p>
                </div>
              </div>
            </div>

            <div class="social-connect">
              <h4>Connect With Us</h4>
              <div class="social-links">
                <a 
                  href="https://www.facebook.com/share/1HCJxANdbk/?mibextid=wwXIfr" 
                  target="_blank" 
                  rel="noopener noreferrer" 
                  class="social-link facebook"
                >
                  <i class="fab fa-facebook-f"></i>
                  <span class="social-name">Facebook</span>
                </a>
                <a 
                  href="https://www.instagram.com/kedesh_limited?igsh=MXJoNTkwamZlNmQ1MA%3D%3D&utm_source=qr" 
                  target="_blank" 
                  rel="noopener noreferrer" 
                  class="social-link instagram"
                >
                  <i class="fab fa-instagram"></i>
                  <span class="social-name">Instagram</span>
                </a>
              </div>
            </div>

            <div class="license-badge-sm">
              <i class="fas fa-certificate"></i>
              <span>Certificate of Incorporation No: 178821040</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Map Section -->
      <div class="map-section">
        <div class="map-card">
          <div class="map-header">
            <i class="fas fa-map-marked-alt"></i>
            <h4>Find Us Here</h4>
          </div>
          <div class="map-wrapper">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d126706.09445926883!2d35.701302!3d-6.162959!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x184d3b6c8b6b6b6b%3A0x6b6b6b6b6b6b6b6b!2sDodoma%2C%20Tanzania!5e0!3m2!1sen!2s!4v1700000000000!5m2!1sen!2s" 
              width="100%" 
              height="350" 
              style="border:0; border-radius: 20px;" 
              allowfullscreen="" 
              loading="lazy">
            </iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactComponent'
}
</script>

<style scoped>
.contact-component {
  width: 100%;
  overflow-x: hidden;
  padding-bottom: 60px;
}

/* Hero Section */
.contact-hero {
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
  border-radius: 0 0 60px 60px;
  padding: 60px 20px 80px;
  margin-bottom: 60px;
  text-align: center;
  position: relative;
}

.contact-hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 20% 30%, rgba(37, 99, 235, 0.1), transparent);
  pointer-events: none;
}

.contact-hero-content {
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

.contact-title {
  font-size: 3rem;
  font-weight: 800;
  color: white;
  margin-bottom: 15px;
}

.contact-title .highlight {
  background: linear-gradient(135deg, #60a5fa, #a78bfa);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.contact-subtitle {
  font-size: 1.1rem;
  color: #94a3b8;
}

/* Contact Info Card - Full Width */
.contact-info-card {
  background: white;
  border-radius: 32px;
  padding: 45px;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.contact-info-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 30px 50px -15px rgba(37, 99, 235, 0.15);
}

.info-header {
  text-align: center;
  margin-bottom: 40px;
}

.info-icon {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
}

.info-icon i {
  font-size: 2.2rem;
  color: white;
}

.info-header h3 {
  font-size: 1.8rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 10px;
}

.info-header p {
  color: #64748b;
  font-size: 1rem;
}

/* Info Details - Grid Layout */
.info-details {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 25px;
  margin-bottom: 40px;
}

.detail-item {
  display: flex;
  gap: 20px;
  padding: 20px;
  border-radius: 24px;
  transition: all 0.3s ease;
  background: #f8fafc;
}

.detail-item:hover {
  background: linear-gradient(135deg, #eef2ff, #ffffff);
  transform: translateX(8px);
}

.detail-icon {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.detail-icon i {
  font-size: 1.5rem;
  color: white;
}

.detail-content h4 {
  font-size: 1.1rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 8px;
}

.detail-content p {
  font-size: 0.95rem;
  color: #475569;
  margin: 0;
  line-height: 1.5;
}

.detail-content .small {
  font-size: 0.8rem;
  color: #64748b;
  margin-top: 5px;
}

/* Social Connect - Enhanced */
.social-connect {
  text-align: center;
  padding: 30px;
  background: linear-gradient(135deg, #f8fafc, #ffffff);
  border-radius: 28px;
  margin-bottom: 25px;
}

.social-connect h4 {
  font-size: 1.2rem;
  margin-bottom: 20px;
  color: #0f172a;
  font-weight: 700;
}

.social-links {
  display: flex;
  gap: 30px;
  justify-content: center;
  flex-wrap: wrap;
}

.social-link {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  padding: 12px 28px;
  border-radius: 50px;
  color: white;
  text-decoration: none;
  transition: all 0.3s ease;
  font-weight: 600;
  font-size: 1rem;
}

.social-link i {
  font-size: 1.3rem;
}

.social-name {
  font-size: 0.95rem;
}

.social-link.facebook { 
  background: #1877f2;
  box-shadow: 0 5px 15px rgba(24, 119, 242, 0.3);
}

.social-link.instagram { 
  background: linear-gradient(135deg, #f58529, #dd2a7b, #8134af, #515bd4);
  box-shadow: 0 5px 15px rgba(221, 42, 123, 0.3);
}

.social-link:hover {
  transform: translateY(-5px) scale(1.05);
  filter: brightness(1.05);
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
}

/* License Badge */
.license-badge-sm {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  background: linear-gradient(135deg, #fef3c7, #fffbeb);
  padding: 15px 20px;
  border-radius: 20px;
  font-size: 0.85rem;
  color: #d97706;
  border: 1px solid #fde68a;
}

.license-badge-sm i {
  font-size: 1.2rem;
}

/* Map Section */
.map-section {
  margin-top: 50px;
}

.map-card {
  background: white;
  border-radius: 32px;
  padding: 25px;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.map-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 25px 45px -15px rgba(37, 99, 235, 0.15);
}

.map-header {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 20px;
}

.map-header i {
  font-size: 1.5rem;
  color: #2563eb;
}

.map-header h4 {
  font-size: 1.2rem;
  font-weight: 600;
  color: #0f172a;
  margin: 0;
}

.map-wrapper {
  border-radius: 20px;
  overflow: hidden;
}

/* Responsive */
@media (max-width: 768px) {
  .contact-title {
    font-size: 2rem;
  }
  
  .contact-hero {
    padding: 40px 20px 60px;
  }
  
  .contact-info-card {
    padding: 25px;
  }
  
  .info-details {
    grid-template-columns: 1fr;
    gap: 15px;
  }
  
  .detail-item {
    padding: 15px;
  }
  
  .detail-icon {
    width: 50px;
    height: 50px;
  }
  
  .detail-icon i {
    font-size: 1.2rem;
  }
  
  .info-header h3 {
    font-size: 1.4rem;
  }
  
  .social-links {
    flex-direction: column;
    align-items: center;
    gap: 15px;
  }
  
  .social-link {
    width: 80%;
    justify-content: center;
  }
  
  .license-badge-sm {
    flex-direction: column;
    text-align: center;
  }
}

/* Tablet Responsive */
@media (min-width: 769px) and (max-width: 1024px) {
  .info-details {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .social-links {
    gap: 20px;
  }
}
</style>