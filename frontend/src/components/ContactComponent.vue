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
        <!-- Contact Information Column -->
        <div class="col-lg-5">
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
                  <p>Kedesh Limited, Plot No. 123 Kikuyu Street<br>P.O. Box 456, Dodoma, Tanzania</p>
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
                  <p>info@kedesh.co.tz</p>
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
                <a href="#" class="social-link facebook"><i class="fab fa-facebook-f"></i></a>
                <a href="#" class="social-link twitter"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link linkedin"><i class="fab fa-linkedin-in"></i></a>
                <a href="#" class="social-link instagram"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-link youtube"><i class="fab fa-youtube"></i></a>
              </div>
            </div>

            <div class="license-badge-sm">
              <i class="fas fa-certificate"></i>
              <span>Certificate of Incorporation No: 178821040</span>
            </div>
          </div>
        </div>

        <!-- Contact Form Column -->
        <div class="col-lg-7">
          <div class="contact-form-card">
            <div class="form-header">
              <div class="form-icon">
                <i class="fas fa-paper-plane"></i>
              </div>
              <h3>Send Us a Message</h3>
              <p>Fill out the form below and we'll get back to you within 24 hours</p>
            </div>

            <form @submit.prevent="submitForm" class="contact-form">
              <div class="row g-3">
                <div class="col-md-6">
                  <div class="form-group">
                    <label><i class="fas fa-user"></i> Full Name</label>
                    <input 
                      type="text" 
                      class="form-control-modern" 
                      v-model="form.name" 
                      placeholder="Enter your full name"
                      required>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label><i class="fas fa-envelope"></i> Email Address</label>
                    <input 
                      type="email" 
                      class="form-control-modern" 
                      v-model="form.email" 
                      placeholder="your@email.com"
                      required>
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label><i class="fas fa-phone"></i> Phone Number (Optional)</label>
                    <input 
                      type="tel" 
                      class="form-control-modern" 
                      v-model="form.phone" 
                      placeholder="+255 XXX XXX XXX">
                  </div>
                </div>
                <div class="col-md-6">
                  <div class="form-group">
                    <label><i class="fas fa-tag"></i> Service Interested In</label>
                    <select class="form-control-modern" v-model="form.service">
                      <option value="">Select a service</option>
                      <option value="Digital Marketing">Digital Marketing</option>
                      <option value="Video Production">Video Production</option>
                      <option value="System Development">System Development</option>
                      <option value="Brand Strategy">Brand Strategy</option>
                      <option value="Cloud Solutions">Cloud Solutions</option>
                      <option value="Other">Other</option>
                    </select>
                  </div>
                </div>
                <div class="col-12">
                  <div class="form-group">
                    <label><i class="fas fa-comment"></i> Your Message</label>
                    <textarea 
                      class="form-control-modern" 
                      rows="5" 
                      v-model="form.message" 
                      placeholder="Tell us about your project or inquiry..."
                      required></textarea>
                  </div>
                </div>
                <div class="col-12">
                  <div class="form-check">
                    <input type="checkbox" class="form-check-input" id="privacyCheck" v-model="form.privacy">
                    <label class="form-check-label" for="privacyCheck">
                      I agree to the <a href="#" @click.prevent="$parent.navigate('privacy')">Privacy Policy</a>
                    </label>
                  </div>
                </div>
                <div class="col-12">
                  <button type="submit" class="btn-submit" :disabled="isSubmitting">
                    <span v-if="!isSubmitting">
                      Send Message <i class="fas fa-paper-plane ms-2"></i>
                    </span>
                    <span v-else>
                      Sending... <i class="fas fa-spinner fa-spin ms-2"></i>
                    </span>
                  </button>
                </div>
              </div>
            </form>

            <div class="form-footer">
              <i class="fas fa-shield-alt"></i>
              <span>Your information is protected by our Privacy Policy</span>
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

    <!-- Toast Notification -->
    <div v-if="showToast" :class="['toast-notification', toastType]">
      <i :class="toastIcon"></i>
      <span>{{ toastMessage }}</span>
    </div>
  </div>
</template>

<script>
import emailjs from '@emailjs/browser'

export default {
  name: 'ContactComponent',
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: '',
        service: '',
        message: '',
        privacy: false
      },
      isSubmitting: false,
      showToast: false,
      toastMessage: '',
      toastType: 'success',
      // EmailJS Configuration - Replace with your credentials
      emailConfig: {
        publicKey: 'YOUR_PUBLIC_KEY',     // Get from EmailJS dashboard
        serviceId: 'YOUR_SERVICE_ID',     // Create service in EmailJS
        templateId: 'YOUR_TEMPLATE_ID'    // Create template in EmailJS
      }
    }
  },
  computed: {
    toastIcon() {
      return this.toastType === 'success' ? 'fas fa-check-circle' : 'fas fa-exclamation-circle'
    }
  },
  methods: {
    async submitForm() {
      // Validation
      if (!this.form.name || !this.form.email || !this.form.message) {
        this.showToastMessage('Please fill in all required fields', 'error')
        return
      }
      
      if (!this.form.privacy) {
        this.showToastMessage('Please agree to the Privacy Policy', 'error')
        return
      }
      
      if (!this.isValidEmail(this.form.email)) {
        this.showToastMessage('Please enter a valid email address', 'error')
        return
      }
      
      this.isSubmitting = true
      
      try {
        // Prepare email template parameters
        const templateParams = {
          to_name: 'Kedesh Limited',
          to_email: 'info@kedesh.co.tz',
          from_name: this.form.name,
          from_email: this.form.email,
          phone: this.form.phone || 'Not provided',
          service: this.form.service || 'Not specified',
          message: this.form.message,
          reply_to: this.form.email
        }
        
        // Send email using EmailJS
        const response = await emailjs.send(
          this.emailConfig.serviceId,
          this.emailConfig.templateId,
          templateParams,
          {
            publicKey: this.emailConfig.publicKey,
          }
        )
        
        if (response.status === 200) {
          this.showToastMessage(`Thank you ${this.form.name}! Your message has been sent successfully. We'll contact you within 24 hours.`, 'success')
          
          // Reset form
          this.form = {
            name: '',
            email: '',
            phone: '',
            service: '',
            message: '',
            privacy: false
          }
        } else {
          throw new Error('Failed to send')
        }
      } catch (error) {
        console.error('Email sending error:', error)
        this.showToastMessage('Failed to send message. Please try again or contact us directly.', 'error')
      } finally {
        this.isSubmitting = false
      }
    },
    
    isValidEmail(email) {
      const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
      return re.test(email)
    },
    
    showToastMessage(message, type) {
      this.toastMessage = message
      this.toastType = type
      this.showToast = true
      
      setTimeout(() => {
        this.showToast = false
      }, 5000)
    }
  },
  mounted() {
    // Initialize EmailJS
    emailjs.init({
      publicKey: this.emailConfig.publicKey,
    })
  }
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

/* Contact Info Card */
.contact-info-card {
  background: white;
  border-radius: 32px;
  padding: 35px;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.08);
  height: 100%;
  transition: all 0.3s ease;
}

.contact-info-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 30px 50px -15px rgba(37, 99, 235, 0.15);
}

.info-header {
  text-align: center;
  margin-bottom: 30px;
}

.info-icon {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
}

.info-icon i {
  font-size: 2rem;
  color: white;
}

.info-header h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 8px;
}

.info-header p {
  color: #64748b;
  font-size: 0.9rem;
}

.info-details {
  margin-bottom: 30px;
}

.detail-item {
  display: flex;
  gap: 18px;
  margin-bottom: 25px;
  padding: 15px;
  border-radius: 20px;
  transition: all 0.3s ease;
}

.detail-item:hover {
  background: #f8fafc;
  transform: translateX(5px);
}

.detail-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #eef2ff, #fff);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.detail-icon i {
  font-size: 1.3rem;
  color: #2563eb;
}

.detail-content h4 {
  font-size: 1rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 5px;
}

.detail-content p {
  font-size: 0.9rem;
  color: #475569;
  margin: 0;
  line-height: 1.5;
}

.detail-content .small {
  font-size: 0.75rem;
  color: #64748b;
  margin-top: 3px;
}

/* Social Connect */
.social-connect {
  text-align: center;
  padding-top: 20px;
  border-top: 1px solid #e2e8f0;
}

.social-connect h4 {
  font-size: 1rem;
  margin-bottom: 15px;
  color: #0f172a;
}

.social-links {
  display: flex;
  gap: 12px;
  justify-content: center;
}

.social-link {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  transition: all 0.3s ease;
  text-decoration: none;
}

.social-link.facebook { background: #1877f2; }
.social-link.twitter { background: #1da1f2; }
.social-link.linkedin { background: #0077b5; }
.social-link.instagram { background: #e4405f; }
.social-link.youtube { background: #ff0000; }

.social-link:hover {
  transform: translateY(-5px);
  filter: brightness(1.1);
}

.license-badge-sm {
  display: flex;
  align-items: center;
  gap: 10px;
  background: #fef3c7;
  padding: 12px 15px;
  border-radius: 16px;
  margin-top: 25px;
  font-size: 0.75rem;
  color: #d97706;
}

/* Contact Form Card */
.contact-form-card {
  background: white;
  border-radius: 32px;
  padding: 35px;
  box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.08);
  height: 100%;
}

.form-header {
  text-align: center;
  margin-bottom: 30px;
}

.form-icon {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
}

.form-icon i {
  font-size: 2rem;
  color: white;
}

.form-header h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 8px;
}

.form-header p {
  color: #64748b;
  font-size: 0.9rem;
}

/* Form Styles */
.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.85rem;
  font-weight: 600;
  color: #0f172a;
  margin-bottom: 8px;
}

.form-group label i {
  color: #2563eb;
  font-size: 0.8rem;
}

.form-control-modern {
  width: 100%;
  padding: 14px 18px;
  border: 2px solid #e2e8f0;
  border-radius: 16px;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  background: #f8fafc;
}

.form-control-modern:focus {
  outline: none;
  border-color: #2563eb;
  background: white;
  box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.1);
}

.form-control-modern:hover {
  border-color: #cbd5e1;
}

select.form-control-modern {
  cursor: pointer;
}

textarea.form-control-modern {
  resize: vertical;
}

.form-check {
  margin-bottom: 20px;
}

.form-check-input {
  width: 18px;
  height: 18px;
  margin-right: 10px;
  cursor: pointer;
}

.form-check-input:checked {
  background-color: #2563eb;
  border-color: #2563eb;
}

.form-check-label {
  font-size: 0.85rem;
  color: #475569;
}

.form-check-label a {
  color: #2563eb;
  text-decoration: none;
}

.form-check-label a:hover {
  text-decoration: underline;
}

.btn-submit {
  width: 100%;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 16px 32px;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1rem;
  color: white;
  transition: all 0.3s ease;
  cursor: pointer;
}

.btn-submit:hover:not(:disabled) {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(37, 99, 235, 0.3);
}

.btn-submit:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.form-footer {
  margin-top: 20px;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: 0.75rem;
  color: #64748b;
}

.form-footer i {
  color: #10b981;
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

/* Toast Notification */
.toast-notification {
  position: fixed;
  bottom: 30px;
  right: 30px;
  background: white;
  padding: 16px 24px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
  z-index: 1000;
  animation: slideInRight 0.3s ease;
}

.toast-notification.success {
  border-left: 4px solid #10b981;
}

.toast-notification.success i {
  color: #10b981;
}

.toast-notification.error {
  border-left: 4px solid #ef4444;
}

.toast-notification.error i {
  color: #ef4444;
}

.toast-notification i {
  font-size: 1.2rem;
}

.toast-notification span {
  font-size: 0.9rem;
  color: #0f172a;
}

@keyframes slideInRight {
  from {
    transform: translateX(100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* Responsive */
@media (max-width: 768px) {
  .contact-title {
    font-size: 2rem;
  }
  
  .contact-hero {
    padding: 40px 20px 60px;
  }
  
  .contact-info-card, .contact-form-card {
    padding: 25px;
  }
  
  .detail-item {
    padding: 10px;
  }
  
  .toast-notification {
    bottom: 20px;
    right: 20px;
    left: 20px;
    padding: 12px 16px;
  }
}
</style>