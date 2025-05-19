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
    .features label, .features .field { display: block; margin-bottom: 8px; }
    .field select { width: 100%; padding: 5px; }
    #result { margin-top: 20px; font-size: 1.2em; text-align: center; }
    button { display: block; margin: 20px auto; padding: 10px 20px; font-size: 1em; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Escolha você seu plano</h1>
  <p>Marque as funcionalidades que você precisa. O plano ideal aparecerá automaticamente.</p>

  <form id="catalogForm">
    <div class="features">
      <label><input type="checkbox" value="Dashboard"> Dashboard</label>
      <label><input type="checkbox" value="Boleto/Remessa"> Boleto/Remessa</label>
      <div class="field">
        <label for="numUsers">Número de Usuários:</label>
        <select id="numUsers">
          <option value="0">Selecione...</option>
          <option value="0">01 - Essencial</option>
          <option value="1">02 - Standard</option>
          <option value="2">03 - Premium</option>
        </select>
      </div>
      <label><input type="checkbox" value="Orçamento"> Orçamento</label>
      <label><input type="checkbox" value="Pedido de Venda"> Pedido de Venda</label>
      <label><input type="checkbox" value="NFe, NFCe"> NFe, NFCe</label>
      <label><input type="checkbox" value="MFe"> MFe</label>
      <label><input type="checkbox" value="Minhas Notas"> Minhas Notas</label>
      <label><input type="checkbox" value="Portal do Contador"> Portal do Contador</label>
      <label><input type="checkbox" value="Aplicativo para NFCe"> Aplicativo para NFCe</label>
      <!-- demais checkboxes omitidos para brevidade, mantenha anteriores -->
    </div>
  </form>

  <div id="result"></div>
  <button id="fileBtn" style="display:none;">Gerar arquivo de plano</button>

  <script>
    const planNames = ['Essencial', 'Standard', 'Premium'];
    const planPrices = [100, 140, 210];

    // Mapear exigência mínima de plano para cada funcionalidade
    const planos = {
      0: ['Dashboard','Boleto/Remessa','Orçamento','Pedido de Venda','NFe, NFCe','MFe','Minhas Notas','Portal do Contador','Aplicativo para NFCe'],
      1: ['Fluxo de Caixa','Contas a Receber','Contas a Pagar','Importação de XML','Ordem de Compra','Boleto API: Banco Sicoob','Boleto API: Banco Inter','Boleto API: Banco Santander','Boleto API: Sicredi'],
      2: ['Integração Mercado Livre','WhatsApp','Pré Venda Gerencial','Tela PDV Frente de Caixa','Replicação de Dados','Parametrização de Tributos','Ecommerce','Tabelas de Preço','ZPOS','Cadastros Gerais','Cadastro de Kits','Fiscal - Perfil de Tributação','Suporte a Certificado A3','Tabela de Preço por Cliente','Etiquetas Personalizadas','Tabelas de Preço por Produto','Cadastro de Grades','Retaguarda Offline','Plano de Contas','DRE Simplificado','PIX Dinâmico: Banco Sicoob','Envio Automático para Contador']
    };
    const featurePlan = {};
    for (const [planIdx, feats] of Object.entries(planos)) {
      feats.forEach(f => {
        const idx = parseInt(planIdx);
        if (!(f in featurePlan) || idx < featurePlan[f]) featurePlan[f] = idx;
      });
    }

    const featureInputs = document.querySelectorAll('.features input[type=checkbox]');
    const numUsers = document.getElementById('numUsers');
    const resultDiv = document.getElementById('result');
    const fileBtn = document.getElementById('fileBtn');
    let latestMessage = '';

    function calculatePlan() {
      let requiredPlan = 0;
      const selected = [];

      // Checa número de usuários
      const nu = parseInt(numUsers.value);
      if (nu > 0) {
        selected.push(`Número de Usuários: ${['01','02','03'][nu]}`);
        requiredPlan = Math.max(requiredPlan, nu);
      }

      // Checa checkboxes
      featureInputs.forEach(i => {
        if (i.checked) {
          selected.push(i.value);
          const req = featurePlan[i.value] || 0;
          requiredPlan = Math.max(requiredPlan, req);
        }
      });

      const plan = planNames[requiredPlan];
      const price = planPrices[requiredPlan];

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

    numUsers.addEventListener('change', calculatePlan);
    featureInputs.forEach(i => i.addEventListener('change', calculatePlan));
    fileBtn.addEventListener('click', generateFile);
  </script>
</body>
</html>
