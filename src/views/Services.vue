<template>
  <main>
    <section class="services-hero">
      <div class="container">
        <h1>Layanan Kami</h1>
        <p class="lead">Solusi teknologi komprehensif untuk kebutuhan bisnis Anda</p>
      </div>
    </section>

    <section class="services-list">
      <div class="container">
        <div class="services-grid">
          <div v-for="service in services" :key="service.id" class="service-card">
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
import servicesData from '../../data/services.json'

export default {
  name: 'Services',
  data() {
    return {
      services: servicesData.services
    }
  }
}
</script>

<style scoped>
.services-hero {
  background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.services-hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.lead {
  font-size: 1.2rem;
  opacity: 0.9;
}

.services-list {
  padding: 4rem 0;
  background-color: #f8f9fa;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.service-card {
  background: white;
  padding: 2.5rem;
  border-radius: 15px;
  box-shadow: 0 5px 20px rgba(0,0,0,0.1);
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.service-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 15px 40px rgba(0,0,0,0.15);
}

.service-icon {
  font-size: 4rem;
  margin-bottom: 1.5rem;
}

.service-card h3 {
  color: #2c3e50;
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.service-card p {
  color: #7f8c8d;
  line-height: 1.6;
  font-size: 1rem;
}

@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }
  
  .services-hero h1 {
    font-size: 2rem;
  }
}
</style>