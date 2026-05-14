<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Calculadora VGV · Rio de Janeiro</title>
<style>
:root {
  --bg: #F5F4F0; --surface: #FFFFFF; --surface2: #EEEDE9;
  --border: rgba(0,0,0,0.09); --border-md: rgba(0,0,0,0.15);
  --text: #1A1A18; --text-muted: #6B6B67; --text-hint: #9C9C98;
  --green: #0F6E56; --green-bg: #E1F5EE; --green-text: #085041;
  --blue: #185FA5; --blue-bg: #E6F1FB; --blue-text: #0C447C;
  --amber-bg: #FAEEDA; --amber-text: #633806;
  --r: 12px; --r-sm: 8px;
}
@media (prefers-color-scheme: dark) {
  :root {
    --bg:#181816;--surface:#222220;--surface2:#2C2C2A;
    --border:rgba(255,255,255,0.08);--border-md:rgba(255,255,255,0.14);
    --text:#EEEDE9;--text-muted:#9C9C98;--text-hint:#6B6B67;
    --green:#1D9E75;--green-bg:#04342C;--green-text:#9FE1CB;
    --blue:#378ADD;--blue-bg:#042C53;--blue-text:#B5D4F4;
    --amber-bg:#412402;--amber-text:#FAC775;
  }
}
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;}
.app{max-width:500px;margin:0 auto;padding:20px 16px 60px;}

.header{margin-bottom:24px;}
.header-row{display:flex;align-items:center;gap:10px;margin-bottom:6px;}
.logo{width:38px;height:38px;background:var(--green);border-radius:var(--r-sm);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.logo svg{width:20px;height:20px;stroke:white;fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;}
.header h1{font-size:19px;font-weight:700;letter-spacing:-0.02em;}
.badge{display:inline-flex;align-items:center;font-size:10px;font-weight:600;padding:3px 9px;border-radius:20px;background:var(--green-bg);color:var(--green-text);letter-spacing:.04em;}
.header-sub{font-size:13px;color:var(--text-muted);line-height:1.5;}

.card{background:var(--surface);border-radius:var(--r);border:1px solid var(--border);padding:16px;margin-bottom:14px;}
.card-title{font-size:13px;font-weight:600;color:var(--text);margin-bottom:14px;display:flex;align-items:center;gap:8px;}
.step-num{width:22px;height:22px;border-radius:50%;background:var(--green);color:white;font-size:11px;font-weight:700;display:flex;align-items:center;justify-content:center;flex-shrink:0;}

.field{margin-bottom:14px;}
.field:last-child{margin-bottom:0;}
.flabel{font-size:13px;color:var(--text-muted);margin-bottom:5px;display:flex;align-items:center;gap:4px;}
.req{color:var(--green);font-size:11px;}
.fhint{font-size:11px;color:var(--text-hint);margin-top:4px;line-height:1.5;}

input[type=text],input[type=number],select{
  width:100%;padding:11px 13px;font-size:15px;color:var(--text);
  background:var(--surface2);border:1px solid var(--border);border-radius:var(--r-sm);
  outline:none;appearance:none;-webkit-appearance:none;transition:border-color .15s,background .15s;
}
input:focus,select:focus{border-color:var(--green);background:var(--surface);}
input::placeholder{color:var(--text-hint);}
select{cursor:pointer;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='6' viewBox='0 0 10 6'%3E%3Cpath fill='%239C9C98' d='M5 6L0 0h10z'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 13px center;padding-right:34px;}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:10px;}

.stepper{display:flex;align-items:center;background:var(--surface2);border:1px solid var(--border);border-radius:var(--r-sm);overflow:hidden;transition:border-color .15s;}
.stepper:focus-within{border-color:var(--green);}
.stepper input{flex:1;text-align:center;background:transparent;border:none;font-size:16px;font-weight:500;padding:10px 2px;color:var(--text);min-width:0;}
.stepper input:focus{outline:none;}
.s-btn{width:44px;min-width:44px;height:44px;display:flex;align-items:center;justify-content:center;cursor:pointer;background:transparent;border:none;color:var(--text-muted);font-size:20px;font-weight:300;transition:background .1s;flex-shrink:0;-webkit-tap-highlight-color:transparent;}
.s-btn:active{background:var(--border-md);}
.s-pfx{padding-left:10px;font-size:13px;color:var(--text-hint);flex-shrink:0;}
.s-sfx{padding-right:10px;font-size:13px;color:var(--text-hint);flex-shrink:0;}

.ap-row{display:flex;gap:6px;margin-bottom:8px;}
.ap-btn{flex:1;padding:8px 2px;font-size:12px;font-weight:500;cursor:pointer;border-radius:var(--r-sm);border:1px solid var(--border);background:var(--surface2);color:var(--text-muted);text-align:center;transition:all .15s;-webkit-tap-highlight-color:transparent;}
.ap-btn.active{border-color:var(--green);background:var(--green-bg);color:var(--green-text);font-weight:700;}
.ap-desc{font-size:10px;color:var(--text-hint);line-height:1.6;margin-bottom:10px;}

.zone-info-box{background:var(--surface2);border-radius:var(--r-sm);padding:12px 14px;margin-top:10px;display:none;}
.zone-info-box.show{display:block;}
.zi-title{font-size:11px;font-weight:600;color:var(--text-hint);text-transform:uppercase;letter-spacing:.06em;margin-bottom:10px;}
.zi-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;}
.zi-lbl{font-size:11px;color:var(--text-hint);margin-bottom:2px;}
.zi-val{font-size:14px;font-weight:600;color:var(--text);}
.zi-ref{font-size:10px;color:var(--text-hint);margin-top:10px;padding-top:8px;border-top:1px solid var(--border);line-height:1.5;}

/* Results */
.result-block{border-radius:var(--r);border:1px solid var(--border);overflow:hidden;margin-bottom:14px;background:var(--surface);}
.rb-header{padding:12px 16px 10px;border-bottom:1px solid var(--border);}
.rb-tag{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:.06em;color:var(--text-hint);margin-bottom:4px;}
.rb-name{font-size:13px;font-weight:600;color:var(--text);}
.rb-vgv{padding:16px 16px 12px;}
.rb-vgv-lbl{font-size:12px;color:var(--text-muted);margin-bottom:4px;}
.rb-vgv-num{font-size:30px;font-weight:800;letter-spacing:-.03em;color:var(--text);line-height:1;}
.rb-stats{display:grid;grid-template-columns:1fr 1fr;gap:10px;padding:12px 16px;border-top:1px solid var(--border);}
.rs-lbl{font-size:11px;color:var(--text-hint);margin-bottom:2px;}
.rs-val{font-size:14px;font-weight:600;color:var(--text);}
.rb-permuta{display:flex;justify-content:space-between;align-items:center;padding:12px 16px;background:var(--blue-bg);border-top:1px solid var(--border);}
.rp-lbl{font-size:12px;color:var(--blue-text);}
.rp-val{font-size:18px;font-weight:700;color:var(--blue-text);}

.compare-card{background:var(--surface);border-radius:var(--r);border:1px solid var(--border);padding:14px 16px;margin-bottom:14px;}
.cc-title{font-size:12px;font-weight:600;color:var(--text-muted);margin-bottom:10px;}
.cc-legend{display:flex;gap:14px;margin-bottom:12px;}
.cc-dot{width:8px;height:8px;border-radius:50%;display:inline-block;margin-right:4px;vertical-align:middle;}
.cc-dot.g{background:var(--green);}
.cc-dot.b{background:var(--blue);}
.cc-leg-lbl{font-size:11px;color:var(--text-hint);}
.cc-row{display:flex;justify-content:space-between;align-items:center;padding:8px 0;border-bottom:1px solid var(--border);}
.cc-row:last-child{border-bottom:none;}
.cc-lbl{font-size:13px;color:var(--text-muted);}
.cc-vals{display:flex;gap:14px;}
.cc-v{font-size:13px;font-weight:600;}
.cc-v.g{color:var(--green);}
.cc-v.b{color:var(--blue);}

.disclaimer{background:var(--amber-bg);border-radius:var(--r-sm);padding:12px 14px;font-size:11px;color:var(--amber-text);line-height:1.6;margin-bottom:14px;}
.disclaimer strong{font-weight:700;}

.btn{width:100%;padding:14px;font-size:15px;font-weight:600;cursor:pointer;border-radius:var(--r);border:none;display:flex;align-items:center;justify-content:center;gap:8px;transition:opacity .15s,transform .1s;-webkit-tap-highlight-color:transparent;}
.btn:active{transform:scale(.98);}
.btn-g{background:var(--green);color:white;}
.btn-g:hover{opacity:.9;}
.btn-ol{background:transparent;border:1px solid var(--border-md);color:var(--text-muted);margin-top:8px;}
.btn-ol:hover{background:var(--surface2);}
.hidden{display:none!important;}
</style>
</head>
<body>
<div class="app">

<!-- HEADER -->
<div class="header">
  <div class="header-row">
    <div class="logo">
      <svg viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
    </div>
    <div>
      <h1>Calculadora VGV</h1>
      <span class="badge">LC 270/2024 · Rio de Janeiro</span>
    </div>
  </div>
  <p class="header-sub">Estime o potencial de venda de um terreno para incorporadoras com base na legislação vigente.</p>
</div>

<!-- CARD 1: DADOS DO PROJETO -->
<div class="card">
  <div class="card-title"><span class="step-num">1</span> Dados do Projeto</div>

  <div class="field">
    <div class="flabel">Nome do Projeto <span class="req">*</span></div>
    <input type="text" id="nomeProjeto" placeholder="Ex: Terreno Botafogo 1" />
  </div>

  <div class="row2">
    <div class="field">
      <div class="flabel">Área do Terreno (m2) <span class="req">*</span></div>
      <div class="stepper">
        <button class="s-btn" onclick="step('areaTotalTerreno',-50)">−</button>
        <input type="number" id="areaTotalTerreno" placeholder="0" min="0" inputmode="numeric" oninput="onAnyChange()" />
        <button class="s-btn" onclick="step('areaTotalTerreno',50)">+</button>
      </div>
    </div>
    <div class="field">
      <div class="flabel">Valor do Terreno</div>
      <div class="stepper">
        <span class="s-pfx">R$</span>
        <input type="number" id="valorTerreno" placeholder="0" min="0" inputmode="numeric" oninput="onAnyChange()" />
      </div>
      <div class="fhint">Deixe em branco se ainda não souber</div>
    </div>
  </div>

  <div class="row2">
    <div class="field">
      <div class="flabel">Preço Venda Unitário (R$) <span class="req">*</span></div>
      <div class="stepper">
        <span class="s-pfx">$</span>
        <input type="number" id="precoUnitario" placeholder="0,00" min="0" inputmode="numeric" oninput="onAnyChange()" />
        <button class="s-btn" onclick="step('precoUnitario',-10000)">−</button>
        <button class="s-btn" onclick="step('precoUnitario',10000)">+</button>
      </div>
    </div>
    <div class="field">
      <div class="flabel">Valor do m²</div>
      <div class="stepper">
        <span class="s-pfx">$</span>
        <input type="number" id="valorM2" placeholder="0,00" min="0" inputmode="numeric" oninput="onM2Change()" />
      </div>
      <div class="fhint">Calculado automaticamente pelo Valor do Terreno ÷ Área</div>
    </div>
  </div>

  <div class="field">
    <div class="flabel">Tamanho de cada unidade (m²) <span class="req">*</span></div>
    <div class="stepper">
      <button class="s-btn" onclick="step('areaUnidade',-5)">−</button>
      <input type="number" id="areaUnidade" placeholder="0" min="1" inputmode="numeric" oninput="onAnyChange()" />
      <button class="s-btn" onclick="step('areaUnidade',5)">+</button>
      <span class="s-sfx">m²</span>
    </div>
  </div>

  <div class="field">
    <div class="flabel">Permuta (%) <span class="req">*</span></div>
    <div class="stepper">
      <button class="s-btn" onclick="step('permutaPct',-0.5)">−</button>
      <span class="s-pfx">%</span>
      <input type="number" id="permutaPct" value="7" min="0" max="100" step="0.5" inputmode="decimal" oninput="onAnyChange()" />
      <button class="s-btn" onclick="step('permutaPct',0.5)">+</button>
    </div>
    <div class="fhint">Percentual do VGV Total destinado ao proprietário do terreno como forma de pagamento. Padrão do mercado: 7%</div>
  </div>
</div>

<!-- CARD 2: ZONEAMENTO -->
<div class="card">
  <div class="card-title"><span class="step-num">2</span> Zoneamento do Terreno</div>
  <div class="fhint" style="margin-bottom:10px;">A localização define o quanto a lei permite construir. Selecione a Área de Planejamento e a zona específica do terreno.</div>

  <div class="ap-row" id="apRow">
    <button class="ap-btn active" data-ap="AP1" onclick="selectAP('AP1')">AP 1</button>
    <button class="ap-btn" data-ap="AP2" onclick="selectAP('AP2')">AP 2</button>
    <button class="ap-btn" data-ap="AP3" onclick="selectAP('AP3')">AP 3</button>
    <button class="ap-btn" data-ap="AP4" onclick="selectAP('AP4')">AP 4</button>
    <button class="ap-btn" data-ap="AP5" onclick="selectAP('AP5')">AP 5</button>
  </div>
  <div class="ap-desc">AP 1 = Centro / Zona Sul &nbsp;·&nbsp; AP 2 = Zona Sul / Tijuca &nbsp;·&nbsp; AP 3 = Zona Norte &nbsp;·&nbsp; AP 4 = Barra / Jacarepaguá &nbsp;·&nbsp; AP 5 = Zona Oeste</div>

  <div class="field">
    <div class="flabel">Zona / Subzona <span class="req">*</span></div>
    <select id="zonaSelect" onchange="onZoneChange()"></select>
    <div class="fhint">Não sabe a zona? Consulte o mapa de zoneamento da Prefeitura ou pergunte ao arquiteto responsável.</div>
  </div>

  <div id="zoneInfo" class="zone-info-box">
    <div class="zi-title" id="ziTitle">O que a lei permite nessa zona</div>
    <div class="zi-grid">
      <div><div class="zi-lbl">Pode construir até</div><div class="zi-val" id="zCAM">—</div></div>
      <div><div class="zi-lbl">Ocupa no máx. do terreno</div><div class="zi-val" id="zTO">—</div></div>
      <div><div class="zi-lbl">Altura máxima</div><div class="zi-val" id="zGab">—</div></div>
      <div><div class="zi-lbl">Lote mínimo</div><div class="zi-val" id="zLote">—</div></div>
    </div>
    <div class="zi-ref" id="zRef"></div>
  </div>
</div>

<!-- CARD 3: DIMENSIONAMENTO -->
<div class="card">
  <div class="card-title"><span class="step-num">3</span> Dimensionamento do Projeto <span style="font-size:11px;font-weight:400;color:var(--text-hint);margin-left:4px;">(opcional)</span></div>
  <div class="fhint" style="margin-bottom:14px;">Preencha se já tiver uma ideia do empreendimento. O VGV Total também será calculado com base nesses dados e comparado com o potencial máximo da legislação.</div>

  <div class="row2">
    <div class="field">
      <div class="flabel">Blocos</div>
      <div class="stepper">
        <button class="s-btn" onclick="step('blocos',-1)">−</button>
        <input type="number" id="blocos" placeholder="0" min="0" inputmode="numeric" oninput="onAnyChange()" />
        <button class="s-btn" onclick="step('blocos',1)">+</button>
      </div>
    </div>
    <div class="field">
      <div class="flabel">Pavimentos</div>
      <div class="stepper">
        <button class="s-btn" onclick="step('pavimentos',-1)">−</button>
        <input type="number" id="pavimentos" placeholder="0" min="0" inputmode="numeric" oninput="onAnyChange()" />
        <button class="s-btn" onclick="step('pavimentos',1)">+</button>
      </div>
    </div>
  </div>

  <div class="field">
    <div class="flabel">Aptos por Pavimento</div>
    <div class="stepper">
      <button class="s-btn" onclick="step('aptosPav',-1)">−</button>
      <input type="number" id="aptosPav" placeholder="0" min="0" inputmode="numeric" oninput="onAnyChange()" />
      <button class="s-btn" onclick="step('aptosPav',1)">+</button>
    </div>
    <div class="fhint">Total de unidades = Blocos × Pavimentos × Aptos por Pavimento</div>
  </div>

  <div class="field">
    <div class="flabel">VGV Total</div>
    <div class="stepper" style="opacity:.6;pointer-events:none;">
      <span class="s-pfx">$</span>
      <input type="text" id="vgvTotalDisplay" placeholder="0,00" readonly />
    </div>
    <div class="fhint">Calculado automaticamente após preencher os campos acima e clicar em Calcular</div>
  </div>
</div>

<!-- BOTÃO -->
<div id="calcBtn">
  <button class="btn btn-g" onclick="calcular()">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="2" width="16" height="20" rx="2"/><line x1="8" y1="6" x2="16" y2="6"/><line x1="8" y1="10" x2="16" y2="10"/><line x1="8" y1="14" x2="12" y2="14"/></svg>
    Calcular VGV
  </button>
</div>

<!-- RESULTADOS -->
<div id="resultsSection" class="hidden">

  <div style="font-size:11px;font-weight:600;text-transform:uppercase;letter-spacing:.07em;color:var(--text-hint);margin:4px 0 12px;">Resultados</div>

  <!-- Potencial pelo zoneamento -->
  <div class="result-block">
    <div class="rb-header">
      <div class="rb-tag">📐 Potencial máximo — o que a lei permite</div>
      <div class="rb-name" id="rz-name">—</div>
    </div>
    <div class="rb-vgv">
      <div class="rb-vgv-lbl">VGV Total</div>
      <div class="rb-vgv-num" id="rz-vgv">—</div>
    </div>
    <div class="rb-stats">
      <div><div class="rs-lbl">Área total edificável</div><div class="rs-val" id="rz-ate">—</div></div>
      <div><div class="rs-lbl">Unidades possíveis</div><div class="rs-val" id="rz-un">—</div></div>
      <div><div class="rs-lbl">Pavimentos máx.</div><div class="rs-val" id="rz-gab">—</div></div>
      <div><div class="rs-lbl">Valor do m²</div><div class="rs-val" id="rz-m2">—</div></div>
    </div>
    <div class="rb-permuta">
      <div class="rp-lbl" id="rz-p-lbl">Permuta</div>
      <div class="rp-val" id="rz-p">—</div>
    </div>
  </div>

  <!-- Projeto do usuário -->
  <div class="result-block hidden" id="blockUsuario">
    <div class="rb-header">
      <div class="rb-tag">🏗️ Projeto informado</div>
      <div class="rb-name" id="ru-name">—</div>
    </div>
    <div class="rb-vgv">
      <div class="rb-vgv-lbl">VGV Total</div>
      <div class="rb-vgv-num" id="ru-vgv">—</div>
    </div>
    <div class="rb-stats">
      <div><div class="rs-lbl">Total de unidades</div><div class="rs-val" id="ru-un">—</div></div>
      <div><div class="rs-lbl">Blocos × Pav. × Aptos</div><div class="rs-val" id="ru-comp">—</div></div>
      <div><div class="rs-lbl">Aproveitamento do potencial</div><div class="rs-val" id="ru-pot">—</div></div>
      <div><div class="rs-lbl">Valor do m²</div><div class="rs-val" id="ru-m2">—</div></div>
    </div>
    <div class="rb-permuta">
      <div class="rp-lbl" id="ru-p-lbl">Permuta</div>
      <div class="rp-val" id="ru-p">—</div>
    </div>
  </div>

  <!-- Comparativo -->
  <div class="compare-card hidden" id="compareCard">
    <div class="cc-title">Comparativo entre as estimativas</div>
    <div class="cc-legend">
      <div><span class="cc-dot g"></span><span class="cc-leg-lbl">Potencial máximo legal</span></div>
      <div><span class="cc-dot b"></span><span class="cc-leg-lbl">Projeto informado</span></div>
    </div>
    <div class="cc-row">
      <span class="cc-lbl">VGV Total</span>
      <div class="cc-vals"><span class="cc-v g" id="cv-vz">—</span><span class="cc-v b" id="cv-vu">—</span></div>
    </div>
    <div class="cc-row">
      <span class="cc-lbl">Unidades</span>
      <div class="cc-vals"><span class="cc-v g" id="cv-uz">—</span><span class="cc-v b" id="cv-uu">—</span></div>
    </div>
    <div class="cc-row">
      <span class="cc-lbl">Permuta (%)</span>
      <div class="cc-vals"><span class="cc-v g" id="cv-pz">—</span><span class="cc-v b" id="cv-pu">—</span></div>
    </div>
    <div class="cc-row">
      <span class="cc-lbl">Valor do Terreno</span>
      <div class="cc-vals"><span class="cc-v g" id="cv-tz">—</span><span class="cc-v b" id="cv-tu">—</span></div>
    </div>
  </div>

  <div class="disclaimer">
    <strong>Atenção:</strong> Esta é uma estimativa de viabilidade baseada nos parâmetros do Anexo XXI da LC 270/2024 (Plano Diretor do Rio de Janeiro). Não substitui análise técnica de arquiteto ou engenheiro habilitado, nem consulta prévia à Prefeitura. Os números reais podem variar por APAC, restrições de loteamento, cota altimétrica ou legislações específicas.
  </div>

  <button class="btn btn-g" onclick="exportar()">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4M7 10l5 5 5-5M12 15V3"/></svg>
    Exportar Relatório
  </button>
  <button class="btn btn-ol" onclick="resetar()">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 101.5-5M3 3v6h6"/></svg>
    Novo Cálculo
  </button>
</div>

</div>
<script>
const ZONAS={
  AP1:[
    {id:"ZRM1-A",label:"ZRM 1 A",cam:2.0,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM1-B",label:"ZRM 1 B",cam:3.0,to:70,gabarito:"4 Pav. / 14m",loteMin:360},
    {id:"ZRM1-C",label:"ZRM 1 C",cam:3.0,to:70,gabarito:"7 Pav. / 27m",loteMin:360},
    {id:"ZRM1-D",label:"ZRM 1 D",cam:1.0,to:50,gabarito:"2 Pav. / 8m",loteMin:360},
    {id:"ZRM2-A",label:"ZRM 2 A",cam:2.5,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM2-B",label:"ZRM 2 B",cam:4.0,to:70,gabarito:"12 Pav. / 36m",loteMin:360},
    {id:"ZRM2-C",label:"ZRM 2 C",cam:6.0,to:70,gabarito:"15 Pav. / 46m",loteMin:360},
    {id:"ZRM3-A",label:"ZRM 3 A",cam:4.0,to:70,gabarito:"8 Pav. / 26m",loteMin:360},
    {id:"ZRM3-B",label:"ZRM 3 B",cam:6.0,to:70,gabarito:"15 Pav. / 46m",loteMin:360},
    {id:"ZRM3-C",label:"ZRM 3 C",cam:6.0,to:70,gabarito:"15 Pav. / 46m",loteMin:360},
    {id:"ZCA2",label:"ZCA 2",cam:0.1,to:10,gabarito:"2 Pav. / 8m",loteMin:10000},
    {id:"ZRU1",label:"ZRU",cam:0.5,to:30,gabarito:"2 Pav. / 8m",loteMin:3000},
  ],
  AP2:[
    {id:"ZRM1-A2",label:"ZRM 1 A",cam:2.0,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM1-B2",label:"ZRM 1 B",cam:3.0,to:70,gabarito:"4 Pav. / 14m",loteMin:360},
    {id:"ZRM1-C2",label:"ZRM 1 C",cam:3.0,to:70,gabarito:"7 Pav. / 27m",loteMin:360},
    {id:"ZRM1-D2",label:"ZRM 1 D",cam:1.0,to:50,gabarito:"2 Pav. / 8m",loteMin:360},
    {id:"ZRM2-A2",label:"ZRM 2 A",cam:2.5,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM2-B2",label:"ZRM 2 B",cam:4.0,to:70,gabarito:"12 Pav. / 36m",loteMin:360},
    {id:"ZRM2-C2",label:"ZRM 2 C",cam:6.0,to:70,gabarito:"15 Pav. / 46m",loteMin:360},
    {id:"ZRM3-A2",label:"ZRM 3 A",cam:4.0,to:70,gabarito:"8 Pav. / 26m",loteMin:360},
    {id:"ZRM3-B2",label:"ZRM 3 B",cam:6.0,to:70,gabarito:"15 Pav. / 46m",loteMin:360},
    {id:"ZCA2-2",label:"ZCA 2",cam:0.1,to:10,gabarito:"2 Pav. / 8m",loteMin:10000},
    {id:"ZCA2-B2",label:"ZCA 2 B",cam:0.2,to:20,gabarito:"2 Pav. / 8m",loteMin:5000},
    {id:"ZRU2",label:"ZRU",cam:0.5,to:30,gabarito:"2 Pav. / 8m",loteMin:3000},
  ],
  AP3:[
    {id:"ZRM1-A3",label:"ZRM 1 A",cam:2.0,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM2-A3",label:"ZRM 2 A",cam:2.5,to:70,gabarito:"5 Pav. / 17m",loteMin:360},
    {id:"ZRM2-B3",label:"ZRM 2 B",cam:4.0,to:70,gabarito:"9 Pav. / 29m",loteMin:360},
    {id:"ZRM3-A3",label:"ZRM 3 A",cam:4.0,to:70,gabarito:"9 Pav. / 29m",loteMin:360},
    {id:"ZRM3-B3",label:"ZRM 3 B",cam:6.0,to:70,gabarito:"12 Pav. / 38m",loteMin:360},
    {id:"ZRU3",label:"ZRU",cam:0.5,to:30,gabarito:"2 Pav. / 8m",loteMin:3000},
    {id:"ZCA3",label:"ZCA",cam:0.1,to:10,gabarito:"2 Pav. / 8m",loteMin:10000},
  ],
  AP4:[
    {id:"ZRM1-A4",label:"ZRM 1 A",cam:2.0,to:70,gabarito:"3 Pav. / 11m",loteMin:360},
    {id:"ZRM2-A4",label:"ZRM 2 A",cam:2.5,to:70,gabarito:"5 Pav. / 17m",loteMin:360},
    {id:"ZRM2-B4",label:"ZRM 2 B",cam:3.0,to:70,gabarito:"6 Pav. / 20m",loteMin:360},
    {id:"ZRM3-A4",label:"ZRM 3 A",cam:3.0,to:70,gabarito:"6 Pav. / 20m",loteMin:360},
    {id:"ZRU4",label:"ZRU",cam:0.5,to:30,gabarito:"2 Pav. / 8m",loteMin:3000},
    {id:"ZCA4",label:"ZCA",cam:0.1,to:10,gabarito:"2 Pav. / 8m",loteMin:10000},
  ],
  AP5:[
    {id:"ZRM1-A5",label:"ZRM 1 A",cam:1.5,to:60,gabarito:"3 Pav. / 11m",loteMin:450},
    {id:"ZRM2-A5",label:"ZRM 2 A",cam:2.0,to:60,gabarito:"4 Pav. / 14m",loteMin:450},
    {id:"ZRM2-B5",label:"ZRM 2 B",cam:2.5,to:60,gabarito:"5 Pav. / 17m",loteMin:450},
    {id:"ZRM3-A5",label:"ZRM 3 A",cam:3.0,to:60,gabarito:"6 Pav. / 20m",loteMin:450},
    {id:"ZRU5",label:"ZRU",cam:0.4,to:25,gabarito:"2 Pav. / 8m",loteMin:5000},
    {id:"ZCA5",label:"ZCA",cam:0.1,to:10,gabarito:"2 Pav. / 8m",loteMin:10000},
  ]
};

let apAtiva="AP1", zonaAtiva=null;
const R=n=>n.toLocaleString('pt-BR',{style:'currency',currency:'BRL',maximumFractionDigits:0});
const N=n=>n.toLocaleString('pt-BR');

function step(id,d){
  const el=document.getElementById(id);
  const v=parseFloat(el.value)||0,mn=parseFloat(el.min)||0,mx=parseFloat(el.max)||9999999;
  el.value=Math.max(mn,Math.min(mx,+(v+d).toFixed(4)));
  onAnyChange();
}

// Valor do Terreno → calcula Valor do m² automaticamente
document.getElementById('valorTerreno').addEventListener('input', function(){
  const area=parseFloat(document.getElementById('areaTotalTerreno').value)||0;
  const val=parseFloat(this.value)||0;
  if(area>0 && val>0){
    document.getElementById('valorM2').value=Math.round(val/area);
  } else {
    document.getElementById('valorM2').value='';
  }
  onAnyChange();
});

// Valor do m² → calcula Valor do Terreno automaticamente
function onM2Change(){
  const area=parseFloat(document.getElementById('areaTotalTerreno').value)||0;
  const m2=parseFloat(document.getElementById('valorM2').value)||0;
  if(area>0 && m2>0){
    document.getElementById('valorTerreno').value=Math.round(area*m2);
  } else {
    document.getElementById('valorTerreno').value='';
  }
  onAnyChange();
}

// Área do terreno → recalcula m² se valor do terreno preenchido
document.getElementById('areaTotalTerreno').addEventListener('input', function(){
  const area=parseFloat(this.value)||0;
  const val=parseFloat(document.getElementById('valorTerreno').value)||0;
  if(area>0 && val>0){
    document.getElementById('valorM2').value=Math.round(val/area);
  }
  onAnyChange();
});

function selectAP(ap){
  apAtiva=ap;
  document.querySelectorAll('.ap-btn').forEach(b=>b.classList.toggle('active',b.dataset.ap===ap));
  populateZones();
  document.getElementById('zoneInfo').classList.remove('show');
  document.getElementById('resultsSection').classList.add('hidden');
  zonaAtiva=null;
}

function populateZones(){
  const sel=document.getElementById('zonaSelect');
  sel.innerHTML='<option value="">Selecione a zona / subzona...</option>';
  (ZONAS[apAtiva]||[]).forEach(z=>{
    const o=document.createElement('option');
    o.value=z.id;
    o.textContent=z.label+' — até '+z.cam+'× a área  |  '+z.gabarito;
    sel.appendChild(o);
  });
}

function onZoneChange(){
  const id=document.getElementById('zonaSelect').value;
  if(!id){document.getElementById('zoneInfo').classList.remove('show');zonaAtiva=null;return;}
  zonaAtiva=(ZONAS[apAtiva]||[]).find(z=>z.id===id);
  if(!zonaAtiva)return;
  document.getElementById('zCAM').textContent=zonaAtiva.cam+'× a área do terreno';
  document.getElementById('zTO').textContent=zonaAtiva.to+'% do terreno';
  document.getElementById('zGab').textContent=zonaAtiva.gabarito;
  document.getElementById('zLote').textContent=N(zonaAtiva.loteMin)+' m²';
  document.getElementById('ziTitle').textContent=zonaAtiva.label+' — '+apAtiva+' · O que a lei permite';
  document.getElementById('zRef').textContent='Fonte: Anexo XXI, LC 270/2024 (Plano Diretor do Rio de Janeiro). CAM = coeficiente de aproveitamento máximo, com Outorga Onerosa do Direito de Construir.';
  document.getElementById('zoneInfo').classList.add('show');
  document.getElementById('resultsSection').classList.add('hidden');
}

function onAnyChange(){
  document.getElementById('resultsSection').classList.add('hidden');
  document.getElementById('vgvTotalDisplay').value='';
}

function calcular(){
  if(!zonaAtiva){alert('Selecione a zona do terreno primeiro.');return;}
  const area=parseFloat(document.getElementById('areaTotalTerreno').value);
  const preco=parseFloat(document.getElementById('precoUnitario').value);
  const areaU=parseFloat(document.getElementById('areaUnidade').value);
  const valTer=parseFloat(document.getElementById('valorTerreno').value)||0;
  const m2Input=parseFloat(document.getElementById('valorM2').value)||0;
  const permPct=parseFloat(document.getElementById('permutaPct').value)||7;
  const nome=document.getElementById('nomeProjeto').value.trim()||'Projeto';
  const blocos=parseInt(document.getElementById('blocos').value)||0;
  const pavs=parseInt(document.getElementById('pavimentos').value)||0;
  const aptos=parseInt(document.getElementById('aptosPav').value)||0;

  if(!area||area<=0){alert('Informe a Área do Terreno.');return;}
  if(!preco||preco<=0){alert('Informe o Preço Venda Unitário.');return;}
  if(!areaU||areaU<=0){alert('Informe o tamanho de cada unidade.');return;}

  // Cálculo pelo zoneamento
  const ate_z=Math.round(area*zonaAtiva.cam);
  const un_z=Math.floor(ate_z/areaU);
  const vgv_z=un_z*preco;
  const perm_z=Math.round(vgv_z*permPct/100);
  const m2_ter=valTer>0?Math.round(valTer/area):(m2Input>0?m2Input:null);
  const permLabel='Permuta ('+permPct.toFixed(1).replace('.',',')+'%)';

  // Cálculo pelo projeto
  const temP=blocos>0&&pavs>0&&aptos>0;
  const un_u=blocos*pavs*aptos;
  const vgv_u=un_u*preco;
  const perm_u=Math.round(vgv_u*permPct/100);
  const potPct=vgv_z>0?(vgv_u/vgv_z*100):0;

  // Preencher campo VGV Total no card 3
  document.getElementById('vgvTotalDisplay').value=temP
    ? vgv_u.toLocaleString('pt-BR',{minimumFractionDigits:2,maximumFractionDigits:2})
    : vgv_z.toLocaleString('pt-BR',{minimumFractionDigits:2,maximumFractionDigits:2});

  // Bloco zoneamento
  document.getElementById('rz-name').textContent=nome+' · '+zonaAtiva.label+' · '+apAtiva;
  document.getElementById('rz-vgv').textContent=R(vgv_z);
  document.getElementById('rz-ate').textContent=N(ate_z)+' m²';
  document.getElementById('rz-un').textContent=N(un_z)+' unidades';
  document.getElementById('rz-gab').textContent=zonaAtiva.gabarito;
  document.getElementById('rz-m2').textContent=m2_ter?R(m2_ter)+'/m²':'—';
  document.getElementById('rz-p-lbl').textContent=permLabel;
  document.getElementById('rz-p').textContent=R(perm_z);

  // Bloco projeto
  if(temP){
    document.getElementById('ru-name').textContent=nome+' · '+blocos+(blocos>1?' Blocos':' Bloco')+' · '+pavs+' Pav. · '+aptos+' Aptos/Pav.';
    document.getElementById('ru-vgv').textContent=R(vgv_u);
    document.getElementById('ru-un').textContent=N(un_u)+' unidades';
    document.getElementById('ru-comp').textContent=blocos+' × '+pavs+' × '+aptos;
    document.getElementById('ru-pot').textContent=potPct.toFixed(1).replace('.',',')+'% do potencial legal';
    document.getElementById('ru-m2').textContent=m2_ter?R(m2_ter)+'/m²':'—';
    document.getElementById('ru-p-lbl').textContent=permLabel;
    document.getElementById('ru-p').textContent=R(perm_u);
    document.getElementById('blockUsuario').classList.remove('hidden');
    // Comparativo
    document.getElementById('cv-vz').textContent=R(vgv_z);
    document.getElementById('cv-vu').textContent=R(vgv_u);
    document.getElementById('cv-uz').textContent=N(un_z)+' un.';
    document.getElementById('cv-uu').textContent=N(un_u)+' un.';
    document.getElementById('cv-pz').textContent=R(perm_z);
    document.getElementById('cv-pu').textContent=R(perm_u);
    document.getElementById('cv-tz').textContent=valTer>0?R(valTer):'—';
    document.getElementById('cv-tu').textContent=valTer>0?R(valTer):'—';
    document.getElementById('compareCard').classList.remove('hidden');
  } else {
    document.getElementById('blockUsuario').classList.add('hidden');
    document.getElementById('compareCard').classList.add('hidden');
  }

  document.getElementById('resultsSection').classList.remove('hidden');
  setTimeout(()=>document.getElementById('resultsSection').scrollIntoView({behavior:'smooth'}),50);
}

function exportar(){
  const area=parseFloat(document.getElementById('areaTotalTerreno').value)||0;
  const preco=parseFloat(document.getElementById('precoUnitario').value)||0;
  const areaU=parseFloat(document.getElementById('areaUnidade').value)||0;
  const valTer=parseFloat(document.getElementById('valorTerreno').value)||0;
  const m2Input=parseFloat(document.getElementById('valorM2').value)||0;
  const permPct=parseFloat(document.getElementById('permutaPct').value)||7;
  const nome=document.getElementById('nomeProjeto').value.trim()||'Projeto';
  const blocos=parseInt(document.getElementById('blocos').value)||0;
  const pavs=parseInt(document.getElementById('pavimentos').value)||0;
  const aptos=parseInt(document.getElementById('aptosPav').value)||0;
  if(!zonaAtiva)return;

  const ate_z=Math.round(area*zonaAtiva.cam);
  const un_z=Math.floor(ate_z/areaU);
  const vgv_z=un_z*preco;
  const perm_z=Math.round(vgv_z*permPct/100);
  const m2_ter=valTer>0?Math.round(valTer/area):(m2Input>0?m2Input:null);
  const temP=blocos>0&&pavs>0&&aptos>0;
  const un_u=blocos*pavs*aptos;
  const vgv_u=un_u*preco;
  const perm_u=Math.round(vgv_u*permPct/100);
  const potPct=vgv_z>0?(vgv_u/vgv_z*100):0;
  const hoje=new Date().toLocaleDateString('pt-BR');
  const pLbl=permPct.toFixed(1).replace('.',',')+'% do VGV Total';

  const projetoHTML=temP?`
  <tr><td colspan="2" class="s">Projeto Informado</td></tr>
  <tr><td>Blocos</td><td>${blocos}</td></tr>
  <tr><td>Pavimentos</td><td>${pavs}</td></tr>
  <tr><td>Aptos por Pavimento</td><td>${aptos}</td></tr>
  <tr><td>Total de Unidades</td><td>${N(un_u)}</td></tr>
  <tr><td>VGV Total — Projeto Informado</td><td class="big">${R(vgv_u)}</td></tr>
  <tr><td>Permuta (${pLbl})</td><td>${R(perm_u)}</td></tr>
  <tr><td>Aproveitamento do Potencial Legal</td><td>${potPct.toFixed(1).replace('.',',')}%</td></tr>`:'';

  const html=`<!DOCTYPE html><html lang="pt-BR"><head><meta charset="UTF-8"><title>VGV – ${nome}</title>
<style>
body{font-family:Arial,sans-serif;color:#1a1a18;padding:40px;max-width:680px;margin:0 auto;font-size:14px;}
.top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:28px;padding-bottom:16px;border-bottom:2px solid #1a1a18;}
h1{font-size:22px;font-weight:700;margin:0 0 3px;}.sub{font-size:12px;color:#6b6b67;}
.badge{font-size:10px;background:#e1f5ee;color:#085041;padding:3px 10px;border-radius:20px;font-weight:700;}
table{width:100%;border-collapse:collapse;}
td{padding:9px 0;border-bottom:1px solid #f0efeb;vertical-align:top;}
td:last-child{font-weight:600;text-align:right;}
.s{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.08em;color:#9c9c98;padding-top:20px;}
.big{font-size:22px;font-weight:800;}
.pb{background:#e6f1fb;border-radius:8px;padding:12px 16px;margin-top:12px;display:flex;justify-content:space-between;align-items:center;}
.pb2{background:#e1f5ee;border-radius:8px;padding:12px 16px;margin-top:8px;display:flex;justify-content:space-between;align-items:center;}
.pl{font-size:12px;color:#185fa5;}.pv{font-size:18px;font-weight:700;color:#0c447c;}
.pl2{font-size:12px;color:#085041;}.pv2{font-size:18px;font-weight:700;color:#0f6e56;}
.disc{font-size:10px;color:#9c9c98;line-height:1.7;margin-top:28px;padding-top:14px;border-top:1px solid #f0efeb;}
</style></head><body>
<div class="top">
  <div><h1>Relatório de Viabilidade VGV</h1><div class="sub">Nome do Projeto: ${nome} · Gerado em ${hoje}</div></div>
  <span class="badge">LC 270/2024 · Rio de Janeiro</span>
</div>
<table>
  <tr><td colspan="2" class="s">Dados do Projeto</td></tr>
  <tr><td>Nome do Projeto</td><td>${nome}</td></tr>
  <tr><td>Área do Terreno (m2)</td><td>${N(area)} m²</td></tr>
  ${valTer>0?`<tr><td>Valor do Terreno</td><td>${R(valTer)}</td></tr>`:''}
  ${m2_ter?`<tr><td>Valor do m²</td><td>${R(m2_ter)}/m²</td></tr>`:''}
  <tr><td>Preço Venda Unitário (R$)</td><td>${R(preco)}</td></tr>
  <tr><td>Tamanho de cada unidade</td><td>${N(areaU)} m²</td></tr>
  <tr><td>Permuta (%)</td><td>${permPct.toFixed(1).replace('.',',')}%</td></tr>

  <tr><td colspan="2" class="s">Zoneamento — LC 270/2024 · ${apAtiva}</td></tr>
  <tr><td>Zona / Subzona</td><td>${zonaAtiva.label}</td></tr>
  <tr><td>Pode construir até (CAM)</td><td>${zonaAtiva.cam}× a área do terreno</td></tr>
  <tr><td>Taxa de Ocupação Máxima</td><td>${zonaAtiva.to}%</td></tr>
  <tr><td>Pavimentos Máximos</td><td>${zonaAtiva.gabarito}</td></tr>
  <tr><td>Lote Mínimo</td><td>${N(zonaAtiva.loteMin)} m²</td></tr>

  <tr><td colspan="2" class="s">Potencial Máximo Legal</td></tr>
  <tr><td>Área Total Edificável</td><td>${N(ate_z)} m²</td></tr>
  <tr><td>Unidades Possíveis</td><td>${N(un_z)}</td></tr>
  <tr><td>VGV Total — Potencial Legal</td><td class="big">${R(vgv_z)}</td></tr>
  ${projetoHTML}
</table>
<div class="pb"><div class="pl">Permuta — ${pLbl} (Potencial Legal)</div><div class="pv">${R(perm_z)}</div></div>
${temP?`<div class="pb2"><div class="pl2">Permuta — ${pLbl} (Projeto Informado)</div><div class="pv2">${R(perm_u)}</div></div>`:''}
<div class="disc">Estimativa de viabilidade baseada nos parâmetros do Anexo XXI da LC 270/2024 (Plano Diretor do Rio de Janeiro), com referência às LC 274/2024 e LC 281/2025. Não constitui análise técnica assinada por profissional habilitado nem substitui consulta prévia à SMU. Parâmetros podem variar por APAC, restrições de loteamento, cota altimétrica ou legislação específica. Gerado em ${hoje}.</div>
</body></html>`;

  const blob=new Blob([html],{type:'text/html'});
  const url=URL.createObjectURL(blob);
  const a=document.createElement('a');
  a.href=url;
  a.download='VGV_'+nome.replace(/\s+/g,'_')+'_'+hoje.replace(/\//g,'-')+'.html';
  document.body.appendChild(a);a.click();document.body.removeChild(a);URL.revokeObjectURL(url);
}

function resetar(){
  document.getElementById('resultsSection').classList.add('hidden');
  document.getElementById('vgvTotalDisplay').value='';
  window.scrollTo({top:0,behavior:'smooth'});
}

populateZones();
</script>
</body>
</html>
