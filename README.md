<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Water Flow - Eastern Cape Booty Call Service</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
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
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header & Logo */
header {
  background-color: rgba(0, 0, 0, 0.9);
  padding: 20px 0;
  border-bottom: 2px solid var(--primary-red);
  position: sticky;
  top: 0;
  z-index: 1000;
  backdrop-filter: blur(10px);
}

.logo-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.logo {
  font-size: 2.5rem;
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: var(--primary-red);
  text-shadow: 0 0 15px rgba(255, 59, 48, 0.5);
  display: flex;
  align-items: center;
}

.logo i {
  margin-right: 15px;
  font-size: 2.8rem;
  color: var(--primary-red);
}

.logo-text {
  position: relative;
}

.logo-text::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(to right, var(--primary-red), transparent);
}

.slogan {
  color: var(--accent-gold);
  font-size: 1.1rem;
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 10px;
  text-align: center;
}

.location-badge {
  background: linear-gradient(45deg, var(--primary-red), #ff6b6b);
  color: white;
  padding: 8px 20px;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 10px;
  display: inline-block;
}

/* Main Content */
.main-content {
  padding: 40px 0;
  min-height: calc(100vh - 180px);
}

/* Step Containers */
.step-container {
  display: none;
  background-color: var(--dark-gray);
  border-radius: 15px;
  padding: 40px;
  margin: 30px auto;
  max-width: 900px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
  border: 1px solid var(--medium-gray);
}

.active-step {
  display: block;
  animation: fadeIn 0.5s ease;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

.step-title {
  font-size: 2rem;
  margin-bottom: 25px;
  color: var(--primary-red);
  text-align: center;
  position: relative;
  padding-bottom: 15px;
}

.step-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 3px;
  background-color: var(--primary-red);
}

/* Step 1: Location Search */
.search-container {
  margin: 30px 0;
}

.search-box {
  position: relative;
  margin-bottom: 20px;
}

.search-input {
  width: 100%;
  padding: 15px 50px 15px 20px;
  background-color: var(--light-gray);
  border: 2px solid var(--medium-gray);
  border-radius: 10px;
  color: var(--text-light);
  font-size: 1rem;
  transition: all 0.3s ease;
}

.search-input:focus {
  outline: none;
  border-color: var(--primary-red);
  box-shadow: 0 0 15px rgba(255, 59, 48, 0.2);
}

.search-icon {
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--text-muted);
  font-size: 1.2rem;
}

.city-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  gap: 15px;
  margin: 20px 0;
  max-height: 400px;
  overflow-y: auto;
  padding: 10px;
}

.city-card {
  background: var(--medium-gray);
  border-radius: 10px;
  padding: 15px;
  text-align: center;
  cursor: pointer;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.city-card:hover {
  transform: translateY(-5px);
  border-color: var(--primary-red);
  box-shadow: 0 10px 20px rgba(255, 59, 48, 0.2);
}

.city-card.selected {
  background: rgba(255, 59, 48, 0.1);
  border-color: var(--primary-red);
}

.city-card i {
  font-size: 2rem;
  color: var(--primary-red);
  margin-bottom: 10px;
}

.city-name {
  font-weight: 600;
  margin-bottom: 5px;
}

.booty-count {
  font-size: 0.8rem;
  color: var(--accent-gold);
}

/* Step 2: Available Booty Calls */
.booty-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  margin: 30px 0;
}

.booty-card {
  background: linear-gradient(135deg, var(--medium-gray), var(--dark-gray));
  border-radius: 12px;
  overflow: hidden;
  border: 2px solid transparent;
  transition: all 0.3s ease;
}

.booty-card:hover {
  transform: translateY(-5px);
  border-color: var(--primary-red);
  box-shadow: 0 10px 25px rgba(255, 59, 48, 0.3);
}

.booty-card.featured {
  border-color: var(--accent-gold);
  position: relative;
}

.booty-card.featured::before {
  content: 'POPULAR';
  position: absolute;
  top: 10px;
  right: -35px;
  background: var(--accent-gold);
  color: black;
  padding: 5px 35px;
  transform: rotate(45deg);
  font-size: 0.8rem;
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
  padding: 20px;
}

.booty-name {
  color: var(--primary-red);
  font-size: 1.3rem;
  margin-bottom: 5px;
}

.booty-location {
  color: var(--text-muted);
  font-size: 0.9rem;
  margin-bottom: 10px;
}

.booty-features {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin: 15px 0;
}

.feature-tag {
  background: rgba(255, 59, 48, 0.2);
  color: var(--primary-red);
  padding: 5px 10px;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
}

.feature-tag.accommodation {
  background: rgba(255, 215, 0, 0.2);
  color: var(--accent-gold);
}

.booty-pricing {
  background: rgba(0, 0, 0, 0.3);
  border-radius: 8px;
  padding: 15px;
  margin-top: 15px;
}

.price-tag {
  font-size: 1.8rem;
  color: var(--accent-gold);
  font-weight: 800;
  margin-bottom: 5px;
}

.price-note {
  font-size: 0.9rem;
  color: var(--text-muted);
}

/* Step 3: Booking Form */
.booking-form {
  background: var(--medium-gray);
  border-radius: 10px;
  padding: 30px;
  margin: 30px 0;
}

.form-row {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-bottom: 20px;
}

.form-group {
  margin-bottom: 20px;
}

.form-label {
  display: block;
  margin-bottom: 8px;
  font-weight: 600;
  color: var(--text-muted);
}

.form-input, .form-select {
  width: 100%;
  padding: 15px;
  background-color: var(--light-gray);
  border: 1px solid var(--medium-gray);
  border-radius: 8px;
  color: var(--text-light);
  font-size: 1rem;
  transition: border 0.3s;
}

.form-input:focus, .form-select:focus {
  outline: none;
  border-color: var(--primary-red);
}

.time-info {
  background: rgba(255, 59, 48, 0.1);
  border-radius: 8px;
  padding: 15px;
  margin: 10px 0;
  font-size: 0.9rem;
  color: var(--text-muted);
}

.time-info strong {
  color: var(--accent-gold);
}

.selfie-upload {
  border: 2px dashed var(--primary-red);
  border-radius: 10px;
  padding: 30px;
  text-align: center;
  margin: 25px 0;
  cursor: pointer;
  transition: all 0.3s ease;
}

.selfie-upload:hover {
  background: rgba(255, 59, 48, 0.05);
}

.selfie-upload i {
  font-size: 3rem;
  color: var(--primary-red);
  margin-bottom: 15px;
}

#selfiePreview {
  display: none;
  max-width: 200px;
  border-radius: 8px;
  margin: 15px auto;
}

.terms-agreement {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  margin: 25px 0;
}

.terms-agreement input {
  margin-top: 5px;
}

/* Payment Box */
.payment-box {
  background: rgba(255, 59, 48, 0.1);
  border: 2px solid var(--primary-red);
  border-radius: 10px;
  padding: 25px;
  margin: 30px 0;
  text-align: center;
}

.payment-box i {
  font-size: 3rem;
  color: var(--primary-red);
  margin-bottom: 15px;
}

.pay-button {
  background: linear-gradient(45deg, #ff3b30, #ff6b6b);
  color: white;
  border: none;
  padding: 15px 40px;
  border-radius: 8px;
  font-size: 1.2rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  margin-top: 15px;
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.pay-button:hover {
  background: linear-gradient(45deg, #ff6b6b, #ff3b30);
  transform: translateY(-3px);
  box-shadow: 0 10px 20px rgba(255, 59, 48, 0.4);
}

/* Success Screen */
.success-container {
  text-align: center;
  padding: 50px 30px;
}

.success-icon {
  font-size: 5rem;
  color: var(--success);
  margin-bottom: 30px;
  animation: bounce 1s ease;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
  40% {transform: translateY(-20px);}
  60% {transform: translateY(-10px);}
}

.booking-summary {
  background: rgba(255, 59, 48, 0.1);
  border-radius: 10px;
  padding: 30px;
  margin: 40px 0;
  text-align: left;
}

.summary-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.summary-item {
  background: rgba(255, 255, 255, 0.05);
  border-radius: 8px;
  padding: 15px;
}

.summary-label {
  color: var(--text-muted);
  font-size: 0.9rem;
  margin-bottom: 5px;
}

.summary-value {
  color: var(--accent-gold);
  font-size: 1.1rem;
  font-weight: 600;
}

/* Buttons */
.btn {
  padding: 15px 30px;
  background: linear-gradient(45deg, var(--primary-red), var(--dark-red));
  color: white;
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  display: inline-block;
  text-align: center;
  text-decoration: none;
  min-width: 200px;
}

.btn:hover {
  background: linear-gradient(45deg, var(--dark-red), var(--primary-red));
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(255, 59, 48, 0.4);
}

.btn:disabled {
  background: var(--medium-gray);
  cursor: not-allowed;
  transform: none;
  box-shadow: none;
}

.btn-gold {
  background: linear-gradient(45deg, #ffd700, #ffaa00);
  color: black;
}

.btn-gold:hover {
  background: linear-gradient(45deg, #ffaa00, #ffd700);
  box-shadow: 0 5px 15px rgba(255, 215, 0, 0.4);
}

.btn-back {
  background: transparent;
  border: 2px solid var(--light-gray);
  margin-right: 15px;
}

.btn-back:hover {
  background: var(--light-gray);
  border-color: var(--light-gray);
}

.button-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 40px;
  flex-wrap: wrap;
}

/* Footer */
footer {
  background-color: var(--dark-gray);
  padding: 30px 0;
  text-align: center;
  border-top: 1px solid var(--medium-gray);
  margin-top: 50px;
}

.footer-links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 20px;
  margin-bottom: 20px;
}

.footer-links a {
  color: var(--text-muted);
  text-decoration: none;
  transition: color 0.3s;
}

.footer-links a:hover {
  color: var(--primary-red);
}

.copyright {
  color: var(--text-muted);
  font-size: 0.9rem;
  margin-top: 20px;
}

.disclaimer {
  font-size: 0.8rem;
  color: var(--warning);
  margin-top: 10px;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
}

/* Responsive */
@media (max-width: 768px) {
  .logo {
    font-size: 2rem;
  }
  
  .step-container {
    padding: 30px 20px;
    margin: 20px 10px;
  }
  
  .button-container {
    flex-direction: column;
    align-items: center;
  }
  
  .btn-back {
    margin-right: 0;
    margin-bottom: 10px;
  }
  
  .booty-grid {
    grid-template-columns: 1fr;
  }
  
  .city-grid {
    grid-template-columns: repeat(2, 1fr);
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
        <p style="text-align: center; color: var(--accent-gold); margin-bottom: 20px; font-size: 1.1rem;">
          <i class="fas fa-map-marker-alt"></i> Find available booty calls in your city
        </p>
        
        <div class="search-box">
          <input type="text" id="citySearch" class="search-input" placeholder="Search for your city...">
          <div class="search-icon">
            <i class="fas fa-search"></i>
          </div>
        </div>
        
        <div class="city-grid" id="cityGrid">
          <!-- Cities will be populated by JavaScript -->
        </div>
      </div>
      
      <div style="text-align: center; margin-top: 40px; color: var(--text-muted);">
        <p><i class="fas fa-info-circle"></i> Click on your city to see available booty calls</p>
      </div>
    </div>

    <!-- Step 2: Available Booty Calls -->
    <div class="step-container" id="step2">
      <h2 class="step-title">Available in <span id="selectedCityDisplay">Your Area</span></h2>
      
      <div class="booty-grid" id="bootyGrid">
        <!-- Booty calls will be populated by JavaScript -->
      </div>
      
      <div class="button-container">
        <button class="btn btn-back" id="back-to-search">Change Location</button>
      </div>
    </div>

    <!-- Step 3: Booking Form -->
    <div class="step-container" id="step3">
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
              <option value="2">2 Hours</option>
              <option value="4">4 Hours</option>
              <option value="6">6 Hours</option>
            </select>
          </div>
        </div>
        
        <!-- Selfie Upload -->
        <div class="form-group">
          <label class="form-label">Verify Identity - Upload Selfie *</label>
          <div class="selfie-upload" id="selfieUpload">
            <i class="fas fa-camera"></i>
            <h4>Click to Upload Selfie</h4>
            <p style="color: var(--text-muted); font-size: 0.9rem;">
              Take a selfie now to verify you're a real person
            </p>
            <input type="file" id="selfieInput" accept="image/*" capture="user" style="display: none;">
            <img id="selfiePreview" alt="Selfie Preview">
          </div>
          <p style="color: var(--text-muted); font-size: 0.85rem; margin-top: 10px;">
            <i class="fas fa-shield-alt"></i> Your selfie is only used for verification and will be deleted after booking confirmation.
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
          <button class="pay-button" id="payNowBtn">
            <i class="fas fa-credit-card"></i> Pay Now
          </button>
        </div>
        
        <div class="button-container">
          <button type="button" class="btn btn-back" id="back-to-booty">Back to Booty Calls</button>
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
          <p>Click the button below to proceed to our secure payment gateway</p>
          <a href="https://securepay.ikhokha.com/fgx22b1yj70w2bn" target="_blank" class="pay-button">
            <i class="fas fa-external-link-alt"></i> Go to Payment Page
          </a>
          <p style="margin-top: 15px; font-size: 0.9rem; color: var(--text-muted);">
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
      <a href="#"><i class="fas fa-phone-alt"></i> Support: 067 123 4567</a>
      <a href="#"><i class="fas fa-ban"></i> Cancel Policy</a>
    </div>
    <div class="copyright">
      &copy; 2023 Water Flow Eastern Cape. Adults 18+ only.
    </div>
    <div class="disclaimer">
      <i class="fas fa-exclamation-circle"></i> All services are between consenting adults. 
      Payment is required before service delivery. Selfie verification is mandatory for all bookings.
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

// Eastern Cape Cities (comprehensive list)
const easternCapeCities = [
  { name: "East London", bootyCalls: 8 },
  { name: "Gqeberha (Port Elizabeth)", bootyCalls: 6 },
  { name: "Mthatha", bootyCalls: 4 },
  { name: "Qonce (King William's Town)", bootyCalls: 3 },
  { name: "Bhisho", bootyCalls: 2 },
  { name: "Graaff-Reinet", bootyCalls: 2 },
  { name: "Jeffrey's Bay", bootyCalls: 3 },
  { name: "Stutterheim", bootyCalls: 2 },
  { name: "Somerset East", bootyCalls: 1 },
  { name: "Cradock", bootyCalls: 2 },
  { name: "Aliwal North", bootyCalls: 2 },
  { name: "Maclear", bootyCalls: 1 },
  { name: "Butterworth", bootyCalls: 2 },
  { name: "Lady Frere", bootyCalls: 1 },
  { name: "Port Alfred", bootyCalls: 3 },
  { name: "Kenton-on-Sea", bootyCalls: 2 },
  { name: "St Francis Bay", bootyCalls: 2 },
  { name: "Patensie", bootyCalls: 1 },
  { name: "Kirkwood", bootyCalls: 1 },
  { name: "Uitenhage", bootyCalls: 3 },
  { name: "Despatch", bootyCalls: 2 },
  { name: "Adelaide", bootyCalls: 1 },
  { name: "Bedford", bootyCalls: 1 },
  { name: "Fort Beaufort", bootyCalls: 2 },
  { name: "Alice", bootyCalls: 2 },
  { name: "Hogsback", bootyCalls: 1 },
  { name: "Willowmore", bootyCalls: 1 },
  { name: "Jansenville", bootyCalls: 1 },
  { name: "Aberdeen", bootyCalls: 1 },
  { name: "Steytlerville", bootyCalls: 1 }
];

// Booty Calls data
const bootyCallsByCity = {
  "East London": [
    {
      id: 1,
      name: "Candice",
      age: 24,
      images: ["https://images.unsplash.com/photo-1517841905240-472988babdf9?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 800,
      accommodation: true,
      description: "Professional and discreet, available for night/day bookings",
      features: ["Verified", "Accommodation Available", "24/7", "Top Rated"]
    },
    {
      id: 2,
      name: "Nomtha",
      age: 28,
      images: ["https://images.unsplash.com/photo-1524250502761-1ac6f2e30d43?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 700,
      accommodation: false,
      description: "Sweet and caring, specializes in night sessions",
      features: ["Verified", "Popular", "Flexible", "New"]
    },
    {
      id: 3,
      name: "Zinhle",
      age: 22,
      images: ["https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 750,
      accommodation: true,
      description: "VIP experience with luxury accommodation",
      features: ["Verified", "VIP", "Accommodation Available", "Luxury"]
    }
  ],
  "Gqeberha (Port Elizabeth)": [
    {
      id: 4,
      name: "Sindi",
      age: 26,
      images: ["https://images.unsplash.com/photo-1494790108755-2616c113a1c0?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 850,
      accommodation: true,
      description: "Premium service with beach view accommodation",
      features: ["Verified", "VIP", "Accommodation Available", "Beach View"]
    },
    {
      id: 5,
      name: "Amahle",
      age: 25,
      images: ["https://images.unsplash.com/photo-1488426862026-3ee34a7d66df?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 600,
      accommodation: false,
      description: "Friendly and fun for day bookings",
      features: ["Verified", "Day Specialist", "Friendly"]
    }
  ],
  "Mthatha": [
    {
      id: 6,
      name: "Aphiwe",
      age: 25,
      images: ["https://images.unsplash.com/photo-1508214751196-bcfd4ca60f91?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 600,
      accommodation: false,
      description: "Sweet and accommodating for day bookings",
      features: ["Verified", "Day Specialist", "Friendly"]
    }
  ],
  "Qonce (King William's Town)": [
    {
      id: 7,
      name: "Buhle",
      age: 23,
      images: ["https://images.unsplash.com/photo-1487412720507-e7ab37603c6f?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 650,
      accommodation: true,
      description: "Available for both night and day bookings",
      features: ["Verified", "Accommodation Available", "Flexible"]
    }
  ],
  "Jeffrey's Bay": [
    {
      id: 8,
      name: "Jade",
      age: 22,
      images: ["https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80"],
      price: 900,
      accommodation: true,
      description: "Premium service with luxury accommodation",
      features: ["Verified", "VIP", "Accommodation Available", "Luxury"]
    }
  ]
};

// Initialize cities grid
function initializeCities() {
  const cityGrid = document.getElementById('cityGrid');
  cityGrid.innerHTML = '';
  
  easternCapeCities.forEach(city => {
    const cityCard = document.createElement('div');
    cityCard.className = 'city-card';
    cityCard.dataset.city = city.name;
    
    const bootyCalls = bootyCallsByCity[city.name] || [];
    const bootyCount = bootyCalls.length;
    
    cityCard.innerHTML = `
      <i class="fas fa-map-marker-alt"></i>
      <div class="city-name">${city.name}</div>
      <div class="booty-count">${bootyCount} booty calls</div>
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
      card.style.display = 'block';
    } else {
      card.style.display = 'none';
    }
  });
});

// City selection
function selectCity(cityName) {
  // Remove selection from all cities
  document.querySelectorAll('.city-card').forEach(card => {
    card.classList.remove('selected');
  });
  
  // Add selection to clicked city
  const selectedCard = document.querySelector(`[data-city="${cityName}"]`);
  if (selectedCard) {
    selectedCard.classList.add('selected');
  }
  
  // Update booking data
  bookingData.selectedCity = cityName;
  
  // Update selected city display
  document.getElementById('selectedCityDisplay').textContent = cityName;
  
  // Immediately show booty calls for this city
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
        <i class="fas fa-users-slash" style="font-size: 3rem; color: var(--text-muted); margin-bottom: 20px;"></i>
        <h3>No Booty Calls Available</h3>
        <p style="color: var(--text-muted);">No booty calls are currently available in ${cityName}.</p>
        <p style="color: var(--text-muted); margin-top: 10px;">Please check back later or select another city.</p>
      </div>
    `;
    return;
  }
  
  bootyCalls.forEach(bootyCall => {
    const bootyCard = document.createElement('div');
    bootyCard.className = 'booty-card';
    if (bootyCall.features.includes('Popular')) {
      bootyCard.classList.add('featured');
    }
    
    const featuresHTML = bootyCall.features.map(feature => {
      const className = feature === 'Accommodation Available' ? 'accommodation' : '';
      return `<span class="feature-tag ${className}">${feature}</span>`;
    }).join('');
    
    bootyCard.innerHTML = `
      <img src="${bootyCall.images[0]}" alt="${bootyCall.name}" class="booty-img">
      <div class="booty-info">
        <h3 class="booty-name">${bootyCall.name}, ${bootyCall.age}</h3>
        <p class="booty-location">${cityName}</p>
        <p style="font-size: 0.9rem; color: var(--text-muted); margin: 10px 0;">
          ${bootyCall.description}
        </p>
        <div class="booty-features">
          ${featuresHTML}
        </div>
        <div class="booty-pricing">
          <div class="price-tag">R${bootyCall.price}</div>
          <p class="price-note">${bootyCall.accommodation ? '✓ Accommodation available' : '✓ Transport included'}</p>
        </div>
        <button class="btn" style="width: 100%; margin-top: 15px;" onclick="selectBootyCall(${bootyCall.id})">
          Book This Booty Call
        </button>
      </div>
    `;
    
    bootyGrid.appendChild(bootyCard);
  });
}

// Select booty call
function selectBootyCall(bootyCallId) {
  const city = bookingData.selectedCity;
  const bootyCalls = bootyCallsByCity[city];
  const bootyCall = bootyCalls.find(b => b.id === bootyCallId);
  
  if (bootyCall) {
    bookingData.selectedBooty = bootyCall;
    document.getElementById('bootyNameDisplay').textContent = bootyCall.name;
    document.getElementById('bookingAmount').textContent = bootyCall.price;
    document.getElementById('finalBootyName').textContent = `${bootyCall.name}, ${bootyCall.age}`;
    bookingData.price = bootyCall.price;
    
    goToStep(3);
  }
}

// Calculate end time based on start time and duration
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
    price = Math.round(basePrice * 0.75); // 25% off for 4 hours
  } else if (duration === '2') {
    price = Math.round(basePrice * 0.5); // 50% off for 2 hours
  }
  
  bookingData.duration = duration;
  bookingData.price = price;
  document.getElementById('bookingAmount').textContent = price;
  
  // Recalculate end time
  calculateEndTime();
});

// Start time change
document.getElementById('start-time').addEventListener('change', function() {
  calculateEndTime();
});

// Selfie upload functionality
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
      
      // Update upload area
      const uploadArea = document.getElementById('selfieUpload');
      uploadArea.innerHTML = `
        <i class="fas fa-check-circle" style="color: var(--success);"></i>
        <h4>Selfie Uploaded Successfully</h4>
        <p style="color: var(--text-muted); font-size: 0.9rem;">
          Your selfie has been uploaded for verification
        </p>
        <img id="selfiePreview" src="${e.target.result}" alt="Selfie Preview" style="max-width: 200px; border-radius: 8px; margin: 15px auto; display: block;">
        <button class="btn" style="margin-top: 10px; padding: 8px 20px;" onclick="document.getElementById('selfieInput').click()">
          Upload Different Selfie
        </button>
      `;
    };
    reader.readAsDataURL(file);
  }
});

// Pay now button
document.getElementById('payNowBtn').addEventListener('click', function(e) {
  e.preventDefault();
  
  // Validate form
  const fullName = document.getElementById('full-name').value;
  const phone = document.getElementById('phone').value;
  const location = document.getElementById('location').value;
  const date = document.getElementById('date').value;
  const startTime = document.getElementById('start-time').value;
  const duration = document.getElementById('duration').value;
  
  if (!fullName || !phone || !location || !date || !startTime || !duration) {
    alert('Please fill in all required fields');
    return;
  }
  
  if (!bookingData.selfieUploaded) {
    alert('Please upload a selfie for verification');
    return;
  }
  
  if (!document.getElementById('terms').checked) {
    alert('You must agree to the terms and conditions');
    return;
  }
  
  // Update success screen with booking details
  document.getElementById('finalBootyName').textContent = `${bookingData.selectedBooty?.name}, ${bookingData.selectedBooty?.age}`;
  document.getElementById('finalLocation').textContent = location;
  
  const dateObj = new Date(date);
  const formattedDate = dateObj.toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
  
  // Format time for display
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
  
  // Proceed to payment step
  goToStep(4);
});

// Navigation functions
function goToStep(step) {
  // Hide all steps
  document.querySelectorAll('.step-container').forEach(container => {
    container.classList.remove('active-step');
  });

  // Show the selected step
  document.getElementById(`step${step}`).classList.add('active-step');
  
  // Update step tracking
  currentStep = step;
}

// Back buttons
document.getElementById('back-to-search').addEventListener('click', () => goToStep(1));
document.getElementById('back-to-booty').addEventListener('click', () => goToStep(2));

// Initialize
document.addEventListener('DOMContentLoaded', function() {
  // Initialize cities
  initializeCities();
  
  // Set minimum date to today
  const today = new Date().toISOString().split('T')[0];
  document.getElementById('date').min = today;
  document.getElementById('date').value = today;
  
  // Set default start time to 8 PM
  document.getElementById('start-time').value = '20:00';
  calculateEndTime();
  
  // Animate logo
  const logoFire = document.querySelector('.fa-fire');
  setInterval(() => {
    logoFire.style.transform = 'scale(1.1)';
    setTimeout(() => {
      logoFire.style.transform = 'scale(1)';
    }, 300);
  }, 2000);
});
</script>
</body>
</html>
