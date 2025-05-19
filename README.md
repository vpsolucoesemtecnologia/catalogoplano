<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Catálogo Interativo de Funcionalidades</title>
  <style>
    body { font-family: Arial, sans-serif; max-width: 900px; margin: 20px auto; padding: 0 10px; }
    h1 { text-align: center; }
    table { width: 100%; border-collapse: collapse; margin-top: 20px; }
    th, td { border: 1px solid #ccc; padding: 8px; text-align: left; }
    th { background: #f4f4f4; }
    #result { margin-top: 20px; font-size: 1.2em; text-align: center; }
    button { display: block; margin: 20px auto; padding: 10px 20px; font-size: 1em; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Escolha suas Funcionalidades</h1>
  <p>Marque as funcionalidades que você precisa. O plano ideal aparecerá automaticamente.</p>

  <form id="catalogForm">
    <table>
      <tr><th>Selecionar</th><th>Funcionalidade</th></tr>
      <!-- Linha de cada funcionalidade -->
      <tr><td><input type="checkbox" value="Dashboard"></td><td>Dashboard</td></tr>
      <tr><td><input type="checkbox" value="Boleto/Remessa"></td><td>Boleto/Remessa</td></tr>
      <tr><td><input type="checkbox" value="Número de Usuários"></td><td>Número de Usuários</td></tr>
      <tr><td><input type="checkbox" value="Orçamento"></td><td>Orçamento</td></tr>
      <tr><td><input type="checkbox" value="Pedido de Venda"></td><td>Pedido de Venda</td></tr>
      <tr><td><input type="checkbox" value="NFe, NFCe"></td><td>NFe, NFCe</td></tr>
      <tr><td><input type="checkbox" value="MFe"></td><td>MFe</td></tr>
      <tr><td><input type="checkbox" value="Minhas Notas"></td><td>Minhas Notas</td></tr>
      <tr><td><input type="checkbox" value="Portal do Contador"></td><td>Portal do Contador</td></tr>
      <tr><td><input type="checkbox" value="Aplicativo para NFCe"></td><td>Aplicativo para NFCe</td></tr>
      <tr><td><input type="checkbox" value="Fluxo de Caixa"></td><td>Fluxo de Caixa</td></tr>
      <tr><td><input type="checkbox" value="Contas a Receber"></td><td>Contas a Receber</td></tr>
      <tr><td><input type="checkbox" value="Contas a Pagar"></td><td>Contas a Pagar</td></tr>
      <tr><td><input type="checkbox" value="Importação de XML"></td><td>Importação de XML</td></tr>
      <tr><td><input type="checkbox" value="Fator de Conversão"></td><td>Fator de Conversão</td></tr>
      <tr><td><input type="checkbox" value="Ordem de Compra"></td><td>Ordem de Compra</td></tr>
      <tr><td><input type="checkbox" value="Preço Atacado e Varejo"></td><td>Preço Atacado e Varejo</td></tr>
      <tr><td><input type="checkbox" value="Conversão CFOP"></td><td>Conversão CFOP</td></tr>
      <tr><td><input type="checkbox" value="Ordem de Serviço"></td><td>Ordem de Serviço</td></tr>
      <tr><td><input type="checkbox" value="Mercado Livre"></td><td>Integração Mercado Livre</td></tr>
      <tr><td><input type="checkbox" value="WhatsApp"></td><td>WhatsApp</td></tr>
      <tr><td><input type="checkbox" value="Pré Venda Gerencial"></td><td>Pré Venda Gerencial</td></tr>
      <tr><td><input type="checkbox" value="Tela PDV Frente de Caixa"></td><td>Tela PDV Frente de Caixa</td></tr>
      <tr><td><input type="checkbox" value="Replicação de Dados"></td><td>Replicação de Dados</td></tr>
      <tr><td><input type="checkbox" value="Parametrização de Tributos"></td><td>Parametrização de Tributos</td></tr>
      <tr><td><input type="checkbox" value="Ecommerce"></td><td>Ecommerce</td></tr>
      <tr><td><input type="checkbox" value="Tabelas de Preço"></td><td>Tabelas de Preço</td></tr>
      <tr><td><input type="checkbox" value="ZPOS"></td><td>ZPOS: Integração com Vero, Stone, Rede, PagSeguro, Cielo, Sicredi, Caixa e BIN</td></tr>
      <tr><td><input type="checkbox" value="Cadastros Gerais"></td><td>Cadastros: Clientes, Fornecedores, Transportadoras, Produtos</td></tr>
      <tr><td><input type="checkbox" value="Cadastro de Kits"></td><td>Cadastro de Kits</td></tr>
      <tr><td><input type="checkbox" value="Fiscal Perfil de Tributação"></td><td>Fiscal - Perfil de Tributação</td></tr>
      <tr><td><input type="checkbox" value="Suporte Certificado A3"></td><td>Suporte a Certificado A3</td></tr>
      <tr><td><input type="checkbox" value="Tabela de Preço por Cliente"></td><td>Tabela de Preço por Cliente</td></tr>
      <tr><td><input type="checkbox" value="Etiquetas Personalizadas"></td><td>Etiquetas Personalizadas</td></tr>
      <tr><td><input type="checkbox" value="Tabelas de Preço por Produto"></td><td>Tabelas de Preço por Produto</td></tr>
      <tr><td><input type="checkbox" value="Cadastro de Grades"></td><td>Cadastro de Grades</td></tr>
      <tr><td><input type="checkbox" value="Retaguarda Offline"></td><td>Retaguarda Offline (plugin nativo para SC)</td></tr>
      <tr><td><input type="checkbox" value="Boleto API Sicoob"></td><td>Boleto API: Banco Sicoob</td></tr>
      <tr><td><input type="checkbox" value="Boleto API Inter"></td><td>Boleto API: Banco Inter</td></tr>
      <tr><td><input type="checkbox" value="Boleto API Santander"></td><td>Boleto API: Banco Santander</td></tr>
      <tr><td><input type="checkbox" value="Boleto API Sicredi"></td><td>Boleto API: Banco Sicredi</td></tr>
      <tr><td><input type="checkbox" value="Plano de Contas"></td><td>Plano de Contas</td></tr>
      <tr><td><input type="checkbox" value="DRE Simplificado"></td><td>DRE Simplificado</td></tr>
      <tr><td><input type="checkbox" value="PIX Dinâmico Sicoob"></td><td>PIX Dinâmico: Banco Sicoob</td></tr>
      <tr><td><input type="checkbox" value="Envio Automático Contador"></td><td>Envio Automático para Contador (XML de Saída/Entrada, Sintegra e SPED)</td></tr>
    </table>
  </form>

  <div id="result"></div>
  <button id="whatsappBtn" style="display:none;">Enviar no WhatsApp</button>

  <script>
    const essentialPrice = 100;
    const standardPrice = 140;
    const premiumPrice = 210;

    // Mapear funcionalidades a planos
    const premiumFeatures = [
      "Mercado Livre","Ecommerce","Parametrização de Tributos","ZPOS","PIX Dinâmico Sicoob",
      "Envio Automático Contador"
    ];
    const standardFeatures = [
      "Fluxo de Caixa","Contas a Receber","Contas a Pagar","Importação de XML",
      "Ordem de Compra"
    ];

    const featureInputs = document.querySelectorAll('table input[type=checkbox]');
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
        whatsappBtn.style.display = 'block';
        whatsappBtn.onclick = () => window.open(url, '_blank');
      } else {
        whatsappBtn.style.display = 'none';
      }
    }

    featureInputs.forEach(i => i.addEventListener('change', calculatePlan));
  </script>
</body>
</html>
