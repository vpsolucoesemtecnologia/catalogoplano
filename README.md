
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Catálogo Interativo de Funcionalidades</title>
  <style>
    body { background-color: #e8f4fd; font-family: Arial, sans-serif; margin: 0; padding: 0; }
    .container { display: flex; flex-wrap: wrap; max-width: 1200px; margin: 20px auto; }
    .features { flex: 1 1 60%; padding: 20px; }
    .features h1 { margin-bottom: 10px; }
    .features p { margin-bottom: 20px; }
    .two-columns { display: flex; gap: 20px; }
    .column { flex: 1; }
    .column label, .features .field { display: block; margin-bottom: 8px; }
    .field select { width: 100%; padding: 5px; margin-bottom: 16px; }
    .sidebar { flex: 1 1 35%; background: #ffffff; padding: 20px; margin: 20px; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); position: sticky; top: 20px; height: fit-content; }
    .sidebar h2 { margin-top: 0; text-align: center; }
    .plan-table { width: 100%; border-collapse: collapse; margin-top: 10px; }
    .plan-table th, .plan-table td { border: 1px solid #ccc; padding: 8px; text-align: center; }
    .plan-table th { background: #f4f4f4; }
    button { display: block; margin: 20px auto; padding: 10px 20px; font-size: 1em; cursor: pointer; }
  </style>
</head>
<body>
  <div class="container">
    <div class="features">
      <h1>Escolha você seu plano</h1>
      <p>Marque as funcionalidades que você precisa.</p>
      <div class="field">
        <label for="numUsers">Número de Usuários:</label>
        <select id="numUsers">
          <option value="-1">Selecione...</option>
          <option value="0">1 Plano Essencial</option>
          <option value="1">3 Plano Standard</option>
          <option value="2">Ilimitado Plano Premium</option>
        </select>
      </div>
      <div class="two-columns">
        <div class="column">
          <label><input type="checkbox" value="Dashboard"> Dashboard</label>
          <label><input type="checkbox" value="Boleto/Remessa"> Boleto/Remessa</label>
          <label><input type="checkbox" value="Orçamento"> Orçamento</label>
          <label><input type="checkbox" value="Pedido de Venda"> Pedido de Venda</label>
          <label><input type="checkbox" value="NFe, NFCe"> NFe, NFCe</label>
          <label><input type="checkbox" value="MFe"> MFe</label>
          <label><input type="checkbox" value="Minhas Notas"> Minhas Notas</label>
          <label><input type="checkbox" value="Portal do Contador"> Portal do Contador</label>
          <label><input type="checkbox" value="Aplicativo para NFCe"> Aplicativo para NFCe</label>
          <label><input type="checkbox" value="Fluxo de Caixa"> Fluxo de Caixa</label>
          <label><input type="checkbox" value="Contas a Receber"> Contas a Receber</label>
        </div>
        <div class="column">
          <label><input type="checkbox" value="Contas a Pagar"> Contas a Pagar</label>
          <label><input type="checkbox" value="Importação de XML"> Importação de XML</label>
          <label><input type="checkbox" value="Fator de Conversão"> Fator de Conversão</label>
          <label><input type="checkbox" value="Ordem de Compra"> Ordem de Compra</label>
          <label><input type="checkbox" value="Preço Atacado e Varejo"> Preço Atacado e Varejo</label>
          <label><input type="checkbox" value="Conversão CFOP"> Conversão CFOP</label>
          <label><input type="checkbox" value="Ordem de Serviço"> Ordem de Serviço</label>
          <label><input type="checkbox" value="Integração Mercado Livre"> Integração Mercado Livre</label>
          <label><input type="checkbox" value="WhatsApp"> WhatsApp</label>
          <label><input type="checkbox" value="Pré Venda Gerencial"> Pré Venda Gerencial</label>
        </div>
      </div>
    </div>
    <div class="sidebar">
      <h2>Seu Plano</h2>
      <table class="plan-table">
        <thead>
          <tr><th>Plano</th><th>Preço (R$)</th></tr>
        </thead>
        <tbody>
          <tr><td id="planName">-</td><td id="planPrice">-</td></tr>
        </tbody>
      </table>
      <button id="fileBtn" style="display:none;">Gerar arquivo de plano</button>
    </div>
  </div>

  <script>
    const planNames = ['Essencial', 'Standard', 'Premium'];
    const planPrices = [100, 140, 210];

    const planos = {
      0: ['Dashboard','Boleto/Remessa','Orçamento','Pedido de Venda','NFe, NFCe','MFe','Minhas Notas','Portal do Contador','Aplicativo para NFCe','Fluxo de Caixa','Contas a Receber'],
      1: ['Contas a Pagar','Importação de XML','Fator de Conversão','Ordem de Compra','Preço Atacado e Varejo','Conversão CFOP','Ordem de Serviço','Integração Mercado Livre','WhatsApp','Pré Venda Gerencial'],
      2: ['Tela PDV Frente de Caixa','Replicação de Dados','Parametrização de Tributos','Ecommerce','Tabelas de Preço','ZPOS','Cadastros Gerais','Cadastro de Kits','Fiscal - Perfil de Tributação','Suporte a Certificado A3','Tabela de Preço por Cliente','Etiquetas Personalizadas','Tabelas de Preço por Produto','Cadastro de Grades','Retaguarda Offline','Plano de Contas','DRE Simplificado','PIX Dinâmico: Banco Sicoob','Envio Automático para Contador','Boleto API: Banco Sicoob','Boleto API: Banco Inter','Boleto API: Banco Santander','Boleto API: Sicredi']
    };
    const featurePlan = {};
    Object.entries(planos).forEach(([planIdx, feats]) => {
      feats.forEach(f => {
        const idx = parseInt(planIdx);
        if (!(f in featurePlan) || idx < featurePlan[f]) featurePlan[f] = idx;
      });
    });

    const featureInputs = document.querySelectorAll('.features input[type=checkbox]');
    const numUsers = document.getElementById('numUsers');
    const planNameCell = document.getElementById('planName');
    const planPriceCell = document.getElementById('planPrice');
    const fileBtn = document.getElementById('fileBtn');
    let latestMessage = '';

    function calculatePlan() {
      let requiredPlan = 0;
      const selected = [];
      const nu = parseInt(numUsers.value);
      if (nu >= 0) {
        const userText = numUsers.options[numUsers.selectedIndex].text;
        selected.push(`Número de Usuários: ${userText}`);
        requiredPlan = Math.max(requiredPlan, nu);
      }
      featureInputs.forEach(i => {
        if (i.checked) {
          selected.push(i.value);
          const req = featurePlan[i.value] || 0;
          requiredPlan = Math.max(requiredPlan, req);
        }
      });
      const plan = planNames[requiredPlan];
      const price = planPrices[requiredPlan];
      planNameCell.textContent = plan;
      planPriceCell.textContent = price;
      latestMessage = `Plano ideal: ${plan} (R$ ${price})\nFuncionalidades: ${selected.join(', ')}`;
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
```
