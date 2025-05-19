
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
      <label><input type="checkbox" value="Dashboard"> Dashboard</label>
      <label><input type="checkbox" value="Boleto/Remessa"> Boleto/Remessa</label>
      <label><input type="checkbox" value="Número de Usuários"> Número de Usuários</label>
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
      <label><input type="checkbox" value="Retaguarda Offline"> Retaguarda Offline (plugin nativo para SC)</label>
      <label><input type="checkbox" value="Boleto API: Banco Sicoob"> Boleto API: Banco Sicoob</label>      
      <label><input type="checkbox" value="Boleto API: Banco Inter"> Boleto API: Banco Inter</label>
      <label><input type="checkbox" value="Boleto API: Banco Santander"> Boleto API: Banco Santander</label>
      <label><input type="checkbox" value="Boleto API: Sicredi"> Boleto API: Sicredi</label>
      <label><input type="checkbox" value="Plano de Contas"> Plano de Contas</label>
      <label><input type="checkbox" value="DRE Simplificado"> DRE Simplificado</label>
      <label><input type="checkbox" value="PIX Dinâmico: Banco Sicoob"> PIX Dinâmico: Banco Sicoob</label>
      <label><input type="checkbox" value="Envio Automático para Contador (XML de Saída/Entrada, Sintegra e SPED)"> Envio Automático para Contador (XML de Saída/Entrada, Sintegra e SPED)</label>
    </div>
  </form>

  <div id="result"></div>
  <button id="fileBtn" style="display:none;">Gerar arquivo de plano</button>

  <script>
    const essentialPrice = 100;
    const standardPrice = 140;
    const premiumPrice = 210;

    const premiumFeatures = [
      "Integração Mercado Livre",
      "Ecommerce",
      "Parametrização de Tributários",
      "ZPOS",
      "PIX Dinâmico: Banco Sicoob",
      "Envio Automático para Contador (XML de Saída/Entrada, Sintegra e SPED)"
    ];
    const standardFeatures = [
      "Fluxo de Caixa",
      "Contas a Receber",
      "Contas a Pagar",
      "Importação de XML",
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

      latestMessage = `Plano ideal: ${plan} (R$ ${price})\\nFuncionalidades: ${selected.join(', ')}`;
      resultDiv.innerHTML = `<p>${latestMessage.replace(/\\n/g,'<br>')}</p>`;

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
