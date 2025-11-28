# Viral-content-<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>♛ VIP Viral Vault</title>
  <meta name="description" content="VIP Viral Vault - secure access flow (demo).">
  <!-- NOTE: Set a real CSP header from your server for improved security -->
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg1:#0a001f;
      --bg2:#1a0033;
      --gold:#ffd700;
      --accent:#8b00ff;
    }
    html,body{height:100%}
    body {
      margin:0; padding:0; min-height:100vh;
      background: linear-gradient(135deg, var(--bg1), var(--bg2));
      color: var(--gold);
      font-family: 'Playfair Display', serif;
      display:flex; align-items:center; justify-content:center;
      text-align:center;
    }
    .container {
      background: rgba(10,0,30,0.85);
      border: 2px solid var(--gold);
      border-radius: 20px;
      padding: 36px 22px;
      max-width: 420px;
      width: calc(100% - 40px);
      box-shadow: 0 0 40px rgba(255,215,0,0.25);
    }
    h1 { font-family: 'Cinzel', serif; font-size:2.4rem; margin:8px 0; color:var(--gold); text-shadow:0 0 12px #ff00ff;}
    .crown{font-size:2.4rem}
    .price{font-size:1.6rem; color:#fff; background:var(--accent); padding:8px 20px; border-radius:40px; display:inline-block; margin:12px 0;}
    .qr{background:#fff; padding:12px; border-radius:12px; display:inline-block; margin:14px 0; box-shadow:0 0 12px rgba(255,215,0,0.12)}
    .qr img{width:220px;height:220px;display:block}
    .btn {
      background: linear-gradient(45deg, var(--gold), #ffea00);
      color: #000; padding:12px 26px; border-radius:40px;
      font-weight:bold; font-size:1rem; text-decoration:none; display:inline-block; margin:8px;
      box-shadow:0 5px 12px rgba(0,0,0,0.35);
    }
    .pay-collect {
      display:flex; gap:8px; align-items:center; justify-content:center; flex-wrap:wrap; margin-top:8px;
    }
    input[type="tel"], input[type="text"] {
      padding:12px; font-size:1rem; width:78%; border:none; border-radius:40px; text-align:center; margin:12px 0;
      outline: none;
    }
    button.secondary {
      background:var(--accent); color:var(--gold); padding:10px 18px; border:2px solid var(--gold); border-radius:40px;
      font-size:1rem; cursor:pointer; font-weight:bold;
    }
    .hidden{display:none}
    .success a{ color:var(--gold); font-size:1rem; text-decoration:underline;}
    .note{font-size:0.85rem; color:#ffeaa8; margin-top:8px}
    .error{color:#ff8b8b; font-weight:bold}
    @media (max-width:420px){ .qr img{width:180px;height:180px} }
  </style>
</head>
<body>

  <main class="container" id="app" role="main" aria-labelledby="title">
    <div class="crown" aria-hidden="true">♛</div>
    <h1 id="title">VIP VIRAL VAULT</h1>
    <p>Limited Access • Ultra Premium Content</p>
    <div class="price">Only ₹30</div>

    <section id="purchase-step" aria-labelledby="purchase-title">
      <div class="qr" aria-hidden="true">
        <!-- Static QR points to UPI payment URI; for production, generate server-side with exact txn params -->
        <img src="https://api.qrserver.com/v1/create-qr-code/?size=260x260&data=upi://pay?pa=9540455341@fam&pn=VIPViralVault&am=30.00&cu=INR" alt="QR code to pay ₹30">
      </div>

      <p class="note">UPI ID: <strong>9540455341@fam</strong></p>

      <div class="pay-collect">
        <a class="btn" id="pay-link" href="upi://pay?pa=9540455341@fam&pn=VIPViralVault&am=30.00&cu=INR&tn=Exclusive%20Access" rel="noopener noreferrer">
          Pay ₹30 Instantly
        </a>

        <button class="secondary" id="i-paid-btn" type="button">I Paid — Verify</button>
      </div>

      <p class="note">After completing payment in your UPI app, enter the transaction reference (UTR/TXN ID) below and click Verify. Do NOT share sensitive info here.</p>

      <form id="verify-form" onsubmit="return false;" aria-describedby="verify-note">
        <label for="txn" class="hidden">Transaction reference</label>
        <input id="txn" name="txn" type="text" inputmode="latin" placeholder="Enter transaction reference (UTR/TXN ID)" aria-label="Transaction reference" autocomplete="off">
        <br>
        <button id="verify-btn" class="secondary" type="button">Verify Payment</button>
        <div id="status" role="status" aria-live="polite"></div>
      </form>
    </section>

    <section id="access-granted" class="hidden" aria-hidden="true">
      <h2>♛ ACCESS GRANTED ♛</h2>
      <p class="success">
        <a id="vip-link" href="https://ig.me/j/AbagxQgTkzH7UtF2/" target="_blank" rel="noopener noreferrer">Click Here – Your VIP Link</a>
      </p>
    </section>

    <p class="note" id="legal">By paying you agree to the service terms. This demo requires server-side verification; do not rely on client-side checks alone.</p>
  </main>

  <script>
    // Frontend logic: expects a server endpoint at POST /api/verify-payment
    // Body: { txn: string } -> returns JSON { ok: boolean, accessUrl?: string, message?: string }
    // Implement server-side verification with your payment provider/UPI reconciliation.
    (function(){
      const iPaidBtn = document.getElementById('i-paid-btn');
      const verifyBtn = document.getElementById('verify-btn');
      const txnInput = document.getElementById('txn');
      const status = document.getElementById('status');
      const purchaseStep = document.getElementById('purchase-step');
      const accessGranted = document.getElementById('access-granted');


