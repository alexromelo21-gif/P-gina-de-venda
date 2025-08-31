<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Página de Vendas - Template</title>
  <!-- Fonte similar usada no modelo -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg-dark: #0a0a0a;
      --bg-light: #111111;
      --primary: #d4af37; /* dourado */
      --text: #ffffff;
      --text-muted: #cccccc;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: var(--bg-dark);
      color: var(--text);
      line-height: 1.6;
    }

    header {
      text-align: center;
      padding: 3rem 1rem;
      background: var(--bg-light);
    }

    header h1 {
      font-size: 2rem;
      font-weight: 700;
      color: var(--primary);
    }

    header p {
      font-size: 1.2rem;
      color: var(--text-muted);
      margin-top: 1rem;
    }

    .btn-primary {
      display: inline-block;
      margin-top: 2rem;
      padding: 1rem 2rem;
      background: var(--primary);
      color: var(--bg-dark);
      font-weight: 700;
      text-decoration: none;
      border-radius: 8px;
      transition: 0.3s;
    }

    .btn-primary:hover {
      opacity: 0.8;
    }

    section {
      padding: 4rem 1rem;
      max-width: 1000px;
      margin: auto;
    }

    .section-title {
      text-align: center;
      font-size: 1.8rem;
      font-weight: 600;
      margin-bottom: 2rem;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 2rem;
    }

    .card {
      background: var(--bg-light);
      padding: 2rem;
      border-radius: 12px;
      text-align: center;
    }

    .card h3 {
      color: var(--primary);
      margin-bottom: 1rem;
    }

    /* Contador regressivo */
    .countdown {
      display: flex;
      justify-content: center;
      gap: 1rem;
      margin: 2rem 0;
    }

    .time-box {
      background: var(--bg-light);
      padding: 1rem 1.5rem;
      border-radius: 10px;
      text-align: center;
    }

    .time-box span {
      display: block;
      font-size: 2rem;
      font-weight: 700;
      color: var(--primary);
    }

    .time-box small {
      font-size: 0.8rem;
      color: var(--text-muted);
    }

    footer {
      background: var(--bg-light);
      text-align: center;
      padding: 2rem;
      font-size: 0.9rem;
      color: var(--text-muted);
    }
  </style>
</head>
<body>

  <!-- Hero -->
  <header>
    <h1>Lorem ipsum dolor sit amet</h1>
    <p>Subtítulo ou promessa aqui</p>
    <a href="#" class="btn-primary">Call to Action</a>
  </header>

  <!-- Benefícios -->
  <section>
    <h2 class="section-title">Benefícios / Destaques</h2>
    <div class="grid-3">
      <div class="card">
        <h3>Benefício 1</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      </div>
      <div class="card">
        <h3>Benefício 2</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      </div>
      <div class="card">
        <h3>Benefício 3</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
      </div>
    </div>
  </section>

  <!-- Como funciona -->
  <section>
    <h2 class="section-title">Como Funciona</h2>
    <p style="text-align:center; max-width:700px; margin:auto;">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. 
      Praesent libero. Sed cursus ante dapibus diam.
    </p>
  </section>

  <!-- Oferta com contador -->
  <section>
    <h2 class="section-title">Oferta Especial</h2>

    <!-- Contador regressivo -->
    <div class="countdown" id="countdown">
      <div class="time-box">
        <span id="days">00</span>
        <small>Dias</small>
      </div>
      <div class="time-box">
        <span id="hours">00</span>
        <small>Horas</small>
      </div>
      <div class="time-box">
        <span id="minutes">00</span>
        <small>Min</small>
      </div>
      <div class="time-box">
        <span id="seconds">00</span>
        <small>Seg</small>
      </div>
    </div>

    <p style="text-align:center; font-size:1.5rem; color: var(--primary);">
      De R$XXX por apenas R$YYY
    </p>
    <div style="text-align:center;">
      <a href="#" class="btn-primary">Garantir Agora</a>
    </div>
  </section>

  <!-- Rodapé -->
  <footer>
    <p>© 2025 Sua Marca - Todos os direitos reservados</p>
  </footer>

  <!-- Script do contador -->
  <script>
    // Defina aqui a data de expiração (AAAA, MM -1, DD, HH, MM, SS)
    const endDate = new Date(2025, 8, 31, 23, 59, 59).getTime();

    const timer = setInterval(function () {
      const now = new Date().getTime();
      const distance = endDate - now;

      if (distance < 0) {
        clearInterval(timer);
        document.getElementById("countdown").innerHTML = "Oferta Expirada!";
        return;
      }

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      document.getElementById("days").innerText = days;
      document.getElementById("hours").innerText = hours;
      document.getElementById("minutes").innerText = minutes;
      document.getElementById("seconds").innerText = seconds;
    }, 1000);
  </script>
</body>
</html>