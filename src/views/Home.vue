<template>
  <main>
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero-container">
        <h1 class="hero-title">{{ companyData.name }}</h1>
        <p class="hero-subtitle">{{ companyData.tagline }}</p>
        <p class="hero-description">{{ companyData.description }}</p>
        <router-link to="/services" class="cta-button">Our Services</router-link>
      </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
      <div class="stats-container">
        <div class="stat-item">
          <h3>Founded</h3>
          <p>{{ companyData.founded }}</p>
        </div>
        <div class="stat-item">
          <h3>Employees</h3>
          <p>{{ companyData.employees }}</p>
        </div>
        <div class="stat-item">
          <h3>Locations</h3>
          <p>{{ companyData.locations.length }}+</p>
        </div>
      </div>
    </section>

    <!-- Services Preview -->
    <section class="services-preview">
      <div class="container">
        <h2>Our Services</h2>
        <div class="services-grid">
          <div v-for="service in featuredServices" :key="service.id" class="service-card">
            <div class="service-icon">{{ service.icon }}</div>
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import companyData from '../../data/company.json'
import servicesData from '../../data/services.json'

export default {
  name: 'Home',
  data() {
    return {
      companyData: companyData
    }
  },
  computed: {
    featuredServices() {
      return servicesData.services.slice(0, 3)
    }
  }
}
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.hero-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero-title {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: bold;
}

.hero-subtitle {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  opacity: 0.9;
}

.hero-description {
  font-size: 1.1rem;
  margin-bottom: 2rem;
  opacity: 0.8;
}

.cta-button {
  display: inline-block;
  background-color: #3498db;
  color: white;
  padding: 12px 30px;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  transition: background-color 0.3s ease;
}

.cta-button:hover {
  background-color: #2980b9;
}

.stats {
  background-color: #f8f9fa;
  padding: 3rem 0;
}

.stats-container {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
  padding: 0 2rem;
}

.stat-item {
  text-align: center;
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.stat-item h3 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.stat-item p {
  font-size: 2rem;
  font-weight: bold;
  color: #3498db;
}

.services-preview {
  padding: 4rem 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.services-preview h2 {
  text-align: center;
  margin-bottom: 3rem;
  color: #2c3e50;
  font-size: 2.5rem;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.service-card {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  text-align: center;
  transition: transform 0.3s ease;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.service-card h3 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.service-card p {
  color: #7f8c8d;
  line-height: 1.6;
}
</style>