<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Catálogo Interativo de Funcionalidades</title>
  <style>
    body { background-color: #e8f4fd; font-family: Arial, sans-serif; max-width: 900px; margin: 20px auto; padding: 0 10px; }
    h1 { text-align: center; }
    .features { column-count: 2; column-gap: 40px; margin-top: 20px; }
    .features label { display: block; margin-bottom: 8px; }
    #result { margin-top: 20px; font-size: 1.2em; text-align: center; }
    button { display: block; margin: 20px auto; padding: 10px 20px; font-size: 1em; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Escolha você seu plano</h1>
  <p>Marque as funcionalidades que você precisa. O plano ideal aparecerá automaticamente.</p>

  <form id="catalogForm">
    <div class="features">
      <!-- Lista de funcionalidades em duas colunas -->
      <label><input type="checkbox" value="Dashboard"> Dashboard</label>
      <!-- restante das funcionalidades omitidas para brevidade -->
    </div>
  </form>

  <div id="result"></div>
  <button id="fileBtn" style="display:none;">Gerar arquivo de plano</button>

  <script>
    const essentialPrice = 100;
    const standardPrice = 140;
    const premiumPrice = 210;

    const premiumFeatures = [
      "Mercado Livre","Ecommerce","Parametrização de Tributos","ZPOS","PIX Dinâmico Sicoob",
      "Envio Automático Contador"
    ];
    const standardFeatures = [
      "Fluxo de Caixa","Contas a Receber","Contas a Pagar","Importação de XML",
      "Ordem de Compra"
    ];

    const featureInputs = document.querySelectorAll('.features input[type=checkbox]');
    const resultDiv = document.getElementById('result');
    const fileBtn = document.getElementById('fileBtn');
    let latestMessage = '';

    function calculatePlan() {
      const selected = Array.from(featureInputs)
        .filter(i => i.checked)
        .map(i => i.value);

      let plan = 'Essencial';
      let price = essentialPrice;

      if (selected.some(f => premiumFeatures.includes(f))) {
        plan = 'Premium';
        price = premiumPrice;
      } else if (selected.some(f => standardFeatures.includes(f))) {
        plan = 'Standard';
        price = standardPrice;
      }

      latestMessage = `Plano ideal: ${plan} (R$ ${price})\nFuncionalidades: ${selected.join(', ')}`;
      resultDiv.innerHTML = `<p>${latestMessage.replace(/\n/g,'<br>')}</p>`;

      fileBtn.style.display = selected.length ? 'block' : 'none';
    }

    function generateFile() {
      const blob = new Blob([latestMessage], { type: 'text/plain' });
      const link = document.createElement('a');
      link.href = URL.createObjectURL(blob);
      link.download = 'plano.txt';
      link.click();
    }

    featureInputs.forEach(i => i.addEventListener('change', calculatePlan));
    fileBtn.addEventListener('click', generateFile);
  </script>
</body>
</html>
