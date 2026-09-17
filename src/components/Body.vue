<template>
  <section class="ambassador-hero">
    <div class="hero-container">
      <!-- Main Title Section -->
      <div class="hero-header">
        <span class="badge">PROGRAM AMBASADORSKI</span>
        <h1>Zostań Ambasadorem <span>Lavish Care</span></h1>
        <p class="subtitle">
          Promuj Markę. Zostań Częścią Naszego Zespołu.<br />
          Dołącz do programu Lavish Care Ambassador i współpracuj z nami, prezentując nasze produkty swojej społeczności.
        </p>
      </div>

      <!-- Features Cards Grid -->
      <div class="features-grid">
        <!-- Feature 1 -->
        <div class="feature-card">
          <div class="icon-box">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2" />
              <circle cx="9" cy="7" r="4" />
              <polyline points="16 11 18 13 22 9" />
            </svg>
          </div>
          <h3>Łatwa Rejestracja</h3>
          <p>Wypełnij swoje dane tylko raz i szybko prześlij zgłoszenie.</p>
        </div>

        <!-- Feature 2 -->
        <div class="feature-card">
          <div class="icon-box">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z" />
            </svg>
          </div>
          <h3>Oficjalna Współpraca z Marką</h3>
          <p>Zostań oficjalnym Ambasadorem Lavish Care i reprezentuj markę poprzez własne treści oraz media społecznościowe.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Component logic (if needed in the future)
</script>

<style scoped>
.ambassador-hero {
  width: 100%;
  background: radial-gradient(circle at top, #1a1a1a 0%, #121212 100%);
  color: #ffffff;
  padding: 60px 20px;
  box-sizing: border-box;
}

.hero-container {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 50px;
}

/* Header Styles */
.hero-header {
  text-align: center;
  max-width: 800px;
}

.badge {
  display: inline-block;
  background: rgba(199, 156, 77, 0.894);
  color: #3d3b37;
  border: 1px solid rgba(227, 169, 63, 0.623);
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 2px;
  margin-bottom: 20px;
}

.hero-header h1 {
  font-size: clamp(2rem, 5vw, 3.2rem);
  font-weight: 800;
  letter-spacing: 1px;
  margin: 0 0 20px 0;
  line-height: 1.2;
}

.hero-header h1 span {
  color: #42403d;
}

.subtitle {
  color: #b0b0b0;
  font-size: clamp(1rem, 2vw, 1.2rem);
  line-height: 1.6;
  margin: 0;
}

/* Grid & Cards Styles */
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  width: 100%;
}

.feature-card {
  background: rgba(255, 255, 255, 0.02);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 35px 25px;
  text-align: center;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.feature-card:hover {
  transform: translateY(-5px);
  border-color: rgba(197, 160, 89, 0.4);
  background: rgba(255, 255, 255, 0.04);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

.icon-box {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, #2a2a2a 0%, #151515 100%);
  border: 1px solid #3a3834;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
  color: #6a665e;
}

.icon-box svg {
  width: 28px;
  height: 28px;
}

.feature-card h3 {
  font-size: 1.3rem;
  font-weight: 700;
  margin: 0 0 12px 0;
  color: #ffffff;
}

.feature-card p {
  color: #a0a0a0;
  font-size: 0.95rem;
  line-height: 1.5;
  margin: 0;
}

/* Responsive Padding */
@media (max-width: 768px) {
  .ambassador-hero {
    padding: 40px 16px;
  }
}
</style>