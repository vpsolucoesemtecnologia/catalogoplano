<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Catálogo Interativo de Funcionalidades</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 800px; margin: 20px auto; padding: 0 10px; }
    h1, h2 { text-align: center; }
    .feature-list { list-style: none; padding: 0; }
    .feature-list li { margin-bottom: 5px; }
    #result { margin-top: 20px; font-size: 1.2em; }
    button { padding: 10px 20px; font-size: 1em; margin-top: 10px; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Escolha suas Funcionalidades</h1>
  <p>Marque as funcionalidades que você precisa. O plano ideal aparecerá automaticamente.</p>

  <ul class="feature-list" id="features">
    <li><label><input type="checkbox" value="Dashboard"> Dashboard</label></li>
    <li><label><input type="checkbox" value="Orçamento"> Orçamento</label></li>
    <li><label><input type="checkbox" value="Pedido de Venda"> Pedido de Venda</label></li>
    <li><label><input type="checkbox" value="NFe/NFCe"> NFe/NFCe</label></li>
    <li><label><input type="checkbox" value="Fluxo de Caixa"> Fluxo de Caixa</label></li>
    <li><label><input type="checkbox" value="Contas a Receber"> Contas a Receber</label></li>
    <li><label><input type="checkbox" value="Contas a Pagar"> Contas a Pagar</label></li>
    <li><label><input type="checkbox" value="Importação de XML"> Importação de XML</label></li>
    <li><label><input type="checkbox" value="Ordem de Compra"> Ordem de Compra</label></li>
    <li><label><input type="checkbox" value="Mercado Livre"> Integração Mercado Livre</label></li>
    <li><label><input type="checkbox" value="Ecommerce"> Ecommerce</label></li>
    <li><label><input type="checkbox" value="Parametrização de Tributos"> Parametrização de Tributos</label></li>
    <li><label><input type="checkbox" value="ZPOS"> Integração ZPOS</label></li>
    <li><label><input type="checkbox" value="PIX Dinâmico"> PIX Dinâmico</label></li>
    <li><label><input type="checkbox" value="Envio automático para contador"> Envio automático para contador</label></li>
  </ul>

  <div id="result"></div>
  <button id="whatsappBtn" style="display:none;">Enviar no WhatsApp</button>

  <script>
    const essentialPrice = 100;
    const standardPrice = 140;
    const premiumPrice = 210;

    const premiumFeatures = [
      "Mercado Livre",
      "Ecommerce",
      "Parametrização de Tributos",
      "ZPOS",
      "PIX Dinâmico",
      "Envio automático para contador"
    ];
    const standardFeatures = [
      "Fluxo de Caixa",
      "Contas a Receber",
      "Contas a Pagar",
      "Importação de XML",
      "Ordem de Compra"
    ];

    const featureInputs = document.querySelectorAll('#features input');
    const resultDiv = document.getElementById('result');
    const whatsappBtn = document.getElementById('whatsappBtn');

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

      resultDiv.innerHTML = `<p>Plano ideal: <strong>${plan}</strong> (R$ ${price})</p>`;

      if (selected.length) {
        const message = `Olá, preciso do plano ${plan} (R$ ${price}) com as seguintes funcionalidades: ${selected.join(', ')}.`;
        const url = `https://wa.me/558496115650?text=${encodeURIComponent(message)}`;
        whatsappBtn.style.display = 'inline-block';
        whatsappBtn.onclick = () => window.open(url);
      } else {
        whatsappBtn.style.display = 'none';
      }
    }

    featureInputs.forEach(i => i.addEventListener('change', calculatePlan));
  </script>
</body>
</html>
