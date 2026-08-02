<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>بانگو | بازارچه محلی آنلاین</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@400;500;700;800;900&family=IBM+Plex+Mono:wght@500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#1c1410;
    --cork:#2c2019;
    --cork-2:#241a14;
    --paper:#f7eedd;
    --paper-2:#efe3cc;
    --bango:#ff6b35;
    --bango-dim:#c9522a;
    --pin:#e63946;
    --ash:#c9beac;
    --ash-dim:#8f8574;
    --line: rgba(247,238,221,0.12);
  }

  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}

  body{
    margin:0;
    background:var(--ink);
    color:var(--ash);
    font-family:'Vazirmatn', system-ui, sans-serif;
    line-height:1.7;
    overflow-x:hidden;
  }

  .mono{
    font-family:'IBM Plex Mono', monospace;
    letter-spacing:0.02em;
  }

  a{color:inherit;}

  /* ---------- top bar ---------- */
  .topbar{
    display:flex;
    align-items:center;
    justify-content:space-between;
    max-width:1080px;
    margin:0 auto;
    padding:28px 24px 0;
  }
  .brand{
    display:flex;
    align-items:center;
    gap:10px;
    font-weight:900;
    font-size:22px;
    color:var(--paper);
  }
  .brand-mark{
    width:34px;height:34px;
    border-radius:9px;
    background:linear-gradient(155deg, var(--bango), var(--pin));
    display:flex;align-items:center;justify-content:center;
    font-family:'IBM Plex Mono',monospace;
    font-weight:600;
    color:var(--ink);
    font-size:16px;
    transform:rotate(-6deg);
  }
  .badge-soon{
    font-family:'IBM Plex Mono', monospace;
    font-size:12px;
    font-weight:600;
    color:var(--bango);
    border:1px solid var(--bango-dim);
    background:rgba(255,107,53,0.08);
    padding:6px 14px;
    border-radius:999px;
    letter-spacing:0.04em;
  }

  /* ---------- hero ---------- */
  .hero{
    max-width:1080px;
    margin:0 auto;
    padding:64px 24px 40px;
    display:grid;
    grid-template-columns:1.05fr 1fr;
    gap:56px;
    align-items:center;
  }
  .eyebrow{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px;
    color:var(--bango);
    letter-spacing:0.08em;
    margin:0 0 18px;
  }
  .eyebrow::before{content:"« ";}
  .eyebrow::after{content:" »";}

  h1{
    font-size:clamp(34px, 5vw, 52px);
    line-height:1.25;
    font-weight:800;
    color:var(--paper);
    margin:0 0 22px;
  }
  h1 span{color:var(--bango);}

  .lede{
    font-size:17px;
    color:var(--ash);
    max-width:46ch;
    margin:0 0 30px;
  }

  .cta-row{display:flex;gap:14px;flex-wrap:wrap;align-items:center;}
  .cta-primary{
    background:var(--bango);
    color:var(--ink);
    font-weight:700;
    font-size:15px;
    padding:14px 26px;
    border-radius:10px;
    text-decoration:none;
    display:inline-block;
    box-shadow:0 8px 20px -8px rgba(255,107,53,0.55);
  }
  .cta-secondary{
    font-size:14px;
    color:var(--ash-dim);
    text-decoration:none;
    border-bottom:1px dashed var(--ash-dim);
    padding-bottom:2px;
  }

  /* ---------- cork board ---------- */
  .board{
    position:relative;
    background:
      radial-gradient(ellipse at 30% 20%, rgba(255,255,255,0.04), transparent 60%),
      var(--cork);
    border-radius:18px;
    padding:38px 24px;
    min-height:340px;
    border:1px solid var(--line);
  }
  .board::before{
    content:"";
    position:absolute; inset:10px;
    border:1px dashed rgba(247,238,221,0.08);
    border-radius:12px;
    pointer-events:none;
  }
  .note{
    background:var(--paper);
    color:#3a2e22;
    border-radius:4px;
    padding:16px 16px 14px;
    width:78%;
    box-shadow:0 14px 24px -10px rgba(0,0,0,0.55);
    position:relative;
    transition:transform .25s ease;
  }
  .note:hover{transform:rotate(0deg) translateY(-2px) !important;}
  .note .pin{
    position:absolute; top:-9px; right:22px;
    width:16px;height:16px;border-radius:50%;
    background:radial-gradient(circle at 35% 30%, #ff8a68, var(--pin) 70%);
    box-shadow:0 3px 5px rgba(0,0,0,0.45);
  }
  .note .title{font-weight:700;font-size:15px;margin:0 0 6px;color:#241a14;}
  .note .price{
    font-family:'IBM Plex Mono', monospace;
    font-size:13px;
    color:var(--bango-dim);
    font-weight:600;
  }
  .note-1{transform:rotate(-4deg); margin-inline-start:0;}
  .note-2{transform:rotate(3deg); margin-inline-start:16%; margin-top:-26px;}
  .note-3{transform:rotate(-2deg); margin-inline-start:8%; margin-top:-18px;}

  /* ---------- categories ---------- */
  .cats-wrap{
    max-width:1080px;
    margin:10px auto 0;
    padding:0 24px 56px;
    border-bottom:1px solid var(--line);
  }
  .cats{
    display:flex;
    flex-wrap:wrap;
    gap:10px;
    justify-content:center;
    padding-bottom:52px;
  }
  .chip{
    font-size:13.5px;
    color:var(--ash);
    background:var(--cork);
    border:1px solid var(--line);
    padding:9px 18px;
    border-radius:999px;
  }
  .chip b{color:var(--paper); font-weight:600;}

  /* ---------- features ---------- */
  .features{
    max-width:1080px;
    margin:0 auto;
    padding:56px 24px 64px;
  }
  .features h2{
    font-size:26px;
    color:var(--paper);
    font-weight:800;
    text-align:center;
    margin:0 0 40px;
  }
  .feat-grid{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:16px;
  }
  .feat-card{
    background:var(--cork);
    border:1px solid var(--line);
    border-radius:14px;
    padding:22px 18px;
  }
  .feat-card .tag{
    font-family:'IBM Plex Mono', monospace;
    font-size:11px;
    color:var(--bango);
    letter-spacing:0.06em;
    display:block;
    margin-bottom:12px;
  }
  .feat-card h3{
    font-size:16px;
    color:var(--paper);
    margin:0 0 8px;
    font-weight:700;
  }
  .feat-card p{
    font-size:13.5px;
    color:var(--ash-dim);
    margin:0;
  }

  /* ---------- footer ---------- */
  footer{
    max-width:1080px;
    margin:0 auto;
    padding:36px 24px 48px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap:16px;
    color:var(--ash-dim);
    font-size:13px;
    border-top:1px solid var(--line);
  }

  @media (max-width:820px){
    .hero{grid-template-columns:1fr; padding-top:44px;}
    .board{order:-1;}
    .feat-grid{grid-template-columns:1fr 1fr;}
    .note{width:88%;}
  }
  @media (max-width:520px){
    .feat-grid{grid-template-columns:1fr;}
    .lede{max-width:none;}
  }

  @media (prefers-reduced-motion: reduce){
    *{transition:none !important;}
  }
</style>
</head>
<body>

  <div class="topbar">
    <div class="brand">
      <span class="brand-mark">ب</span>
      بانگو
    </div>
    <span class="badge-soon">به‌زودی</span>
  </div>

  <section class="hero">
    <div>
      <p class="eyebrow">بازارچه محلی آنلاین</p>
      <h1>هرچی نیاز داری،<br>همین <span>دور و ورته</span></h1>
      <p class="lede">
        بانگو جایی‌ برای خرید و فروش محلیه؛ ملک، خودرو، کالای دیجیتال، لوازم خونه و خیلی چیزای دیگه.
        مستقیم با فروشنده حرف بزن، بدون واسطه و بدون رد و بدل کردن شماره.
      </p>
      <div class="cta-row">
        <a class="cta-primary" href="#features">امکانات بانگو</a>
        <a class="cta-secondary" href="mailto:hello@bango.app">تماس با ما</a>
      </div>
    </div>

    <div class="board">
      <div class="note note-1">
        <span class="pin"></span>
        <p class="title">آپارتمان ۸۰ متری — تهران</p>
        <p class="price">۲٬۵۰۰٬۰۰۰٬۰۰۰ تومان</p>
      </div>
      <div class="note note-2">
        <span class="pin"></span>
        <p class="title">پژو ۲۰۶ مدل ۱۴۰۰</p>
        <p class="price">۸۵۰٬۰۰۰٬۰۰۰ تومان</p>
      </div>
      <div class="note note-3">
        <span class="pin"></span>
        <p class="title">دوچرخه دست دوم</p>
        <p class="price">۱٬۲۰۰٬۰۰۰ تومان</p>
      </div>
    </div>
  </section>

  <div class="cats-wrap">
    <div class="cats">
      <span class="chip"><b>املاک</b></span>
      <span class="chip"><b>خودرو</b></span>
      <span class="chip"><b>کالای دیجیتال</b></span>
      <span class="chip"><b>لوازم خانه</b></span>
      <span class="chip"><b>استخدام</b></span>
      <span class="chip"><b>خدمات</b></span>
    </div>
  </div>

  <section class="features" id="features">
    <h2>چیزهایی که بانگو رو متفاوت می‌کنه</h2>
    <div class="feat-grid">
      <div class="feat-card">
        <span class="tag mono">گفتگو</span>
        <h3>چت مستقیم</h3>
        <p>همون‌جای اپ با فروشنده حرف بزن، بدون رد و بدل کردن شماره تلفن.</p>
      </div>
      <div class="feat-card">
        <span class="tag mono">مکان</span>
        <h3>نزدیک من</h3>
        <p>آگهی‌های اطراف خودت رو روی نقشه پیدا کن، دقیق و سریع.</p>
      </div>
      <div class="feat-card">
        <span class="tag mono">ثبت آگهی</span>
        <h3>چند ثانیه‌ای</h3>
        <p>عکس بگیر، قیمت بذار، منتشر کن — بدون فرم‌های طولانی.</p>
      </div>
      <div class="feat-card">
        <span class="tag mono">دیده‌شدن</span>
        <h3>ویژه‌سازی آگهی</h3>
        <p>آگهیت رو بالای لیست ببر تا سریع‌تر فروش بره.</p>
      </div>
    </div>
  </section>

  <footer>
    <span>بانگو در حال ساخته شدنه — به‌زودی می‌بینیمت.</span>
    <span>© ۱۴۰۵ Bango</span>
  </footer>

</body>
</html>
