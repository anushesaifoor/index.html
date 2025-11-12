<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Artify — Tools that power artists</title>
  <meta name="description" content="Artify gives artists the tools to showcase, sell, and manage their careers. Marketplace, blogs, forums, analytics, and finance tools in one place." />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns=%27http://www.w3.org/2000/svg%27 viewBox=%270 0 100 100%27%3E%3Ccircle cx=%2750%27 cy=%2750%27 r=%2748%27 fill=%27%23000%27/%3E%3Ctext x=%2750%25%27 y=%2758%25%27 font-size=%2755%27 text-anchor=%27middle%27 fill=%27%23fff%27 font-family=%27system-ui%2C -apple-system%2C Segoe UI%2C Roboto%2C Helvetica%2C Arial%2C sans-serif%27%3EA%3C/text%3E%3C/svg%3E" />
  <meta property="og:title" content="Artify — Tools that power artists" />
  <meta property="og:description" content="Showcase. Sell. Track. Connect. One platform for your art career." />
  <meta property="og:type" content="website" />
  <meta property="og:image" content="https://example.com/og-artify.png" />
  <meta name="theme-color" content="#0b0b0c" />
  <style>
    :root{
      --bg:#0b0b0c; --text:#e7e7ea; --muted:#a9a9b3; --brand:#8f5cff; --brand-2:#24e1b9;
      --card:#111114; --stroke:#2a2a33; --ok:#24e1b9; --warn:#ffd166;
      --shadow: 0 10px 25px rgba(0,0,0,.35), 0 2px 8px rgba(0,0,0,.35);
      color-scheme: dark light;
    }
    @media (prefers-color-scheme: light){
      :root{ --bg:#ffffff; --text:#1b1b1f; --muted:#555; --card:#f7f7fb; --stroke:#dedee6; --shadow: 0 8px 18px rgba(0,0,0,.08), 0 1px 3px rgba(0,0,0,.06); }
    }
    *{ box-sizing: border-box }
    html,body{ height:100% }
    body{
      margin:0; font: 16px/1.5 system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif;
      background: radial-gradient(1200px 600px at 10% -10%, rgba(143,92,255,.18), transparent 60%),
                  radial-gradient(900px 500px at 100% 10%, rgba(36,225,185,.14), transparent 60%),
                  var(--bg);
      color:var(--text);
    }
    .container{ width:min(1120px, 92vw); margin-inline:auto }
    a{ color:inherit; text-decoration:none }
    .btn{
      display:inline-flex; align-items:center; gap:.5rem; padding:.85rem 1.1rem; border-radius:.8rem;
      border:1px solid var(--stroke); background:linear-gradient(180deg, rgba(255,255,255,.06), rgba(255,255,255,0));
      box-shadow: var(--shadow); transition:.2s transform ease, .2s box-shadow ease, .2s background ease;
      will-change: transform;
    }
    .btn:hover{ transform: translateY(-1px) scale(1.01) }
    .btn.primary{ background: linear-gradient(90deg, var(--brand), var(--brand-2)); color:#0a0a0a; border:0; font-weight:700 }
    .btn.ghost{ background: transparent }
    .tag{ font-size:.75rem; padding:.25rem .6rem; border:1px solid var(--stroke); border-radius:999px; color:var(--muted) }
    nav{ position:sticky; top:0; backdrop-filter:saturate(140%) blur(8px); background: color-mix(in oklab, var(--bg), transparent 35%); border-bottom:1px solid var(--stroke); z-index:40 }
    nav .row{ display:flex; align-items:center; justify-content:space-between; min-height:64px }
    .nav-links{ display:flex; gap:1.2rem; align-items:center }
    .logo{ display:flex; align-items:center; gap:.6rem; font-weight:800; letter-spacing:.2px }
    .logo .mark{ width:28px; height:28px; border-radius:8px; background: conic-gradient(from 180deg, var(--brand), var(--brand-2)); box-shadow: var(--shadow) }
    .hero{ padding: clamp(2rem, 5vw, 4rem) 0 2rem; text-align:center }
    .hero h1{
      font-size:clamp(2.2rem, 5vw + .5rem, 4rem); line-height:1.05; margin:0 0 .8rem;
      letter-spacing:-.02em;
    }
    .hero p{ margin:0 auto 1.2rem; max-width:60ch; color:var(--muted) }
    .hero .cta{ display:flex; gap:.8rem; justify-content:center; flex-wrap:wrap; margin-top:1rem }
    .grid{ display:grid; gap:1rem }
    .features{ padding: 2rem 0 }
    .features .grid{ grid-template-columns: repeat(auto-fit, minmax(240px, 1fr)) }
    .card{
      background:var(--card); border:1px solid var(--stroke); border-radius:1rem; padding:1rem; box-shadow: var(--shadow);
    }
    .card h3{ margin:.2rem 0 .2rem; font-size:1.05rem }
    .card p{ margin:.3rem 0 0; color:var(--muted) }
    .icon{ width:28px; height:28px }
    .split{ display:grid; gap:1.2rem; grid-template-columns: 1.2fr 1fr; align-items:center }
    @media (max-width: 900px){ .split{ grid-template-columns: 1fr } }
    .shot{
      aspect-ratio: 16/10; width:100%; border:1px dashed var(--stroke); border-radius:1rem; display:grid; place-items:center; color:var(--muted);
      background:
        linear-gradient(90deg, color-mix(in oklab, var(--brand) 20%, transparent), transparent 60%),
        linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,0));
    }
    .section{ padding: 2.5rem 0 }
    .section h2{ margin:0 0 .6rem; font-size: clamp(1.4rem, 2.2vw + .5rem, 2.2rem) }
    .muted{ color:var(--muted) }

    .timeline{ position:relative; padding-left:1.25rem }
    .timeline::before{ content:""; position:absolute; inset:0 auto 0 .4rem; width:2px; background:var(--stroke); border-radius:2px }
    .t-item{ position:relative; padding:.5rem 0 .5rem 1rem }
    .t-item::before{ content:""; position:absolute; left:-.25rem; top:.9rem; width:.7rem; height:.7rem; border-radius:50%; background:var(--brand) }
    .pricing .grid{ grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)) }
    .price-card .price{ font-size:2rem; font-weight:800 }
    .price-card ul{ margin:.6rem 0 0; padding:0; list-style:none }
    .price-card li{ padding:.35rem 0; display:flex; gap:.5rem; align-items:baseline }
    .check{ width:1rem; height:1rem; border-radius:3px; background:var(--ok) }

    .faq details{ border:1px solid var(--stroke); border-radius:.8rem; padding:.9rem 1rem; background:var(--card) }
    .faq details + details{ margin-top:.7rem }
    footer{ border-top:1px solid var(--stroke); padding:1.5rem 0; color:var(--muted) }

    .kbd{ font: .9rem ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; padding:.15rem .35rem; border-radius:.4rem; background: var(--card); border:1px solid var(--stroke) }

    .sr-only{ position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); white-space:nowrap; border:0 }
    .skip{ position:absolute; left:0; top:-40px; background:var(--brand); color:#000; padding:.5rem .75rem; border-radius:.5rem }
    .skip:focus{ top:10px }
  </style>
  <script>
    // Smooth scroll for internal anchors
    addEventListener('DOMContentLoaded', () => {
      document.querySelectorAll('a[href^="#"]').forEach(a => {
        a.addEventListener('click', e => {
          const id = a.getAttribute('href').slice(1);
          const el = document.getElementById(id);
          if (el){ e.preventDefault(); el.scrollIntoView({behavior:'smooth', block:'start'}); }
        });
      });

      // Simple email capture with local validation
      const form = document.getElementById('waitlist-form');
      form?.addEventListener('submit', e => {
        e.preventDefault();
        const email = form.querySelector('input[type="email"]');
        const plan = form.querySelector('select');
        const out = document.getElementById('form-out');
        const ok = email.checkValidity();
        if(!ok){ email.reportValidity(); return; }
        localStorage.setItem('artify_waitlist', JSON.stringify({ email: email.value.trim(), plan: plan.value, ts: Date.now() }));
        out.textContent = "Confirmed. We’ll notify you when your account is ready.";
        form.reset();
      });
    });
  </script>
  <!-- Structured data -->
  <script type="application/ld+json">
  {
    "@context":"https://schema.org",
    "@type":"WebApplication",
    "name":"Artify",
    "applicationCategory":"Multimedia",
    "description":"Platform for artists to showcase, sell, and manage their careers.",
    "offers":{
      "@type":"Offer",
      "price":"0",
      "priceCurrency":"USD"
    },
    "operatingSystem":"Any",
    "creator":{
      "@type":"Organization",
      "name":"Artify"
    },
    "url":"https://artify.example"
  }
  </script>
</head>
<body>
  <a href="#main" class="skip">Skip to content</a>

  <!-- NAV -->
  <nav aria-label="Primary">
    <div class="container row">
      <div class="logo">
        <span class="mark" aria-hidden="true"></span>
        <span>Artify</span>
      </div>
      <div class="nav-links">
        <a href="#features">Features</a>
        <a href="#story">Story</a>
        <a href="#pricing">Pricing</a>
        <a href="#faq">FAQ</a>
        <a class="btn ghost" href="#join">Join</a>
      </div>
    </div>
  </nav>

  <main id="main">
    <!-- HERO -->
    <header class="hero container">
      <p class="tag" aria-label="Model">Built by artists. Scales like software.</p>
      <h1>Ship your art career like a product.</h1>
      <p>Artify gives you a clean stack: showcase, marketplace, blog, forum, analytics, and finance tools. Fewer tabs. More output.</p>
      <div class="cta">
        <a class="btn primary" href="#join" aria-label="Get started">Get started free</a>
        <a class="btn" href="#features" aria-label="See features">See how it works</a>
      </div>
      <div class="section split" style="margin-top:1.5rem">
        <div class="shot" role="img" aria-label="Dashboard preview">
          <span>Dashboard preview placeholder</span>
        </div>
        <div class="card">
          <h2>What you get</h2>
          <ul>
            <li>Showcase pages with fast media</li>
            <li>Marketplace with secure checkout</li>
            <li>Blog and story tooling</li>
            <li>Community forum access</li>
            <li>Sales analytics and finance tracking</li>
            <li>Custom sites and priority support on paid plans</li>
          </ul>
          <p class="muted" style="margin-top:.6rem">No gimmicks. Just the stack artists asked for.</p>
        </div>
      </div>
    </header>

    <!-- FEATURES -->
    <section id="features" class="features container section" aria-labelledby="features-h">
      <h2 id="features-h">Core features</h2>
      <p class="muted">Pick the levers that move your work. Ignore the rest.</p>
      <div class="grid" style="margin-top:.8rem">
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M4 5h16v14H4z" stroke="currentColor" stroke-width="1.5"/><path d="M4 9h16" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Showcase</h3>
          <p>Responsive galleries, video, and high-res zoom without the bloat.</p>
        </article>
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M6 6h12v12H6z" stroke="currentColor" stroke-width="1.5"/><path d="M9 12h6M9 15h6M9 9h6" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Marketplace</h3>
          <p>Sell originals, prints, and commissions. Inventory, variants, taxes.</p>
        </article>
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M4 5h16v6H4zM4 13h10v6H4z" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Blog</h3>
          <p>Publish process, drop notes, or long-form. Own your narrative.</p>
        </article>
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><circle cx="7" cy="7" r="3" stroke="currentColor" stroke-width="1.5"/><circle cx="17" cy="17" r="3" stroke="currentColor" stroke-width="1.5"/><path d="M10 10l4 4" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Forum</h3>
          <p>Peer feedback, collabs, and sane critique loops.</p>
        </article>
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M4 18c4-8 12-8 16 0" stroke="currentColor" stroke-width="1.5"/><circle cx="12" cy="8" r="2" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Analytics</h3>
          <p>Sales, traffic, and subscriber growth without creepy tracking.</p>
        </article>
        <article class="card">
          <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><path d="M5 12h14M5 16h10M5 8h8" stroke="currentColor" stroke-width="1.5"/><path d="M15 4l4 4-4 4" stroke="currentColor" stroke-width="1.5"/></svg>
          <h3>Finance tools</h3>
          <p>Payouts, fees, and taxes tracked. Stop guessing. Start planning.</p>
        </article>
      </div>
    </section>

    <!-- STORY / EVOLUTION -->
    <section id="story" class="container section" aria-labelledby="story-h">
      <div class="split">
        <div>
          <h2 id="story-h">From frustration to platform</h2>
          <p class="muted">Founded in 2020 by artists and technologists. Started as a simple upload-and-profile site. Grew into a full stack as the community demanded more.</p>
          <div class="timeline" aria-label="Artify timeline">
            <div class="t-item">
              <strong>2020:</strong> Launch. Upload art and build a profile. Early community forms.
            </div>
            <div class="t-item">
              <strong>2021:</strong> Marketplace opens. Artists start selling originals and prints.
            </div>
            <div class="t-item">
              <strong>2022:</strong> Blog and forum ship. Stories and critique tighten the loop.
            </div>
            <div class="t-item">
              <strong>2023–2025:</strong> Finance tools, analytics, and custom sites roll out. Priority support for pros.
            </div>
          </div>
        </div>
        <div class="card">
          <h3>Why it works</h3>
          <ul>
            <li>One platform. Less overhead.</li>
            <li>Owning your audience beats chasing algorithms.</li>
            <li>Data you can act on. No noise.</li>
            <li>Community that ships work, not drama.</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- PRICING -->
    <section id="pricing" class="container section pricing" aria-labelledby="pricing-h">
      <h2 id="pricing-h">Pricing that follows your growth</h2>
      <p class="muted">Start free. Upgrade when revenue justifies it.</p>
      <div class="grid" style="margin-top:.8rem">
        <article class="card price-card" aria-labelledby="free-h">
          <h3 id="free-h">Free</h3>
          <p class="price">$0</p>
          <p class="muted">Solid basics to start.</p>
          <ul>
            <li><span class="check"></span> Showcase portfolio</li>
            <li><span class="check"></span> Blog</li>
            <li><span class="check"></span> Forum access</li>
            <li><span class="check"></span> Basic analytics</li>
          </ul>
          <a class="btn" href="#join">Create free account</a>
        </article>

        <article class="card price-card" aria-labelledby="pro-h">
          <h3 id="pro-h">Pro</h3>
          <p class="price">$19<span class="muted" style="font-size:1rem">/mo</span></p>
          <p class="muted">For active sellers.</p>
          <ul>
            <li><span class="check"></span> Everything in Free</li>
            <li><span class="check"></span> Sell in marketplace</li>
            <li><span class="check"></span> Commission requests</li>
            <li><span class="check"></span> Advanced analytics</li>
          </ul>
          <a class="btn primary" href="#join">Start Pro trial</a>
        </article>

        <article class="card price-card" aria-labelledby="studio-h">
          <h3 id="studio-h">Studio</h3>
          <p class="price">$49<span class="muted" style="font-size:1rem">/mo</span></p>
          <p class="muted">For career focus.</p>
          <ul>
            <li><span class="check"></span> Everything in Pro</li>
            <li><span class="check"></span> Custom website builder</li>
            <li><span class="check"></span> Team members</li>
            <li><span class="check"></span> Priority support</li>
          </ul>
          <a class="btn" href="#join">Talk to sales</a>
        </article>
      </div>
    </section>

    <!-- SOCIAL PROOF / COMMUNITY -->
    <section class="container section" aria-labelledby="community-h">
      <h2 id="community-h">A community that moves work forward</h2>
      <p class="muted">Forum prompts, critique threads, and collabs that end in shipped pieces.</p>
      <div class="grid" style="grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); margin-top:1rem">
        <div class="card">
          <strong>“Artify trimmed my stack from 6 tools to 1.”</strong>
          <p class="muted">Illustrator • Berlin</p>
        </div>
        <div class="card">
          <strong>“Sales went up when buyers could follow my process.”</strong>
          <p class="muted">Painter • Austin</p>
        </div>
        <div class="card">
          <strong>“I stopped guessing taxes.”</strong>
          <p class="muted">Sculptor • Tokyo</p>
        </div>
      </div>
    </section>

    <!-- JOIN -->
    <section id="join" class="container section" aria-labelledby="join-h">
      <div class="split">
        <div>
          <h2 id="join-h">Get started in minutes</h2>
          <p class="muted">Create your profile. Import work. Publish your first drop. Upgrade when you need to sell.</p>
          <ul>
            <li>Sign up free. No card required.</li>
            <li>Import from your drive or link media.</li>
            <li>Publish a clean portfolio with one URL.</li>
          </ul>
        </div>
        <form id="waitlist-form" class="card" aria-label="Join form">
          <label for="email">Email</label>
          <input id="email" name="email" type="email" required placeholder="you@studio.com"
                 style="margin:.4rem 0 .8rem; width:100%; padding:.8rem; border-radius:.6rem; border:1px solid var(--stroke); background:var(--bg); color:var(--text)" />
          <label for="plan">Plan</label>
          <select id="plan" name="plan" style="margin:.4rem 0 1rem; width:100%; padding:.7rem; border-radius:.6rem; border:1px solid var(--stroke); background:var(--bg); color:var(--text)">
            <option>Free</option>
            <option>Pro</option>
            <option>Studio</option>
          </select>
          <button class="btn primary" type="submit">Create my account</button>
          <p id="form-out" class="muted" role="status" style="margin-top:.7rem"></p>
          <p class="muted" style="font-size:.85rem">By continuing you agree to the Terms and Privacy Policy.</p>
        </form>
      </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="container section faq" aria-labelledby="faq-h">
      <h2 id="faq-h">FAQ</h2>
      <details>
        <summary><strong>How does the freemium model work?</strong></summary>
        <p>You start on Free. When you want to sell, upgrade to Pro. If you need custom sites or team access, pick Studio.</p>
      </details>
      <details>
        <summary><strong>Can I bring my own domain?</strong></summary>
        <p>Yes on paid plans. Map your domain in settings. SSL handled automatically.</p>
      </details>
      <details>
        <summary><strong>How are payments handled?</strong></summary>
        <p>Secure checkout with standard processors. Payouts and fees visible in Finance.</p>
      </details>
      <details>
        <summary><strong>Do I own my content?</strong></summary>
        <p>Yes. You keep rights to your work. We provide hosting and tooling.</p>
      </details>
    </section>
  </main>

  <footer>
    <div class="container" style="display:grid; gap:1rem; grid-template-columns: 1fr auto; align-items:center">
      <p>©️ <span id="y"></span> Artify. All rights reserved.</p>
      <div style="display:flex; gap:1rem">
        <a href="#privacy">Privacy</a>
        <a href="#terms">Terms</a>
        <span class="kbd">⌘</span><span class="muted">+K for quick find</span>
      </div>
    </div>
  </footer>

  <script>
    // Footer year
    document.getElementById('y').textContent = new Date().getFullYear();

    // Minimal command palette
    (function(){
      const overlay = document.createElement('div');
      overlay.style.cssText = "position:fixed; inset:0; background:rgba(0,0,0,.4); display:none; place-items:center; z-index:1000";
      overlay.setAttribute('aria-hidden','true');
      overlay.innerHTML = `
        <div role="dialog" aria-modal="true" aria-label="Quick find" class="card" style="width:min(680px,92vw); padding:0">
          <div style="padding:.8rem 1rem; border-bottom:1px solid var(--stroke)">Quick find</div>
          <input aria-label="Search" autofocus style="width:100%; padding:1rem; border:0; outline:none; background:var(--bg); color:var(--text)" placeholder="Type: features, pricing, join, story" />
          <div id="k-results" style="max-height:40vh; overflow:auto; padding:.5rem 1rem"></div>
        </div>`;
      document.body.appendChild(overlay);

      const map = [
        {k:"features", id:"features"},
        {k:"pricing", id:"pricing"},
        {k:"join", id:"join"},
        {k:"story", id:"story"},
        {k:"faq", id:"faq"}
      ];

      function openK(){ overlay.style.display = "grid"; overlay.querySelector('input').focus(); }
      function closeK(){ overlay.style.display = "none"; }

      document.addEventListener('keydown', e=>{
        if((e.metaKey || e.ctrlKey) && e.key.toLowerCase()==='k'){ e.preventDefault(); openK(); }
        if(e.key==='Escape') closeK();
      });

      overlay.addEventListener('click', e=>{ if(e.target===overlay) closeK(); });

      const input = overlay.querySelector('input');
      const results = overlay.querySelector('#k-results');
      input.addEventListener('input', ()=>{
        const q = input.value.toLowerCase().trim();
        results.innerHTML = "";
        map.filter(x=> x.k.includes(q)).forEach(x=>{
          const a = document.createElement('a');
          a.href = '#'+x.id;
          a.textContent = x.k;
          a.className = 'btn ghost';
          a.style.margin = '.3rem .2rem';
          a.addEventListener('click', ()=> closeK());
          results.appendChild(a);
        });
      });
    })();
  </script>
</body>
</html>
