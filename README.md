
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
    .two-columns { display: flex; gap: 20px; margin-bottom: 20px; }
    .column { flex: 1; }
    .column label { display: block; margin-bottom: 8px; }
    .sidebar { flex: 1 1 35%; background: #fff; padding: 20px; margin: 20px; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); position: sticky; top: 20px; }
    .sidebar h2 { margin-top: 0; text-align: center; }
    .plan-table { width: 100%; border-collapse: collapse; margin-top: 10px; }
    .plan-table th, .plan-table td { border: 1px solid #ccc; padding: 8px; text-align: center; }
    .plan-table th { background: #f4f4f4; }
    .selected-list { margin-top: 20px; }
    .selected-list h3 { margin: 0 0 10px; font-size: 1em; }
    .selected-list ul { list-style: none; padding: 0; max-height: 200px; overflow-y: auto; }
    .selected-list li { background: #f9f9f9; margin-bottom: 4px; padding: 6px; border-radius: 4px; font-size: 0.9em; }
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
          <option value="0">1 - Essencial</option>
          <option value="1" selected>3 - Standard</option>
          <option value="2">Ilimitado - Premium</option>
        </select>
      </div>
      <div class="two-columns">
        <div class="column">
          <!-- Coluna 1 -->
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
        </div>
        <div class="column">
          <!-- Coluna 2 -->
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
        </div>
      </div>
      <div class="two-columns">
        <div class="column">
          <label><input type="checkbox" value="ZPOS"> ZPOS</label>
          <label><input type="checkbox" value="Cadastros Gerais"> Cadastros
          </label>
          <label><input type="checkbox" value="Cadastro de Kits"> Cadastro de Kits</label>
          <label><input type="checkbox" value="Fiscal - Perfil de Tributação"> Fiscal - Perfil de Tributação</label>
          <label><input type="checkbox" value="Suporte a Certificado A3"> Suporte a Certificado A3</label>
          <label><input type="checkbox" value="Tabela de Preço por Cliente"> Tabela de Preço por Cliente</label>
          <label><input type="checkbox" value="Etiquetas Personalizadas"> Etiquetas Personalizadas</label>
          <label><input type="checkbox" value="Tabelas de Preço por Produto"> Tabelas de Preço por Produto</label>
        </div>
        <div class="column">
          <label><input type="checkbox" value="Cadastro de Grades"> Cadastro de Grades</label>
          <label><input type="checkbox" value="Retaguarda Offline"> Retaguarda Offline</label>
          <label><input type="checkbox" value="Plano de Contas"> Plano de Contas</label>
          <label><input type="checkbox" value="DRE Simplificado"> DRE Simplificado</label>
          <label><input type="checkbox" value="PIX Dinâmico: Banco Sicoob"> PIX Dinâmico</label>
          <label><input type="checkbox" value="Envio Automático para Contador"> Envio Automático para Contador</label>
          <label><input type="checkbox" value="Boleto API: Banco Sicoob"> Boleto Sicoob</label>
          <label><input type="checkbox" value="Boleto API: Banco Inter"> Boleto Inter</label>
          <label><input type="checkbox" value="Boleto API: Banco Santander"> Boleto Santander</label>
          <label><input type="checkbox" value="Boleto API: Sicredi"> Boleto Sicredi</label>
        </div>
      </div>
    </div>
    <div class="sidebar">
      <h2>Seu Plano</h2>
      <table class="plan-table">
        <thead><tr><th>Plano</th><th>Preço (R$)</th></tr></thead>
        <tbody><tr><td id="planName">-</td><td id="planPrice">-</td></tr></tbody>
      </table>
      <div class="selected-list">
        <h3>Funcionalidades Selecionadas:</h3>
        <ul id="selectedList"></ul>
      </div>
      <button id="whatsappBtn" class="whatsapp-btn" style="display:none;">Enviar no WhatsApp</button>
    </div>
  </div>
  <script>
    // Inicializa seleção e cálculo com Standard
    window.addEventListener('DOMContentLoaded', () => { document.getElementById('numUsers').value = '1'; update(); });
    const planNames=['Essencial','Standard','Premium'],planPrices=[100,140,210];
    const planos={
      0:['Dashboard','Boleto/Remessa','Orçamento','Pedido de Venda','NFe, NFCe','MFe','Minhas Notas','Portal do Contador','Aplicativo para NFCe','Fluxo de Caixa','Contas a Receber','Contas a Pagar','Importação de XML','Fator de Conversão','Ordem de Compra','Preço Atacado e Varejo','Conversão CFOP'],
      1:['Ordem de Serviço','Integração Mercado Livre','WhatsApp','Pré Venda Gerencial','Tela PDV Frente de Caixa','Replicação de Dados','Parametrização de Tributos','Ecommerce','Tabelas de Preço','ZPOS','Cadastros Gerais','Cadastro de Kits','Fiscal - Perfil de Tributação','Suporte a Certificado A3','Tabela de Preço por Cliente','Etiquetas Personalizadas','Tabelas de Preço por Produto','Cadastro de Grades','Retaguarda Offline','Plano de Contas','DRE Simplificado','Boleto Sicoob','Boleto Inter','Boleto Santander','Boleto Sicredi','PIX Dinâmico: Banco Sicoob','Envio Automático para Contador'],
      2:[]
    };
    const featurePlan={};Object.entries(planos).forEach(([pi,fe])=>fe.forEach(f=>featurePlan[f]=+pi));
    const inputs=document.querySelectorAll('.features input[type=checkbox]'),numUsers=document.getElementById('numUsers'),planNameCell=document.getElementById('planName'),planPriceCell=document.getElementById('planPrice'),selectedList=document.getElementById('selectedList'),whatsappBtn=document.getElementById('whatsappBtn');let msg='';
    function update(){let rp=0,sel=[];const nu=parseInt(numUsers.value);if(nu>=0){sel.push(`Número de Usuários: ${numUsers.options[numUsers.selectedIndex].text}`);rp=Math.max(rp,nu)};inputs.forEach(i=>{if(i.checked){sel.push(i.value);rp=Math.max(rp,featurePlan[i.value]||0)}});const p=planNames[rp],pr=planPrices[rp];planNameCell.textContent=p;planPriceCell.textContent=pr;selectedList.innerHTML=sel.map(s=>`<li>${s}</li>`).join('');msg=`Olá, gostaria do plano ${p} (R$ ${pr}) com: ${sel.join(', ')}`;whatsappBtn.style.display=sel.length?'block':'none'}
    function send(){window.open(`https://wa.me/558496115650?text=${encodeURIComponent(msg)}`,'_blank')}
    numUsers.addEventListener('change',update);inputs.forEach(i=>i.addEventListener('change',update));whatsappBtn.addEventListener('click',send);
  </script>
</body>
</html>
