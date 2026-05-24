<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Discord Server Service</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@2.44.0/tabler-icons.min.css" />
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: #0e0e12;
      color: #e8e6f0;
      min-height: 100vh;
    }

    .hero {
      position: relative;
      overflow: hidden;
      padding: 80px 24px 60px;
      text-align: center;
    }

    .hero::before {
      content: '';
      position: absolute;
      top: -60px; left: 50%; transform: translateX(-50%);
      width: 600px; height: 400px;
      background: radial-gradient(ellipse at center, rgba(88,101,242,0.18) 0%, transparent 70%);
      pointer-events: none;
    }

    .badge {
      display: inline-flex; align-items: center; gap: 6px;
      background: rgba(88,101,242,0.12);
      border: 0.5px solid rgba(88,101,242,0.4);
      border-radius: 20px;
      padding: 5px 14px;
      font-size: 12px;
      color: #a8b4ff;
      margin-bottom: 24px;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      font-weight: 500;
    }

    .dot {
      width: 6px; height: 6px;
      border-radius: 50%;
      background: #5865f2;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    h1 {
      font-family: 'Syne', sans-serif;
      font-size: clamp(32px, 6vw, 56px);
      font-weight: 800;
      line-height: 1.1;
      margin-bottom: 16px;
      color: #ffffff;
      letter-spacing: -0.02em;
    }

    h1 span {
      background: linear-gradient(135deg, #5865f2, #9b8cff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .subtitle {
      font-size: 17px;
      color: #8e8ba0;
      max-width: 480px;
      margin: 0 auto 48px;
      line-height: 1.6;
      font-weight: 300;
    }

    .pricing-strip {
      display: flex;
      justify-content: center;
      gap: 10px;
      flex-wrap: wrap;
      margin-bottom: 52px;
    }

    .price-tag {
      background: #1a1a22;
      border: 0.5px solid #2e2e3a;
      border-radius: 12px;
      padding: 8px 16px;
      font-size: 13px;
      color: #b8b4c8;
    }

    .price-tag strong { color: #7cfc9e; font-weight: 500; }

    .form-card {
      max-width: 560px;
      margin: 0 auto;
      background: #141418;
      border: 0.5px solid #2a2a36;
      border-radius: 20px;
      padding: 40px;
    }

    .form-label {
      display: block;
      font-size: 12px;
      font-weight: 500;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      color: #6e6a80;
      margin-bottom: 8px;
    }

    .form-group { margin-bottom: 20px; }

    .form-input {
      width: 100%;
      background: #0e0e12;
      border: 0.5px solid #2a2a36;
      border-radius: 10px;
      padding: 12px 16px;
      font-size: 15px;
      color: #e8e6f0;
      font-family: 'DM Sans', sans-serif;
      outline: none;
      transition: border-color 0.2s;
    }

    .form-input:focus { border-color: rgba(88,101,242,0.6); }
    .form-input::placeholder { color: #3e3b4e; }
    textarea.form-input { resize: vertical; min-height: 90px; }

    .price-slider-wrap {
      background: #0e0e12;
      border: 0.5px solid #2a2a36;
      border-radius: 10px;
      padding: 16px;
    }

    .price-display {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
    }

    .price-amount {
      font-family: 'Syne', sans-serif;
      font-size: 28px;
      font-weight: 700;
      color: #7cfc9e;
    }

    .price-note { font-size: 12px; color: #4e4b60; }

    input[type=range] {
      width: 100%;
      accent-color: #5865f2;
      height: 4px;
    }

    .range-labels {
      display: flex;
      justify-content: space-between;
      font-size: 11px;
      color: #3e3b4e;
      margin-top: 6px;
    }

    .type-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 8px;
    }

    .type-btn {
      background: #0e0e12;
      border: 0.5px solid #2a2a36;
      border-radius: 10px;
      padding: 10px 8px;
      font-size: 12px;
      color: #8e8ba0;
      cursor: pointer;
      text-align: center;
      transition: all 0.15s;
      font-family: 'DM Sans', sans-serif;
    }

    .type-btn:hover { border-color: #5865f2; color: #a8b4ff; }
    .type-btn.active {
      background: rgba(88,101,242,0.12);
      border-color: rgba(88,101,242,0.5);
      color: #a8b4ff;
    }

    .submit-btn {
      width: 100%;
      background: #5865f2;
      border: none;
      border-radius: 10px;
      padding: 14px;
      font-size: 15px;
      font-weight: 500;
      color: #ffffff;
      cursor: pointer;
      font-family: 'DM Sans', sans-serif;
      transition: background 0.2s, transform 0.1s;
      margin-top: 8px;
      letter-spacing: 0.01em;
    }

    .submit-btn:hover { background: #4752c4; }
    .submit-btn:active { transform: scale(0.99); }

    .owner-btn {
      position: fixed;
      top: 16px; right: 16px;
      background: #1a1a22;
      border: 0.5px solid #2e2e3a;
      border-radius: 10px;
      padding: 8px 16px;
      font-size: 13px;
      color: #6e6a80;
      cursor: pointer;
      font-family: 'DM Sans', sans-serif;
      display: flex; align-items: center; gap: 6px;
      transition: all 0.2s;
      z-index: 100;
    }

    .owner-btn:hover { border-color: #5865f2; color: #a8b4ff; }

    .modal-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.8);
      z-index: 200;
      align-items: center;
      justify-content: center;
    }

    .modal-overlay.show { display: flex; }

    .modal {
      background: #141418;
      border: 0.5px solid #2a2a36;
      border-radius: 16px;
      padding: 32px;
      width: 90%;
      max-width: 440px;
    }

    .modal h2 {
      font-family: 'Syne', sans-serif;
      font-size: 20px;
      font-weight: 700;
      margin-bottom: 20px;
      color: #ffffff;
    }

    .modal .close-btn {
      float: right;
      background: none;
      border: none;
      color: #6e6a80;
      cursor: pointer;
      font-size: 18px;
      line-height: 1;
    }

    .panel {
      display: none;
      max-width: 760px;
      margin: 0 auto;
      padding: 24px;
    }

    .panel.show { display: block; }

    .panel-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 24px;
    }

    .panel-title {
      font-family: 'Syne', sans-serif;
      font-size: 22px;
      font-weight: 700;
      color: #ffffff;
    }

    .back-btn {
      background: #1a1a22;
      border: 0.5px solid #2e2e3a;
      border-radius: 8px;
      padding: 6px 14px;
      font-size: 13px;
      color: #8e8ba0;
      cursor: pointer;
      font-family: 'DM Sans', sans-serif;
    }

    .order-card {
      background: #141418;
      border: 0.5px solid #2a2a36;
      border-radius: 12px;
      padding: 18px 20px;
      margin-bottom: 10px;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 12px;
      align-items: start;
    }

    .order-email { font-size: 14px; font-weight: 500; color: #e8e6f0; margin-bottom: 4px; }
    .order-type { font-size: 13px; color: #6e6a80; margin-bottom: 6px; }
    .order-desc { font-size: 12px; color: #4e4b60; line-height: 1.5; }

    .order-price {
      font-family: 'Syne', sans-serif;
      font-size: 20px;
      font-weight: 700;
      color: #7cfc9e;
      text-align: right;
    }

    .order-time { font-size: 11px; color: #3e3b4e; text-align: right; margin-top: 4px; }

    .empty-state {
      text-align: center;
      padding: 60px 20px;
      color: #3e3b4e;
      font-size: 14px;
    }

    .success-msg {
      display: none;
      background: rgba(124,252,158,0.06);
      border: 0.5px solid rgba(124,252,158,0.2);
      border-radius: 10px;
      padding: 16px;
      text-align: center;
      color: #7cfc9e;
      font-size: 14px;
      margin-top: 16px;
    }

    .error-msg {
      display: none;
      color: #ff6b6b;
      font-size: 12px;
      margin-top: 8px;
    }

    .main-view { padding-bottom: 60px; }
  </style>
</head>
<body>

  <button class="owner-btn" onclick="openOwnerLogin()">
    <i class="ti ti-lock" aria-hidden="true"></i> Owner
  </button>

  <div id="mainView" class="main-view">
    <div class="hero">
      <div class="badge"><div class="dot"></div> Professional Service</div>
      <h1>Your Dream<br><span>Discord Server</span><br>Built Fast.</h1>
      <p class="subtitle">Please enter your email below so the owner can contact you with your order details.</p>
      <div class="pricing-strip">
        <div class="price-tag">🎮 Gaming — <strong>from $1</strong></div>
        <div class="price-tag">💬 Community — <strong>from $3</strong></div>
        <div class="price-tag">🏢 Business — <strong>from $6</strong></div>
        <div class="price-tag">⭐ Premium — <strong>up to $10</strong></div>
      </div>
    </div>

    <div class="form-card">
      <div class="form-group">
        <label class="form-label" for="emailInput">Your Email</label>
        <input class="form-input" type="email" id="emailInput" placeholder="you@example.com" />
        <div class="error-msg" id="emailError">Please enter a valid email address.</div>
      </div>

      <div class="form-group">
        <label class="form-label">What kind of Discord server?</label>
        <div class="type-grid">
          <button class="type-btn" onclick="selectType(this, 'Gaming')">🎮 Gaming</button>
          <button class="type-btn" onclick="selectType(this, 'Community')">💬 Community</button>
          <button class="type-btn" onclick="selectType(this, 'Business')">🏢 Business</button>
          <button class="type-btn" onclick="selectType(this, 'Esports')">🏆 Esports</button>
          <button class="type-btn" onclick="selectType(this, 'Music')">🎵 Music</button>
          <button class="type-btn" onclick="selectType(this, 'Other')">✨ Other</button>
        </div>
      </div>

      <div class="form-group">
        <label class="form-label" for="descInput">Tell me what you want</label>
        <textarea class="form-input" id="descInput" placeholder="E.g. A gaming server for my friends with channels for Minecraft, Valorant, and a general chat..."></textarea>
      </div>

      <div class="form-group">
        <label class="form-label">Your Budget</label>
        <div class="price-slider-wrap">
          <div class="price-display">
            <span class="price-amount" id="priceDisplay">$5</span>
            <span class="price-note">$1 – $10</span>
          </div>
          <input type="range" min="1" max="10" value="5" step="1" id="priceSlider" oninput="updatePrice(this.value)" />
          <div class="range-labels"><span>$1</span><span>$5</span><span>$10</span></div>
        </div>
      </div>

      <button class="submit-btn" onclick="submitOrder()">
        <i class="ti ti-send" aria-hidden="true"></i> Send Order
      </button>
      <div class="success-msg" id="successMsg">✅ Order received! The owner will contact you soon.</div>
    </div>
  </div>

  <div id="panelView" class="panel">
    <div class="panel-header">
      <span class="panel-title">📋 Orders</span>
      <button class="back-btn" onclick="closePanel()">← Back</button>
    </div>
    <div id="ordersList"></div>
  </div>

  <div class="modal-overlay" id="loginModal">
    <div class="modal">
      <button class="close-btn" onclick="closeLogin()"><i class="ti ti-x"></i></button>
      <h2>🔐 Owner Login</h2>
      <div class="form-group">
        <label class="form-label">Password</label>
        <input class="form-input" type="password" id="pwInput" placeholder="Enter password" onkeydown="if(event.key==='Enter')checkPw()" />
        <div class="error-msg" id="pwError">Wrong password. Try again.</div>
      </div>
      <button class="submit-btn" onclick="checkPw()">Enter Panel</button>
    </div>
  </div>

  <script>
    const PASS = 'CURBYCURBY2323';
    let selectedType = '';

    function selectType(el, type) {
      document.querySelectorAll('.type-btn').forEach(b => b.classList.remove('active'));
      el.classList.add('active');
      selectedType = type;
    }

    function updatePrice(val) {
      document.getElementById('priceDisplay').textContent = '$' + val;
    }

    function openOwnerLogin() {
      document.getElementById('loginModal').classList.add('show');
      setTimeout(() => document.getElementById('pwInput').focus(), 100);
    }

    function closeLogin() {
      document.getElementById('loginModal').classList.remove('show');
      document.getElementById('pwInput').value = '';
      document.getElementById('pwError').style.display = 'none';
    }

    function checkPw() {
      const val = document.getElementById('pwInput').value;
      if (val === PASS) {
        closeLogin();
        showPanel();
      } else {
        document.getElementById('pwError').style.display = 'block';
        document.getElementById('pwInput').value = '';
      }
    }

    function showPanel() {
      document.getElementById('mainView').style.display = 'none';
      const panel = document.getElementById('panelView');
      panel.classList.add('show');
      renderOrders();
    }

    function closePanel() {
      document.getElementById('panelView').classList.remove('show');
      document.getElementById('mainView').style.display = 'block';
    }

    function getOrders() {
      try {
        return JSON.parse(localStorage.getItem('dc_orders') || '[]');
      } catch(e) { return []; }
    }

    function saveOrder(order) {
      const orders = getOrders();
      orders.unshift(order);
      localStorage.setItem('dc_orders', JSON.stringify(orders));
    }

    function renderOrders() {
      const orders = getOrders();
      const el = document.getElementById('ordersList');
      if (!orders.length) {
        el.innerHTML = '<div class="empty-state">No orders yet. Check back later!</div>';
        return;
      }
      el.innerHTML = orders.map(o => `
        <div class="order-card">
          <div>
            <div class="order-email">${escHtml(o.email)}</div>
            <div class="order-type">📁 ${escHtml(o.type || 'Not specified')}</div>
            <div class="order-desc">${escHtml(o.desc || '—')}</div>
          </div>
          <div>
            <div class="order-price">$${o.price}</div>
            <div class="order-time">${o.time}</div>
          </div>
        </div>
      `).join('');
    }

    function escHtml(s) {
      return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');
    }

    function submitOrder() {
      const email = document.getElementById('emailInput').value.trim();
      const desc = document.getElementById('descInput').value.trim();
      const price = document.getElementById('priceSlider').value;

      const emailOk = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email);
      document.getElementById('emailError').style.display = emailOk ? 'none' : 'block';
      if (!emailOk) return;

      const now = new Date();
      const time = now.toLocaleDateString('de-DE') + ' ' + now.toLocaleTimeString('de-DE', {hour:'2-digit', minute:'2-digit'});

      saveOrder({ email, type: selectedType, desc, price, time });

      document.getElementById('emailInput').value = '';
      document.getElementById('descInput').value = '';
      document.getElementById('priceSlider').value = 5;
      document.getElementById('priceDisplay').textContent = '$5';
      document.querySelectorAll('.type-btn').forEach(b => b.classList.remove('active'));
      selectedType = '';

      const msg = document.getElementById('successMsg');
      msg.style.display = 'block';
      setTimeout(() => msg.style.display = 'none', 4000);
    }
  </script>

</body>
</html>
