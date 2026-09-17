<template>
  <header class="barber-header">
    <div class="header-container">
      <!-- Αριστερή πλευρά: Logo & Name -->
      <div class="brand">
        <div class="logo-wrapper">
          <!-- Διάβασμα favicon από τον φάκελο public -->
          <img src="/favicon.ico" alt="LavishCare Logo" class="logo-img" />
        </div>
        <span class="brand-name">LAVISH<span>CARE</span></span>
      </div>

      <!-- Δεξιά πλευρά: Badge Ασφαλείας -->
      <div class="verified-badge">
        <span class="pulse-dot"></span>
        <svg class="shield-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
          <path d="m9 12 2 2 4-4"/>
        </svg>
        <span>Bezpieczne & Zweryfikowane</span>
      </div>
    </div>
  </header>
</template>

<style scoped>
.barber-header {
  width: 100%;
  background: rgba(18, 18, 18, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(197, 160, 89, 0.2);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.4);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.header-container {
  width: 100%;
  padding: 14px 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
}

/* Brand styling */
.brand {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-wrapper {
  background: linear-gradient(135deg, #2a2a2a 0%, #151515 100%);
  border: 1px solid #979694;
  width: 40px;
  height: 40px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 8px rgba(197, 160, 89, 0.15);
  overflow: hidden;
  padding: 4px;
  box-sizing: border-box;
}

.logo-img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.brand-name {
  color: #FFFFFF;
  font-weight: 800;
  font-size: 1.3rem;
  letter-spacing: 2px;
  font-family: 'Montserrat', system-ui, sans-serif;
}

.brand-name span {
  color: #b1ada6;
}

/* Badge styling */
.verified-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  color: #E0E0E0;
  font-size: 0.85rem;
  font-weight: 600;
  background: rgba(255, 255, 255, 0.05);
  padding: 6px 14px;
  border-radius: 20px;
  border: 1px solid rgba(76, 175, 80, 0.3);
  letter-spacing: 0.3px;
}

.pulse-dot {
  width: 6px;
  height: 6px;
  background-color: #4CAF50;
  border-radius: 50%;
  box-shadow: 0 0 8px #4CAF50;
}

.shield-icon {
  width: 16px;
  height: 16px;
  stroke: #4CAF50;
}

@media (max-width: 600px) {
  .header-container {
    padding: 12px 16px;
  }

  .brand-name {
    font-size: 1.1rem;
  }

  .verified-badge {
    padding: 5px 10px;
    font-size: 0.75rem;
  }
}
</style>