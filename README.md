# jp-flow
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JP FLOW — Where Hydration Meets Personalization</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700;900&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --black:#0a0908;
    --navy:#0d1b2a;
    --gold:#c9a84c;
    --gold-bright:#e3c878;
    --cream:#f5f0e6;
    --bronze:#8b6f3e;
    --line:rgba(201,168,76,0.25);
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--black);
    color:var(--cream);
    font-family:'Inter',sans-serif;
    font-weight:300;
    overflow-x:hidden;
  }
  h1,h2,h3{font-family:'Playfair Display',serif;}
  a{color:inherit;text-decoration:none;}

  /* ---------- NAV ---------- */
  nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    display:flex;align-items:center;justify-content:space-between;
    padding:18px 6%;
    background:linear-gradient(180deg, rgba(10,9,8,0.95), rgba(10,9,8,0));
    backdrop-filter:blur(4px);
  }
  .nav-logo{display:flex;align-items:center;gap:10px;font-family:'Playfair Display',serif;font-weight:700;letter-spacing:2px;font-size:18px;color:var(--gold-bright);}
  .nav-logo img{height:34px;width:34px;border-radius:50%;border:1px solid var(--line);}
  .nav-links{display:flex;gap:36px;font-size:13px;letter-spacing:1.5px;text-transform:uppercase;}
  .nav-links a{opacity:.75;transition:opacity .3s;}
  .nav-links a:hover{opacity:1;color:var(--gold-bright);}
  .nav-cta{
    border:1px solid var(--gold);
    padding:9px 20px;
    font-size:12px;letter-spacing:1.5px;text-transform:uppercase;
    border-radius:2px;
    transition:all .3s;
  }
  .nav-cta:hover{background:var(--gold);color:var(--black);}
  @media (max-width:820px){ .nav-links{display:none;} }

  /* ---------- HERO ---------- */
  .hero{
    min-height:100vh;
    display:flex;align-items:center;justify-content:center;
    position:relative;
    padding:140px 6% 80px;
    background:
      radial-gradient(ellipse 70% 50% at 50% 30%, rgba(201,168,76,0.08), transparent 70%),
      linear-gradient(180deg, var(--black) 0%, #0c0b0a 60%, var(--black) 100%);
    text-align:center;
  }
  .ring{
    position:absolute;
    border:1px solid var(--line);
    border-radius:50%;
    pointer-events:none;
  }
  .ring1{width:680px;height:680px;top:50%;left:50%;transform:translate(-50%,-50%);animation:spin 90s linear infinite;}
  .ring2{width:560px;height:560px;top:50%;left:50%;transform:translate(-50%,-50%);animation:spin 70s linear infinite reverse;border-style:dashed;}
  @keyframes spin{from{transform:translate(-50%,-50%) rotate(0deg);}to{transform:translate(-50%,-50%) rotate(360deg);}}
  @media (prefers-reduced-motion: reduce){.ring1,.ring2{animation:none;}}

  .hero-inner{position:relative;z-index:2;max-width:780px;}
  .hero-logo{width:118px;height:118px;border-radius:50%;margin-bottom:28px;border:1px solid var(--line);box-shadow:0 0 60px rgba(201,168,76,0.15);}
  .eyebrow{
    font-size:12px;letter-spacing:4px;text-transform:uppercase;color:var(--bronze);
    margin-bottom:22px;font-weight:500;
  }
  .hero h1{
    font-size:clamp(38px,6vw,68px);
    line-height:1.08;
    font-weight:700;
    color:var(--cream);
    margin-bottom:22px;
  }
  .hero h1 em{font-style:normal;color:var(--gold-bright);}
  .hero p.sub{
    font-size:17px;line-height:1.7;color:rgba(245,240,230,0.7);
    max-width:560px;margin:0 auto 38px;
  }
  .hero-ctas{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;}
  .custom-flag{
    display:inline-flex;align-items:center;gap:10px;
    border:1px solid var(--gold);
    background:rgba(201,168,76,0.08);
    padding:10px 22px;border-radius:30px;
    font-size:13px;letter-spacing:0.5px;color:var(--gold-bright);
    font-weight:500;margin-bottom:32px;
  }
  .flag-dot{
    width:8px;height:8px;border-radius:50%;background:var(--gold-bright);
    box-shadow:0 0 0 0 rgba(227,200,120,0.6);
    animation:pulse 2s infinite;
  }
  @keyframes pulse{
    0%{box-shadow:0 0 0 0 rgba(227,200,120,0.5);}
    70%{box-shadow:0 0 0 8px rgba(227,200,120,0);}
    100%{box-shadow:0 0 0 0 rgba(227,200,120,0);}
  }
  @media (prefers-reduced-motion: reduce){.flag-dot{animation:none;}}
  .btn-primary,.btn-secondary{
    padding:15px 34px;font-size:13px;letter-spacing:1.5px;text-transform:uppercase;
    border-radius:2px;transition:all .3s;cursor:pointer;display:inline-block;
  }
  .btn-primary{background:var(--gold);color:var(--black);border:1px solid var(--gold);font-weight:600;}
  .btn-primary:hover{background:var(--gold-bright);box-shadow:0 6px 24px rgba(201,168,76,0.3);}
  .btn-secondary{border:1px solid var(--line);color:var(--cream);}
  .btn-secondary:hover{border-color:var(--gold);color:var(--gold-bright);}

  /* ---------- DIVIDER ---------- */
  .divider{display:flex;align-items:center;justify-content:center;gap:14px;padding:0 6%;opacity:.5;}
  .divider .line{flex:1;height:1px;background:linear-gradient(90deg, transparent, var(--gold), transparent);max-width:140px;}
  .divider .mark{width:6px;height:6px;border-radius:50%;border:1px solid var(--gold);}

  /* ---------- SECTION SHARED ---------- */
  section{padding:100px 6%;position:relative;}
  .section-head{text-align:center;max-width:680px;margin:0 auto 64px;}
  .section-head .eyebrow{margin-bottom:14px;}
  .section-head h2{font-size:clamp(28px,4vw,42px);color:var(--cream);font-weight:600;line-height:1.2;}
  .section-head p{margin-top:16px;color:rgba(245,240,230,0.65);font-size:15px;line-height:1.7;}

  /* ---------- PROBLEM / SOLUTION ---------- */
  .ps-grid{
    display:grid;grid-template-columns:1fr 1fr;gap:48px;max-width:1040px;margin:0 auto;
  }
  .ps-card{
    border:1px solid var(--line);
    padding:40px 36px;
    border-radius:2px;
    background:linear-gradient(145deg, rgba(255,255,255,0.02), transparent);
  }
  .ps-card.solution{
    border:1.5px solid var(--gold);
    background:linear-gradient(145deg, rgba(201,168,76,0.10), rgba(201,168,76,0.02));
    box-shadow:0 0 50px rgba(201,168,76,0.12), inset 0 0 30px rgba(201,168,76,0.04);
    position:relative;
  }
  .ps-card.solution::before{
    content:"What We Do";
    position:absolute;top:-13px;right:28px;
    background:var(--gold);color:var(--black);
    font-size:10px;letter-spacing:1.5px;text-transform:uppercase;font-weight:700;
    padding:5px 14px;border-radius:20px;
  }
  .ps-card.solution h3{color:var(--gold-bright);font-size:24px;}
  .ps-card.solution .tag{color:var(--gold-bright);font-weight:600;}
  .ps-card.solution p{color:rgba(245,240,230,0.85);}
  @media (max-width:760px){ .ps-grid{grid-template-columns:1fr;} }

  /* ---------- PRODUCTS ---------- */
  .product-grid{
    display:grid;grid-template-columns:repeat(3,1fr);gap:28px;max-width:1100px;margin:0 auto;
  }
  .product-card{
    border:1px solid var(--line);
    padding:44px 30px;
    text-align:center;
    border-radius:2px;
    transition:transform .35s, border-color .35s;
    position:relative;
    background:linear-gradient(180deg, rgba(255,255,255,0.015), transparent);
  }
  .product-card:hover{transform:translateY(-6px);border-color:var(--gold);}
  .custom-badge{
    display:inline-flex;align-items:center;gap:6px;
    border:1px solid var(--gold);
    background:rgba(201,168,76,0.10);
    padding:5px 14px;border-radius:20px;
    font-size:10.5px;letter-spacing:1px;text-transform:uppercase;font-weight:600;
    color:var(--gold-bright);margin-bottom:18px;
  }
  .custom-badge .dot{width:5px;height:5px;border-radius:50%;background:var(--gold-bright);}
  .product-size{font-family:'Playfair Display',serif;font-size:34px;color:var(--gold-bright);font-weight:700;margin-bottom:6px;}
  .product-name{font-size:12px;letter-spacing:2px;text-transform:uppercase;color:var(--bronze);margin-bottom:24px;}
  .product-price{font-size:30px;font-weight:600;color:var(--cream);margin-bottom:6px;font-family:'Playfair Display',serif;}
  .product-price span{font-size:14px;color:rgba(245,240,230,0.5);font-family:'Inter',sans-serif;}
  .product-pack{font-size:13px;color:rgba(245,240,230,0.55);margin-bottom:26px;}
  .product-feat{font-size:13px;color:rgba(245,240,230,0.7);line-height:2;list-style:none;text-align:left;}
  .product-feat li{padding-left:18px;position:relative;}
  .product-feat li::before{content:"—";position:absolute;left:0;color:var(--gold);}
  @media (max-width:820px){ .product-grid{grid-template-columns:1fr;max-width:380px;} }

  /* ---------- WHY US ---------- */
  .why-grid{
    display:grid;grid-template-columns:repeat(4,1fr);gap:32px;max-width:1100px;margin:0 auto;
  }
  .why-item{text-align:center;padding:0 10px;}
  .why-icon{
    width:56px;height:56px;border:1px solid var(--gold);border-radius:50%;
    display:flex;align-items:center;justify-content:center;margin:0 auto 20px;
    color:var(--gold-bright);font-family:'Playfair Display',serif;font-size:20px;font-weight:700;
  }
  .why-item h3{font-size:16px;color:var(--cream);margin-bottom:10px;font-weight:600;}
  .why-item p{font-size:13.5px;color:rgba(245,240,230,0.6);line-height:1.7;}
  @media (max-width:900px){ .why-grid{grid-template-columns:repeat(2,1fr);} }
  @media (max-width:520px){ .why-grid{grid-template-columns:1fr;max-width:320px;} }

  /* ---------- CONTACT ---------- */
  .contact-wrap{
    max-width:920px;margin:0 auto;
    display:grid;grid-template-columns:1fr 1fr;gap:60px;
    align-items:start;
  }
  .contact-info h2{font-size:32px;color:var(--cream);margin-bottom:18px;font-weight:600;}
  .contact-info p{font-size:14.5px;color:rgba(245,240,230,0.65);line-height:1.8;margin-bottom:34px;}
  .contact-row{display:flex;gap:16px;margin-bottom:22px;align-items:flex-start;}
  .contact-row .ico{
    width:38px;height:38px;border:1px solid var(--line);border-radius:50%;
    display:flex;align-items:center;justify-content:center;flex-shrink:0;color:var(--gold);font-size:15px;
  }
  .contact-row .txt{font-size:14px;color:rgba(245,240,230,0.8);line-height:1.6;}
  .contact-row .txt .label{display:block;font-size:11px;letter-spacing:1.5px;text-transform:uppercase;color:var(--bronze);margin-bottom:4px;}

  form{display:flex;flex-direction:column;gap:18px;}
  form label{font-size:11px;letter-spacing:1.5px;text-transform:uppercase;color:var(--bronze);margin-bottom:6px;display:block;}
  form input,form select,form textarea{
    width:100%;background:rgba(255,255,255,0.03);border:1px solid var(--line);
    color:var(--cream);padding:13px 14px;font-family:'Inter',sans-serif;font-size:14px;
    border-radius:2px;outline:none;transition:border-color .3s;
  }
  form input:focus,form select:focus,form textarea:focus{border-color:var(--gold);}
  form select{appearance:none;cursor:pointer;}
  form textarea{resize:vertical;min-height:90px;}
  .form-submit{
    background:var(--gold);color:var(--black);border:none;
    padding:15px;font-size:13px;letter-spacing:1.5px;text-transform:uppercase;font-weight:600;
    border-radius:2px;cursor:pointer;transition:background .3s;margin-top:6px;
  }
  .form-submit:hover{background:var(--gold-bright);}
  .form-note{font-size:12px;color:rgba(245,240,230,0.45);margin-top:10px;text-align:center;}
  @media (max-width:760px){ .contact-wrap{grid-template-columns:1fr;gap:48px;} }

  /* ---------- FOOTER ---------- */
  footer{
    border-top:1px solid var(--line);
    padding:32px 6%;
    display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px;
  }
  footer .f-left{display:flex;align-items:center;gap:10px;font-size:13px;color:rgba(245,240,230,0.55);}
  footer .f-left img{height:24px;width:24px;border-radius:50%;}
  footer .f-right{display:flex;gap:22px;font-size:13px;}
  footer .f-right a{color:rgba(245,240,230,0.55);transition:color .3s;}
  footer .f-right a:hover{color:var(--gold-bright);}

  /* focus visibility */
  a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible, select:focus-visible{
    outline:2px solid var(--gold-bright); outline-offset:2px;
  }
</style>
</head>
<body>

<nav>
  <div class="nav-logo"><img src="logo.png" alt="JP FLOW"> JP FLOW</div>
  <div class="nav-links">
    <a href="#problem">About</a>
    <a href="#products">Products</a>
    <a href="#why">Why Us</a>
    <a href="#contact">Contact</a>
  </div>
  <a href="#contact" class="nav-cta">Get in Touch</a>
</nav>

<section class="hero">
  <div class="ring ring1"></div>
  <div class="ring ring2"></div>
  <div class="hero-inner">
    <img src="logo.png" alt="JP FLOW logo" class="hero-logo">
    <div class="eyebrow">Sukhlia, Indore</div>
    <h1>Your Brand, <em>Bottled.</em><br>Every Sip Is an Advertisement.</h1>
    <div class="custom-flag">
      <span class="flag-dot"></span> We Make 100% Custom-Branded Water Bottles
    </div>
    <p class="sub">JP FLOW replaces the generic water bottle on your tables with one carrying your own logo — turning every glass of water into a moving billboard for your business.</p>
    <div class="hero-ctas">
      <a href="#contact" class="btn-primary">Request a Sample</a>
      <a href="#products" class="btn-secondary">View Products</a>
    </div>
  </div>
</section>

<div class="divider"><div class="line"></div><div class="mark"></div><div class="line"></div></div>

<section id="problem">
  <div class="section-head">
    <div class="eyebrow">The Concept</div>
    <h2>Hydration Marketing</h2>
    <p>A simple shift in what's already on every table — built for cafes, restaurants, and hotels in Indore.</p>
  </div>
  <div class="ps-grid">
    <div class="ps-card">
      <span class="tag">The Problem</span>
      <h3>You're Advertising Someone Else</h3>
      <p>Right now, every bottle you serve carries a competitor's brand — Bisleri, Kinley, or a generic label. Your guests hold it through their entire meal, and you've paid for the privilege of promoting a brand that isn't yours.</p>
    </div>
    <div class="ps-card solution">
      <span class="tag">The Solution</span>
      <h3>Your Logo, In Their Hands</h3>
      <p>JP FLOW prints your logo on every bottle we deliver — at a lower cost than what you're paying now. Same water, same purity, but now it's your name on the table, not someone else's.</p>
    </div>
  </div>
</section>

<div class="divider"><div class="line"></div><div class="mark"></div><div class="line"></div></div>

<section id="products">
  <div class="section-head">
    <div class="eyebrow">Pricing</div>
    <h2>Three Sizes, One Standard of Purity</h2>
    <p>Custom label design included free with every order. Minimum order starts at just one pack.</p>
  </div>
  <div class="product-grid">
    <div class="product-card">
      <div class="custom-badge"><span class="dot"></span>Customizable</div>
      <div class="product-size">250<span style="font-size:16px;">ml</span></div>
      <div class="product-name">Compact</div>
      <div class="product-price">₹4<span>/ bottle</span></div>
      <div class="product-pack">40 bottles per pack</div>
      <ul class="product-feat">
        <li>Ideal for cafes & desks</li>
        <li>Custom label included</li>
        <li>FSSAI certified</li>
      </ul>
    </div>
    <div class="product-card">
      <div class="custom-badge"><span class="dot"></span>Customizable</div>
      <div class="product-size">500<span style="font-size:16px;">ml</span></div>
      <div class="product-name">Signature</div>
      <div class="product-price">₹6<span>/ bottle</span></div>
      <div class="product-pack">24 bottles per pack</div>
      <ul class="product-feat">
        <li>Our most ordered size</li>
        <li>Custom label included</li>
        <li>FSSAI certified</li>
      </ul>
    </div>
    <div class="product-card">
      <div class="custom-badge"><span class="dot"></span>Customizable</div>
      <div class="product-size">1<span style="font-size:16px;">L</span></div>
      <div class="product-name">Reserve</div>
      <div class="product-price">₹9<span>/ bottle</span></div>
      <div class="product-pack">9 bottles per pack</div>
      <ul class="product-feat">
        <li>Best for hotel rooms</li>
        <li>Custom label included</li>
        <li>FSSAI certified</li>
      </ul>
    </div>
  </div>
</section>

<div class="divider"><div class="line"></div><div class="mark"></div><div class="line"></div></div>

<section id="why">
  <div class="section-head">
    <div class="eyebrow">Why JP FLOW</div>
    <h2>Built on Proof, Not Promises</h2>
  </div>
  <div class="why-grid">
    <div class="why-item">
      <div class="why-icon">7</div>
      <h3>7-Stage Purification</h3>
      <p>RO, UV, and Ozonation — every batch, every day.</p>
    </div>
    <div class="why-item">
      <div class="why-icon">✓</div>
      <h3>FSSAI Certified</h3>
      <p>Fully compliant manufacturing, from Day 1.</p>
    </div>
    <div class="why-item">
      <div class="why-icon">NABL</div>
      <h3>Lab Verified Monthly</h3>
      <p>Independent testing at an accredited Indore lab.</p>
    </div>
    <div class="why-item">
      <div class="why-icon">1</div>
      <h3>Low Minimum Order</h3>
      <p>Start with just one pack — no large commitment.</p>
    </div>
  </div>
</section>

<div class="divider"><div class="line"></div><div class="mark"></div><div class="line"></div></div>

<section id="contact">
  <div class="contact-wrap">
    <div class="contact-info">
      <div class="eyebrow">Get Started</div>
      <h2>Put Your Brand on the Table</h2>
      <p>Tell us about your cafe, restaurant, or hotel — we'll prepare a free custom label mockup and send sample bottles to try.</p>

      <div class="contact-row">
        <div class="ico">@</div>
        <div class="txt"><span class="label">Email</span><a href="mailto:Jpflowindore@gmail.com">Jpflowindore@gmail.com</a></div>
      </div>
      <div class="contact-row">
        <div class="ico">☏</div>
        <div class="txt"><span class="label">Phone</span>+91 80855 46237 · +91 97536 06583</div>
      </div>
      <div class="contact-row">
        <div class="ico">⌖</div>
        <div class="txt"><span class="label">Address</span>247, Shyam Nagar NX-A, MR-10 Road,<br>Sukhlia, Indore (M.P.)</div>
      </div>
      <div class="contact-row">
        <div class="ico">◎</div>
        <div class="txt"><span class="label">Instagram</span>@jpflowindore</div>
      </div>
    </div>

    <form id="inquiryForm">
      <div>
        <label for="bname">Business Name</label>
        <input type="text" id="bname" name="bname" required placeholder="e.g. Cafe De Casa">
      </div>
      <div>
        <label for="btype">Business Type</label>
        <select id="btype" name="btype" required>
          <option value="">Select one</option>
          <option>Cafe</option>
          <option>Restaurant</option>
          <option>Hotel</option>
          <option>Corporate Office</option>
          <option>Other</option>
        </select>
      </div>
      <div>
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" name="phone" required placeholder="+91">
      </div>
      <div>
        <label for="msg">Message (Optional)</label>
        <textarea id="msg" name="msg" placeholder="Tell us about your monthly bottle requirement..."></textarea>
      </div>
      <button type="submit" class="form-submit">Request a Free Sample</button>
      <div class="form-note">We'll reach out within 24 hours with a custom label preview.</div>
    </form>
  </div>
</section>

<footer>
  <div class="f-left"><img src="logo.png" alt="JP FLOW"> JP FLOW — Where Hydration Meets Personalization</div>
  <div class="f-right">
    <a href="#problem">About</a>
    <a href="#products">Products</a>
    <a href="#contact">Contact</a>
  </div>
</footer>

<script>
document.getElementById('inquiryForm').addEventListener('submit', function(e){
  e.preventDefault();
  const name = document.getElementById('bname').value;
  const phone = document.getElementById('phone').value;
  const type = document.getElementById('btype').value;
  const msg = document.getElementById('msg').value;
  const text = `Hi JP FLOW, I'd like to request a sample.%0A%0ABusiness Name: ${name}%0AType: ${type}%0APhone: ${phone}%0AMessage: ${msg}`;
  window.open(`https://wa.me/918085546237?text=${text}`, '_blank');
});
</script>

</body>
</html>
