# JKS-MY-COURIER-AND-RIDE-BOOKING# <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>My Courier Delivery & Ride Booking</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      background: white;
      color: #333;
    }
    header {
      background: #87ceeb; /* sky blue */
      color: white;
      padding: 1rem;
      text-align: center;
      font-size: 1.2rem;
      font-weight: bold;
    }
    nav {
      background: #87ceeb;
      padding: 10px 0;
      text-align: center;
      color: white;
      font-weight: bold;
      font-size: 16px;
    }
    .container {
      max-width: 900px;
      margin: 20px auto;
      padding: 1rem;
      border: 2px solid #87ceeb;
      border-radius: 8px;
    }
    #dashboard {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
    }
    .dashboard-card {
      border: 2px solid #87ceeb;
      border-radius: 8px;
      padding: 20px;
      width: 250px;
      background-color: #f9fcff;
      text-align: center;
      cursor: pointer;
      font-weight: bold;
      color: #87ceeb;
      transition: background-color 0.3s, color 0.3s;
    }
    .dashboard-card:hover {
      background-color: #87ceeb;
      color: white;
    }
    .tabs {
      display: flex;
      justify-content: space-around;
      margin-bottom: 1rem;
    }
    button.tab-btn {
      padding: 0.5rem 1rem;
      background: white;
      border: 2px solid #87ceeb;
      border-radius: 4px;
      cursor: pointer;
      color: #87ceeb;
      font-weight: bold;
      transition: background-color 0.3s, color 0.3s;
    }
    button.tab-btn.active, button.tab-btn:hover {
      background: #87ceeb;
      color: white;
    }
    .section {
      display: none;
      margin-top: 1rem;
      border-top: 1px solid #87ceeb;
      padding-top: 1rem;
    }
    .section.active {
      display: block;
    }
    label {
      display: block;
      margin: 0.75rem 0 0.25rem;
      font-weight: bold;
    }
    select, input[type="radio"] {
      margin-right: 0.5rem;
    }
    .vehicle-options label {
      display: inline-block;
      margin-right: 1rem;
      font-weight: normal;
    }
    .whatsapp-link {
      display: inline-block;
      margin-top: 15px;
      background-color: #25d366;
      color: white;
      padding: 10px 18px;
      border-radius: 5px;
      text-decoration: none;
      font-weight: bold;
      font-size: 14px;
    }
    .whatsapp-link:hover {
      background-color: #1ebe57;
    }
    form.contact-form {
      margin-top: 15px;
      max-width: 400px;
    }
    form.contact-form label {
      display: block;
      margin: 8px 0 4px;
      font-weight: bold;
    }
    form.contact-form input, form.contact-form textarea {
      width: 100%;
      padding: 8px;
      border: 1px solid #87ceeb;
      border-radius: 4px;
      box-sizing: border-box;
      font-size: 14px;
    }
    form.contact-form textarea {
      resize: vertical;
      min-height: 60px;
    }
    form.contact-form button {
      margin-top: 12px;
      background-color: #87ceeb;
      color: white;
      border: none;
      padding: 10px 18px;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }
    form.contact-form button:hover {
      background-color: #649dd9;
    }
    .back-btn {
      background-color: #87ceeb;
      color: white;
      border: none;
      border-radius: 5px;
      padding: 10px 18px;
      cursor: pointer;
      font-weight: bold;
      margin-bottom: 15px;
    }
  </style>
</head>
<body>
  <header>
    My Courier Delivery & Ride Booking
  </header>

  <div class="container">

    <!-- Dashboard -->
    <section id="dashboard">
      <div class="dashboard-card" onclick="showSection('courier')">Courier</div>
      <div class="dashboard-card" onclick="showSection('ride')">Ride Booking</div>
      <div class="dashboard-card" onclick="showSection('rent')">Rental Vehicle</div>
    </section>

    <!-- Courier Section -->
    <section id="courier" class="section">
      <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>

      <h3>Courier</h3>
      <label>Choose Location:</label>
      <select id="courierLocation">
        <option value="send">Send</option>
        <option value="receive">Receive</option>
      </select>

      <label>Vehicle Type:</label>
      <div class="vehicle-options">
        <label><input type="radio" name="courierVehicle" value="bike" checked /> Bike</label>
        <label><input type="radio" name="courierVehicle" value="auto" /> Auto</label>
        <label><input type="radio" name="courierVehicle" value="car" /> Car</label>
        <label><input type="radio" name="courierVehicle" value="miniauto" /> Mini Auto</label>
        <label><input type="radio" name="courierVehicle" value="lorry" /> Lorry</label>
      </div>

      <form class="contact-form" id="courierForm" onsubmit="handleSubmit(event, 'Courier')">
        <label for="name-courier">Name:</label>
        <input type="text" id="name-courier" name="name" required />
        <label for="email-courier">Email:</label>
        <input type="email" id="email-courier" name="email" required />
        <label for="phone-courier">Phone:</label>
        <input type="tel" id="phone-courier" name="phone" required />
        <label for="message-courier">Message:</label>
        <textarea id="message-courier" name="message" required></textarea>
        <button type="submit">Submit via WhatsApp</button>
      </form>
    </section>

    <!-- Ride Booking Section -->
    <section id="ride" class="section">
      <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>

      <h3>Ride Booking</h3>
      <label>Select Ride Type:</label>
      <div class="vehicle-options">
        <label><input type="radio" name="rideType" value="bike" checked /> Bike</label>
        <label><input type="radio" name="rideType" value="auto" /> Auto</label>
        <label><input type="radio" name="rideType" value="car" /> Car</label>
      </div>

      <form class="contact-form" id="rideForm" onsubmit="handleSubmit(event, 'Ride Booking')">
        <label for="name-ride">Name:</label>
        <input type="text" id="name-ride" name="name" required />
        <label for="email-ride">Email:</label>
        <input type="email" id="email-ride" name="email" required />
        <label for="phone-ride">Phone:</label>
        <input type="tel" id="phone-ride" name="phone" required />
        <label for="message-ride">Message:</label>
        <textarea id="message-ride" name="message" required></textarea>
        <button type="submit">Submit via WhatsApp</button>
      </form>
    </section>

    <!-- Rental Vehicle Section -->
    <section id="rent" class="section">
      <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>

      <h3>Rental Vehicle</h3>
      <label>Select Mode:</label>
      <div class="vehicle-options">
        <label><input type="radio" name="rentMode" value="self" checked /> Self</label>
        <label><input type="radio" name="rentMode" value="driver" /> With Driver</label>
      </div>

      <div id="selfVehicleOptions">
        <label>Choose Vehicle:</label>
        <div class="vehicle-options">
          <label><input type="radio" name="selfVehicle" value="bike" checked /> Bike</label>
          <label><input type="radio" name="selfVehicle" value="car" /> Car</label>
          <label><input type="radio" name="selfVehicle" value="auto" /> Auto</label>
        </div>
      </div>

      <div id="driverVehicleOptions" style="display:none;">
        <label>Choose Vehicle:</label>
        <div class="vehicle-options">
          <label><input type="radio" name="driverVehicle" value="bike" /> Bike</label>
          <label><input type="radio" name="driverVehicle" value="car" /> Car</label>
          <label><input type="radio" name="driverVehicle" value="auto" /> Auto</label>
          <label><input type="radio" name="driverVehicle" value="bolero" /> Bolero</label>
          <label><input type="radio" name="driverVehicle" value="volvo" /> Volvo</label>
          <label><input type="radio" name="driverVehicle" value="jeep" /> Jeep</label>
        </div>
      </div>

      <form class="contact-form" id="rentForm" onsubmit="handleSubmit(event, 'Rental Vehicle')">
        <label for="name-rent">Name:</label>
        <input type="text" id="name-rent" name="name" required />
        <label for="email-rent">Email:</label>
        <input type="email" id="email-rent" name="email" required />
        <label for="phone-rent">Phone:</label>
        <input type="tel" id="phone-rent" name="phone" required />
        <label for="message-rent">Message:</label>
        <textarea id="message-rent" name="message" required></textarea>
        <button type="submit">Submit via WhatsApp</button>
      </form>
    </section>

  </div>

  <script>
    const dashboard = document.getElementById('dashboard');
    const courierSection = document.getElementById('courier');
    const rideSection = document.getElementById('ride');
    const rentSection = document.getElementById('rent');

    function showSection(sectionId) {
      dashboard.style.display = 'none';
      courierSection.classList.remove('active');
      rideSection.classList.remove('active');
      rentSection.classList.remove('active');

      if(sectionId === 'courier') courierSection.classList.add('active');
      if(sectionId === 'ride') rideSection.classList.add('active');
      if(sectionId === 'rent') rentSection.classList.add('active');
    }

    function showDashboard() {
      courierSection.classList.remove('active');
      rideSection.classList.remove('active');
      rentSection.classList.remove('active');
      dashboard.style.display = 'flex';
    }

    // Rental vehicle mode toggle
    const rentModeRadios = document.getElementsByName('rentMode');
    const selfVehicleOptions = document.getElementById('selfVehicleOptions');
    const driverVehicleOptions = document.getElementById('driverVehicleOptions');

    rentModeRadios.forEach(radio => {
      radio.addEventListener('change', () => {
        if (radio.value === 'self') {
          selfVehicleOptions.style.display = 'block';
          driverVehicleOptions.style.display = 'none';
        } else {
          selfVehicleOptions.style.display = 'none';
          driverVehicleOptions.style.display = 'block';
        }
      });
    });

    // Form handler to open WhatsApp with pre-filled message
    function handleSubmit(event, section) {
      event.preventDefault();
      const form = event.target;
      const name = form.name.value.trim();
      const email = form.email.value.trim();
      const phone = form.phone.value.trim();
      const message = form.message.value.trim();

      if (!name || !email || !phone || !message) {
        alert('Please fill all fields.');
        return;
      }

      // Compose WhatsApp message text for URL encoding
      const whatsappNumber = '8977143043';
      const textMsg = `Name: ${name}%0AEmail: ${email}%0APhone: ${phone}%0AService: ${section}%0AMessage: ${encodeURIComponent(message)}`;
      const whatsappURL = `https://wa.me/${whatsappNumber}?text=${textMsg}`;

      // Open WhatsApp in new tab/window
      window.open(whatsappURL, '_blank');

      // Optional: reset form
      form.reset();
    }

    // On page load show dashboard
    document.addEventListener('DOMContentLoaded', () => {
      showDashboard();
    });
  </script>
</body>
</html>
