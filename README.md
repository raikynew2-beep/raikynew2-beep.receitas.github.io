<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="description" content="Receitas diferentes em PDF: escolha, pague no Pix e receba ingredientes, medidas e passo a passo.">
<meta name="theme-color" content="#FFF3F6">
<title>Panela de Domingo</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Nunito:wght@400;600;700;800&display=swap">
<style>
/* Layout: cabeçalho fixo, hero em duas colunas (texto + como funciona), grade de cards pastel por categoria, carrinho em gaveta lateral e Pix em tela própria dentro da gaveta. */
:root{
  --bg:#FFF3F6; --surface:#FFFFFF; --ink:#3B2030; --muted:#7B6372; --line:#F1D7DF;
  --accent:#E5436D; --accent-ink:#FFFFFF; --accent-soft:#FFE0E8;
  --pix:#0A7F72; --pix-ink:#FFFFFF; --pix-soft:#D8F1EC;
  --warn-bg:#FFF1C9; --warn-ink:#6B4E00; --err:#B3203F;
  --t-doces:#FFD6E0; --t-bolos:#FFE9A8; --t-salgados:#FFD9B8; --t-paes:#EBD9C4; --t-almoco:#CDEBDD; --t-fit:#E0D6FA;
  --shadow:0 8px 28px rgba(120,40,70,.10);
  --font-display:'Fredoka','Nunito',system-ui,sans-serif;
  --font-body:'Nunito',system-ui,-apple-system,'Segoe UI',sans-serif;
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#241420; --surface:#33202C; --ink:#FCE9F0; --muted:#C9A9B8; --line:#4B2F3E;
    --accent:#FF7096; --accent-ink:#2B0F1A; --accent-soft:#4A2433;
    --pix:#3FD2BF; --pix-ink:#052B26; --pix-soft:#1C4540;
    --warn-bg:#4A3A12; --warn-ink:#FFE9A8; --err:#FF8FA6;
    --t-doces:#5A2A3E; --t-bolos:#5A4A22; --t-salgados:#5A3A24; --t-paes:#4A3A2E; --t-almoco:#254A3C; --t-fit:#3E3566;
    --shadow:0 8px 28px rgba(0,0,0,.35);
    color-scheme:dark;
  }
}
:root[data-theme="dark"]{
  --bg:#241420; --surface:#33202C; --ink:#FCE9F0; --muted:#C9A9B8; --line:#4B2F3E;
  --accent:#FF7096; --accent-ink:#2B0F1A; --accent-soft:#4A2433;
  --pix:#3FD2BF; --pix-ink:#052B26; --pix-soft:#1C4540;
  --warn-bg:#4A3A12; --warn-ink:#FFE9A8; --err:#FF8FA6;
  --t-doces:#5A2A3E; --t-bolos:#5A4A22; --t-salgados:#5A3A24; --t-paes:#4A3A2E; --t-almoco:#254A3C; --t-fit:#3E3566;
  --shadow:0 8px 28px rgba(0,0,0,.35);
  color-scheme:dark;
}

*{box-sizing:border-box}
body{background:var(--bg); color:var(--ink); font:16px/1.55 var(--font-body); -webkit-font-smoothing:antialiased}
body::before{content:""; position:fixed; inset:0 0 auto; height:env(safe-area-inset-top,0px); z-index:10; background:var(--bg)}
h1,h2,h3{font-family:var(--font-display); margin:0; text-wrap:balance; line-height:1.15}
p{margin:0}
button{font:inherit; color:inherit}
:focus-visible{outline:3px solid var(--accent); outline-offset:2px}
.wrap{width:100%; max-width:1120px; margin:0 auto; padding-left:max(16px,env(safe-area-inset-left,0px)); padding-right:max(16px,env(safe-area-inset-right,0px))}

/* Cabeçalho */
.top{position:sticky; top:env(safe-area-inset-top,0px); z-index:20; background:var(--bg); border-bottom:1px solid var(--line)}
.top-in{display:flex; align-items:center; justify-content:space-between; gap:12px; padding-block:12px}
.brand{display:flex; align-items:center; gap:10px; font-family:var(--font-display); font-weight:700; font-size:22px; letter-spacing:.2px}

/* Botões */
.btn{display:inline-flex; align-items:center; justify-content:center; gap:8px; border:2px solid transparent; border-radius:999px; padding:10px 18px; font-weight:800; cursor:pointer; text-decoration:none; line-height:1.2; transition:transform .12s ease, background-color .12s ease}
.btn:active{transform:scale(.97)}
.btn-primary{background:var(--accent); color:var(--accent-ink)}
.btn-outline{background:transparent; border-color:var(--accent); color:var(--ink)}
.btn-ghost{background:transparent; color:var(--muted); padding-inline:10px}
.btn-pix{background:var(--pix); color:var(--pix-ink)}
.btn-block{width:100%; padding-block:14px; font-size:17px}
.badge{display:inline-grid; place-items:center; min-width:22px; height:22px; padding:0 6px; border-radius:999px; background:var(--accent); color:var(--accent-ink); font-size:13px; font-weight:800}
.btn-cart{background:var(--surface); border-color:var(--line); color:var(--ink)}

/* Hero */
.hero{padding-block:clamp(28px,6vw,56px)}
.hero-grid{display:grid; grid-template-columns:minmax(0,1.2fr) minmax(0,.8fr); gap:32px; align-items:center}
.eyebrow{display:inline-block; background:var(--accent-soft); color:var(--ink); border-radius:999px; padding:5px 14px; font-weight:800; font-size:14px; letter-spacing:.4px; margin-bottom:16px}
.hero h1{font-size:clamp(34px,6vw,56px); font-weight:700}
.lead{margin-top:14px; font-size:18px; color:var(--muted); max-width:46ch}
.tiers{list-style:none; margin:20px 0 24px; padding:0; display:flex; flex-wrap:wrap; gap:10px}
.tiers li{background:var(--surface); border:1px solid var(--line); border-radius:999px; padding:7px 14px; font-size:15px}
.tiers strong{font-weight:800}
.how{background:var(--surface); border:1px solid var(--line); border-radius:28px; padding:22px; box-shadow:var(--shadow)}
.how h2{font-size:22px; margin-bottom:14px}
.how ol{list-style:none; margin:0; padding:0; display:grid; gap:16px}
.how li{display:flex; gap:14px; align-items:flex-start}
.how .n{flex:none; width:34px; height:34px; border-radius:50%; background:var(--accent-soft); display:grid; place-items:center; font-family:var(--font-display); font-weight:700}
.how strong{display:block; font-weight:800}
.how p{color:var(--muted); font-size:15px}

/* Cardápio */
.menu{padding-bottom:48px}
.menu h2{font-size:clamp(26px,4vw,34px)}
.menu-head{display:flex; flex-wrap:wrap; align-items:baseline; justify-content:space-between; gap:8px 16px}
.count{color:var(--muted); font-size:15px}
.chips{display:flex; gap:8px; overflow-x:auto; padding:16px 0 18px; scrollbar-width:thin}
.chip{flex:none; border:2px solid var(--line); background:var(--surface); border-radius:999px; padding:8px 16px; font-weight:700; cursor:pointer; display:inline-flex; align-items:center; gap:8px}
.chip span{color:var(--muted); font-size:13px; font-weight:700}
.chip[aria-pressed="true"]{background:var(--accent); border-color:var(--accent); color:var(--accent-ink)}
.chip[aria-pressed="true"] span{color:inherit; opacity:.85}
.grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(250px,1fr)); gap:20px}
.card{background:var(--surface); border:1px solid var(--line); border-radius:26px; overflow:hidden; display:flex; flex-direction:column; min-width:0}
.tile{position:relative; width:100%; aspect-ratio:16/10; max-width:100%; border:0; cursor:pointer; display:block; overflow:hidden; background:var(--t-doces)}
.tile svg{position:absolute; inset:0; width:100%; height:100%; display:block; transition:transform .3s ease}
.tile:hover svg{transform:scale(1.05)}
.tag{position:absolute; z-index:1; top:12px; left:12px; background:var(--surface); border-radius:999px; padding:3px 12px; font-size:13px; font-weight:800}
.c-doces{background:var(--t-doces)} .c-bolos{background:var(--t-bolos)} .c-salgados{background:var(--t-salgados)}
.c-paes{background:var(--t-paes)} .c-almoco{background:var(--t-almoco)} .c-fit{background:var(--t-fit)}
.card-body{padding:16px 18px 18px; display:flex; flex-direction:column; gap:8px; flex:1; min-width:0}
.card h3{font-size:20px; font-weight:600}
.card .desc{color:var(--muted); font-size:15px}
.meta{color:var(--muted); font-size:14px; font-weight:600}
.buy{margin-top:auto; padding-top:10px; display:flex; align-items:center; justify-content:space-between; gap:8px; flex-wrap:wrap}
.price{font-family:var(--font-display); font-weight:600; font-size:24px; font-variant-numeric:tabular-nums}
.buy-actions{display:flex; gap:4px; align-items:center}

/* Rodapé e barra do carrinho */
.foot{border-top:1px solid var(--line); padding-block:28px 112px; color:var(--muted); font-size:14px}
.foot p+p{margin-top:6px}
.dock{position:fixed; left:0; right:0; bottom:0; display:flex; justify-content:center; padding:0 max(16px,env(safe-area-inset-right,0px)) calc(14px + env(safe-area-inset-bottom,0px)) max(16px,env(safe-area-inset-left,0px)); pointer-events:none; z-index:15}
.dock-btn{pointer-events:auto; border:0; border-radius:999px; background:var(--accent); color:var(--accent-ink); font-weight:800; font-size:16px; padding:14px 26px; cursor:pointer; box-shadow:0 10px 30px rgba(0,0,0,.25); max-width:100%}

/* Janelas */
dialog{border:0; padding:0; color:var(--ink); background:var(--surface); max-width:100vw; max-height:100dvh}
dialog::backdrop{background:rgba(40,12,26,.55)}
#detail{width:min(560px,calc(100% - 24px)); max-width:calc(100% - 24px); max-height:calc(100dvh - 24px); border-radius:28px; overflow:auto}
#detail[open]{animation:pop .2s ease-out}
#cart{margin:0 0 0 auto; width:min(460px,100%); max-width:100%; height:100dvh; max-height:100dvh; border-radius:28px 0 0 28px; overflow:hidden}
#cart[open]{animation:slide .26s ease-out}
@keyframes pop{from{opacity:0; transform:translateY(10px) scale(.98)}}
@keyframes slide{from{transform:translateX(40px); opacity:0}}
@media (max-width:520px){#cart{border-radius:0}}
.icon-btn{border:0; background:var(--accent-soft); color:var(--ink); width:40px; height:40px; border-radius:50%; font-size:22px; line-height:1; cursor:pointer; flex:none}
.d-tile{aspect-ratio:16/9; position:relative; overflow:hidden}
.d-tile svg{position:absolute; inset:0; width:100%; height:100%; display:block}
.d-close{position:absolute; z-index:1; top:12px; right:12px}
.d-body{padding:20px 22px 24px; display:grid; gap:14px}
.d-body h2{font-size:28px}
.d-meta{display:flex; flex-wrap:wrap; gap:8px}
.d-meta span{background:var(--bg); border:1px solid var(--line); border-radius:999px; padding:4px 12px; font-size:14px; font-weight:700}
.d-body h3{font-size:17px}
.d-list{margin:0; padding-left:20px; display:grid; gap:4px; color:var(--muted)}
.d-note{background:var(--accent-soft); border-radius:16px; padding:12px 14px; font-size:15px}
.d-buy{display:flex; align-items:center; justify-content:space-between; gap:12px; flex-wrap:wrap; padding-top:4px}

.sheet{display:flex; flex-direction:column; height:100%; min-height:0}
.sheet-head{display:flex; align-items:center; justify-content:space-between; gap:12px; padding:max(16px,env(safe-area-inset-top,0px)) max(18px,env(safe-area-inset-right,0px)) 12px 20px; border-bottom:1px solid var(--line)}
.sheet-head h2{font-size:22px}
.view{display:flex; flex-direction:column; flex:1; min-height:0}
.scroll{flex:1; overflow:auto; padding:16px max(18px,env(safe-area-inset-right,0px)) 16px 20px; display:grid; gap:16px; align-content:start}
.sheet-foot{border-top:1px solid var(--line); padding:14px max(18px,env(safe-area-inset-right,0px)) max(16px,env(safe-area-inset-bottom,0px)) 20px; display:grid; gap:10px; background:var(--surface)}
.items{list-style:none; margin:0; padding:0; display:grid; gap:10px}
.items li{display:flex; align-items:center; gap:12px; background:var(--bg); border-radius:18px; padding:10px 12px}
.mini{flex:none; width:56px; height:56px; border-radius:14px; overflow:hidden; position:relative}
.mini svg{display:block; width:100%; height:100%}
.items .info{flex:1; min-width:0}
.items strong{display:block; font-weight:800; overflow-wrap:anywhere}
.items small{color:var(--muted); font-size:14px; font-variant-numeric:tabular-nums}
.empty{text-align:center; padding:28px 8px; color:var(--muted); display:grid; gap:14px; justify-items:center}
.hint{background:var(--warn-bg); color:var(--warn-ink); border-radius:14px; padding:10px 14px; font-size:14px; font-weight:700}
.sum{display:grid; gap:4px; font-variant-numeric:tabular-nums}
.sum div{display:flex; justify-content:space-between; gap:12px}
.sum .off{color:var(--pix)}
.sum .tot{font-family:var(--font-display); font-weight:600; font-size:24px; padding-top:4px}
.form{display:grid; gap:12px}
.form h3{font-size:17px}
.field{display:grid; gap:4px}
.field label{font-weight:800; font-size:14px}
.field input{width:100%; border:2px solid var(--line); background:var(--bg); color:var(--ink); border-radius:14px; padding:12px 14px; font:inherit; font-size:16px}
.field input:focus{border-color:var(--accent); outline:none}
.err{color:var(--err); font-weight:700; font-size:14px; min-height:1.2em}

.demo{background:var(--warn-bg); color:var(--warn-ink); border-radius:14px; padding:10px 14px; font-size:14px; font-weight:700}
.order-top{display:flex; justify-content:space-between; align-items:flex-end; gap:12px}
.order-top .lbl{color:var(--muted); font-size:14px; font-weight:700}
.order-top .val{font-family:var(--font-display); font-weight:700; font-size:34px; line-height:1; font-variant-numeric:tabular-nums}
.qr{background:#fff; padding:14px; border-radius:20px; width:min(240px,72%); margin:0 auto; border:1px solid var(--line)} /* QR sempre escuro sobre branco para leitura */
.qr svg{display:block; width:100%; height:auto}
.code{width:100%; resize:none; border:2px solid var(--line); background:var(--bg); color:var(--ink); border-radius:14px; padding:10px 12px; font:12px/1.4 ui-monospace,Menlo,Consolas,monospace; word-break:break-all}
.steps{margin:0; padding-left:20px; display:grid; gap:6px; color:var(--muted); font-size:15px}
.fine{color:var(--muted); font-size:14px}

@media (max-width:760px){
  .hero-grid{grid-template-columns:minmax(0,1fr)}
}
@media (prefers-reduced-motion: reduce){
  *,*::before,*::after{animation:none!important; transition:none!important}
}
</style>

<style>
:root{color-scheme:light}
html{-webkit-text-size-adjust:100%}
body{margin:0}
img{max-width:100%}
[hidden]{display:none!important}
</style>
</head>
<body>
<header class="top">
  <div class="wrap top-in">
    <div class="brand">
      <svg viewBox="0 0 32 32" width="32" height="32" aria-hidden="true">
        <path d="M5 14h22v7a7 7 0 0 1-7 7h-8a7 7 0 0 1-7-7z" fill="var(--accent)"/>
        <rect x="3" y="11" width="26" height="4" rx="2" fill="var(--ink)"/>
        <path d="M12 8c-1.4-2 1.4-3 0-5.5M17 8c-1.4-2 1.4-3 0-5.5M22 8c-1.4-2 1.4-3 0-5.5" stroke="var(--accent)" stroke-width="2" fill="none" stroke-linecap="round"/>
      </svg>
      Panela de Domingo
    </div>
    <button class="btn btn-cart" id="openCart" type="button">Carrinho <span class="badge" id="badge">0</span></button>
  </div>
</header>

<main>
  <section class="hero">
    <div class="wrap hero-grid">
      <div>
        <p class="eyebrow">Receitas digitais em PDF</p>
        <h1>Receitas diferentes para fazer em casa</h1>
        <p class="lead">Combinações que fogem das receitas de sempre. Escolha, pague no Pix e receba o PDF com ingredientes, medidas e passo a passo.</p>
        <ul class="tiers">
          <li><strong>3 receitas</strong> com 15% de desconto</li>
          <li><strong>5 receitas</strong> com 25% de desconto</li>
        </ul>
        <button class="btn btn-primary" id="goMenu" type="button">Ver as receitas</button>
      </div>
      <aside class="how" aria-labelledby="howTitle">
        <h2 id="howTitle">Como funciona</h2>
        <ol>
          <li><span class="n">1</span><div><strong>Escolha</strong><p>Adicione as receitas que quiser ao carrinho.</p></div></li>
          <li><span class="n">2</span><div><strong>Pague com Pix</strong><p>Copie o código ou leia o QR Code no app do seu banco.</p></div></li>
          <li><span class="n">3</span><div><strong>Envie o comprovante</strong><p>Você recebe o PDF assim que o pagamento for confirmado.</p></div></li>
        </ol>
      </aside>
    </div>
  </section>

  <section class="menu" id="receitas">
    <div class="wrap">
      <div class="menu-head">
        <h2>Cardápio de receitas</h2>
        <p class="count" id="count"></p>
      </div>
      <div class="chips" id="chips" role="group" aria-label="Filtrar por categoria"></div>
      <div class="grid" id="grid"></div>
    </div>
  </section>
</main>

<footer class="foot">
  <div class="wrap">
    <p><strong>Panela de Domingo</strong> · Receitas digitais em PDF, sem envio de produto físico.</p>
    <p>Pagamento por Pix. O pedido é liberado depois da confirmação do pagamento.</p>
  </div>
</footer>

<div class="dock" id="dock" hidden>
  <button class="dock-btn" id="dockBtn" type="button"></button>
</div>

<dialog id="detail" aria-label="Detalhes da receita"><div id="detailBody"></div></dialog>

<dialog id="cart" aria-labelledby="cTitle">
  <div class="sheet">
    <div class="sheet-head">
      <h2 id="cTitle">Seu carrinho</h2>
      <button class="icon-btn" type="button" data-close aria-label="Fechar">×</button>
    </div>

    <div class="view" id="viewCart">
      <div class="scroll">
        <ul class="items" id="cartItems"></ul>
        <div class="empty" id="cartEmpty" hidden>
          <p>Seu carrinho está vazio. Que tal começar por um bolo?</p>
          <button class="btn btn-outline" type="button" data-close>Ver receitas</button>
        </div>
        <div class="hint" id="cartHint" hidden></div>
        <form class="form" id="buyerForm" novalidate>
          <h3>Para quem enviamos as receitas?</h3>
          <div class="field">
            <label for="fNome">Seu nome</label>
            <input id="fNome" name="nome" type="text" autocomplete="name" placeholder="Maria Souza">
          </div>
          <div class="field">
            <label for="fContato">WhatsApp ou e-mail</label>
            <input id="fContato" name="contato" type="text" autocomplete="email" placeholder="(11) 91234-5678 ou maria@email.com">
          </div>
          <p class="err" id="formErr" role="alert"></p>
        </form>
      </div>
      <div class="sheet-foot">
        <div class="sum" id="sum"></div>
        <button class="btn btn-pix btn-block" id="genPix" type="button">Pagar com Pix</button>
      </div>
    </div>

    <div class="view" id="viewPix" hidden>
      <div class="scroll">
        <div class="demo" id="demoNote" hidden>Modo demonstração: este código não envia dinheiro para ninguém. Coloque a chave Pix da loja para vender de verdade.</div>
        <div class="order-top">
          <div><p class="lbl">Pedido <span id="orderId"></span></p><p class="val" id="orderVal"></p></div>
        </div>
        <div class="qr" id="qrBox"></div>
        <div class="field">
          <label for="pixCode">Pix copia e cola</label>
          <textarea class="code" id="pixCode" rows="5" readonly></textarea>
        </div>
        <button class="btn btn-outline btn-block" id="copyBtn" type="button">Copiar código Pix</button>
        <ol class="steps">
          <li>Abra o app do seu banco e escolha Pix.</li>
          <li>Cole o código ou leia o QR Code.</li>
          <li>Confira o valor e o nome de quem recebe, depois confirme.</li>
          <li>Envie o comprovante pelo botão abaixo.</li>
        </ol>
        <p class="fine">As receitas são enviadas depois que o pagamento for confirmado.</p>
      </div>
      <div class="sheet-foot">
        <a class="btn btn-primary btn-block" id="waLink" href="#" target="_blank" rel="noopener">Enviar comprovante no WhatsApp</a>
        <button class="btn btn-ghost" id="backBtn" type="button">Voltar ao carrinho</button>
      </div>
    </div>
  </div>
</dialog>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcode-generator/1.4.4/qrcode.min.js"></script>
<script>
(function(){
  /* Configuração da loja. Preencha para receber de verdade. */
  var CONFIG = {
    loja: 'Panela de Domingo',
    pixKey: '',      /* chave Pix: e-mail, CPF/CNPJ, telefone com +55 ou chave aleatória */
    pixNome: '',     /* nome do recebedor, como no banco */
    pixCidade: '',   /* cidade do recebedor */
    whatsapp: ''     /* número com DDI e DDD, ex.: 5511912345678 */
  };
  var CONFIGURED = !!(CONFIG.pixKey && CONFIG.pixNome && CONFIG.pixCidade);

  var RECEITAS = [
    {id:'pudim-tapioca', nome:'Pudim de Tapioca com Calda de Rapadura e Gengibre', cat:'Doces', preco:790, tempo:'1 h 30', porcoes:'8 porções', nivel:'Fácil',
      desc:'Textura de pudim com a mastigada leve da tapioca, coberto por uma calda de rapadura que esquenta no final.',
      ingr:['1 xícara de tapioca granulada','1 lata de leite de coco','1 pedaço de rapadura'], total:8, etapas:7},
    {id:'brigadeiro-cafe', nome:'Brigadeiro de Café com Cardamomo e Flor de Sal', cat:'Doces', preco:690, tempo:'40 min', porcoes:'30 unidades', nivel:'Fácil',
      desc:'Brigadeiro para adultos, feito com café coado, perfume de cardamomo e flor de sal por cima.',
      ingr:['1 lata de leite condensado','2 colheres de café forte','3 vagens de cardamomo'], total:6, etapas:5},
    {id:'bolo-banana-terra', nome:'Bolo de Banana-da-Terra com Doce de Leite Salgado', cat:'Bolos', preco:990, tempo:'1 h 10', porcoes:'12 fatias', nivel:'Fácil',
      desc:'Bolo úmido de banana-da-terra assada, com calda de doce de leite e uma pitada de sal.',
      ingr:['3 bananas-da-terra maduras','1 xícara de açúcar mascavo','1 lata de doce de leite'], total:10, etapas:8},
    {id:'bolo-vulcao', nome:'Bolo Vulcão de Goiabada com Queijo Coalho', cat:'Bolos', preco:990, tempo:'1 h', porcoes:'10 fatias', nivel:'Médio',
      desc:'Goiabada derretida que escorre como lava e queijo coalho dourado por cima.',
      ingr:['300 g de goiabada cascão','200 g de queijo coalho','3 ovos'], total:9, etapas:9},
    {id:'bolinho-arroz', nome:'Bolinho Crocante de Arroz com Linguiça e Geleia de Pimenta', cat:'Salgados', preco:890, tempo:'50 min', porcoes:'24 unidades', nivel:'Fácil',
      desc:'Aproveita o arroz de ontem: casquinha crocante, linguiça dentro e geleia de pimenta para molhar.',
      ingr:['3 xícaras de arroz cozido','200 g de linguiça calabresa','1 xícara de farinha de rosca'], total:11, etapas:9},
    {id:'empadinha-baiao', nome:'Empadinha de Baião de Dois com Queijo Coalho', cat:'Salgados', preco:890, tempo:'1 h 20', porcoes:'20 unidades', nivel:'Médio',
      desc:'Massa amanteigada que desmancha, com recheio cremoso de baião de dois e queijo coalho.',
      ingr:['2 xícaras de farinha de trigo','1 xícara de feijão-de-corda cozido','150 g de queijo coalho'], total:12, etapas:10},
    {id:'pao-mandioca', nome:'Pão de Mandioca com Coco e Erva-Doce', cat:'Pães', preco:990, tempo:'2 h', porcoes:'1 pão grande', nivel:'Médio',
      desc:'Miolo macio de mandioca, cheiro de coco e erva-doce, ótimo para o café da manhã.',
      ingr:['400 g de mandioca cozida','1/2 xícara de coco ralado','1 colher de erva-doce'], total:9, etapas:8},
    {id:'pao-abobora', nome:'Pão Trançado de Abóbora, Canela e Laranja', cat:'Pães', preco:990, tempo:'2 h 30', porcoes:'1 pão trançado', nivel:'Médio',
      desc:'Pão alaranjado e trançado, perfumado de canela e raspas de laranja.',
      ingr:['2 xícaras de abóbora cozida','1 laranja (raspas e suco)','1 pau de canela'], total:10, etapas:9},
    {id:'moqueca-banana', nome:'Moqueca de Banana-da-Terra e Palmito', cat:'Almoço', preco:1090, tempo:'45 min', porcoes:'4 porções', nivel:'Fácil',
      desc:'Moqueca vegana com leite de coco e azeite de dendê, cheia de sabor e sem peixe.',
      ingr:['3 bananas-da-terra','1 vidro de palmito','1 vidro de leite de coco'], total:11, etapas:7},
    {id:'cuscuz-camarao', nome:'Cuscuz de Frigideira com Camarão e Creme de Milho', cat:'Almoço', preco:1090, tempo:'35 min', porcoes:'4 porções', nivel:'Fácil',
      desc:'Cuscuz dourado na frigideira, com camarão e um creme de milho verde feito na hora.',
      ingr:['2 xícaras de flocão de milho','300 g de camarão limpo','2 espigas de milho verde'], total:10, etapas:7},
    {id:'cookie-grao', nome:'Cookie de Grão-de-Bico e Cacau', cat:'Fit', preco:790, tempo:'35 min', porcoes:'12 unidades', nivel:'Fácil',
      desc:'Cookie macio feito com grão-de-bico, cacau e pasta de amendoim, sem farinha de trigo.',
      ingr:['1 xícara de grão-de-bico cozido','3 colheres de cacau em pó','2 colheres de pasta de amendoim'], total:7, etapas:6},
    {id:'panqueca-beterraba', nome:'Panqueca de Beterraba com Ricota e Ervas', cat:'Fit', preco:690, tempo:'30 min', porcoes:'2 porções', nivel:'Fácil',
      desc:'Panqueca rosada de beterraba, recheada com ricota fresca e ervas.',
      ingr:['1 beterraba cozida','2 ovos','150 g de ricota fresca'], total:8, etapas:6}
  ];

  /* Ilustrações originais em SVG, uma por receita */
  var BG = '<circle cx="36" cy="40" r="26" fill="#fff" opacity=".3"/><circle cx="292" cy="152" r="34" fill="#fff" opacity=".25"/><circle cx="272" cy="36" r="12" fill="#fff" opacity=".3"/><circle cx="52" cy="168" r="10" fill="#fff" opacity=".25"/>';
  var PLATE = '<ellipse cx="160" cy="158" rx="112" ry="14" fill="#000" opacity=".12"/><ellipse cx="160" cy="128" rx="106" ry="38" fill="#FFF9F2"/><ellipse cx="160" cy="128" rx="86" ry="29" fill="#F1E3D6"/>';
  var SHADOW = '<ellipse cx="160" cy="160" rx="104" ry="12" fill="#000" opacity=".14"/>';
  var ART = {
    'pudim-tapioca': PLATE +
      '<path d="M108 128 C108 78 212 78 212 128 Z" fill="#FFE7A3"/>' +
      '<path d="M114 108 C128 84 192 84 206 108 C198 118 194 102 184 114 C176 124 170 106 160 116 C152 124 146 106 136 116 C128 122 122 114 114 108 Z" fill="#B5651D"/>' +
      '<ellipse cx="148" cy="96" rx="14" ry="4" fill="#fff" opacity=".45"/>' +
      '<rect x="226" y="104" width="9" height="32" rx="4.5" transform="rotate(25 230 120)" fill="#E8C27A"/>' +
      '<rect x="240" y="108" width="9" height="28" rx="4.5" transform="rotate(-10 244 122)" fill="#D9AE62"/>',
    'brigadeiro-cafe': PLATE +
      '<path d="M101 126 L105 144 L131 144 L135 126 Z" fill="#F4B6C2"/><circle cx="118" cy="120" r="19" fill="#5B3A29"/><circle cx="112" cy="113" r="4" fill="#7A5240"/><rect x="121" y="106" width="5" height="3" rx="1" fill="#fff"/><rect x="113" y="124" width="4" height="3" rx="1" fill="#fff"/>' +
      '<path d="M143 126 L147 144 L173 144 L177 126 Z" fill="#F4B6C2"/><circle cx="160" cy="120" r="19" fill="#5B3A29"/><circle cx="154" cy="113" r="4" fill="#7A5240"/><rect x="163" y="106" width="5" height="3" rx="1" fill="#fff"/><rect x="156" y="125" width="4" height="3" rx="1" fill="#fff"/>' +
      '<path d="M185 126 L189 144 L215 144 L219 126 Z" fill="#F4B6C2"/><circle cx="202" cy="120" r="19" fill="#5B3A29"/><circle cx="196" cy="113" r="4" fill="#7A5240"/><rect x="205" y="106" width="5" height="3" rx="1" fill="#fff"/><rect x="198" y="124" width="4" height="3" rx="1" fill="#fff"/>' +
      '<ellipse cx="248" cy="132" rx="10" ry="7" fill="#4A2C1B"/><path d="M240 132 Q248 128 256 132" stroke="#8A6248" stroke-width="2" fill="none"/>' +
      '<ellipse cx="72" cy="132" rx="11" ry="6" transform="rotate(-20 72 132)" fill="#A8C686"/>',
    'bolo-banana-terra': PLATE +
      '<rect x="96" y="88" width="128" height="50" rx="12" fill="#D9984B"/>' +
      '<path d="M96 100 C96 84 224 84 224 100 L224 106 C216 106 216 124 208 124 C200 124 200 108 190 108 C180 108 180 130 170 130 C160 130 160 108 150 108 C140 108 140 122 132 122 C124 122 124 106 116 106 C106 106 106 118 96 118 Z" fill="#8A4A1F"/>' +
      '<circle cx="130" cy="90" r="9" fill="#FFD86B" stroke="#E0B13A" stroke-width="2"/><circle cx="160" cy="87" r="9" fill="#FFD86B" stroke="#E0B13A" stroke-width="2"/><circle cx="190" cy="90" r="9" fill="#FFD86B" stroke="#E0B13A" stroke-width="2"/>' +
      '<rect x="140" y="98" width="3" height="3" fill="#fff"/><rect x="176" y="100" width="3" height="3" fill="#fff"/><rect x="204" y="97" width="3" height="3" fill="#fff"/>',
    'bolo-vulcao': PLATE +
      '<path d="M100 138 L126 84 L194 84 L220 138 Z" fill="#D9884E"/>' +
      '<ellipse cx="160" cy="84" rx="34" ry="9" fill="#7E1F2E"/>' +
      '<path d="M138 86 C134 100 138 112 134 124 C132 132 144 132 144 124 C146 112 142 100 146 90 Z" fill="#B3263C"/>' +
      '<path d="M178 90 C176 104 182 116 180 128 C180 134 190 134 190 126 C190 112 188 100 186 88 Z" fill="#B3263C"/>' +
      '<rect x="234" y="122" width="15" height="15" rx="2" transform="rotate(14 241 129)" fill="#FFE08A"/><rect x="68" y="126" width="14" height="14" rx="2" transform="rotate(-12 75 133)" fill="#FFE08A"/><rect x="250" y="108" width="12" height="12" rx="2" transform="rotate(30 256 114)" fill="#F5CE6B"/>',
    'bolinho-arroz': PLATE +
      '<circle cx="112" cy="122" r="24" fill="#E8A23C"/><circle cx="152" cy="112" r="26" fill="#EDB04A"/><circle cx="194" cy="124" r="23" fill="#E49A34"/>' +
      '<circle cx="104" cy="116" r="2.5" fill="#C97B1E"/><circle cx="118" cy="130" r="2.5" fill="#C97B1E"/><circle cx="146" cy="104" r="2.5" fill="#C97B1E"/><circle cx="160" cy="120" r="2.5" fill="#C97B1E"/><circle cx="188" cy="118" r="2.5" fill="#C97B1E"/><circle cx="200" cy="132" r="2.5" fill="#C97B1E"/>' +
      '<path d="M232 112 H270 C270 130 260 138 251 138 C242 138 232 130 232 112 Z" fill="#fff"/><ellipse cx="251" cy="112" rx="19" ry="5" fill="#D7263D"/>' +
      '<path d="M58 128 C70 116 84 122 88 134 C78 136 66 136 58 128 Z" fill="#D7263D"/><path d="M58 128 C54 124 52 121 50 117" stroke="#3E8E41" stroke-width="3" fill="none" stroke-linecap="round"/>',
    'empadinha-baiao': PLATE +
      '<path d="M110 140 L104 106 H146 L140 140 Z" fill="#E8B35C"/><path d="M104 106 C104 88 146 88 146 106 Z" fill="#C97B2E"/><rect x="114" y="94" width="7" height="5" rx="1" fill="#FFE9A8"/><rect x="128" y="97" width="7" height="5" rx="1" fill="#FFE9A8"/><circle cx="124" cy="92" r="3" fill="#4C9A3E"/>' +
      '<g transform="translate(76 0)"><path d="M110 140 L104 106 H146 L140 140 Z" fill="#E8B35C"/><path d="M104 106 C104 88 146 88 146 106 Z" fill="#C97B2E"/><rect x="114" y="94" width="7" height="5" rx="1" fill="#FFE9A8"/><rect x="128" y="97" width="7" height="5" rx="1" fill="#FFE9A8"/><circle cx="131" cy="92" r="3" fill="#4C9A3E"/></g>' +
      '<path d="M62 134 q8 -14 16 -2 q-8 10 -16 2 Z" fill="#4C9A3E"/>',
    'pao-mandioca': PLATE +
      '<ellipse cx="160" cy="118" rx="74" ry="42" fill="#D9A066"/><ellipse cx="160" cy="106" rx="62" ry="30" fill="#E6B47E"/>' +
      '<path d="M128 100 L146 122 M156 94 L174 118 M184 98 L198 118" stroke="#B77B40" stroke-width="5" stroke-linecap="round"/>' +
      '<rect x="120" y="96" width="9" height="4" rx="2" fill="#fff"/><rect x="170" y="92" width="9" height="4" rx="2" fill="#fff"/><rect x="196" y="104" width="9" height="4" rx="2" fill="#fff"/><rect x="140" y="124" width="9" height="4" rx="2" fill="#fff"/>' +
      '<path transform="translate(244 128)" d="M0-13 L3-4 L13-7 L6 0 L13 7 L3 4 L0 13 L-3 4 L-13 7 L-6 0 L-13 -7 L-3 -4Z" fill="#7A4326"/>',
    'pao-abobora': PLATE +
      '<rect x="96" y="96" width="128" height="44" rx="22" fill="#F2A65A"/>' +
      '<path d="M118 98 L134 138 M140 98 L156 138 M162 98 L178 138 M184 98 L200 138" stroke="#D17F2E" stroke-width="5" stroke-linecap="round"/>' +
      '<path d="M146 98 L130 138 M168 98 L152 138 M190 98 L174 138" stroke="#F8C27F" stroke-width="4" stroke-linecap="round"/>' +
      '<ellipse cx="160" cy="104" rx="52" ry="5" fill="#fff" opacity=".25"/>' +
      '<circle cx="250" cy="118" r="20" fill="#FFB347"/><circle cx="250" cy="118" r="16" fill="#FFC970"/><path d="M250 102 V134 M234 118 H266 M239 107 L261 129 M261 107 L239 129" stroke="#FFB347" stroke-width="2"/>' +
      '<rect x="56" y="122" width="40" height="8" rx="4" transform="rotate(-14 76 126)" fill="#8A4B2A"/>',
    'moqueca-banana': SHADOW +
      '<path d="M98 98 H222 C222 144 194 158 160 158 C126 158 98 144 98 98 Z" fill="#B5532F"/><ellipse cx="160" cy="98" rx="62" ry="12" fill="#8E3D20"/><ellipse cx="160" cy="98" rx="55" ry="9" fill="#F29A2E"/>' +
      '<circle cx="136" cy="97" r="7" fill="#FFD86B"/><circle cx="162" cy="101" r="7" fill="#FFD86B"/><circle cx="186" cy="96" r="7" fill="#FFD86B"/><circle cx="150" cy="94" r="5" fill="#FFF3D1"/><circle cx="174" cy="94" r="5" fill="#FFF3D1"/>' +
      '<circle cx="126" cy="100" r="4" fill="#4C9A3E"/><circle cx="198" cy="100" r="4" fill="#4C9A3E"/><circle cx="160" cy="92" r="4" fill="#4C9A3E"/>' +
      '<circle cx="95" cy="110" r="8" fill="none" stroke="#8E3D20" stroke-width="4"/><circle cx="225" cy="110" r="8" fill="none" stroke="#8E3D20" stroke-width="4"/>',
    'cuscuz-camarao': SHADOW +
      '<ellipse cx="160" cy="128" rx="92" ry="30" fill="#3B3B3F"/><rect x="244" y="122" width="52" height="10" rx="5" fill="#3B3B3F"/><ellipse cx="160" cy="124" rx="80" ry="23" fill="#F5D76E"/>' +
      '<circle cx="110" cy="122" r="3" fill="#E6B800"/><circle cx="196" cy="128" r="3" fill="#E6B800"/><circle cx="150" cy="136" r="3" fill="#E6B800"/><circle cx="212" cy="118" r="3" fill="#E6B800"/><circle cx="128" cy="134" r="3" fill="#E6B800"/>' +
      '<path transform="translate(116 112)" d="M0 0 C10 -14 28 -10 28 4 C20 -2 10 -2 0 8 Z" fill="#FF8A65"/>' +
      '<path transform="translate(150 120)" d="M0 0 C10 -14 28 -10 28 4 C20 -2 10 -2 0 8 Z" fill="#FF7A55"/>' +
      '<path transform="translate(182 110)" d="M0 0 C10 -14 28 -10 28 4 C20 -2 10 -2 0 8 Z" fill="#FF8A65"/>' +
      '<circle cx="140" cy="112" r="3" fill="#4C9A3E"/><circle cx="178" cy="124" r="3" fill="#4C9A3E"/><circle cx="214" cy="126" r="3" fill="#4C9A3E"/>',
    'cookie-grao': PLATE +
      '<circle cx="116" cy="124" r="28" fill="#6B4226"/><circle cx="170" cy="114" r="30" fill="#7A4C2D"/><circle cx="214" cy="134" r="24" fill="#6B4226"/>' +
      '<ellipse cx="108" cy="116" rx="5" ry="3.5" fill="#3B2314"/><ellipse cx="124" cy="132" rx="5" ry="3.5" fill="#3B2314"/><ellipse cx="162" cy="104" rx="5" ry="3.5" fill="#3B2314"/><ellipse cx="180" cy="122" rx="5" ry="3.5" fill="#3B2314"/><ellipse cx="208" cy="130" rx="4.5" ry="3" fill="#3B2314"/><ellipse cx="222" cy="140" rx="4.5" ry="3" fill="#3B2314"/>' +
      '<circle cx="252" cy="126" r="7" fill="#E3C48A"/><circle cx="264" cy="134" r="7" fill="#E3C48A"/><circle cx="250" cy="124" r="1.5" fill="#B89355"/><circle cx="262" cy="132" r="1.5" fill="#B89355"/>',
    'panqueca-beterraba': PLATE +
      '<ellipse cx="160" cy="124" rx="84" ry="32" fill="#C23B77"/><ellipse cx="160" cy="112" rx="72" ry="26" fill="#D2518A"/>' +
      '<ellipse cx="160" cy="104" rx="26" ry="14" fill="#FFFDF8"/><ellipse cx="160" cy="98" rx="16" ry="9" fill="#fff"/>' +
      '<path d="M116 114 q6 -10 14 -2 q-6 8 -14 2 Z" fill="#4C9A3E"/><path d="M196 112 q8 -10 14 0 q-8 8 -14 0 Z" fill="#4C9A3E"/><path d="M152 92 q6 -8 12 0 q-6 6 -12 0 Z" fill="#4C9A3E"/>'
  };
  function art(r, hidden){
    return '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 200" preserveAspectRatio="xMidYMid slice" ' +
      (hidden ? 'aria-hidden="true"' : 'role="img" aria-label="Ilustração: ' + r.nome + '"') + '>' + BG + ART[r.id] + '</svg>';
  }
  var CATS = ['Todas','Doces','Bolos','Salgados','Pães','Almoço','Fit'];
  var SLUG = {Doces:'doces', Bolos:'bolos', Salgados:'salgados', 'Pães':'paes', 'Almoço':'almoco', Fit:'fit'};
  var BY = {}; RECEITAS.forEach(function(r){ BY[r.id] = r; });

  var BRL = new Intl.NumberFormat('pt-BR', {style:'currency', currency:'BRL'});
  function money(c){ return BRL.format(c/100); }
  function $(s){ return document.querySelector(s); }

  var cart = [];
  var filter = 'Todas';
  var order = null;
  try {
    var saved = JSON.parse(localStorage.getItem('pdd-cart') || '[]');
    if (Array.isArray(saved)) cart = saved.filter(function(id){ return BY[id]; });
  } catch(e) {}
  function persist(){ try { localStorage.setItem('pdd-cart', JSON.stringify(cart)); } catch(e) {} }

  function totals(){
    var sub = cart.reduce(function(s,id){ return s + BY[id].preco; }, 0);
    var n = cart.length;
    var pct = n >= 5 ? 25 : (n >= 3 ? 15 : 0);
    var desc = Math.round(sub * pct / 100);
    return {n:n, sub:sub, pct:pct, desc:desc, total:sub-desc};
  }
  function plural(n, a, b){ return n + ' ' + (n === 1 ? a : b); }

  /* Catálogo */
  function renderChips(){
    $('#chips').innerHTML = CATS.map(function(c){
      var n = c === 'Todas' ? RECEITAS.length : RECEITAS.filter(function(r){ return r.cat === c; }).length;
      return '<button type="button" class="chip" data-cat="' + c + '" aria-pressed="' + (c === filter) + '">' + c + '<span>' + n + '</span></button>';
    }).join('');
  }
  function cardHtml(r){
    var inCart = cart.indexOf(r.id) > -1;
    return '<article class="card">' +
      '<button type="button" class="tile c-' + SLUG[r.cat] + '" data-open="' + r.id + '" aria-label="Ver detalhes: ' + r.nome + '">' +
        art(r, true) + '<span class="tag">' + r.cat + '</span></button>' +
      '<div class="card-body"><h3>' + r.nome + '</h3><p class="desc">' + r.desc + '</p>' +
      '<p class="meta">' + r.tempo + ' · ' + r.porcoes + ' · ' + r.nivel + '</p>' +
      '<div class="buy"><span class="price">' + money(r.preco) + '</span><span class="buy-actions">' +
        '<button type="button" class="btn btn-ghost" data-open="' + r.id + '">Detalhes</button>' +
        '<button type="button" class="btn ' + (inCart ? 'btn-outline' : 'btn-primary') + '" data-toggle="' + r.id + '">' + (inCart ? '✓ No carrinho' : 'Adicionar') + '</button>' +
      '</span></div></div></article>';
  }
  function renderGrid(){
    var list = RECEITAS.filter(function(r){ return filter === 'Todas' || r.cat === filter; });
    $('#grid').innerHTML = list.map(cardHtml).join('');
    $('#count').textContent = plural(list.length, 'receita', 'receitas');
  }

  /* Detalhe */
  function openDetail(id){
    var r = BY[id]; if (!r) return;
    var inCart = cart.indexOf(id) > -1;
    $('#detailBody').innerHTML =
      '<div class="d-tile c-' + SLUG[r.cat] + '">' + art(r, false) +
      '<button type="button" class="icon-btn d-close" data-close aria-label="Fechar">×</button></div>' +
      '<div class="d-body"><h2>' + r.nome + '</h2><p>' + r.desc + '</p>' +
      '<div class="d-meta"><span>' + r.tempo + '</span><span>' + r.porcoes + '</span><span>' + r.nivel + '</span></div>' +
      '<h3>O que vem no PDF</h3><ul class="d-list">' +
        '<li>Lista com ' + r.total + ' ingredientes e medidas</li>' +
        '<li>Passo a passo em ' + r.etapas + ' etapas</li>' +
        '<li>Dica da casa para dar certo</li></ul>' +
      '<h3>Uma prévia dos ingredientes</h3><ul class="d-list">' + r.ingr.map(function(i){ return '<li>' + i + '</li>'; }).join('') + '<li>e mais ' + (r.total - r.ingr.length) + ' no PDF</li></ul>' +
      '<div class="d-buy"><span class="price">' + money(r.preco) + '</span>' +
      '<button type="button" class="btn ' + (inCart ? 'btn-outline' : 'btn-primary') + '" data-toggle="' + r.id + '" data-keep>' + (inCart ? '✓ No carrinho' : 'Adicionar ao carrinho') + '</button></div></div>';
    openDlg($('#detail'));
  }

  function openDlg(d){ if (d.showModal) { if (!d.open) d.showModal(); } else d.setAttribute('open',''); }
  function closeDlg(d){ if (d.close) d.close(); else d.removeAttribute('open'); }

  /* Carrinho */
  function toggle(id){
    var i = cart.indexOf(id);
    if (i > -1) cart.splice(i,1); else cart.push(id);
    persist(); update();
  }
  function update(){
    var t = totals();
    $('#badge').textContent = t.n;
    var dock = $('#dock');
    dock.hidden = t.n === 0;
    $('#dockBtn').textContent = 'Ver carrinho · ' + plural(t.n, 'receita', 'receitas') + ' · ' + money(t.total);
    renderGrid();
    renderCart(t);
    if ($('#detail').open) {
      var b = $('#detailBody [data-toggle]');
      if (b) {
        var on = cart.indexOf(b.getAttribute('data-toggle')) > -1;
        b.className = 'btn ' + (on ? 'btn-outline' : 'btn-primary');
        b.textContent = on ? '✓ No carrinho' : 'Adicionar ao carrinho';
      }
    }
  }
  function renderCart(t){
    var has = t.n > 0;
    $('#cartEmpty').hidden = has;
    $('#buyerForm').hidden = !has;
    $('#genPix').hidden = !has;
    $('#sum').hidden = !has;
    $('#cartItems').innerHTML = cart.map(function(id){
      var r = BY[id];
      return '<li><span class="mini c-' + SLUG[r.cat] + '">' + art(r, true) + '</span>' +
        '<div class="info"><strong>' + r.nome + '</strong><small>' + r.cat + ' · ' + money(r.preco) + '</small></div>' +
        '<button type="button" class="btn btn-ghost" data-rm="' + id + '" aria-label="Remover ' + r.nome + '">Remover</button></li>';
    }).join('');
    var hint = $('#cartHint');
    if (!has) hint.hidden = true;
    else {
      hint.hidden = false;
      if (t.n < 3) hint.textContent = 'Leve mais ' + plural(3 - t.n, 'receita', 'receitas') + ' e ganhe 15% de desconto.';
      else if (t.n < 5) hint.textContent = '15% de desconto aplicado. Com mais ' + plural(5 - t.n, 'receita', 'receitas') + ' o desconto sobe para 25%.';
      else hint.textContent = 'Desconto máximo de 25% aplicado.';
    }
    var h = '<div><span>Subtotal</span><span>' + money(t.sub) + '</span></div>';
    if (t.pct) h += '<div class="off"><span>Desconto de ' + t.pct + '%</span><span>− ' + money(t.desc) + '</span></div>';
    h += '<div class="tot"><span>Total</span><span>' + money(t.total) + '</span></div>';
    $('#sum').innerHTML = h;
  }

  /* Pix (BR Code estático) */
  function tlv(id, val){ return id + String(val.length).padStart(2,'0') + val; }
  function crc16(str){
    var crc = 0xFFFF;
    for (var i = 0; i < str.length; i++) {
      crc ^= str.charCodeAt(i) << 8;
      for (var j = 0; j < 8; j++) { crc = (crc & 0x8000) ? ((crc << 1) ^ 0x1021) : (crc << 1); crc &= 0xFFFF; }
    }
    return crc.toString(16).toUpperCase().padStart(4,'0');
  }
  function clean(s, max){
    return s.normalize('NFD').replace(/[̀-ͯ]/g,'').replace(/[^A-Za-z0-9 ]/g,'').toUpperCase().slice(0,max).trim();
  }
  function pixPayload(key, nome, cidade, cents, txid){
    var mai = tlv('00','BR.GOV.BCB.PIX') + tlv('01', key);
    var p = tlv('00','01') + tlv('01','11') + tlv('26', mai) + tlv('52','0000') + tlv('53','986') +
      tlv('54', (cents/100).toFixed(2)) + tlv('58','BR') + tlv('59', clean(nome,25)) + tlv('60', clean(cidade,15)) +
      tlv('62', tlv('05', txid));
    p += '6304';
    return p + crc16(p);
  }
  function genId(){
    var a = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789', s = '';
    for (var i = 0; i < 6; i++) s += a[Math.floor(Math.random()*a.length)];
    return s;
  }
  function qrSvg(text){
    try {
      if (typeof qrcode !== 'function') return '';
      var q = qrcode(0,'M'); q.addData(text); q.make();
      return q.createSvgTag({cellSize:4, margin:0, scalable:true});
    } catch(e) { return ''; }
  }

  function validate(){
    var nome = $('#fNome').value.trim(), contato = $('#fContato').value.trim();
    var digits = contato.replace(/\D/g,'');
    var mail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(contato);
    if (nome.length < 2) return 'Digite seu nome.';
    if (!mail && digits.length < 10) return 'Digite um WhatsApp com DDD ou um e-mail válido.';
    return '';
  }

  function showPix(){
    var msg = validate();
    $('#formErr').textContent = msg;
    if (msg) { (msg.indexOf('nome') > -1 ? $('#fNome') : $('#fContato')).focus(); return; }
    var t = totals();
    var id = genId();
    var key = CONFIGURED ? CONFIG.pixKey : 'demo@exemplo.com';
    var nome = CONFIGURED ? CONFIG.pixNome : 'Panela de Domingo';
    var cidade = CONFIGURED ? CONFIG.pixCidade : 'Sao Paulo';
    var payload = pixPayload(key, nome, cidade, t.total, 'PDD' + id);
    order = {id:id, total:t.total, payload:payload};

    $('#orderId').textContent = '#' + id;
    $('#orderVal').textContent = money(t.total);
    $('#pixCode').value = payload;
    var svg = qrSvg(payload);
    $('#qrBox').innerHTML = svg;
    $('#qrBox').hidden = !svg;
    $('#demoNote').hidden = CONFIGURED;
    $('#copyBtn').textContent = 'Copiar código Pix';

    var nomes = cart.map(function(i){ return BY[i].nome; }).join(', ');
    var text = 'Olá! Fiz o pedido #' + id + ' na ' + CONFIG.loja + ' e paguei ' + money(t.total) + ' no Pix.\n' +
      'Receitas: ' + nomes + '\nNome: ' + $('#fNome').value.trim() + '\nContato: ' + $('#fContato').value.trim() + '\nSegue o comprovante:';
    var num = CONFIG.whatsapp.replace(/\D/g,'');
    $('#waLink').href = 'https://wa.me/' + (num ? num : '') + '?text=' + encodeURIComponent(text);

    $('#cTitle').textContent = 'Pagamento via Pix';
    $('#viewCart').hidden = true;
    $('#viewPix').hidden = false;
    $('#viewPix .scroll').scrollTop = 0;
  }
  function backToCart(){
    $('#cTitle').textContent = 'Seu carrinho';
    $('#viewPix').hidden = true;
    $('#viewCart').hidden = false;
  }
  function copyCode(){
    var ta = $('#pixCode'), btn = $('#copyBtn');
    function fail(){ ta.focus(); ta.select(); btn.textContent = 'Código selecionado: copie'; }
    try {
      navigator.clipboard.writeText(ta.value).then(function(){
        btn.textContent = '✓ Código copiado';
        setTimeout(function(){ btn.textContent = 'Copiar código Pix'; }, 2500);
      }, fail);
    } catch(e) { fail(); }
  }

  /* Eventos */
  document.addEventListener('click', function(e){
    var el = e.target.closest('[data-toggle],[data-open],[data-cat],[data-rm],[data-close]');
    if (!el) return;
    if (el.hasAttribute('data-toggle')) { toggle(el.getAttribute('data-toggle')); }
    else if (el.hasAttribute('data-open')) { openDetail(el.getAttribute('data-open')); }
    else if (el.hasAttribute('data-cat')) { filter = el.getAttribute('data-cat'); renderChips(); renderGrid(); }
    else if (el.hasAttribute('data-rm')) { toggle(el.getAttribute('data-rm')); }
    else if (el.hasAttribute('data-close')) { closeDlg(el.closest('dialog')); }
  });
  ['#detail','#cart'].forEach(function(s){
    $(s).addEventListener('click', function(e){ if (e.target === this) closeDlg(this); });
  });
  function openCart(){ backToCart(); openDlg($('#cart')); }
  $('#openCart').addEventListener('click', openCart);
  $('#dockBtn').addEventListener('click', openCart);
  $('#goMenu').addEventListener('click', function(){ $('#receitas').scrollIntoView({behavior:'smooth'}); });
  $('#genPix').addEventListener('click', showPix);
  $('#buyerForm').addEventListener('submit', function(e){ e.preventDefault(); showPix(); });
  $('#backBtn').addEventListener('click', backToCart);
  $('#copyBtn').addEventListener('click', copyCode);

  renderChips();
  update();
})();
</script>
</body>
</html>
