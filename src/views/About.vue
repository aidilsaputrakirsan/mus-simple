<template>
  <main>
    <section class="about-hero">
      <div class="container">
        <h1>About {{ companyData.name }}</h1>
        <p class="lead">{{ companyData.description }}</p>
      </div>
    </section>

    <section class="about-content">
      <div class="container">
        <div class="content-grid">
          <div class="mission-vision">
            <div class="mission">
              <h2>Our Mission</h2>
              <p>{{ companyData.mission }}</p>
            </div>
            <div class="vision">
              <h2>Our Vision</h2>
              <p>{{ companyData.vision }}</p>
            </div>
          </div>
          
          <div class="company-info">
            <h2>Company Overview</h2>
            <div class="info-grid">
              <div class="info-item">
                <strong>Founded:</strong> {{ companyData.founded }}
              </div>
              <div class="info-item">
                <strong>Team Size:</strong> {{ companyData.employees }}
              </div>
              <div class="info-item">
                <strong>Locations:</strong>
                <ul>
                  <li v-for="location in companyData.locations" :key="location">
                    {{ location }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
import companyData from '../../data/company.json'

export default {
  name: 'About',
  data() {
    return {
      companyData: companyData
    }
  }
}
</script>

<style scoped>
.about-hero {
  background-color: #34495e;
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.about-hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.lead {
  font-size: 1.2rem;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

.about-content {
  padding: 4rem 0;
}

.content-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.mission-vision {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.mission, .vision {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 10px;
}

.mission h2, .vision h2 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.company-info {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

.company-info h2 {
  color: #2c3e50;
  margin-bottom: 2rem;
}

.info-grid {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.info-item {
  padding: 1rem;
  background: #f8f9fa;
  border-radius: 5px;
}

.info-item strong {
  color: #2c3e50;
}

.info-item ul {
  margin-top: 0.5rem;
  margin-left: 1rem;
}

@media (max-width: 768px) {
  .content-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .about-hero h1 {
    font-size: 2rem;
  }
}
</style>