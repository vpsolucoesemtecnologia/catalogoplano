
<html lang="pt-BR">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Catálogo Interativo de Funcionalidades</title>
  <style>
    body { background-color: #e8f4fd; font-family: Arial, sans-serif; margin: 0; padding: 0; }
    .container { display: flex; flex-wrap: wrap; max-width: 1200px; margin: 20px auto; }
    .features { flex: 1 1 60%; padding: 20px; }
    .features h1 { margin-bottom: 10px; }
    .features p { margin-bottom: 20px; }
    .field { margin-bottom: 16px; }
    .field select { width: 100%; padding: 5px; }
    .two-columns { display: flex; gap: 20px; }
    .column { flex: 1; }
    .column label { display: block; margin-bottom: 8px; }
    .sidebar { flex: 1 1 35%; background: #fff; padding: 20px; margin: 20px; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); position: sticky; top: 20px; }
    .sidebar h2 { margin-top: 0; text-align: center; }
    .plan-table { width: 100%; border-collapse: collapse; margin-top: 10px; }
    .plan-table th, .plan-table td { border: 1px solid #ccc; padding: 8px; text-align: center; }
    .plan-table th { background: #f4f4f4; }
    .whatsapp-btn { display: block; width: 100%; text-align: center; margin-top: 20px; padding: 10px; background: #25D366; color: #fff; border: none; border-radius: 4px; font-size: 1em; cursor: pointer; }
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
          <option value="0">1 - Essencial</option>
          <option value="1">3 - Standard</option>
          <option value="2">Ilimitado - Premium</option>
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
          <label><input type="checkbox" value="Contas a Pagar"> Contas a Pagar</label>
          <label><input type="checkbox" value="Importação de XML"> Importação de XML</label>
          <label><input type="checkbox" value="Fator de Conversão"> Fator de Conversão</label>
          <label><input type="checkbox" value="Ordem de Compra"> Ordem de Compra</label>
          <label><input type="checkbox" value="Preço Atacado e Varejo"> Preço Atacado e Varejo</label>
          <label><input type="checkbox" value="Conversão CFOP"> Conversão CFOP</label>
        </div>
        <div class="column">
          <label><input type="checkbox" value="Ordem de Serviço"> Ordem de Serviço</label>
          <label><input type="checkbox" value="Integração Mercado Livre"> Integração Mercado Livre</label>
          <label><input type="checkbox" value="WhatsApp"> WhatsApp</label>
          <label><input type="checkbox" value="Pré Venda Gerencial"> Pré Venda Gerencial</label>
          <label><input type="checkbox" value="Tela PDV Frente de Caixa"> Tela PDV Frente de Caixa</label>
          <label><input type="checkbox" value="Replicação de Dados"> Replicação de Dados</label>
          <label><input type="checkbox" value="Parametrização de Tributos"> Parametrização de Tributos</label>
          <label><input type="checkbox" value="Ecommerce"> Ecommerce</label>
          <label><input type="checkbox" value="Tabelas de Preço"> Tabelas de Preço</label>
          <label><input type="checkbox" value="ZPOS"> ZPOS: Integração Vero, Stone, Rede, PagSeguro, Cielo, Sicredi, Caixa e BIN</label>
          <label><input type="checkbox" value="Cadastros Gerais"> Cadastros: Clientes, Fornecedores, Transportadoras, Produtos</label>
          <label><input type="checkbox" value="Cadastro de Kits"> Cadastro de Kits</label>
          <label><input type="checkbox" value="Fiscal - Perfil de Tributação"> Fiscal - Perfil de Tributação</label>
          <label><input type="checkbox" value="Suporte a Certificado A3"> Suporte a Certificado A3</label>
          <label><input type="checkbox" value="Tabela de Preço por Cliente"> Tabela de Preço por Cliente</label>
          <label><input type="checkbox" value="Etiquetas Personalizadas"> Etiquetas Personalizadas</label>
          <label><input type="checkbox" value="Tabelas de Preço por Produto"> Tabelas de Preço por Produto</label>
          <label><input type="checkbox" value="Cadastro de Grades"> Cadastro de Grades</label>
          <label><input type="checkbox" value="Retaguarda Offline"> Retaguarda Offline</label>
          <label><input type="checkbox" value="Boleto API: Banco Sicoob"> Boleto API Sicoob</label>
          <label><input type="checkbox" value="Boleto API: Banco Inter"> Boleto API Inter</label>
          <label><input type="checkbox" value="Boleto API: Banco Santander"> Boleto API Santander</label>
          <label><input type="checkbox" value="Boleto API: Sicredi"> Boleto API Sicredi</label>
          <label><input type="checkbox" value="Plano de Contas"> Plano de Contas</label>
          <label><input type="checkbox" value="DRE Simplificado"> DRE Simplificado</label>
          <label><input type="checkbox" value="PIX Dinâmico: Banco Sicoob"> PIX Dinâmico Sicoob</label>
          <label><input type="checkbox" value="Envio Automático para Contador"> Envio Automático para Contador</label>
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
      <button id="whatsappBtn" class="whatsapp-btn" style="display:none;">Enviar no WhatsApp</button>
    </div>
  </div>

  <script>
    const planNames = ['Essencial', 'Standard', 'Premium'];
    const planPrices = [100, 140, 210];

    const planos = {
      0: [
        'Dashboard','Boleto/Remessa','Orçamento','Pedido de Venda','NFe, NFCe','MFe','Minhas Notas','Portal do Contador','Aplicativo para NFCe','Fluxo de Caixa','Contas a Receber','Contas a Pagar','Importação de XML','Fator de Conversão','Ordem de Compra','Preço Atacado e Varejo','Conversão CFOP'
      ],
      1: [
        'Ordem de Serviço','Integração Mercado Livre','WhatsApp','Pré Venda Gerencial','Tela PDV Frente de Caixa','Replicação de Dados','Parametrização de Tributos','Ecommerce','Tabelas de Preço','ZPOS','Cadastros Gerais','Cadastro de Kits','Fiscal - Perfil de Tributação','Suporte a Certificado A3','Tabela de Preço por Cliente','Etiquetas Personalizadas','Tabelas de Preço por Produto','Cadastro de Grades','Retaguarda Offline','Boleto API: Banco Sicoob','Boleto API: Banco Inter','Boleto API: Banco Santander','Boleto API: Sicredi','Plano de Contas','DRE Simplificado','PIX Dinâmico: Banco Sicoob','Envio Automático para Contador'
      ],
      2: []
    };

    const featurePlan = {};
    Object.entries(planos).forEach(([planIdx, feats]) => {
      feats.forEach(f => {
        featurePlan[f] = parseInt(planIdx);
      });
    });

    const featureInputs = document.querySelectorAll('.features input[type=checkbox]');
    const numUsers = document.getElementById('numUsers');
    const planNameCell = document.getElementById('planName');
    const planPriceCell = document.getElementById('planPrice');
    const whatsappBtn = document.getElementById('whatsappBtn');
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

      latestMessage = `Olá, gostaria do plano ${plan} (R$ ${price}) com as seguintes funcionalidades: ${selected.join(', ')}`;
      whatsappBtn.style.display = selected.length ? 'block' : 'none';
    }

    function sendWhatsApp() {
      const url = `https://wa.me/558496115650?text=${encodeURIComponent(latestMessage)}`;
      window.open(url, '_blank');
    }

    numUsers.addEventListener('change', calculatePlan);
    featureInputs.forEach(i => i.addEventListener('change', calculatePlan));
    whatsappBtn.addEventListener('click', sendWhatsApp);
  </script>
</body>
</html>
