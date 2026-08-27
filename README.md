<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<style>
  @import url('https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700&display=swap');

  :root {
    --ink: #161A2E;
    --ivory: #FAFAF8;
    --line: #E7E5DE;
    --teal: #2FD4C4;
    --muted: #8A8F9E;
    --card: #FFFFFF;
  }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    font-family: 'Sora', sans-serif;
    background: var(--ivory);
    color: var(--ink);
  }
  a { text-decoration: none; color: inherit; }

  /* ============ HEADER ============ */
  .topstrip {
    background: var(--ink);
    color: var(--ivory);
    text-align: center;
    font-size: 12px;
    letter-spacing: 0.06em;
    padding: 8px 12px;
  }
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 18px 40px;
    border-bottom: 1px solid var(--line);
    background: var(--ivory);
    position: sticky;
    top: 0;
    z-index: 20;
  }
  .logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-weight: 700;
    font-size: 22px;
    letter-spacing: 0.5px;
  }
  nav {
    display: flex;
    gap: 30px;
    font-size: 14px;
    font-weight: 500;
  }
  nav a { position: relative; padding-bottom: 4px; }
  nav a:hover { color: var(--teal); }
  .header-icons {
    display: flex;
    align-items: center;
    gap: 20px;
  }
  .icon-btn {
    background: none;
    border: none;
    cursor: pointer;
    color: var(--ink);
    display: flex;
    align-items: center;
  }
  .cart-count {
    background: var(--teal);
    color: var(--ink);
    font-size: 10px;
    font-weight: 700;
    border-radius: 999px;
    width: 16px;
    height: 16px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-left: -10px;
    margin-top: -14px;
  }
  @media (max-width: 860px) {
    header { padding: 14px 20px; }
    nav { display: none; }
  }

  /* ============ MODELO / HOME ============ */
  .hero {
    display: grid;
    grid-template-columns: 1.1fr 0.9fr;
    align-items: center;
    gap: 40px;
    max-width: 1200px;
    margin: 0 auto;
    padding: 70px 40px;
  }
  @media (max-width: 860px) {
    .hero { grid-template-columns: 1fr; padding: 40px 20px; text-align: center; }
    .hero-art { order: -1; }
  }
  .eyebrow {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 11px;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--teal);
    background: rgba(47,212,196,0.1);
    padding: 6px 12px;
    border-radius: 999px;
    margin-bottom: 20px;
  }
  .hero h1 {
    font-size: clamp(32px, 4.5vw, 50px);
    line-height: 1.08;
    margin: 0 0 18px;
    font-weight: 700;
  }
  .hero p {
    color: var(--muted);
    font-size: 16px;
    max-width: 46ch;
    margin-bottom: 28px;
  }
  @media (max-width: 860px) { .hero p { margin-left: auto; margin-right: auto; } }
  .btn-primary {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--ink);
    color: var(--ivory);
    font-weight: 600;
    font-size: 14px;
    padding: 14px 26px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
  }
  .btn-primary .dot { width: 6px; height: 6px; border-radius: 50%; background: var(--teal); }

  .hero-art {
    background: var(--ink);
    border-radius: 16px;
    aspect-ratio: 4/3.2;
    display: grid;
    place-items: center;
    position: relative;
    overflow: hidden;
  }
  .hero-art svg { width: 46%; }
  .hero-art::after {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 70% 20%, rgba(47,212,196,0.25), transparent 55%);
  }

  section.block { max-width: 1200px; margin: 0 auto; padding: 10px 40px 60px; }
  @media (max-width: 860px) { section.block { padding: 10px 20px 44px; } }
  .block-head {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    margin-bottom: 24px;
  }
  .block-head h2 { font-size: 22px; margin: 0; }
  .block-head a { font-size: 13px; color: var(--teal); font-weight: 600; }

  .cat-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 16px;
  }
  @media (max-width: 860px) { .cat-grid { grid-template-columns: repeat(2, 1fr); } }
  .cat-card {
    background: var(--card);
    border: 1px solid var(--line);
    border-radius: 12px;
    padding: 26px 18px;
    text-align: center;
    transition: transform 0.15s ease, border-color 0.15s ease;
  }
  .cat-card:hover { transform: translateY(-3px); border-color: var(--teal); }
  .cat-card .ic {
    width: 42px; height: 42px;
    margin: 0 auto 12px;
    border-radius: 10px;
    background: rgba(22,26,46,0.05);
    display: grid; place-items: center;
  }
  .cat-card span { font-size: 13.5px; font-weight: 600; }

  .prod-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
  }
  @media (max-width: 860px) { .prod-grid { grid-template-columns: repeat(2, 1fr); gap: 14px; } }
  .prod-card {
    background: var(--card);
    border: 1px solid var(--line);
    border-radius: 12px;
    overflow: hidden;
    transition: box-shadow 0.15s ease, transform 0.15s ease;
  }
  .prod-card:hover { transform: translateY(-3px); box-shadow: 0 14px 26px rgba(22,26,46,0.08); }
  .prod-img {
    aspect-ratio: 1;
    background: linear-gradient(160deg, #F0F1EC, #E7E5DE);
    display: grid; place-items: center;
  }
  .prod-img svg { width: 40%; opacity: 0.5; }
  .prod-info { padding: 14px 14px 16px; }
  .prod-info .tag { font-size: 10.5px; letter-spacing: 0.1em; text-transform: uppercase; color: var(--teal); font-weight: 600; }
  .prod-info h3 { font-size: 14.5px; margin: 6px 0 8px; font-weight: 600; }
  .prod-info .row { display: flex; align-items: center; justify-content: space-between; }
  .prod-info .price { font-weight: 700; font-size: 15px; }
  .prod-info .add {
    width: 30px; height: 30px; border-radius: 50%;
    border: 1px solid var(--ink); background: transparent;
    display: grid; place-items: center; cursor: pointer;
  }
  .prod-info .add:hover { background: var(--ink); color: var(--ivory); }

  .banner {
    background: var(--ink);
    color: var(--ivory);
    border-radius: 16px;
    padding: 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    flex-wrap: wrap;
  }
  .banner h3 { font-size: 22px; margin: 0 0 6px; }
  .banner p { color: #B7BAC2; margin: 0; font-size: 14px; }
  .banner .btn-primary { background: var(--teal); color: var(--ink); }

  /* ============ FOOTER ============ */
  footer {
    background: var(--ink);
    color: #C9CBD6;
    margin-top: 20px;
  }
  .footer-top {
    max-width: 1200px;
    margin: 0 auto;
    padding: 56px 40px 40px;
    display: grid;
    grid-template-columns: 1.4fr 1fr 1fr 1.2fr;
    gap: 32px;
  }
  @media (max-width: 860px) {
    .footer-top { grid-template-columns: 1fr 1fr; padding: 40px 20px; }
  }
  .footer-brand .logo { color: var(--ivory); margin-bottom: 14px; }
  .footer-brand p { font-size: 13px; line-height: 1.6; color: #9497A6; max-width: 32ch; }
  .footer-social {
    display: flex; gap: 10px; margin-top: 16px;
  }
  .footer-social a {
    width: 32px; height: 32px; border-radius: 50%;
    border: 1px solid #2A2D45;
    display: grid; place-items: center;
  }
  .footer-social a:hover { border-color: var(--teal); color: var(--teal); }
  .footer-col h4 {
    font-size: 12.5px; text-transform: uppercase; letter-spacing: 0.1em;
    color: var(--ivory); margin: 0 0 16px;
  }
  .footer-col ul { list-style: none; padding: 0; margin: 0; display: flex; flex-direction: column; gap: 10px; }
  .footer-col a { font-size: 13.5px; color: #9497A6; }
  .footer-col a:hover { color: var(--teal); }
  .newsletter { font-size: 13px; color: #9497A6; margin-bottom: 12px; }
  .news-form { display: flex; border: 1px solid #2A2D45; border-radius: 8px; overflow: hidden; }
  .news-form input {
    flex: 1; background: transparent; border: none; padding: 10px 12px;
    color: var(--ivory); font-size: 13px; outline: none;
  }
  .news-form button {
    background: var(--teal); color: var(--ink); border: none; padding: 0 16px;
    font-weight: 700; font-size: 13px; cursor: pointer;
  }
  .footer-bottom {
    border-top: 1px solid #23263C;
    padding: 20px 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    max-width: 1200px;
    margin: 0 auto;
  }
  @media (max-width: 860px) { .footer-bottom { padding: 20px; justify-content: center; text-align: center; } }
  .footer-bottom span { font-size: 12px; color: #7C7F91; }
  .pay-icons { display: flex; gap: 8px; }
  .pay-icons div {
    width: 36px; height: 24px; border-radius: 4px;
    background: #1F2238; border: 1px solid #2A2D45;
    display: grid; place-items: center; font-size: 9px; color: #7C7F91; font-weight: 700;
  }
</style>
</head>
<body>

<div class="topstrip">FRETE GRÁTIS ACIMA DE R$199 · ENTREGA PARA TODO O BRASIL</div>

<!-- ============ HEADER ============ -->
<header>
  <div class="logo">
    <svg width="26" height="26" viewBox="0 0 100 100"><path d="M10 78 L50 14 L90 78" fill="none" stroke="#161A2E" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/><path d="M28 58 Q50 38 72 58" fill="none" stroke="#2FD4C4" stroke-width="7" stroke-linecap="round"/><circle cx="50" cy="14" r="6.5" fill="#2FD4C4"/></svg>
    aluak
  </div>
  <nav>
    <a href="#">Início</a>
    <a href="#">Iluminação</a>
    <a href="#">Segurança</a>
    <a href="#">Escritório</a>
    <a href="#">Sobre</a>
  </nav>
  <div class="header-icons">
    <button class="icon-btn" aria-label="Buscar">
      <svg width="19" height="19" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="11" cy="11" r="7"/><path d="M21 21l-4.3-4.3"/></svg>
    </button>
    <button class="icon-btn" aria-label="Conta">
      <svg width="19" height="19" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="8" r="4"/><path d="M4 21c0-4 4-6 8-6s8 2 8 6"/></svg>
    </button>
    <button class="icon-btn" aria-label="Sacola" style="position:relative;">
      <svg width="19" height="19" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 8h12l-1 12H7L6 8z"/><path d="M9 8V6a3 3 0 016 0v2"/></svg>
    </button>
    <span class="cart-count">2</span>
  </div>
</header>

<!-- ============ MODELO / PÁGINA INICIAL ============ -->
<main>
  <section class="hero">
    <div>
      <span class="eyebrow"><svg width="10" height="10" viewBox="0 0 24 24" fill="currentColor"><circle cx="12" cy="12" r="10"/></svg> Automação residencial simples</span>
      <h1>Sua casa,<br>mais inteligente.</h1>
      <p>Iluminação, segurança e automação com instalação fácil — sem fio, sem complicação, direto no seu celular.</p>
      <button class="btn-primary"><span class="dot"></span> Ver coleção completa</button>
    </div>
    <div class="hero-art">
      <svg viewBox="0 0 100 100"><path d="M10 78 L50 14 L90 78" fill="none" stroke="#FAFAF8" stroke-width="7" stroke-linecap="round" stroke-linejoin="round"/><path d="M28 58 Q50 38 72 58" fill="none" stroke="#2FD4C4" stroke-width="5.5" stroke-linecap="round"/><circle cx="50" cy="14" r="5" fill="#2FD4C4"/></svg>
    </div>
  </section>

  <section class="block">
    <div class="block-head"><h2>Categorias</h2><a href="#">Ver todas</a></div>
    <div class="cat-grid">
      <div class="cat-card"><div class="ic">💡</div><span>Iluminação</span></div>
      <div class="cat-card"><div class="ic">🔒</div><span>Segurança</span></div>
      <div class="cat-card"><div class="ic">🖥️</div><span>Escritório</span></div>
      <div class="cat-card"><div class="ic">🏠</div><span>Automação</span></div>
    </div>
  </section>

  <section class="block">
    <div class="block-head"><h2>Mais vendidos</h2><a href="#">Ver tudo</a></div>
    <div class="prod-grid">
      <div class="prod-card">
        <div class="prod-img"><svg viewBox="0 0 24 24" fill="none" stroke="#161A2E" stroke-width="1.5"><path d="M9 18h6M10 21h4M12 3a6 6 0 00-4 10c1 1 1 2 1 3h6c0-1 0-2 1-3a6 6 0 00-4-10z"/></svg></div>
        <div class="prod-info">
          <span class="tag">Iluminação</span>
          <h3>Fita LED Wi-Fi RGB</h3>
          <div class="row"><span class="price">R$ 89,90</span><button class="add">+</button></div>
        </div>
      </div>
      <div class="prod-card">
        <div class="prod-img"><svg viewBox="0 0 24 24" fill="none" stroke="#161A2E" stroke-width="1.5"><rect x="4" y="8" width="16" height="10" rx="2"/><path d="M8 8V6a4 4 0 018 0v2"/></svg></div>
        <div class="prod-info">
          <span class="tag">Segurança</span>
          <h3>Fechadura Digital</h3>
          <div class="row"><span class="price">R$ 249,90</span><button class="add">+</button></div>
        </div>
      </div>
      <div class="prod-card">
        <div class="prod-img"><svg viewBox="0 0 24 24" fill="none" stroke="#161A2E" stroke-width="1.5"><rect x="3" y="5" width="18" height="13" rx="2"/><path d="M8 21h8M12 18v3"/></svg></div>
        <div class="prod-info">
          <span class="tag">Escritório</span>
          <h3>Carregador Sem Fio</h3>
          <div class="row"><span class="price">R$ 69,90</span><button class="add">+</button></div>
        </div>
      </div>
      <div class="prod-card">
        <div class="prod-img"><svg viewBox="0 0 24 24" fill="none" stroke="#161A2E" stroke-width="1.5"><circle cx="12" cy="12" r="3"/><path d="M12 2v3M12 19v3M2 12h3M19 12h3"/></svg></div>
        <div class="prod-info">
          <span class="tag">Automação</span>
          <h3>Câmera Wi-Fi 360°</h3>
          <div class="row"><span class="price">R$ 159,90</span><button class="add">+</button></div>
        </div>
      </div>
    </div>
  </section>

  <section class="block">
    <div class="banner">
      <div>
        <h3>Primeira compra com 10% off</h3>
        <p>Use o cupom BEMVINDO10 e receba em casa em poucos dias.</p>
      </div>
      <button class="btn-primary">Aproveitar agora</button>
    </div>
  </section>
</main>

<!-- ============ FOOTER ============ -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="logo">
        <svg width="24" height="24" viewBox="0 0 100 100"><path d="M10 78 L50 14 L90 78" fill="none" stroke="#FAFAF8" stroke-width="10" stroke-linecap="round" stroke-linejoin="round"/><path d="M28 58 Q50 38 72 58" fill="none" stroke="#2FD4C4" stroke-width="7" stroke-linecap="round"/><circle cx="50" cy="14" r="6.5" fill="#2FD4C4"/></svg>
        aluak
      </div>
      <p>Produtos de casa inteligente pensados para o dia a dia — simples de instalar, fáceis de usar.</p>
      <div class="footer-social">
        <a href="#" aria-label="Instagram"><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1"/></svg></a>
        <a href="#" aria-label="TikTok"><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M14 4v9.5a3.5 3.5 0 11-3.5-3.5"/><path d="M14 4c0 2.5 2 4.5 4.5 4.5"/></svg></a>
      </div>
    </div>
    <div class="footer-col">
      <h4>Loja</h4>
      <ul>
        <li><a href="#">Iluminação</a></li>
        <li><a href="#">Segurança</a></li>
        <li><a href="#">Escritório</a></li>
        <li><a href="#">Automação</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Atendimento</h4>
      <ul>
        <li><a href="#">Fale conosco</a></li>
        <li><a href="#">Trocas e devoluções</a></li>
        <li><a href="#">Política de privacidade</a></li>
        <li><a href="#">Termos de serviço</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Fique por dentro</h4>
      <p class="newsletter">Novidades e promoções direto no seu e-mail.</p>
      <div class="news-form">
        <input type="email" placeholder="seu e-mail">
        <button>Enviar</button>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 Aluak. Todos os direitos reservados.</span>
    <div class="pay-icons">
      <div>PIX</div><div>VISA</div><div>MC</div><div>ELO</div>
    </div>
  </div>
</footer>

</body>
</html>
