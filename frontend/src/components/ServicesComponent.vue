<template>
  <div class="services-component">
    <!-- If no service selected, show services grid -->
    <div v-if="!selectedService">
      <!-- Hero Section -->
      <div class="services-hero">
        <div class="services-hero-content">
          <div class="hero-badge">
            <i class="fas fa-crown"></i>
            <span>Premium Solutions</span>
          </div>
          <h2 class="services-title">Our Premium Services</h2>
          <p class="services-subtitle">End-to-end digital solutions crafted for modern enterprises.</p>
        </div>
      </div>

      <!-- Services Grid -->
      <div class="services-grid-container">
        <div class="services-grid">
          <div 
            class="service-card-wrapper" 
            v-for="(service, index) in serviceList" 
            :key="service.title"
            :style="{ animationDelay: `${index * 0.1}s` }"
          >
            <div class="service-card">
              <div class="card-glow"></div>
              
              <div class="service-icon-wrapper">
                <div class="service-icon">
                  <i :class="service.icon"></i>
                </div>
                <div class="icon-backdrop"></div>
              </div>
              
              <h3 class="service-title">{{ service.title }}</h3>
              
              <div class="service-divider">
                <span></span>
                <i class="fas fa-circle"></i>
                <span></span>
              </div>
              
              <p class="service-description">{{ service.shortDesc }}</p>
              
              <div class="service-footer">
                <button class="service-btn" @click="viewServiceDetails(service)">
                  Learn More <i class="fas fa-arrow-right"></i>
                </button>
              </div>
              
              <div class="card-decoration">
                <div class="dot dot-1"></div>
                <div class="dot dot-2"></div>
                <div class="dot dot-3"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Service Details Page -->
    <div v-else class="service-details-page">
      <button class="back-button" @click="goBack">
        <i class="fas fa-arrow-left"></i> Back to All Services
      </button>

      <div class="service-details-hero" :style="{ backgroundImage: `linear-gradient(135deg, rgba(0,0,0,0.85), rgba(37,99,235,0.75)), url(${selectedService.detailImage})` }">
        <div class="service-details-content">
          <div class="service-badge">
            <i :class="selectedService.icon"></i>
            {{ selectedService.title }}
          </div>
          <h1>{{ selectedService.title }}</h1>
          <p>{{ selectedService.tagline }}</p>
        </div>
      </div>

      <div class="container">
        <div class="service-details-grid">
          <!-- Overview Section -->
          <div class="details-card overview-card">
            <h2><i class="fas fa-info-circle"></i> Service Overview</h2>
            <p>{{ selectedService.fullDescription }}</p>
          </div>

          <!-- Key Features -->
          <div class="details-card features-card">
            <h2><i class="fas fa-star"></i> Key Features</h2>
            <div class="features-list">
              <div v-for="(feature, idx) in selectedService.features" :key="idx" class="feature-item">
                <i class="fas fa-check-circle"></i>
                <span>{{ feature }}</span>
              </div>
            </div>
          </div>

          <!-- Benefits -->
          <div class="details-card benefits-card">
            <h2><i class="fas fa-gem"></i> Benefits</h2>
            <div class="benefits-list">
              <div v-for="(benefit, idx) in selectedService.benefits" :key="idx" class="benefit-item">
                <div class="benefit-icon">
                  <i :class="benefit.icon"></i>
                </div>
                <div class="benefit-content">
                  <h4>{{ benefit.title }}</h4>
                  <p>{{ benefit.description }}</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Process -->
          <div class="details-card process-card">
            <h2><i class="fas fa-chart-line"></i> Our Process</h2>
            <div class="process-steps">
              <div v-for="(step, idx) in selectedService.process" :key="idx" class="step-item">
                <div class="step-number">{{ idx + 1 }}</div>
                <div class="step-content">
                  <h4>{{ step.title }}</h4>
                  <p>{{ step.description }}</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Technologies (for tech services) -->
          <div v-if="selectedService.technologies" class="details-card tech-card">
            <h2><i class="fas fa-microchip"></i> Technologies We Use</h2>
            <div class="tech-list">
              <span v-for="tech in selectedService.technologies" :key="tech" class="tech-tag">
                {{ tech }}
              </span>
            </div>
          </div>

          <!-- Portfolio/Case Studies -->
          <div class="details-card cta-card">
            <h2><i class="fas fa-rocket"></i> Ready to Get Started?</h2>
            <p>Let's discuss how {{ selectedService.title }} can transform your business.</p>
            <button class="cta-button" @click="$parent.navigate('contact')">
              Request a Quote <i class="fas fa-arrow-right"></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ServicesComponent',
  data() {
    return {
      selectedService: null,
      serviceList: [
        { 
          title: "Video Production", 
          icon: "fas fa-film", 
          shortDesc: "Corporate videos, motion graphics, drone footage & professional storytelling that captivates audiences.",
          tagline: "Bring your stories to life with cinematic excellence",
          detailImage: "https://images.unsplash.com/photo-1492691527719-9d1e07e534b4?w=1200&h=600&fit=crop",
          fullDescription: "Our video production service delivers high-quality, cinematic content that captures your brand's essence and engages your target audience. From concept development to final editing, we handle every aspect of production with professional equipment and creative expertise. Whether you need corporate videos, product demonstrations, event coverage, or social media content, our team ensures your message is communicated effectively and memorably.",
          features: [
            "Professional 4K/8K cinematography",
            "Expert scriptwriting and storyboarding",
            "Professional voiceover and audio mixing",
            "Motion graphics and visual effects",
            "Drone aerial footage",
            "Color grading and post-production"
          ],
          benefits: [
            { icon: "fas fa-chart-line", title: "Increased Engagement", description: "Video content generates 1200% more shares than text and images combined" },
            { icon: "fas fa-hand-holding-usd", title: "Higher ROI", description: "Landing pages with video convert 80% better than those without" },
            { icon: "fas fa-users", title: "Brand Trust", description: "Professional videos build credibility and trust with your audience" }
          ],
          process: [
            { title: "Discovery & Planning", description: "We learn about your brand, goals, and target audience to create a strategic plan" },
            { title: "Pre-Production", description: "Scriptwriting, storyboarding, location scouting, and scheduling" },
            { title: "Production", description: "Professional filming with state-of-the-art equipment and expert crew" },
            { title: "Post-Production", description: "Editing, color grading, sound design, and motion graphics" },
            { title: "Delivery & Optimization", description: "Final delivery in multiple formats optimized for your platforms" }
          ]
        },
        { 
          title: "Website and App Development", 
          icon: "fas fa-laptop-code", 
          shortDesc: "Custom websites, mobile apps, AI integrations & secure enterprise platforms tailored to your needs.",
          tagline: "Build powerful digital experiences that drive results",
          detailImage: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?w=1200&h=600&fit=crop",
          fullDescription: "We create stunning, responsive websites and powerful mobile applications that deliver exceptional user experiences. Our development team uses the latest technologies to build scalable, secure, and high-performance digital solutions. From e-commerce platforms to custom CRM systems, we turn your ideas into reality with clean code and intuitive design.",
          features: [
            "Responsive web design (mobile-first approach)",
            "iOS and Android native app development",
            "E-commerce and payment gateway integration",
            "CMS integration (WordPress, custom solutions)",
            "API development and third-party integrations",
            "Progressive Web Apps (PWA)"
          ],
          benefits: [
            { icon: "fas fa-tachometer-alt", title: "Fast Performance", description: "Optimized code ensures lightning-fast load times" },
            { icon: "fas fa-shield-alt", title: "Enterprise Security", description: "Bank-grade security protocols protect your data" },
            { icon: "fas fa-chart-line", title: "Scalable Architecture", description: "Solutions that grow with your business" }
          ],
          process: [
            { title: "Requirement Analysis", description: "Understanding your business needs and technical requirements" },
            { title: "UI/UX Design", description: "Creating intuitive and beautiful interfaces" },
            { title: "Development", description: "Agile development with regular updates and testing" },
            { title: "Quality Assurance", description: "Rigorous testing across all devices and browsers" },
            { title: "Deployment & Support", description: "Launch and ongoing maintenance and updates" }
          ],
          technologies: ["React", "Vue.js", "Node.js", "Python", "Flutter", "Firebase", "AWS", "MongoDB", "PostgreSQL"]
        },
        { 
          title: "Brand Strategy", 
          icon: "fas fa-chart-simple", 
          shortDesc: "Identity design, market positioning & creative direction that sets you apart from competitors.",
          tagline: "Create a brand that resonates and endures",
          detailImage: "https://images.unsplash.com/photo-1561070791-2526d30994b5?w=1200&h=600&fit=crop",
          fullDescription: "Our brand strategy service helps you define, articulate, and activate your brand's unique identity. We work closely with you to develop a comprehensive brand strategy that aligns with your business goals and resonates with your target audience. From visual identity to brand voice, we create cohesive brand experiences that build loyalty and drive growth.",
          features: [
            "Brand discovery and positioning workshops",
            "Logo design and visual identity systems",
            "Brand messaging and voice development",
            "Market research and competitor analysis",
            "Brand guidelines and style guides",
            "Brand activation and launch strategies"
          ],
          benefits: [
            { icon: "fas fa-heart", title: "Emotional Connection", description: "Build deep connections with your target audience" },
            { icon: "fas fa-chart-line", title: "Market Differentiation", description: "Stand out from competitors with unique positioning" },
            { icon: "fas fa-dollar-sign", title: "Premium Pricing", description: "Strong brands command higher prices and loyalty" }
          ],
          process: [
            { title: "Discovery", description: "Deep-dive research into your business, audience, and market" },
            { title: "Strategy Development", description: "Creating a roadmap for your brand's success" },
            { title: "Creative Direction", description: "Developing visual and verbal identity elements" },
            { title: "Implementation", description: "Rolling out your brand across all touchpoints" },
            { title: "Evolution", description: "Ongoing brand management and refinement" }
          ]
        },
        { 
          title: "Cloud Solutions", 
          icon: "fas fa-cloud-arrow-up", 
          shortDesc: "AWS/Azure deployment, DevOps & managed hosting for scalable and reliable infrastructure.",
          tagline: "Scale your business with enterprise cloud infrastructure",
          detailImage: "https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=1200&h=600&fit=crop",
          fullDescription: "Our cloud solutions help businesses leverage the power of cloud computing for scalability, reliability, and cost efficiency. We provide end-to-end cloud services including migration, deployment, management, and optimization on major cloud platforms like AWS, Azure, and Google Cloud. Focus on your core business while we handle your infrastructure.",
          features: [
            "Cloud migration and assessment",
            "DevOps implementation and CI/CD pipelines",
            "Infrastructure as Code (Terraform, CloudFormation)",
            "Container orchestration (Kubernetes, Docker)",
            "Cloud security and compliance",
            "24/7 monitoring and managed services"
          ],
          benefits: [
            { icon: "fas fa-chart-line", title: "Cost Optimization", description: "Pay only for what you use with flexible pricing" },
            { icon: "fas fa-bolt", title: "High Availability", description: "99.99% uptime with multi-region deployment" },
            { icon: "fas fa-shield-alt", title: "Enterprise Security", description: "Advanced security and compliance features" }
          ],
          process: [
            { title: "Assessment", description: "Evaluating your current infrastructure and needs" },
            { title: "Architecture Design", description: "Designing optimal cloud architecture" },
            { title: "Migration", description: "Smooth migration with minimal disruption" },
            { title: "Optimization", description: "Fine-tuning for performance and cost" },
            { title: "Managed Services", description: "Ongoing monitoring and support" }
          ],
          technologies: ["AWS", "Azure", "Google Cloud", "Docker", "Kubernetes", "Terraform", "Jenkins", "Prometheus"]
        },
        { 
          title: "Support & Maintenance", 
          icon: "fas fa-headset", 
          shortDesc: "24/7 technical assistance, proactive monitoring and continuous improvement for peace of mind.",
          tagline: "Round-the-clock support for uninterrupted business operations",
          detailImage: "https://images.unsplash.com/photo-1541746972996-4e0b0f43e02a?w=1200&h=600&fit=crop",
          fullDescription: "Our comprehensive support and maintenance service ensures your digital assets remain secure, updated, and performing optimally. We provide proactive monitoring, rapid incident response, and continuous improvement to keep your business running smoothly. With our 24/7 support team, you can focus on growing your business while we handle the technical details.",
          features: [
            "24/7 technical support and incident response",
            "Proactive system monitoring and alerts",
            "Regular security patches and updates",
            "Performance optimization and tuning",
            "Backup management and disaster recovery",
            "Monthly reporting and analytics"
          ],
          benefits: [
            { icon: "fas fa-clock", title: "Peace of Mind", description: "24/7 coverage means no downtime worries" },
            { icon: "fas fa-chart-line", title: "Optimized Performance", description: "Regular updates keep systems running smoothly" },
            { icon: "fas fa-shield-alt", title: "Enhanced Security", description: "Proactive security measures protect your data" }
          ],
          process: [
            { title: "Onboarding", description: "Setting up monitoring and support systems" },
            { title: "Monitoring", description: "24/7 proactive system monitoring" },
            { title: "Incident Response", description: "Rapid response to any issues" },
            { title: "Maintenance", description: "Regular updates and optimizations" },
            { title: "Reporting", description: "Detailed monthly performance reports" }
          ]
        },
        { 
          title: "Digital Marketing", 
          icon: "fas fa-bullhorn", 
          shortDesc: "SEO, performance marketing, analytics & conversion optimization that drives real business growth.",
          tagline: "Drive measurable growth with data-driven marketing",
          detailImage: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=1200&h=600&fit=crop",
          fullDescription: "Our digital marketing services combine creativity with data-driven strategies to deliver measurable results. We help businesses increase visibility, generate quality leads, and maximize conversions through integrated marketing campaigns. From SEO to social media advertising, we create comprehensive strategies that align with your business goals.",
          features: [
            "Search Engine Optimization (SEO)",
            "Pay-Per-Click advertising (Google Ads, Social)",
            "Social media marketing and management",
            "Content marketing and strategy",
            "Email marketing campaigns",
            "Analytics and conversion tracking"
          ],
          benefits: [
            { icon: "fas fa-chart-line", title: "Measurable ROI", description: "Track every dollar spent and results achieved" },
            { icon: "fas fa-bullseye", title: "Targeted Reach", description: "Reach exactly the right audience" },
            { icon: "fas fa-chart-line", title: "Scalable Growth", description: "Campaigns that scale with your business" }
          ],
          process: [
            { title: "Audit & Analysis", description: "Analyzing current marketing performance" },
            { title: "Strategy Development", description: "Creating a tailored marketing strategy" },
            { title: "Implementation", description: "Launching campaigns across channels" },
            { title: "Optimization", description: "Continuous testing and improvement" },
            { title: "Reporting", description: "Detailed performance analytics and insights" }
          ]
        }
      ]
    }
  },
  methods: {
    viewServiceDetails(service) {
      this.selectedService = service
      window.scrollTo({ top: 0, behavior: 'smooth' })
    },
    goBack() {
      this.selectedService = null
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  },
  mounted() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('animate-in')
        }
      })
    }, { threshold: 0.1 })
    
    const cards = document.querySelectorAll('.service-card-wrapper')
    cards.forEach(card => observer.observe(card))
  }
}
</script>

<style scoped>
.services-component {
  width: 100%;
  overflow-x: hidden;
}

/* Services Hero Section */
.services-hero {
  text-align: center;
  margin-bottom: 60px;
  padding: 40px 20px;
  background: linear-gradient(135deg, #f8fafc 0%, #ffffff 100%);
  border-radius: 40px;
  position: relative;
  overflow: hidden;
}

.services-hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 20% 30%, rgba(37, 99, 235, 0.05) 0%, transparent 70%);
  pointer-events: none;
}

.services-hero-content {
  position: relative;
  z-index: 1;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: linear-gradient(135deg, #2563eb15, #7c3aed15);
  padding: 8px 20px;
  border-radius: 50px;
  margin-bottom: 20px;
  border: 1px solid rgba(37, 99, 235, 0.2);
}

.hero-badge i {
  color: #2563eb;
  font-size: 0.9rem;
}

.hero-badge span {
  font-size: 0.85rem;
  font-weight: 600;
  color: #2563eb;
  letter-spacing: 0.5px;
}

.services-title {
  font-size: 2.8rem;
  font-weight: 800;
  background: linear-gradient(135deg, #0f172a, #2563eb);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  margin-bottom: 15px;
  letter-spacing: -0.02em;
}

.services-subtitle {
  font-size: 1.1rem;
  color: #64748b;
  max-width: 600px;
  margin: 0 auto;
}

/* Services Grid */
.services-grid-container {
  padding: 20px 0 40px;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 32px;
}

.service-card-wrapper {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 0.6s cubic-bezier(0.2, 0.9, 0.4, 1.1) forwards;
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

/* Service Card */
.service-card {
  position: relative;
  background: white;
  border-radius: 28px;
  padding: 40px 28px;
  text-align: center;
  transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1.2);
  box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.08);
  overflow: hidden;
  cursor: pointer;
  height: 100%;
  display: flex;
  flex-direction: column;
  z-index: 1;
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  opacity: 0;
  transition: opacity 0.4s ease;
  z-index: -1;
  border-radius: 28px;
}

.service-card:hover {
  transform: translateY(-12px);
  box-shadow: 0 30px 45px -15px rgba(37, 99, 235, 0.25);
}

.service-card:hover::before {
  opacity: 0.03;
}

.card-glow {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100%;
  background: radial-gradient(circle at 30% 20%, rgba(37, 99, 235, 0.1), transparent 70%);
  opacity: 0;
  transition: opacity 0.4s ease;
  pointer-events: none;
}

.service-card:hover .card-glow {
  opacity: 1;
}

.service-icon-wrapper {
  position: relative;
  width: 100px;
  height: 100px;
  margin: 0 auto 25px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.service-icon {
  position: relative;
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, #eef2ff, #ffffff);
  border-radius: 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  color: #2563eb;
  transition: all 0.3s cubic-bezier(0.2, 0.9, 0.4, 1.2);
  z-index: 2;
  box-shadow: 0 8px 20px rgba(37, 99, 235, 0.15);
}

.service-card:hover .service-icon {
  transform: scale(1.1) rotate(5deg);
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  color: white;
  box-shadow: 0 12px 28px rgba(37, 99, 235, 0.3);
}

.icon-backdrop {
  position: absolute;
  width: 85px;
  height: 85px;
  background: rgba(37, 99, 235, 0.08);
  border-radius: 30px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  transition: all 0.3s ease;
}

.service-card:hover .icon-backdrop {
  width: 95px;
  height: 95px;
  background: rgba(37, 99, 235, 0.15);
}

.service-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 15px;
  transition: color 0.3s ease;
}

.service-card:hover .service-title {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.service-divider {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  margin: 15px 0 20px;
}

.service-divider span {
  width: 40px;
  height: 2px;
  background: linear-gradient(90deg, #e2e8f0, #2563eb, #e2e8f0);
  border-radius: 2px;
}

.service-divider i {
  font-size: 0.5rem;
  color: #2563eb;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 0.5; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.2); }
}

.service-description {
  font-size: 0.9rem;
  color: #64748b;
  line-height: 1.6;
  margin-bottom: 25px;
  flex-grow: 1;
}

.service-footer {
  margin-top: auto;
}

.service-btn {
  background: transparent;
  border: none;
  padding: 10px 20px;
  font-weight: 600;
  font-size: 0.9rem;
  color: #2563eb;
  cursor: pointer;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  border-radius: 30px;
}

.service-btn i {
  transition: transform 0.3s ease;
  font-size: 0.8rem;
}

.service-card:hover .service-btn {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  color: white;
  padding: 10px 24px;
  box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
}

.service-card:hover .service-btn i {
  transform: translateX(4px);
}

.card-decoration {
  position: absolute;
  bottom: 15px;
  right: 15px;
  display: flex;
  gap: 6px;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.service-card:hover .card-decoration {
  opacity: 1;
}

.dot {
  width: 4px;
  height: 4px;
  border-radius: 50%;
  background: #2563eb;
  opacity: 0.5;
}

.dot-1 { animation: dotPulse 1s ease infinite; }
.dot-2 { animation: dotPulse 1s ease infinite 0.2s; }
.dot-3 { animation: dotPulse 1s ease infinite 0.4s; }

@keyframes dotPulse {
  0%, 100% { opacity: 0.3; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.5); }
}

/* Service Details Page */
.service-details-page {
  padding: 40px 0 60px;
}

.back-button {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: #f1f5f9;
  border: none;
  padding: 12px 24px;
  border-radius: 40px;
  font-weight: 600;
  color: #2563eb;
  cursor: pointer;
  margin-bottom: 30px;
  transition: all 0.3s ease;
}

.back-button:hover {
  background: #2563eb;
  color: white;
  transform: translateX(-5px);
}

.service-details-hero {
  background-size: cover;
  background-position: center;
  border-radius: 40px;
  padding: 100px 40px;
  margin-bottom: 50px;
  color: white;
  text-align: center;
}

.service-details-content .service-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  padding: 10px 24px;
  border-radius: 50px;
  font-size: 1rem;
  font-weight: 600;
  margin-bottom: 25px;
}

.service-details-content h1 {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 20px;
}

.service-details-content p {
  font-size: 1.2rem;
  opacity: 0.9;
  max-width: 700px;
  margin: 0 auto;
}

/* Service Details Grid */
.service-details-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 30px;
}

.details-card {
  background: white;
  border-radius: 28px;
  padding: 35px;
  box-shadow: 0 15px 30px -12px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
}

.details-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 25px 40px -15px rgba(37, 99, 235, 0.15);
}

.details-card h2 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 25px;
  display: flex;
  align-items: center;
  gap: 12px;
}

.details-card h2 i {
  color: #2563eb;
}

.overview-card {
  grid-column: span 2;
}

.overview-card p {
  font-size: 1rem;
  line-height: 1.7;
  color: #475569;
}

.features-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 10px;
  background: #f8fafc;
  border-radius: 16px;
}

.feature-item i {
  color: #10b981;
  font-size: 1.1rem;
}

.feature-item span {
  font-size: 0.9rem;
  color: #334155;
}

.benefits-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.benefit-item {
  display: flex;
  gap: 18px;
  padding: 15px;
  background: #f8fafc;
  border-radius: 20px;
  transition: all 0.3s ease;
}

.benefit-item:hover {
  background: #eef2ff;
  transform: translateX(5px);
}

.benefit-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.benefit-icon i {
  font-size: 1.3rem;
  color: white;
}

.benefit-content h4 {
  font-size: 1rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 5px;
}

.benefit-content p {
  font-size: 0.85rem;
  color: #64748b;
  margin: 0;
}

.process-steps {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.step-item {
  display: flex;
  gap: 18px;
  align-items: flex-start;
}

.step-number {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  font-weight: 700;
  color: white;
  flex-shrink: 0;
}

.step-content h4 {
  font-size: 1rem;
  font-weight: 700;
  color: #0f172a;
  margin-bottom: 5px;
}

.step-content p {
  font-size: 0.85rem;
  color: #64748b;
  margin: 0;
}

.tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.tech-tag {
  background: linear-gradient(135deg, #eef2ff, #ffffff);
  padding: 8px 18px;
  border-radius: 30px;
  font-size: 0.85rem;
  font-weight: 500;
  color: #2563eb;
  border: 1px solid rgba(37, 99, 235, 0.2);
}

.cta-card {
  grid-column: span 2;
  text-align: center;
  background: linear-gradient(135deg, #0f172a, #1e293b);
  color: white;
}

.cta-card h2 {
  color: white;
}

.cta-card h2 i {
  color: #60a5fa;
}

.cta-card p {
  color: #cbd5e1;
  margin-bottom: 25px;
}

.cta-button {
  background: linear-gradient(135deg, #2563eb, #7c3aed);
  border: none;
  padding: 14px 32px;
  border-radius: 50px;
  font-weight: 700;
  font-size: 1rem;
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 25px rgba(37, 99, 235, 0.3);
}

/* Responsive */
@media (max-width: 768px) {
  .services-title {
    font-size: 2rem;
  }
  
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .service-details-grid {
    grid-template-columns: 1fr;
  }
  
  .overview-card,
  .cta-card {
    grid-column: span 1;
  }
  
  .features-list {
    grid-template-columns: 1fr;
  }
  
  .service-details-hero {
    padding: 60px 20px;
  }
  
  .service-details-content h1 {
    font-size: 2rem;
  }
  
  .details-card {
    padding: 25px;
  }
}

@media (min-width: 769px) and (max-width: 1024px) {
  .services-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>