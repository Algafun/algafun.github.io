<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Catálogo de Referrals</title>
  <style>
    body {
      font-family: 'Inter', sans-serif;
      background-color: #f3f4f6;
      margin: 0;
      padding: 0;
      color: #111827;
    }

    header {
      background: #2563eb;
      color: white;
      text-align: center;
      padding: 20px 0;
    }

    header h1 {
      margin: 0;
      font-size: 1.8rem;
    }

    .container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 20px;
      padding: 30px;
      max-width: 1200px;
      margin: auto;
    }

    .card {
      background: white;
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      transition: transform 0.3s, box-shadow 0.3s;
    }

    .card:hover {
      transform: translateY(-4px);
      box-shadow: 0 6px 15px rgba(0,0,0,0.15);
    }

    .card img {
      width: 100%;
      display: block;
    }

    .card-content {
      padding: 16px;
      text-align: center;
    }

    .card-content h3 {
      margin: 0 0 8px;
      font-size: 1.1rem;
      color: #1e3a8a;
    }

    .users {
      font-size: 0.9rem;
      color: #6b7280;
      margin-bottom: 10px;
    }

    .btn {
      display: inline-block;
      padding: 8px 14px;
      background: #2563eb;
      color: white;
      text-decoration: none;
      border-radius: 8px;
      font-weight: 600;
      transition: background 0.3s;
    }

    .btn:hover {
      background: #1d4ed8;
    }
  </style>
</head>
<body>
  <header>
    <h1>🌟 Meus Programas de Referral</h1>
    <p>Ganhe bônus e recompensas com os links abaixo!</p>
  </header>

  <div class="container" id="bannersContainer"></div>

  <script>
    // Lista de banners
    const banners = [
      {
        nome: "CryptoPay",
        usuarios: 18450,
        img: "https://i.imgur.com/xP7bM6X.jpg",
        link: "https://cryptopay.com/?ref=SEULINK"
      },
      {
        nome: "Wise",
        usuarios: 62000,
        img: "https://i.imgur.com/XHn3UPQ.jpg",
        link: "https://wise.com/invite?ref=SEULINK"
      },
      {
        nome: "Binance",
        usuarios: 210000,
        img: "https://i.imgur.com/h1z3JxF.jpg",
        link: "https://www.binance.com/?ref=SEULINK"
      },
      {
        nome: "Revolut",
        usuarios: 34000,
        img: "https://i.imgur.com/1P0U9Bt.jpg",
        link: "https://revolut.com/referral/SEULINK"
      },
      {
        nome: "Coinbase",
        usuarios: 88000,
        img: "https://i.imgur.com/CdW5XnS.jpg",
        link: "https://coinbase.com/join/SEULINK"
      }
    ];

    // Ordena por número de usuários (maior para menor)
    banners.sort((a, b) => b.usuarios - a.usuarios);

    // Gera os cards
    const container = document.getElementById("bannersContainer");
    container.innerHTML = banners.map(banner => `
      <div class="card">
        <a href="${banner.link}" target="_blank">
          <img src="${banner.img}" alt="${banner.nome}">
        </a>
        <div class="card-content">
          <h3>${banner.nome}</h3>
          <div class="users">${banner.usuarios.toLocaleString('pt-BR')} usuários</div>
          <a class="btn" href="${banner.link}" target="_blank">Acessar</a>
        </div>
      </div>
    `).join("");
  </script>
</body>
</html>
