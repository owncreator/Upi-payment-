<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Payment Gateway UI Template</title>
  <style>
    :root{
      --bg:#f6f6f6;
      --card:#ffffff;
      --muted:#9aa0a6;
      --accent:#20b24a;
      --border:#e6e6e6;
      --dark:#222;
      --max-w:1100px;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    *{box-sizing:border-box}
    body{margin:0;background:var(--bg);color:var(--dark);display:flex;align-items:center;justify-content:center;min-height:100vh}
    .wrap{width:100%;max-width:var(--max-w);background:linear-gradient(90deg, rgba(255,255,255,1) 0%, rgba(255,255,255,1) 50%, rgba(250,250,250,1) 50%, rgba(250,250,250,1) 100%);display:grid;grid-template-columns:1fr 420px;gap:0;border-radius:6px;overflow:hidden;box-shadow:0 10px 30px rgba(15,15,15,0.06)}/* left column - payment */
.left{padding:48px 60px;background:var(--card)}
h2{margin:0 0 18px;font-size:20px}
.section-line{height:1px;background:var(--border);margin:18px 0}

.pay-with{font-size:14px;margin-bottom:14px;color:var(--muted)}
.pay-options{display:flex;gap:18px;align-items:center;margin-bottom:18px}
.option{display:flex;align-items:center;gap:8px;color:var(--muted);font-size:14px}
.chips{display:flex;gap:12px;align-items:center}
.chip{width:44px;height:28px;display:inline-block;background:linear-gradient(135deg,#ff6a00,#ff2d55);border-radius:6px}
.visa{font-weight:700;color:#1a66ff}

.form-row{display:flex;gap:18px}
.field{margin:12px 0}
label{display:block;font-size:13px;color:var(--muted);margin-bottom:8px}
input[type=text],input[type=tel],input[type=password]{width:100%;padding:12px;border:1px solid var(--border);border-radius:6px;font-size:14px}
.card-input{position:relative}
.card-brand{position:absolute;right:10px;top:50%;transform:translateY(-50%);}

.small{width:140px}
.checkbox{display:flex;align-items:center;gap:8px;color:var(--muted);font-size:13px;margin-top:8px}

.pay-btn{display:inline-block;margin-top:18px;padding:14px 22px;background:var(--accent);color:white;border-radius:6px;border:none;font-weight:700;font-size:16px;cursor:pointer}
.note{font-size:12px;color:#9aa0a6;margin-top:18px;line-height:1.5}

/* right column - summary */
.right{background:#fafafa;padding:48px 40px;border-left:1px solid var(--border)}
.right h3{margin:0 0 14px;font-size:18px}
.detail{font-size:14px;color:var(--muted);display:flex;justify-content:space-between;gap:8px}

.summary-box{margin-top:18px}
.order-item{display:flex;gap:12px;align-items:center;padding:12px 0;border-bottom:1px solid var(--border)}
.thumb{width:64px;height:52px;border-radius:6px;background:linear-gradient(135deg,#7b61ff,#ff6a9a);display:flex;align-items:center;justify-content:center;color:white;font-weight:700}
.item-ttl{font-weight:600}
.muted{color:var(--muted);font-size:13px}

.coupon{display:flex;gap:8px;margin-top:14px}
.coupon input{flex:1;padding:10px;border-radius:6px;border:1px solid var(--border)}
.coupon button{padding:10px 14px;border-radius:6px;border:1px solid var(--border);background:#efefef;cursor:pointer}

.totals{margin-top:22px}
.totals .row{display:flex;justify-content:space-between;padding:10px 0;border-bottom:1px solid var(--border)}
.total-amount{font-size:28px;font-weight:800;margin-top:10px}

/* responsiveness */
@media (max-width:980px){
  .wrap{grid-template-columns:1fr;max-width:720px}
  .right{order:2}
}
@media (max-width:520px){
  .left{padding:24px}
  .right{padding:24px}
}

  </style>
</head>
<body>
  <div class="wrap">
    <div class="left">
      <h2>Payment</h2>
      <div class="section-line"></div><div class="pay-with">Pay With:</div>
  <div class="pay-options">
    <label class="option"><input type="radio" name="pay" checked> Card</label>
    <label class="option"><input type="radio" name="pay"> Bank Transfer</label>
    <label class="option"><input type="radio" name="pay"> Cryptocurrency</label>
  </div>
  <div class="chips" style="margin-bottom:18px">
    <div class="chip" title="Mastercard"></div>
    <div class="visa">VISA</div>
  </div>

  <div class="field card-input">
    <label>Card Number</label>
    <input id="cardNumber" type="text" placeholder="5399 0000 0000 0000" maxlength="19">
    <div class="card-brand" id="brand">&#9679;&#9679;</div>
  </div>

  <div class="form-row">
    <div class="field small">
      <label>Expiration Date</label>
      <input id="exp" type="text" placeholder="MM/YY" maxlength="5">
    </div>
    <div class="field small">
      <label>CVV</label>
      <input id="cvv" type="password" placeholder="***" maxlength="4">
    </div>
  </div>

  <label class="checkbox"><input type="checkbox"> Save card details</label>

  <button class="pay-btn" id="payBtn">Pay USD250.28</button>

  <div class="note">Your personal data will be used to process your order, support your experience throughout this website, and for other purposes described in our privacy policy.</div>
</div>

<div class="right">
  <h3>Contact Details</h3>
  <div class="detail"><div>Full Name</div><div>John Doe</div></div>
  <div class="detail"><div>Email</div><div>JohnDoe@gmail.com</div></div>
  <div class="detail" style="margin-bottom:6px"><div>Mobile</div><div>+2348345678923</div></div>
  <div style="color:#31a36c;font-size:13px;margin-bottom:18px">Not John Doe? Change Account</div>

  <h3>Order Summary</h3>
  <div class="summary-box">
    <div class="order-item">
      <div class="thumb">PS5</div>
      <div style="flex:1">
        <div class="item-ttl">Sony Play station 5</div>
        <div class="muted">White color with Game Pad</div>
      </div>
      <div style="text-align:right;font-weight:700">$200.80<br><span class="muted" style="font-weight:500">Qty: 1</span></div>
    </div>

    <div class="coupon">
      <input placeholder="Gift or discount code">
      <button>Apply</button>
    </div>

    <div class="totals">
      <div class="row"><div>Subtotal</div><div>$200.80</div></div>
      <div class="row"><div>Shipping</div><div>$49.48</div></div>
      <div style="padding-top:10px">
        <div style="color:var(--muted);font-size:13px">Including $2.24 in taxes</div>
        <div class="total-amount">$250.28</div>
      </div>
    </div>
  </div>

</div>

  </div>  <script>
    // Simple input formatting and interactions
    const cardInput = document.getElementById('cardNumber');
    const exp = document.getElementById('exp');
    const cvv = document.getElementById('cvv');
    const brand = document.getElementById('brand');
    const payBtn = document.getElementById('payBtn');

    cardInput.addEventListener('input', (e)=>{
      let v = e.target.value.replace(/\D/g,'').slice(0,16);
      let parts = v.match(/.{1,4}/g);
      e.target.value = parts ? parts.join(' ') : v;

      // naive brand detection
      if(v.startsWith('4')) brand.textContent = 'VISA';
      else if(/^5[1-5]/.test(v)) brand.textContent = 'Mastercard';
      else brand.textContent = '';
    });

    exp.addEventListener('input', (e)=>{
      let v = e.target.value.replace(/\D/g,'').slice(0,4);
      if(v.length>=3) v = v.slice(0,2) + '/' + v.slice(2);
      e.target.value = v;
    });

    payBtn.addEventListener('click', ()=>{
      payBtn.disabled = true;
      payBtn.textContent = 'Processing...';
      setTimeout(()=>{
        payBtn.textContent = 'Payment Successful';
        payBtn.style.background = '#2dbb6f';
      },1200);
    });
  </script></body>
</html>
