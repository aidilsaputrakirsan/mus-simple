<template>
  <main>
    <section class="contact-hero">
      <div class="container">
        <h1>Contact Us</h1>
        <p class="lead">Get in touch with our team</p>
      </div>
    </section>

    <section class="contact-content">
      <div class="container">
        <div class="contact-grid">
          <div class="contact-info">
            <h2>Get In Touch</h2>
            <p>We'd love to hear from you. Send us a message and we'll respond as soon as possible.</p>
            
            <div class="contact-details">
              <div class="contact-item">
                <h3>📧 Email</h3>
                <p>info@techcorp.com</p>
              </div>
              <div class="contact-item">
                <h3>📞 Phone</h3>
                <p>+62 21 1234 5678</p>
              </div>
              <div class="contact-item">
                <h3>📍 Address</h3>
                <p>Jl. Sudirman No. 123<br>Jakarta 12345, Indonesia</p>
              </div>
            </div>
          </div>

          <div class="contact-form">
            <h2>Send Message</h2>
            <form @submit.prevent="submitForm">
              <div class="form-group">
                <label for="name">Name</label>
                <input 
                  type="text" 
                  id="name" 
                  v-model="form.name" 
                  required
                  placeholder="Your Name"
                >
              </div>
              
              <div class="form-group">
                <label for="email">Email</label>
                <input 
                  type="email" 
                  id="email" 
                  v-model="form.email" 
                  required
                  placeholder="your.email@example.com"
                >
              </div>
              
              <div class="form-group">
                <label for="subject">Subject</label>
                <input 
                  type="text" 
                  id="subject" 
                  v-model="form.subject" 
                  required
                  placeholder="Message Subject"
                >
              </div>
              
              <div class="form-group">
                <label for="message">Message</label>
                <textarea 
                  id="message" 
                  v-model="form.message" 
                  required
                  rows="5"
                  placeholder="Your message here..."
                ></textarea>
              </div>
              
              <button type="submit" class="submit-btn">Send Message</button>
            </form>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  },
  methods: {
    submitForm() {
      // Simple form validation and submission
      alert('Thank you for your message! We will get back to you soon.')
      
      // Reset form
      this.form = {
        name: '',
        email: '',
        subject: '',
        message: ''
      }
    }
  }
}
</script>

<style scoped>
.contact-hero {
  background-color: #e17055;
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.contact-hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.lead {
  font-size: 1.2rem;
  opacity: 0.9;
}

.contact-content {
  padding: 4rem 0;
  background-color: #f8f9fa;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-info h2,
.contact-form h2 {
  color: #2c3e50;
  margin-bottom: 1.5rem;
}

.contact-info p {
  margin-bottom: 2rem;
  color: #7f8c8d;
  line-height: 1.6;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.contact-item {
  background: white;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.contact-item h3 {
  margin-bottom: 0.5rem;
  color: #2c3e50;
}

.contact-form {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: #2c3e50;
  font-weight: bold;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 12px;
  border: 2px solid #e9ecef;
  border-radius: 5px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #3498db;
}

.submit-btn {
  background-color: #3498db;
  color: white;
  padding: 12px 30px;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s ease;
  width: 100%;
}

.submit-btn:hover {
  background-color: #2980b9;
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .contact-hero h1 {
    font-size: 2rem;
  }
}
</style>