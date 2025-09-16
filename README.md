<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Contagem Regressiva para o Natal 🎅</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to right, #ff4e50, #f9d423);
      color: white;
      text-align: center;
      padding-top: 100px;
    }
    h1 {
      font-size: 3em;
    }
    #contador {
      font-size: 2em;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <h1>🎄 Faltam...</h1>
  <div id="contador">Carregando...</div>

  <script>
    function atualizarContagem() {
      const agora = new Date();
      let natal = new Date(agora.getFullYear(), 11, 25); // Dezembro é mês 11 (0-indexado)

      if (agora > natal) {
        natal = new Date(agora.getFullYear() + 1, 11, 25);
      }

      const diff = natal - agora;
      const dias = Math.floor(diff / (1000 * 60 * 60 * 24));
      const horas = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutos = Math.floor((diff / (1000 * 60)) % 60);
      const segundos = Math.floor((diff / 1000) % 60);

      document.getElementById("contador").innerHTML =
        `${dias} dias, ${horas} horas, ${minutos} minutos e ${segundos} segundos 🎁`;
    }

    setInterval(atualizarContagem, 1000);
    atualizarContagem();
  </script>
</body>
</html>
