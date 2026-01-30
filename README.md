<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Water Flow - Eastern Cape Booty Call Service</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-tap-highlight-color: transparent;
}

:root {
  --primary-red: #ff3b30;
  --dark-red: #d32f2f;
  --accent-gold: #ffd700;
  --black: #121212;
  --dark-gray: #1e1e1e;
  --medium-gray: #2d2d2d;
  --light-gray: #3a3a3a;
  --text-light: #f0f0f0;
  --text-muted: #aaaaaa;
  --success: #2ecc71;
  --warning: #e74c3c;
}

body {
  background-color: var(--black);
  color: var(--text-light);
  min-height: 100vh;
  overflow-x: hidden;
  padding-bottom: env(safe-area-inset-bottom);
}

.container {
  max-width: 100%;
  margin: 0 auto;
  padding: 0 15px;
}

/* Mobile Header */
header {
  background-color: rgba(0, 0, 0, 0.95);
  padding: 15px 0;
  border-bottom: 2px solid var(--primary-red);
  position: sticky;
  top: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
}

.logo-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding: 0 10px;
}

.logo {
  font-size: 1.8rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--primary-red);
  text-shadow: 0 0 10px rgba(255, 59, 48, 0.5);
  display: flex;
  align-items: center;
}

.logo i {
  margin-right: 10px;
  font-size: 2rem;
  color: var(--primary-red);
}

.logo-text {
  position: relative;
}

.logo-text::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  height: 2px;
  background: linear-gradient(to right, var(--primary-red), transparent);
}

.slogan {
  color: var(--accent-gold);
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 0.5px;
  margin-top: 8px;
  text-align: center;
}

.location-badge {
  background: linear-gradient(45deg, var(--primary-red), #ff6b6b);
  color: white;
  padding: 6px 15px;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  margin-top: 8px;
  display: inline-block;
}

/* Main Content */
.main-content {
  padding: 20px 0;
  min-height: calc(100vh - 150px);
}

/* Step Containers */
.step-container {
  display: none;
  background-color: var(--dark-gray);
  border-radius: 12px;
  padding: 25px 15px;
  margin: 20px auto;
  max-width: 100%;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  border: 1px solid var(--medium-gray);
}

.active-step {
  display: block;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

.step-title {
  font-size: 1.5rem;
  margin-bottom: 20px;
  color: var(--primary-red);
  text-align: center;
  position: relative;
  padding-bottom: 10px;
}

.step-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 80px;
  height: 2px;
  background-color: var(--primary-red);
}

/* Mobile Search */
.search-container {
  margin: 20px 0;
}

.search-box {
  position: relative;
  margin-bottom: 15px;
}

.search-input {
  width: 100%;
  padding: 14px 45px 14px 15px;
  background-color: var(--light-gray);
  border: 2px solid var(--medium-gray);
  border-radius: 8px;
  color: var(--text-light);
  font-size: 16px; /* Prevents zoom on iOS */
  transition: all 0.3s ease;
  -webkit-appearance: none;
}

.search-input:focus {
  outline: none;
  border-color: var(--primary-red);
  box-shadow: 0 0 10px rgba(255, 59, 48, 0.2);
}

.search-icon {
  position: absolute;
  right: 15px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-muted);
  font-size: 1.1rem;
}

/* City Grid for Mobile */
.city-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
  margin: 15px 0;
  max-height: 300px;
  overflow-y: auto;
  padding: 10px;
  -webkit-overflow-scrolling: touch;
}

.city-card {
  background: var(--medium-gray);
  border-radius: 8px;
  padding: 12px;
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid transparent;
  min-height: 100px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.city-card:hover, .city-card:active {
  border-color: var(--primary-red);
  transform: scale(1.02);
}

.city-card.selected {
  background: rgba(255, 59, 48, 0.1);
  border-color: var(--primary-red);
}

.city-card i {
  font-size: 1.8rem;
  color: var(--primary-red);
  margin-bottom: 8px;
}

.city-name {
  font-weight: 600;
  margin-bottom: 4px;
  font-size: 0.95rem;
  word-break: break-word;
}

.booty-count {
  font-size: 0.75rem;
  color: var(--accent-gold);
}

/* Booty Calls Grid for Mobile */
.booty-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 15px;
  margin: 20px 0;
}

.booty-card {
  background: linear-gradient(135deg, var(--medium-gray), var(--dark-gray));
  border-radius: 10px;
  overflow: hidden;
  border: 2px solid transparent;
  transition: all 0.3s ease;
}

.booty-card:active {
  transform: scale(0.98);
}

.booty-card.featured {
  border-color: var(--accent-gold);
  position: relative;
}

.booty-card.featured::before {
  content: 'AVAILABLE';
  position: absolute;
  top: 10px;
  right: -30px;
  background: var(--accent-gold);
  color: black;
  padding: 4px 30px;
  transform: rotate(45deg);
  font-size: 0.7rem;
  font-weight: bold;
  z-index: 1;
}

.booty-img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-bottom: 2px solid var(--primary-red);
}

.booty-info {
  padding: 15px;
}

.booty-name {
  color: var(--primary-red);
  font-size: 1.2rem;
  margin-bottom: 5px;
}

.booty-details {
  color: var(--text-muted);
  font-size: 0.85rem;
  margin-bottom: 8px;
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  align-items: center;
}

.booty-location {
  background: rgba(255, 59, 48, 0.2);
  color: var(--primary-red);
  padding: 3px 8px;
  border-radius: 12px;
  font-size: 0.75rem;
}

.booty-features {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin: 12px 0;
}

.feature-tag {
  background: rgba(255, 59, 48, 0.2);
  color: var(--primary-red);
  padding: 4px 8px;
  border-radius: 12px;
  font-size: 0.75rem;
  font-weight: 600;
}

.feature-tag.accommodation {
  background: rgba(255, 215, 0, 0.2);
  color: var(--accent-gold);
}

.booty-pricing {
  background: rgba(0, 0, 0, 0.3);
  border-radius: 6px;
  padding: 12px;
  margin-top: 12px;
}

.price-tag {
  font-size: 1.6rem;
  color: var(--accent-gold);
  font-weight: 800;
  margin-bottom: 5px;
}

.price-note {
  font-size: 0.85rem;
  color: var(--text-muted);
}

/* Gallery Section */
.gallery-section {
  margin: 20px 0;
  padding: 15px;
  background: var(--medium-gray);
  border-radius: 10px;
}

.gallery-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
  color: var(--primary-red);
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
  margin-bottom: 15px;
}

.gallery-item {
  aspect-ratio: 1;
  border-radius: 6px;
  overflow: hidden;
  cursor: pointer;
  position: relative;
}

.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.gallery-item:hover img, .gallery-item:active img {
  transform: scale(1.05);
}

.gallery-item.video::after {
  content: '▶';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  background: rgba(0, 0, 0, 0.7);
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
}

/* Ratings Section */
.ratings-section {
  margin: 20px 0;
  padding: 15px;
  background: var(--medium-gray);
  border-radius: 10px;
}

.ratings-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.rating-summary {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 15px;
}

.rating-stars {
  color: var(--accent-gold);
  font-size: 1.2rem;
}

.rating-count {
  color: var(--text-muted);
  font-size: 0.9rem;
}

.reviews-list {
  max-height: 200px;
  overflow-y: auto;
  -webkit-overflow-scrolling: touch;
}

.review-item {
  padding: 10px 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.review-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 5px;
}

.reviewer-name {
  font-weight: 600;
  color: var(--text-light);
}

.review-date {
  color: var(--text-muted);
  font-size: 0.8rem;
}

.review-text {
  color: var(--text-muted);
  font-size: 0.9rem;
  line-height: 1.4;
}

/* Booking Form */
.booking-form {
  background: var(--medium-gray);
  border-radius: 10px;
  padding: 20px;
  margin: 20px 0;
}

.form-row {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-bottom: 15px;
}

.form-group {
  margin-bottom: 15px;
}

.form-label {
  display: block;
  margin-bottom: 6px;
  font-weight: 600;
  color: var(--text-muted);
  font-size: 0.9rem;
}

.form-input, .form-select {
  width: 100%;
  padding: 14px;
  background-color: var(--light-gray);
  border: 1px solid var(--medium-gray);
  border-radius: 8px;
  color: var(--text-light);
  font-size: 16px; /* Prevents zoom on iOS */
  transition: border 0.3s;
  -webkit-appearance: none;
}

.form-input:focus, .form-select:focus {
  outline: none;
  border-color: var(--primary-red);
}

.time-info {
  background: rgba(255, 59, 48, 0.1);
  border-radius: 6px;
  padding: 12px;
  margin: 8px 0;
  font-size: 0.85rem;
  color: var(--text-muted);
}

.time-info strong {
  color: var(--accent-gold);
}

/* Selfie Upload Mobile */
.selfie-upload {
  border: 2px dashed var(--primary-red);
  border-radius: 8px;
  padding: 25px 15px;
  text-align: center;
  margin: 20px 0;
  cursor: pointer;
  transition: all 0.3s ease;
}

.selfie-upload:active {
  background: rgba(255, 59, 48, 0.05);
}

.selfie-upload i {
  font-size: 2.5rem;
  color: var(--primary-red);
  margin-bottom: 12px;
}

#selfiePreview {
  display: none;
  max-width: 150px;
  border-radius: 6px;
  margin: 12px auto;
}

.terms-agreement {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  margin: 20px 0;
  font-size: 0.9rem;
}

.terms-agreement input {
  margin-top: 4px;
  transform: scale(1.2);
}

/* Payment Box */
.payment-box {
  background: rgba(255, 59, 48, 0.1);
  border: 2px solid var(--primary-red);
  border-radius: 8px;
  padding: 20px 15px;
  margin: 20px 0;
  text-align: center;
}

.payment-box i {
  font-size: 2.5rem;
  color: var(--primary-red);
  margin-bottom: 12px;
}

.pay-button {
  background: linear-gradient(45deg, #ff3b30, #ff6b6b);
  color: white;
  border: none;
  padding: 16px 30px;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 12px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  text-decoration: none;
  width: 100%;
  max-width: 300px;
}

.pay-button:active {
  background: linear-gradient(45deg, #ff6b6b, #ff3b30);
  transform: scale(0.98);
}

/* Success Screen */
.success-container {
  text-align: center;
  padding: 30px 15px;
}

.success-icon {
  font-size: 4rem;
  color: var(--success);
  margin-bottom: 20px;
  animation: bounce 1s ease;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
  40% {transform: translateY(-15px);}
  60% {transform: translateY(-8px);}
}

.booking-summary {
  background: rgba(255, 59, 48, 0.1);
  border-radius: 8px;
  padding: 20px;
  margin: 25px 0;
  text-align: left;
}

.summary-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 12px;
  margin-top: 15px;
}

.summary-item {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 6px;
  padding: 12px;
}

.summary-label {
  color: var(--text-muted);
  font-size: 0.8rem;
  margin-bottom: 4px;
}

.summary-value {
  color: var(--accent-gold);
  font-size: 1rem;
  font-weight: 600;
}

/* Buttons for Mobile */
.btn {
  padding: 16px 25px;
  background: linear-gradient(45deg, var(--primary-red), var(--dark-red));
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  text-decoration: none;
  width: 100%;
  max-width: 300px;
  touch-action: manipulation;
}

.btn:active {
  background: linear-gradient(45deg, var(--dark-red), var(--primary-red));
  transform: scale(0.98);
}

.btn:disabled {
  background: var(--medium-gray);
  cursor: not-allowed;
  transform: none;
}

.btn-gold {
  background: linear-gradient(45deg, #ffd700, #ffaa00);
  color: black;
}

.btn-gold:active {
  background: linear-gradient(45deg, #ffaa00, #ffd700);
}

.btn-back {
  background: transparent;
  border: 2px solid var(--light-gray);
  margin-bottom: 10px;
}

.btn-back:active {
  background: var(--light-gray);
}

.button-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  margin-top: 30px;
}

/* Footer Mobile */
footer {
  background-color: var(--dark-gray);
  padding: 25px 15px;
  text-align: center;
  border-top: 1px solid var(--medium-gray);
  margin-top: 40px;
}

.footer-links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 15px;
  margin-bottom: 15px;
}

.footer-links a {
  color: var(--text-muted);
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s;
  padding: 5px 10px;
}

.footer-links a:active {
  color: var(--primary-red);
}

.copyright {
  color: var(--text-muted);
  font-size: 0.8rem;
  margin-top: 15px;
  line-height: 1.4;
}

.disclaimer {
  font-size: 0.75rem;
  color: var(--warning);
  margin-top: 10px;
  line-height: 1.4;
}

/* Swipe Navigation */
.swipe-area {
  display: none;
}

/* Back to Top Button */
.back-to-top {
  position: fixed;
  bottom: 80px;
  right: 20px;
  background: var(--primary-red);
  color: white;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  cursor: pointer;
  z-index: 100;
  box-shadow: 0 4px 15px rgba(255, 59, 48, 0.4);
  transition: all 0.3s ease;
}

.back-to-top:active {
  transform: scale(0.9);
}

/* Tablet Styles */
@media (min-width: 768px) {
  .container {
    max-width: 720px;
    padding: 0 20px;
  }
  
  .logo {
    font-size: 2.2rem;
  }
  
  .step-container {
    padding: 30px 25px;
  }
  
  .city-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
  }
  
  .booty-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }
  
  .button-container {
    flex-direction: row;
    justify-content: center;
    gap: 15px;
  }
  
  .btn {
    width: auto;
    min-width: 200px;
  }
  
  .form-row {
    flex-direction: row;
  }
}

/* Desktop Styles */
@media (min-width: 1024px) {
  .container {
    max-width: 900px;
  }
  
  .city-grid {
    grid-template-columns: repeat(4, 1fr);
  }
  
  .booty-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style>
</head>
<body>
<header>
  <div class="container">
    <div class="logo-container">
      <div class="logo">
        <i class="fas fa-fire"></i>
        <div class="logo-text">Water Flow</div>
      </div>
      <div class="slogan">Eastern Cape Booty Call Service</div>
      <div class="location-badge">
        <i class="fas fa-map-marker-alt"></i> Eastern Cape Exclusive
      </div>
    </div>
  </div>
</header>

<div class="main-content">
  <div class="container">
    <!-- Step 1: Location Search -->
    <div class="step-container active-step" id="step1">
      <h2 class="step-title">Make That Booty Call</h2>
      
      <div class="search-container">
        <p style="text-align: center; color: var(--accent-gold); margin-bottom: 20px; font-size: 1rem;">
          <i class="fas fa-map-marker-alt"></i> Find available booty calls in your city
        </p>
        
        <div class="search-box">
          <input type="text" id="citySearch" class="search-input" placeholder="Search for your city...">
          <div class="search-icon">
            <i class="fas fa-search"></i>
          </div>
        </div>
        
        <div class="city-grid" id="cityGrid">
          <!-- Cities populated by JavaScript -->
        </div>
      </div>
      
      <div style="text-align: center; margin-top: 30px; color: var(--text-muted); font-size: 0.9rem;">
        <p><i class="fas fa-info-circle"></i> Tap on your city to see available booty calls</p>
      </div>
    </div>

    <!-- Step 2: Booty Call Details -->
    <div class="step-container" id="step2">
      <h2 class="step-title">Available in <span id="selectedCityDisplay">Your Area</span></h2>
      
      <div class="booty-grid" id="bootyGrid">
        <!-- Booty calls populated by JavaScript -->
      </div>
      
      <div class="button-container">
        <button class="btn btn-back" id="back-to-search">Change Location</button>
      </div>
    </div>

    <!-- Step 3: Booty Call Profile -->
    <div class="step-container" id="step3">
      <div style="margin-bottom: 20px;">
        <button class="btn-back" onclick="goToStep(2)" style="padding: 10px 15px; font-size: 0.9rem;">
          <i class="fas fa-arrow-left"></i> Back
        </button>
      </div>
      
      <div id="bootyProfile">
        <!-- Profile populated by JavaScript -->
      </div>
    </div>

    <!-- Step 4: Booking Form -->
    <div class="step-container" id="step4">
      <h2 class="step-title">Book <span id="bootyNameDisplay"></span></h2>
      
      <div class="booking-form">
        <div class="form-row">
          <div class="form-group">
            <label class="form-label" for="full-name">Full Name *</label>
            <input type="text" id="full-name" class="form-input" placeholder="First and Last Name" required>
          </div>
          
          <div class="form-group">
            <label class="form-label" for="phone">WhatsApp Number *</label>
            <input type="tel" id="phone" class="form-input" placeholder="+27 63 123 4567" required>
          </div>
        </div>
        
        <div class="form-row">
          <div class="form-group">
            <label class="form-label" for="location">Meeting Location *</label>
            <input type="text" id="location" class="form-input" placeholder="Your address or meeting point" required>
          </div>
          
          <div class="form-group">
            <label class="form-label" for="date">Preferred Date *</label>
            <input type="date" id="date" class="form-input" required>
          </div>
        </div>
        
        <div class="form-row">
          <div class="form-group">
            <label class="form-label" for="start-time">Start Time *</label>
            <select id="start-time" class="form-select" required>
              <option value="">Select start time</option>
              <option value="18:00">6:00 PM</option>
              <option value="19:00">7:00 PM</option>
              <option value="20:00">8:00 PM</option>
              <option value="21:00">9:00 PM</option>
              <option value="22:00">10:00 PM</option>
              <option value="23:00">11:00 PM</option>
              <option value="00:00">12:00 AM</option>
              <option value="01:00">1:00 AM</option>
              <option value="02:00">2:00 AM</option>
              <option value="08:00">8:00 AM</option>
              <option value="09:00">9:00 AM</option>
              <option value="10:00">10:00 AM</option>
              <option value="11:00">11:00 AM</option>
              <option value="12:00">12:00 PM</option>
              <option value="13:00">1:00 PM</option>
              <option value="14:00">2:00 PM</option>
              <option value="15:00">3:00 PM</option>
              <option value="16:00">4:00 PM</option>
              <option value="17:00">5:00 PM</option>
            </select>
            <div id="endTimeDisplay" class="time-info"></div>
          </div>
          
          <div class="form-group">
            <label class="form-label" for="duration">Duration *</label>
            <select id="duration" class="form-select" required>
              <option value="">Select duration</option>
              <option value="2">2 Hours - R400</option>
              <option value="4">4 Hours - R600</option>
              <option value="6">6 Hours - R800</option>
            </select>
          </div>
        </div>
        
        <!-- Selfie Upload -->
        <div class="form-group">
          <label class="form-label">Verify Identity - Upload Selfie *</label>
          <div class="selfie-upload" id="selfieUpload">
            <i class="fas fa-camera"></i>
            <h4>Tap to Upload Selfie</h4>
            <p style="color: var(--text-muted); font-size: 0.85rem;">
              Take a selfie now to verify you're a real person
            </p>
            <input type="file" id="selfieInput" accept="image/*" capture="user" style="display: none;">
            <img id="selfiePreview" alt="Selfie Preview">
          </div>
          <p style="color: var(--text-muted); font-size: 0.8rem; margin-top: 10px;">
            <i class="fas fa-shield-alt"></i> Your selfie is only used for verification
          </p>
        </div>
        
        <div class="form-group">
          <label class="form-label" for="special-requests">Special Requests</label>
          <textarea id="special-requests" class="form-input" rows="3" placeholder="Any specific requests..."></textarea>
        </div>
        
        <div class="terms-agreement">
          <input type="checkbox" id="terms" required>
          <label for="terms">
            I confirm I am 18+ years old and agree to all terms. I understand this is a paid service for consenting adults.
          </label>
        </div>
        
        <div class="payment-box">
          <i class="fas fa-lock"></i>
          <h3>Secure Online Payment Required</h3>
          <p>Complete your booking with secure online payment</p>
          <p style="font-size: 1.2rem; color: var(--accent-gold); margin: 10px 0;">
            Amount: R<span id="bookingAmount">800</span>
          </p>
          <a href="https://securepay.ikhokha.com/fgx22b1yj70w2bn" target="_blank" class="pay-button" id="payNowBtn">
            <i class="fas fa-credit-card"></i> Pay Now
          </a>
          <p style="margin-top: 10px; font-size: 0.85rem; color: var(--text-muted);">
            You will be redirected to our secure payment gateway
          </p>
        </div>
        
        <div class="button-container">
          <button type="button" class="btn btn-back" id="back-to-profile">Back to Profile</button>
        </div>
      </div>
    </div>
    
    <!-- Success Screen -->
    <div class="step-container" id="success-step">
      <div class="success-container">
        <div class="success-icon">
          <i class="fas fa-check-circle"></i>
        </div>
        <h2 class="step-title">Proceed to Payment</h2>
        
        <div class="booking-summary">
          <h3>Booking Summary</h3>
          <div class="summary-grid">
            <div class="summary-item">
              <div class="summary-label">Booty Call</div>
              <div class="summary-value" id="finalBootyName"></div>
            </div>
            <div class="summary-item">
              <div class="summary-label">Location</div>
              <div class="summary-value" id="finalLocation"></div>
            </div>
            <div class="summary-item">
              <div class="summary-label">Date & Time</div>
              <div class="summary-value" id="finalDateTime"></div>
            </div>
            <div class="summary-item">
              <div class="summary-label">Duration</div>
              <div class="summary-value" id="finalDuration"></div>
            </div>
            <div class="summary-item">
              <div class="summary-label">Amount</div>
              <div class="summary-value">R<span id="finalAmount"></span></div>
            </div>
            <div class="summary-item">
              <div class="summary-label">Payment Method</div>
              <div class="summary-value">Online Payment</div>
            </div>
          </div>
        </div>
        
        <div class="payment-box">
          <i class="fas fa-external-link-alt"></i>
          <h3>Complete Your Payment</h3>
          <p>Tap the button below to proceed to our secure payment gateway</p>
          <a href="https://securepay.ikhokha.com/fgx22b1yj70w2bn" target="_blank" class="pay-button">
            <i class="fas fa-external-link-alt"></i> Go to Payment Page
          </a>
          <p style="margin-top: 15px; font-size: 0.85rem; color: var(--text-muted);">
            After payment, you'll receive confirmation via WhatsApp within 15 minutes
          </p>
        </div>
        
        <div class="button-container">
          <button class="btn btn-back" onclick="location.reload()">Make Another Booty Call</button>
        </div>
      </div>
    </div>
  </div>
</div>

<footer>
  <div class="container">
    <div class="footer-links">
      <a href="#"><i class="fas fa-shield-alt"></i> Safety</a>
      <a href="#"><i class="fas fa-question-circle"></i> FAQ</a>
      <a href="#"><i class="fas fa-phone-alt"></i> Support</a>
      <a href="#"><i class="fas fa-ban"></i> Cancel</a>
    </div>
    <div class="copyright">
      &copy; 2023 Water Flow Eastern Cape. Adults 18+ only.
    </div>
    <div class="disclaimer">
      <i class="fas fa-exclamation-circle"></i> All services are between consenting adults. 
    </div>
  </div>
</footer>

<script>
// Data storage
const bookingData = {
  selectedCity: '',
  selectedBooty: null,
  price: 800,
  duration: '6',
  startTime: '',
  endTime: '',
  selfieUploaded: false
};

// Eastern Cape Cities
const easternCapeCities = [
  { name: "East London", bootyCalls: 1 },
  { name: "Gqeberha (Port Elizabeth)", bootyCalls: 0 },
  { name: "Mthatha", bootyCalls: 0 },
  { name: "Qonce (King William's Town)", bootyCalls: 0 },
  { name: "Bhisho", bootyCalls: 0 },
  { name: "Jeffrey's Bay", bootyCalls: 0 },
  { name: "Port Alfred", bootyCalls: 0 },
  { name: "Uitenhage", bootyCalls: 0 },
  { name: "Stutterheim", bootyCalls: 0 },
  { name: "Graaff-Reinet", bootyCalls: 0 }
];

// Booty Calls Data
const bootyCallsByCity = {
  "East London": [
    {
      id: 1,
      name: "Bunny",
      age: 25,
      images: ["https://i.ibb.co/ZpBNL8nm/bunny.jpg"], // Your provided image
      location: "Quigney, East London",
      price: 800,
      accommodation: true,
      availability: "Monday-Saturday, 8PM-2AM",
      bodyType: "Slim",
      ethnicity: "Black",
      description: "Sweet and fun-loving, professional booty call with great personality. Always on time and discreet. Speaks English and Xhosa.",
      features: ["Verified", "Accommodation Available", "Available Now", "Professional"],
      
      // Gallery Images (add more pictures here)
      gallery: [
        { type: "image", url: "https://i.ibb.co/ZpBNL8nm/bunny.jpg" },
        { type: "image", url: "https://via.placeholder.com/600x400/ff3b30/ffffff?text=Bunny+2" },
        { type: "image", url: "https://via.placeholder.com/600x400/ff6b6b/ffffff?text=Bunny+3" },
        { type: "video", url: "#", thumbnail: "https://via.placeholder.com/600x400/9b59b6/ffffff?text=Video+1" },
        { type: "image", url: "https://via.placeholder.com/600x400/3498db/ffffff?text=Bunny+4" },
        { type: "image", url: "https://via.placeholder.com/600x400/2ecc71/ffffff?text=Bunny+5" }
      ],
      
      // Ratings and Reviews
      rating: 4.8,
      totalReviews: 12,
      reviews: [
        {
          name: "Mike",
          date: "2023-10-15",
          rating: 5,
          comment: "Bunny is amazing! Professional and fun. Would definitely book again."
        },
        {
          name: "David",
          date: "2023-10-10",
          rating: 5,
          comment: "Great experience. Bunny is sweet and knows how to have a good time."
        },
        {
          name: "John",
          date: "2023-10-05",
          rating: 4,
          comment: "Good service, arrived on time. Will book again next month."
        },
        {
          name: "Thabo",
          date: "2023-09-28",
          rating: 5,
          comment: "Best booty call in East London! Highly recommended."
        }
      ]
    }
  ]
};

// Initialize cities grid
function initializeCities() {
  const cityGrid = document.getElementById('cityGrid');
  cityGrid.innerHTML = '';
  
  easternCapeCities.forEach(city => {
    const bootyCalls = bootyCallsByCity[city.name] || [];
    const bootyCount = bootyCalls.length;
    
    const cityCard = document.createElement('div');
    cityCard.className = 'city-card';
    cityCard.dataset.city = city.name;
    
    cityCard.innerHTML = `
      <i class="fas fa-map-marker-alt"></i>
      <div class="city-name">${city.name}</div>
      <div class="booty-count">${bootyCount} booty call${bootyCount !== 1 ? 's' : ''}</div>
    `;
    
    cityCard.addEventListener('click', () => selectCity(city.name));
    cityGrid.appendChild(cityCard);
  });
}

// Search functionality
document.getElementById('citySearch').addEventListener('input', function(e) {
  const searchTerm = e.target.value.toLowerCase();
  const cityCards = document.querySelectorAll('.city-card');
  
  cityCards.forEach(card => {
    const cityName = card.querySelector('.city-name').textContent.toLowerCase();
    if (cityName.includes(searchTerm)) {
      card.style.display = 'flex';
    } else {
      card.style.display = 'none';
    }
  });
});

// City selection
function selectCity(cityName) {
  bookingData.selectedCity = cityName;
  document.getElementById('selectedCityDisplay').textContent = cityName;
  displayBootyCalls(cityName);
  goToStep(2);
}

// Display booty calls for a city
function displayBootyCalls(cityName) {
  const bootyGrid = document.getElementById('bootyGrid');
  bootyGrid.innerHTML = '';
  
  const bootyCalls = bootyCallsByCity[cityName] || [];
  
  if (bootyCalls.length === 0) {
    bootyGrid.innerHTML = `
      <div style="grid-column: 1 / -1; text-align: center; padding: 40px;">
        <i class="fas fa-users-slash" style="font-size: 2.5rem; color: var(--text-muted); margin-bottom: 15px;"></i>
        <h3>No Booty Calls Available</h3>
        <p style="color: var(--text-muted);">Check back later or try another city.</p>
      </div>
    `;
    return;
  }
  
  bootyCalls.forEach(bootyCall => {
    const bootyCard = document.createElement('div');
    bootyCard.className = 'booty-card';
    if (bootyCall.features.includes('Available Now')) {
      bootyCard.classList.add('featured');
    }
    
    const featuresHTML = bootyCall.features.map(feature => {
      const className = feature === 'Accommodation Available' ? 'accommodation' : '';
      return `<span class="feature-tag ${className}">${feature}</span>`;
    }).join('');
    
    bootyCard.innerHTML = `
      <img src="${bootyCall.images[0]}" alt="${bootyCall.name}" class="booty-img" loading="lazy">
      <div class="booty-info">
        <h3 class="booty-name">${bootyCall.name}, ${bootyCall.age}</h3>
        <div class="booty-details">
          <span class="booty-location">${bootyCall.location}</span>
          <span style="color: var(--accent-gold);">${bootyCall.bodyType}</span>
        </div>
        <p style="font-size: 0.85rem; color: var(--text-muted); margin: 8px 0;">
          <i class="far fa-clock"></i> ${bootyCall.availability}
        </p>
        <div class="booty-features">
          ${featuresHTML}
        </div>
        <div class="booty-pricing">
          <div class="price-tag">R${bootyCall.price}</div>
          <p class="price-note">${bootyCall.accommodation ? '✓ Accommodation available' : '✓ Transport included'}</p>
        </div>
        <button class="btn" style="width: 100%; margin-top: 12px;" onclick="viewBootyProfile(${bootyCall.id})">
          View Profile & Book
        </button>
      </div>
    `;
    
    bootyGrid.appendChild(bootyCard);
  });
}

// View booty call profile
function viewBootyProfile(bootyCallId) {
  const city = bookingData.selectedCity;
  const bootyCalls = bootyCallsByCity[city];
  const bootyCall = bootyCalls.find(b => b.id === bootyCallId);
  
  if (bootyCall) {
    bookingData.selectedBooty = bootyCall;
    
    // Generate star rating HTML
    const starsHTML = generateStars(bootyCall.rating);
    
    // Generate gallery HTML
    const galleryHTML = bootyCall.gallery.map((item, index) => `
      <div class="gallery-item ${item.type}" onclick="viewImage(${index})">
        <img src="${item.type === 'video' ? item.thumbnail : item.url}" alt="${bootyCall.name} ${index + 1}" loading="lazy">
      </div>
    `).join('');
    
    // Generate reviews HTML
    const reviewsHTML = bootyCall.reviews.map(review => `
      <div class="review-item">
        <div class="review-header">
          <span class="reviewer-name">${review.name}</span>
          <span class="review-date">${new Date(review.date).toLocaleDateString()}</span>
        </div>
        <div style="color: var(--accent-gold); margin: 3px 0;">
          ${generateStars(review.rating)}
        </div>
        <p class="review-text">${review.comment}</p>
      </div>
    `).join('');
    
    const profileHTML = `
      <div class="booty-card featured">
        <img src="${bootyCall.images[0]}" alt="${bootyCall.name}" class="booty-img">
        <div class="booty-info">
          <h3 class="booty-name">${bootyCall.name}, ${bootyCall.age}</h3>
          <div class="booty-details">
            <span class="booty-location">${bootyCall.location}</span>
            <span style="color: var(--accent-gold);">${bootyCall.bodyType} • ${bootyCall.ethnicity}</span>
          </div>
          
          <div style="margin: 15px 0; padding: 12px; background: rgba(255, 59, 48, 0.05); border-radius: 8px;">
            <p style="color: var(--text-muted); font-size: 0.9rem; margin-bottom: 5px;">
              <i class="far fa-clock"></i> <strong>Availability:</strong> ${bootyCall.availability}
            </p>
            <p style="color: var(--text-muted); font-size: 0.9rem;">
              <i class="fas fa-home"></i> <strong>Accommodation:</strong> ${bootyCall.accommodation ? 'Available' : 'Not available'}
            </p>
          </div>
          
          <p style="font-size: 0.9rem; color: var(--text-light); margin: 15px 0; line-height: 1.5;">
            ${bootyCall.description}
          </p>
          
          <div class="booty-features">
            ${bootyCall.features.map(feature => {
              const className = feature === 'Accommodation Available' ? 'accommodation' : '';
              return `<span class="feature-tag ${className}">${feature}</span>`;
            }).join('')}
          </div>
          
          <div class="booty-pricing">
            <div class="price-tag">R${bootyCall.price}</div>
            <p class="price-note">${bootyCall.accommodation ? '✓ Accommodation available' : '✓ Transport included'}</p>
            <button class="btn" style="width: 100%; margin-top: 15px;" onclick="startBooking(${bootyCall.id})">
              Book Now - R${bootyCall.price}
            </button>
          </div>
        </div>
      </div>
      
      <!-- Gallery Section -->
      <div class="gallery-section">
        <div class="gallery-title">
          <h3><i class="fas fa-images"></i> Photos & Videos</h3>
          <span style="font-size: 0.9rem; color: var(--text-muted);">${bootyCall.gallery.length} items</span>
        </div>
        <div class="gallery-grid">
          ${galleryHTML}
        </div>
        <p style="text-align: center; color: var(--text-muted); font-size: 0.85rem; margin-top: 10px;">
          Tap to view larger
        </p>
      </div>
      
      <!-- Ratings Section -->
      <div class="ratings-section">
        <div class="ratings-header">
          <h3><i class="fas fa-star"></i> Ratings & Reviews</h3>
          <span style="font-size: 0.9rem; color: var(--text-muted);">${bootyCall.totalReviews} reviews</span>
        </div>
        <div class="rating-summary">
          <div class="rating-stars">${starsHTML}</div>
          <div>
            <div style="font-size: 1.5rem; font-weight: 600; color: var(--accent-gold);">${bootyCall.rating}/5</div>
            <div style="font-size: 0.85rem; color: var(--text-muted);">${bootyCall.totalReviews} reviews</div>
          </div>
        </div>
        <div class="reviews-list">
          ${reviewsHTML}
        </div>
      </div>
    `;
    
    document.getElementById('bootyProfile').innerHTML = profileHTML;
    goToStep(3);
  }
}

// Generate star rating HTML
function generateStars(rating) {
  const fullStars = Math.floor(rating);
  const hasHalfStar = rating % 1 >= 0.5;
  const emptyStars = 5 - fullStars - (hasHalfStar ? 1 : 0);
  
  let starsHTML = '';
  
  // Full stars
  for (let i = 0; i < fullStars; i++) {
    starsHTML += '<i class="fas fa-star"></i>';
  }
  
  // Half star
  if (hasHalfStar) {
    starsHTML += '<i class="fas fa-star-half-alt"></i>';
  }
  
  // Empty stars
  for (let i = 0; i < emptyStars; i++) {
    starsHTML += '<i class="far fa-star"></i>';
  }
  
  return starsHTML;
}

// Start booking process
function startBooking(bootyCallId) {
  const city = bookingData.selectedCity;
  const bootyCalls = bootyCallsByCity[city];
  const bootyCall = bootyCalls.find(b => b.id === bootyCallId);
  
  if (bootyCall) {
    bookingData.selectedBooty = bootyCall;
    document.getElementById('bootyNameDisplay').textContent = bootyCall.name;
    document.getElementById('bookingAmount').textContent = bootyCall.price;
    document.getElementById('finalBootyName').textContent = `${bootyCall.name}, ${bootyCall.age} - ${bootyCall.location}`;
    bookingData.price = bootyCall.price;
    
    goToStep(4);
  }
}

// View image in gallery
function viewImage(index) {
  const bootyCall = bookingData.selectedBooty;
  if (bootyCall && bootyCall.gallery[index]) {
    const item = bootyCall.gallery[index];
    if (item.type === 'video') {
      alert('Video preview would play here. In a real app, this would open a video player.');
    } else {
      // In a real app, this would open a lightbox
      window.open(item.url, '_blank');
    }
  }
}

// Calculate end time
function calculateEndTime() {
  const startTime = document.getElementById('start-time').value;
  const duration = document.getElementById('duration').value;
  
  if (startTime && duration) {
    const [hours, minutes] = startTime.split(':').map(Number);
    const endHours = (hours + parseInt(duration)) % 24;
    const endTime = `${endHours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}`;
    
    // Format for display
    const formatTime = (time) => {
      const [h, m] = time.split(':').map(Number);
      const period = h >= 12 ? 'PM' : 'AM';
      const displayHour = h % 12 || 12;
      return `${displayHour}:${m.toString().padStart(2, '0')} ${period}`;
    };
    
    const displayText = `From <strong>${formatTime(startTime)}</strong> to <strong>${formatTime(endTime)}</strong> (${duration} hours)`;
    document.getElementById('endTimeDisplay').innerHTML = displayText;
    
    bookingData.startTime = startTime;
    bookingData.endTime = endTime;
    bookingData.duration = duration;
  }
}

// Duration change
document.getElementById('duration').addEventListener('change', function() {
  const duration = this.value;
  const basePrice = bookingData.selectedBooty?.price || 800;
  let price = basePrice;
  
  if (duration === '4') {
    price = Math.round(basePrice * 0.75);
  } else if (duration === '2') {
    price = Math.round(basePrice * 0.5);
  }
  
  bookingData.duration = duration;
  bookingData.price = price;
  document.getElementById('bookingAmount').textContent = price;
  calculateEndTime();
});

// Start time change
document.getElementById('start-time').addEventListener('change', calculateEndTime);

// Selfie upload
document.getElementById('selfieUpload').addEventListener('click', function() {
  document.getElementById('selfieInput').click();
});

document.getElementById('selfieInput').addEventListener('change', function(e) {
  const file = e.target.files[0];
  if (file) {
    const reader = new FileReader();
    reader.onload = function(e) {
      const preview = document.getElementById('selfiePreview');
      preview.src = e.target.result;
      preview.style.display = 'block';
      bookingData.selfieUploaded = true;
      
      const uploadArea = document.getElementById('selfieUpload');
      uploadArea.innerHTML = `
        <i class="fas fa-check-circle" style="color: var(--success);"></i>
        <h4>Selfie Uploaded</h4>
        <img id="selfiePreview" src="${e.target.result}" alt="Selfie Preview" style="max-width: 150px; border-radius: 6px; margin: 12px auto; display: block;">
        <button class="btn" style="margin-top: 10px; padding: 8px 20px; font-size: 0.9rem;" onclick="document.getElementById('selfieInput').click()">
          Upload Different Selfie
        </button>
      `;
    };
    reader.readAsDataURL(file);
  }
});

// Payment validation
document.getElementById('payNowBtn').addEventListener('click', function(e) {
  const fullName = document.getElementById('full-name').value;
  const phone = document.getElementById('phone').value;
  const location = document.getElementById('location').value;
  const date = document.getElementById('date').value;
  const startTime = document.getElementById('start-time').value;
  const duration = document.getElementById('duration').value;
  
  if (!fullName || !phone || !location || !date || !startTime || !duration) {
    alert('Please fill in all required fields');
    e.preventDefault();
    return false;
  }
  
  if (!bookingData.selfieUploaded) {
    alert('Please upload a selfie for verification');
    e.preventDefault();
    return false;
  }
  
  if (!document.getElementById('terms').checked) {
    alert('You must agree to the terms and conditions');
    e.preventDefault();
    return false;
  }
  
  calculateEndTime();
  document.getElementById('finalBootyName').textContent = `${bookingData.selectedBooty?.name}, ${bookingData.selectedBooty?.age} - ${bookingData.selectedBooty?.location}`;
  document.getElementById('finalLocation').textContent = location;
  
  const dateObj = new Date(date);
  const formattedDate = dateObj.toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
  
  const formatTime = (time) => {
    const [h, m] = time.split(':').map(Number);
    const period = h >= 12 ? 'PM' : 'AM';
    const displayHour = h % 12 || 12;
    return `${displayHour}:${m.toString().padStart(2, '0')} ${period}`;
  };
  
  const displayTime = `${formatTime(bookingData.startTime)} to ${formatTime(bookingData.endTime)}`;
  document.getElementById('finalDateTime').textContent = `${formattedDate} (${displayTime})`;
  
  document.getElementById('finalDuration').textContent = `${duration} Hours`;
  document.getElementById('finalAmount').textContent = bookingData.price;
  
  return true;
});

// Navigation functions
function goToStep(step) {
  document.querySelectorAll('.step-container').forEach(container => {
    container.classList.remove('active-step');
  });
  document.getElementById(`step${step}`).classList.add('active-step');
}

// Back buttons
document.getElementById('back-to-search').addEventListener('click', () => goToStep(1));
document.getElementById('back-to-profile').addEventListener('click', () => goToStep(3));

// Initialize
document.addEventListener('DOMContentLoaded', function() {
  initializeCities();
  
  // Set date to today
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('date').min = today;
  document.getElementById('date').value = today;
  
  // Set default start time
  document.getElementById('start-time').value = '20:00';
  calculateEndTime();
  
  // Mobile gestures
  let touchStartX = 0;
  let touchEndX = 0;
  
  document.addEventListener('touchstart', e => {
    touchStartX = e.changedTouches[0].screenX;
  });
  
  document.addEventListener('touchend', e => {
    touchEndX = e.changedTouches[0].screenX;
    handleSwipe();
  });
  
  function handleSwipe() {
    const swipeThreshold = 50;
    const swipeDistance = touchEndX - touchStartX;
    
    if (Math.abs(swipeDistance) > swipeThreshold) {
      if (swipeDistance > 0 && currentStep > 1) {
        // Swipe right - go back
        goToStep(currentStep - 1);
      } else if (swipeDistance < 0 && currentStep < 4) {
        // Swipe left - go forward
        goToStep(currentStep + 1);
      }
    }
  }
  
  // Track current step
  let currentStep = 1;
  const observer = new MutationObserver(() => {
    const activeStep = document.querySelector('.step-container.active-step');
    if (activeStep) {
      const stepId = activeStep.id.replace('step', '');
      currentStep = parseInt(stepId);
    }
  });
  
  observer.observe(document.body, {
    attributes: true,
    attributeFilter: ['class'],
    subtree: true
  });
});

// Simple step tracking for swipe
let currentStep = 1;
function goToStep(step) {
  document.querySelectorAll('.step-container').forEach(container => {
    container.classList.remove('active-step');
  });
  document.getElementById(`step${step}`).classList.add('active-step');
  currentStep = step;
  
  // Scroll to top on step change
  window.scrollTo({ top: 0, behavior: 'smooth' });
}
</script>
</body>
</html>
