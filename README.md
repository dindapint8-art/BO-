[BO - Gestão de Informação.html](https://github.com/user-attachments/files/32384591/BO.-.Gestao.de.Informacao.html)
<!DOCTYPE html>
<html lang="pt">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>ULS Alto Alentejo — Blocos Operatórios</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;background:#f0f2f5;color:#1a1a2e;font-size:14px}

/* ── TOPBAR ── */
.topbar{background:#1a1a2e;color:#fff;padding:0 24px;display:flex;align-items:stretch;justify-content:space-between;min-height:56px}
.topbar-left{display:flex;align-items:center;gap:14px}
.uls-badge{background:#c8102e;color:#fff;font-size:10px;font-weight:800;letter-spacing:.08em;padding:4px 10px;border-radius:4px;text-transform:uppercase}
.topbar h1{font-size:14px;font-weight:600;letter-spacing:.01em;line-height:1.3}
.topbar-sub{font-size:10px;opacity:.55;margin-top:2px}
.topbar-right{display:flex;align-items:center;gap:16px;text-align:right}
.clk-wrap{font-variant-numeric:tabular-nums}
#clk{font-size:15px;font-weight:700;display:block}
#dt{font-size:10px;opacity:.55}

/* ── NAV TABS ── */
.navtabs{display:flex;gap:0;background:#fff;border-bottom:2px solid #e5e7eb;padding:0 24px}
.navtab{padding:11px 18px;font-size:13px;font-weight:500;cursor:pointer;color:#6b7280;border:none;background:transparent;border-bottom:2px solid transparent;margin-bottom:-2px;transition:all .15s;white-space:nowrap}
.navtab:hover{color:#1a1a2e}
.navtab.on{color:#c8102e;border-bottom-color:#c8102e;font-weight:700}
.navtab.back{margin-left:auto;color:#9ca3af;font-size:12px}
.navtab.back:hover{color:#1a1a2e}

/* ── VIEWS ── */
.view{display:none;padding:0}
.view.on{display:block}

/* ══ FOLHA DE ROSTO ══ */
.landing{min-height:calc(100vh - 56px - 44px);display:flex;flex-direction:column;align-items:center;justify-content:center;padding:40px 24px}
.landing-logo{display:flex;align-items:center;gap:16px;margin-bottom:36px}

.logo-text{text-align:left}
.logo-text h2{font-size:20px;font-weight:800;color:#1a1a2e;letter-spacing:-.01em}
.logo-text p{font-size:13px;color:#6b7280;margin-top:2px}
.landing-title{font-size:26px;font-weight:800;color:#1a1a2e;text-align:center;margin-bottom:8px;letter-spacing:-.02em}
.landing-sub{font-size:14px;color:#6b7280;text-align:center;margin-bottom:48px;max-width:480px;line-height:1.6}
.bo-cards{display:grid;grid-template-columns:repeat(2,1fr);gap:20px;max-width:700px;width:100%;margin-bottom:40px}
.bo-card{background:#fff;border:1px solid #e5e7eb;border-radius:16px;padding:28px 24px;cursor:pointer;transition:all .18s;text-align:left;position:relative;overflow:hidden}
.bo-card:hover{border-color:#c8102e;box-shadow:0 4px 24px rgba(200,16,46,.1);transform:translateY(-2px)}
.bo-card::before{content:'';position:absolute;top:0;left:0;right:0;height:4px;background:#e5e7eb;border-radius:4px 4px 0 0}
.bo-card.ptg::before{background:#c8102e}
.bo-card.elv::before{background:#1d4ed8}
.bo-card-header{display:flex;align-items:center;gap:12px;margin-bottom:14px}
.bo-icon{width:44px;height:44px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:22px;flex-shrink:0}
.bo-icon.ptg{background:#fee2e2}
.bo-icon.elv{background:#dbeafe}
.bo-card h3{font-size:16px;font-weight:700;color:#1a1a2e}
.bo-card .bo-hosp{font-size:11px;color:#6b7280;margin-top:2px}
.bo-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:16px}
.bo-stat{background:#f9fafb;border-radius:8px;padding:8px 10px;text-align:center}
.bo-stat-v{font-size:18px;font-weight:700;color:#1a1a2e}
.bo-stat-l{font-size:10px;color:#9ca3af;margin-top:2px}
.bo-btn{display:inline-flex;align-items:center;gap:6px;padding:8px 16px;border-radius:8px;font-size:13px;font-weight:600;color:#fff;border:none;cursor:pointer}
.bo-btn.ptg{background:#c8102e}
.bo-btn.elv{background:#1d4ed8}
.landing-footer{font-size:11px;color:#9ca3af;text-align:center;max-width:500px;line-height:1.6}

/* ── BO DASHBOARD ── */
.bo-topbar{display:flex;align-items:center;gap:12px;padding:14px 24px 0;margin-bottom:0}
.bo-topbar h2{font-size:15px;font-weight:700;color:#1a1a2e}
.bo-topbar .bo-badge{font-size:11px;padding:3px 10px;border-radius:20px;font-weight:700}
.bo-badge-ptg{background:#fee2e2;color:#991b1b}
.bo-badge-elv{background:#dbeafe;color:#1e40af}
.main{padding:16px 24px}
.kpis{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-bottom:16px}
.kpi{background:#fff;border-radius:10px;padding:12px 14px;border:1px solid #e5e7eb}
.kpi-l{font-size:11px;color:#6b7280;margin-bottom:4px;font-weight:500}
.kpi-v{font-size:24px;font-weight:700}
.kpi-s{font-size:11px;color:#9ca3af;margin-top:3px}
.subtabs{display:flex;gap:4px;margin-bottom:14px;flex-wrap:wrap}
.subtab{padding:5px 13px;border-radius:6px;font-size:12px;font-weight:600;cursor:pointer;background:transparent;color:#6b7280;border:1px solid #e5e7eb}
.subtab.on{background:#1a1a2e;color:#fff;border-color:#1a1a2e}
.subview{display:none}
.subview.on{display:block}
.sec{font-size:11px;font-weight:600;color:#6b7280;text-transform:uppercase;letter-spacing:.06em;margin-bottom:8px}
.rooms{display:flex;flex-direction:column;gap:10px;margin-bottom:18px}
.rc{background:#fff;border-radius:10px;border:1px solid #e5e7eb;border-left:4px solid #e5e7eb;overflow:hidden}
.rc.ac{border-left-color:#10b981}
.rc.dl{border-left-color:#ef4444}
.rc.cl{border-left-color:#f59e0b}
.rc.id{border-left-color:#9ca3af}
.rc-hdr{padding:11px 14px;cursor:pointer;user-select:none;display:flex;align-items:center;gap:8px;flex-wrap:wrap}
.rc-hdr:hover{background:#fafafa}
.rn{font-size:13px;font-weight:700;min-width:56px}
.bdg{font-size:11px;padding:3px 9px;border-radius:20px;font-weight:600}
.bac{background:#d1fae5;color:#065f46}
.bdl{background:#fee2e2;color:#991b1b}
.bcl{background:#fef3c7;color:#92400e}
.bid{background:#f3f4f6;color:#4b5563}
.sp{font-size:13px;font-weight:600;flex:1}
.exp{margin-left:auto;font-size:12px;color:#9ca3af;transition:transform .2s}
.exp.open{transform:rotate(180deg)}
.rc-body{padding:0 14px 12px;border-top:1px solid #f3f4f6;display:none}
.rc-body.open{display:block}
.ctabs{display:flex;gap:4px;margin:10px 0 8px;flex-wrap:wrap}
.ctab{padding:4px 10px;border-radius:6px;font-size:11px;font-weight:600;cursor:pointer;background:transparent;color:#6b7280;border:1px solid #e5e7eb}
.ctab.on{background:#1a1a2e;color:#fff;border-color:#1a1a2e}
.cpanel{display:none}
.cpanel.open{display:block}
.rg{display:grid;grid-template-columns:repeat(5,1fr);gap:6px;margin-bottom:6px}
.ri-l{font-size:10px;color:#9ca3af;margin-bottom:2px}
.ri-v{font-size:13px;font-weight:600}
.rv-g{color:#10b981}.rv-w{color:#f59e0b}.rv-d{color:#ef4444}.rv-n{color:#1a1a2e}
.pbw{margin:6px 0}
.pbl{display:flex;justify-content:space-between;font-size:10px;color:#6b7280;margin-bottom:4px}
.pbg{height:5px;background:#f3f4f6;border-radius:3px;overflow:hidden}
.pbf{height:100%;border-radius:3px}
.fg{background:#10b981}.fw{background:#f59e0b}.fd{background:#ef4444}
.safe-tag{font-size:11px;color:#10b981;margin-top:6px;font-weight:600}
.delay-tag{font-size:11px;color:#ef4444;margin:4px 0;font-weight:600}
.team-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:6px}
.member{display:flex;align-items:center;gap:8px;padding:7px 10px;background:#f9fafb;border-radius:8px;border:1px solid #f3f4f6}
.av{width:32px;height:32px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:12px;font-weight:700;flex-shrink:0}
.av-cir{background:#dbeafe;color:#1d4ed8}
.av-ane{background:#ede9fe;color:#6d28d9}
.av-enf{background:#d1fae5;color:#065f46}
.av-ins{background:#fef9c3;color:#854d0e}
.av-aux{background:#fce7f3;color:#9d174d}
.m-name{font-size:12px;font-weight:600;color:#1a1a2e}
.m-role{font-size:10px;color:#6b7280}
.inst-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:8px}
.ibox{display:flex;align-items:center;gap:10px;padding:10px 12px;background:#f9fafb;border-radius:8px;border:1px solid #f3f4f6}
.ibox-ico{width:36px;height:36px;border-radius:8px;background:#fff;border:1px solid #e5e7eb;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0}
.ibox-info{flex:1;min-width:0}
.ibox-name{font-size:12px;font-weight:700;color:#1a1a2e}
.ibox-detail{font-size:10px;color:#6b7280;margin-top:2px}
.ibox-status{display:flex;align-items:center;gap:4px;margin-top:4px}
.st-ok{font-size:10px;font-weight:700;color:#10b981;background:#d1fae5;padding:2px 7px;border-radius:20px}
.st-pend{font-size:10px;font-weight:700;color:#92400e;background:#fef3c7;padding:2px 7px;border-radius:20px}
.st-miss{font-size:10px;font-weight:700;color:#991b1b;background:#fee2e2;padding:2px 7px;border-radius:20px}
.inst-note{font-size:11px;color:#6b7280;margin-top:8px;padding:6px 10px;background:#f9fafb;border-radius:6px;border-left:3px solid #e5e7eb}
.cs3{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:16px}
.csc{background:#fff;border-radius:10px;padding:12px 14px;border:1px solid #e5e7eb}
.cst{font-size:11px;color:#6b7280;margin-bottom:5px}
.csv{font-size:20px;font-weight:700}
.css{font-size:11px;color:#9ca3af;margin-top:2px}
.tov-wrap,.spc-wrap,.ck-wrap{background:#fff;border-radius:10px;padding:12px 14px;border:1px solid #e5e7eb;margin-bottom:16px}
.tor{display:flex;align-items:center;gap:8px;padding:5px 0;border-bottom:1px solid #f3f4f6;font-size:12px}
.tor:last-child{border-bottom:none}
.to-n{min-width:88px;color:#6b7280}
.to-b{flex:1;height:6px;background:#f3f4f6;border-radius:3px;overflow:hidden}
.to-f{height:100%;border-radius:3px}
.to-v{min-width:120px;text-align:right;font-size:12px;font-weight:600}
.sb{display:flex;align-items:center;gap:8px;margin-bottom:7px}
.sb-n{min-width:120px;font-size:12px;color:#6b7280}
.sb-b{flex:1;height:16px;background:#f3f4f6;border-radius:3px;overflow:hidden}
.sb-f{height:100%;border-radius:3px}
.sb-v{min-width:24px;text-align:right;font-size:12px;font-weight:600}
.ck-item{display:flex;align-items:center;gap:8px;padding:5px 0;border-bottom:1px solid #f3f4f6;font-size:12px}
.ck-item:last-child{border-bottom:none}
.ck-ok{color:#10b981;font-weight:700;font-size:14px}
.leg{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:10px;align-items:center}
.li{display:flex;align-items:center;gap:5px;font-size:11px;color:#6b7280}
.ld{width:8px;height:8px;border-radius:50%}
.hint{font-size:11px;color:#9ca3af;font-style:italic;margin-left:auto}
@media(max-width:700px){.kpis,.cs3,.inst-grid,.team-grid,.bo-cards,.bo-stats{grid-template-columns:1fr}.rg{grid-template-columns:repeat(3,1fr)}.bo-cards{max-width:100%}}
</style>
</head>
<body>

<!-- TOPBAR -->
<div class="topbar">
  <div class="topbar-left">
    <img src="data:image/png;base64,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" alt="ULS Alto Alentejo" style="height:38px;display:block;border-radius:4px">
    <div style="border-left:1px solid rgba(255,255,255,.2);padding-left:14px">
      <div style="font-size:10px;opacity:.5;letter-spacing:.08em;text-transform:uppercase;margin-bottom:2px">ULS Alto Alentejo</div>
      <h1>Gestão do Uso Diário dos Blocos Operatórios</h1>
    </div>
  </div>
  <div class="topbar-right">
    <div class="clk-wrap">
      <span id="clk">--:--:--</span>
      <span id="dt"></span>
    </div>
  </div>
</div>

<!-- NAV TABS -->
<div class="navtabs" id="navtabs">
  <button class="navtab on" id="nt-home" onclick="goView('home')">🏠 Início</button>
  <button class="navtab" id="nt-ptg" onclick="goView('ptg')" style="display:none">🏥 BO Portalegre</button>
  <button class="navtab" id="nt-elv" onclick="goView('elv')" style="display:none">🏥 BO Elvas</button>
  <button class="navtab back" id="nt-back" onclick="goHome()" style="display:none">← Voltar ao início</button>
</div>

<!-- ═══ VIEW: HOME ═══ -->
<div class="view on" id="view-home">
<div class="landing">
  <div class="landing-logo">
    <img src="data:image/png;base64,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" alt="ULS Alto Alentejo" style="height:72px;display:block">
  </div>
  <div class="landing-title">Gestão do Uso Diário<br>dos Blocos Operatórios</div>
  <div class="landing-sub">Monitorização em tempo real das salas cirúrgicas, equipas, instrumental e tempos operatórios dos dois blocos operatórios da ULS Alto Alentejo.</div>

  <div class="bo-cards">
    <!-- BO Portalegre -->
    <div class="bo-card ptg" onclick="goBO('ptg')">
      <div class="bo-card-header">
        <div class="bo-icon ptg">🏥</div>
        <div>
          <h3>BO Portalegre</h3>
          <div class="bo-hosp">Hospital Dr. José Maria Grande</div>
        </div>
      </div>
      <div class="bo-stats">
        <div class="bo-stat"><div class="bo-stat-v" style="color:#10b981">3</div><div class="bo-stat-l">Salas ativas</div></div>
        <div class="bo-stat"><div class="bo-stat-v">4</div><div class="bo-stat-l">Salas total</div></div>
        <div class="bo-stat"><div class="bo-stat-v" style="color:#ef4444">+12min</div><div class="bo-stat-l">Atraso médio</div></div>
      </div>
      <button class="bo-btn ptg">Aceder ao BO →</button>
    </div>

    <!-- BO Elvas -->
    <div class="bo-card elv" onclick="goBO('elv')">
      <div class="bo-card-header">
        <div class="bo-icon elv">🏥</div>
        <div>
          <h3>BO Elvas</h3>
          <div class="bo-hosp">Hospital de Santa Luzia de Elvas</div>
        </div>
      </div>
      <div class="bo-stats">
        <div class="bo-stat"><div class="bo-stat-v" style="color:#10b981">2</div><div class="bo-stat-l">Salas ativas</div></div>
        <div class="bo-stat"><div class="bo-stat-v">3</div><div class="bo-stat-l">Salas total</div></div>
        <div class="bo-stat"><div class="bo-stat-v" style="color:#f59e0b">+7min</div><div class="bo-stat-l">Atraso médio</div></div>
      </div>
      <button class="bo-btn elv">Aceder ao BO →</button>
    </div>
  </div>

  <div class="landing-footer">
    Dashboard de monitorização operacional · Dados actualizados a cada 60 segundos<br>
    ULS Alto Alentejo — Serviço de Gestão de Blocos Operatórios
  </div>
</div>
</div>

<!-- ═══ VIEW: BO PORTALEGRE ═══ -->
<div class="view" id="view-ptg">
<div class="bo-topbar">
  <span style="font-size:20px">🏥</span>
  <div>
    <h2>Bloco Operatório — Portalegre <span class="bo-badge bo-badge-ptg">HDJMG</span></h2>
    <div style="font-size:11px;color:#6b7280;margin-top:2px">Hospital Dr. José Maria Grande · 4 salas cirúrgicas</div>
  </div>
</div>
<div class="main">
  <div class="kpis">
    <div class="kpi"><div class="kpi-l">Salas ativas</div><div class="kpi-v" style="color:#10b981">3</div><div class="kpi-s">de 4 disponíveis</div></div>
    <div class="kpi"><div class="kpi-l">Em limpeza</div><div class="kpi-v" style="color:#f59e0b">1</div><div class="kpi-s">tempo médio 22 min</div></div>
    <div class="kpi"><div class="kpi-l">Cirurgias hoje</div><div class="kpi-v">9</div><div class="kpi-s">4 concluídas · 5 em curso/agend.</div></div>
    <div class="kpi"><div class="kpi-l">Atraso médio</div><div class="kpi-v" style="color:#ef4444">+12 min</div><div class="kpi-s">face ao programado</div></div>
  </div>

  <div class="subtabs">
    <button class="subtab on" onclick="ssv('ptg','salas',this)">🛏 Salas</button>
    <button class="subtab" onclick="ssv('ptg','resumo',this)">📊 Resumo do Dia</button>
  </div>

  <div class="subview on" id="sv-ptg-salas">
    <div class="leg">
      <div class="li"><div class="ld" style="background:#10b981"></div>Em cirurgia</div>
      <div class="li"><div class="ld" style="background:#f59e0b"></div>Em limpeza</div>
      <div class="li"><div class="ld" style="background:#9ca3af"></div>Disponível</div>
      <div class="li"><div class="ld" style="background:#ef4444"></div>Com atraso</div>
      <div class="hint">▼ Clique em cada sala para detalhes</div>
    </div>
    <div class="rooms" id="rh"></div>
  </div>

  <div class="subview" id="sv-ptg-resumo">
    <div class="cs3">
      <div class="csc"><div class="cst">Cirurgia Segura — realizadas</div><div class="csv" style="color:#10b981">9 / 9</div><div class="css">Checklist OMS completo</div></div>
      <div class="csc"><div class="cst">Cirurgias programadas hoje</div><div class="csv">9</div><div class="css">início do turno</div></div>
      <div class="csc"><div class="cst">Taxa de execução</div><div class="csv" style="color:#10b981">100%</div><div class="css">sem cancelamentos</div></div>
    </div>
    <div class="sec">Turnover entre cirurgias</div>
    <div class="tov-wrap" id="tov-ptg"></div>
    <div class="sec">Especialidades — distribuição hoje</div>
    <div class="spc-wrap" id="spc-ptg"></div>
    <div class="sec">Cirurgia Segura — Checklist OMS (última concluída)</div>
    <div class="ck-wrap">
      <div style="font-size:13px;font-weight:600;margin-bottom:8px">Sala 1 — Ortopedia / PTJ Direito</div>
      <div id="ck-list-ptg"></div>
    </div>
  </div>
</div>
</div>

<!-- ═══ VIEW: BO ELVAS ═══ -->
<div class="view" id="view-elv">
<div class="bo-topbar">
  <span style="font-size:20px">🏥</span>
  <div>
    <h2>Bloco Operatório — Elvas <span class="bo-badge bo-badge-elv">HSLE</span></h2>
    <div style="font-size:11px;color:#6b7280;margin-top:2px">Hospital de Santa Luzia de Elvas · 3 salas cirúrgicas</div>
  </div>
</div>
<div class="main">
  <div class="kpis">
    <div class="kpi"><div class="kpi-l">Salas ativas</div><div class="kpi-v" style="color:#10b981">2</div><div class="kpi-s">de 3 disponíveis</div></div>
    <div class="kpi"><div class="kpi-l">Em limpeza</div><div class="kpi-v" style="color:#f59e0b">1</div><div class="kpi-s">tempo médio 18 min</div></div>
    <div class="kpi"><div class="kpi-l">Cirurgias hoje</div><div class="kpi-v">7</div><div class="kpi-s">3 concluídas · 4 em curso/agend.</div></div>
    <div class="kpi"><div class="kpi-l">Atraso médio</div><div class="kpi-v" style="color:#f59e0b">+7 min</div><div class="kpi-s">face ao programado</div></div>
  </div>

  <div class="subtabs">
    <button class="subtab on" onclick="ssv('elv','salas',this)">🛏 Salas</button>
    <button class="subtab" onclick="ssv('elv','resumo',this)">📊 Resumo do Dia</button>
  </div>

  <div class="subview on" id="sv-elv-salas">
    <div class="leg">
      <div class="li"><div class="ld" style="background:#10b981"></div>Em cirurgia</div>
      <div class="li"><div class="ld" style="background:#f59e0b"></div>Em limpeza</div>
      <div class="li"><div class="ld" style="background:#9ca3af"></div>Disponível</div>
      <div class="li"><div class="ld" style="background:#ef4444"></div>Com atraso</div>
      <div class="hint">▼ Clique em cada sala para detalhes</div>
    </div>
    <div class="rooms" id="rs"></div>
  </div>

  <div class="subview" id="sv-elv-resumo">
    <div class="cs3">
      <div class="csc"><div class="cst">Cirurgia Segura — realizadas</div><div class="csv" style="color:#10b981">7 / 7</div><div class="css">Checklist OMS completo</div></div>
      <div class="csc"><div class="cst">Cirurgias programadas hoje</div><div class="csv">7</div><div class="css">início do turno</div></div>
      <div class="csc"><div class="cst">Taxa de execução</div><div class="csv" style="color:#10b981">100%</div><div class="css">sem cancelamentos</div></div>
    </div>
    <div class="sec">Turnover entre cirurgias</div>
    <div class="tov-wrap" id="tov-elv"></div>
    <div class="sec">Especialidades — distribuição hoje</div>
    <div class="spc-wrap" id="spc-elv"></div>
    <div class="sec">Cirurgia Segura — Checklist OMS (última concluída)</div>
    <div class="ck-wrap">
      <div style="font-size:13px;font-weight:600;margin-bottom:8px">Sala 1 — Ginecologia / Histeroscopia</div>
      <div id="ck-list-elv"></div>
    </div>
  </div>
</div>
</div>

<script>
var N=new Date();
function p(n){return String(n).padStart(2,'0')}
function ft(d){return p(d.getHours())+':'+p(d.getMinutes())}
function T(h,m){var d=new Date(N);d.setHours(h,m,0,0);return d}
function elp(s){return Math.max(0,Math.round((N-s)/60000))}
function rem2(s,dur){return Math.max(0,dur-elp(s))}

// ── DADOS PORTALEGRE ──
var HR=[
  {nm:'Sala 1',st:'ac',sp:'Ortopedia',cg:'Prótese Total do Joelho (PTJ) — Direito',ip:T(8,0),ir:T(8,10),de:120,sf:true,
   equipa:[
    {nome:'Dr. António Ferreira',papel:'Cirurgião Principal',av:'av-cir',ini:'AF'},
    {nome:'Dr. Rui Mendes',papel:'Cirurgião Assistente',av:'av-cir',ini:'RM'},
    {nome:'Dr.ª Sofia Lopes',papel:'Anestesiologista',av:'av-ane',ini:'SL'},
    {nome:'Enf.ª Carla Nunes',papel:'Enf. Instrumentista',av:'av-enf',ini:'CN'},
    {nome:'Enf.º Pedro Sousa',papel:'Enf. Circulante',av:'av-enf',ini:'PS'},
    {nome:'Aux. Marta Gomes',papel:'Auxiliar de Bloco',av:'av-aux',ini:'MG'},
   ],
   instrumental:[
    {ico:'📦',nm:'Caixa de PTJ',detalhe:'Sistema Zimmer Biomet — NexGen',st:'ok'},
    {ico:'📦',nm:'Caixa de Osteossíntese',detalhe:'Parafusos / placas cortical e esponjosa',st:'ok'},
    {ico:'📦',nm:'Caixa de Instrumental Base',detalhe:'Bisturi, tesouras, pinças, afastadores',st:'ok'},
   ],
   instNota:'Implante PTJ confirmado — tamanho Fémur C / Tíbia 4'
  },
  {nm:'Sala 2',st:'dl',sp:'Cirurgia Geral',cg:'Colecistectomia Laparoscópica',ip:T(8,30),ir:T(8,30),de:90,ex:25,sf:true,
   equipa:[
    {nome:'Dr.ª Helena Costa',papel:'Cirurgiã Principal',av:'av-cir',ini:'HC'},
    {nome:'Dr. Nuno Azevedo',papel:'Anestesiologista',av:'av-ane',ini:'NA'},
    {nome:'Enf.ª Teresa Faria',papel:'Enf. Instrumentista',av:'av-enf',ini:'TF'},
    {nome:'Enf.º João Ribeiro',papel:'Enf. Circulante',av:'av-enf',ini:'JR'},
   ],
   instrumental:[
    {ico:'📦',nm:'Caixa de Laparoscopia',detalhe:'Trocares, câmara HD, insuflador CO₂',st:'ok'},
    {ico:'📦',nm:'Caixa de Bisturi Harmónico',detalhe:'Ultracision Ethicon',st:'ok'},
    {ico:'📦',nm:'Caixa de Instrumental Base',detalhe:'Bisturi, tesouras, pinças',st:'ok'},
   ],
   instNota:'Endobag e clips Ligaclip confirmados no stock de sala'
  },
  {nm:'Sala 3',st:'cl',cg:'Em limpeza — última: Herniorrafia Inguinal',cs:T(N.getHours(),N.getMinutes()-14),ce:20,sf:false,
   equipa:[
    {nome:'Aux. Fátima Rodrigues',papel:'Auxiliar de Limpeza',av:'av-aux',ini:'FR'},
    {nome:'Enf.ª Ana Baptista',papel:'Enf. Circulante (supervisão)',av:'av-enf',ini:'AB'},
   ],
   instrumental:[],instNota:''
  },
  {nm:'Sala 4',st:'id',cg:'Disponível — próxima: Urologia (14:00)',sf:false,equipa:[],instrumental:[],instNota:''},
];

// ── DADOS ELVAS ──
var SR=[
  {nm:'Sala 1',st:'ac',sp:'Ginecologia',cg:'Histeroscopia Diagnóstica + Curetagem',ip:T(9,0),ir:T(9,5),de:60,sf:true,
   equipa:[
    {nome:'Dr.ª Margarida Pinto',papel:'Ginecologista / Cirurgiã',av:'av-cir',ini:'MP'},
    {nome:'Dr. Luís Fernandes',papel:'Anestesiologista',av:'av-ane',ini:'LF'},
    {nome:'Enf.ª Susana Vieira',papel:'Enf. Instrumentista',av:'av-enf',ini:'SV'},
    {nome:'Enf.º Carlos Moura',papel:'Enf. Circulante',av:'av-enf',ini:'CM'},
   ],
   instrumental:[
    {ico:'📦',nm:'Caixa de Histeroscopia',detalhe:'Histeroscópio rígido 4mm + sistema distensão',st:'ok'},
    {ico:'📦',nm:'Caixa de Curetagem',detalhe:'Curetas de Sharman, tenáculo cervical',st:'ok'},
    {ico:'📦',nm:'Caixa de Instrumental Base',detalhe:'Bisturi, pinças, afastadores ginecológicos',st:'ok'},
   ],
   instNota:'Soro fisiológico para distensão uterina (3L) confirmado'
  },
  {nm:'Sala 2',st:'ac',sp:'Neurocirurgia',cg:'Discectomia L4-L5 — Hérnia Discal',ip:T(8,0),ir:T(8,15),de:150,sf:true,
   equipa:[
    {nome:'Prof. Dr. Eduardo Matos',papel:'Neurocirurgião Principal',av:'av-cir',ini:'EM'},
    {nome:'Dr. Filipe Carvalho',papel:'Neurocirurgião Assistente',av:'av-cir',ini:'FC'},
    {nome:'Dr.ª Inês Teixeira',papel:'Anestesiologista',av:'av-ane',ini:'IT'},
    {nome:'Enf.º Rui Gonçalves',papel:'Enf. Instrumentista',av:'av-ins',ini:'RG'},
    {nome:'Enf.ª Beatriz Lima',papel:'Enf. Circulante',av:'av-enf',ini:'BL'},
    {nome:'Téc. Miguel Santos',papel:'Neurofisiologista intra-op.',av:'av-aux',ini:'MS'},
   ],
   instrumental:[
    {ico:'📦',nm:'Caixa de Microcirurgia Espinhal',detalhe:'Micro-tesouras, micro-pinças, bipolar',st:'ok'},
    {ico:'📦',nm:'Caixa de Discectomia / Laminectomia',detalhe:'Goivas, punch Kerrison, afastador METRx',st:'ok'},
    {ico:'📦',nm:'Caixa de Implante TLIF',detalhe:'Cage intradiscal + parafusos pediculares',st:'ok'},
    {ico:'🔬',nm:'Microscópio Zeiss Kinevo',detalhe:'Agendado e confirmado na sala',st:'ok'},
   ],
   instNota:'Monitorização neurofisiológica intra-op. activa — EMG L4-S1 + potenciais evocados'
  },
  {nm:'Sala 3',st:'cl',cg:'Em limpeza — última: Artroscopia do Ombro',cs:T(N.getHours(),N.getMinutes()-8),ce:18,sf:false,
   equipa:[
    {nome:'Aux. Rosa Carvalho',papel:'Auxiliar de Limpeza',av:'av-aux',ini:'RC'},
   ],
   instrumental:[],instNota:''
  },
];

// ── NAVEGAÇÃO ──
var curView='home';
function goView(v){
  document.querySelectorAll('.view').forEach(function(el){el.classList.remove('on')});
  document.getElementById('view-'+v).classList.add('on');
  document.querySelectorAll('.navtab').forEach(function(b){b.classList.remove('on')});
  document.getElementById('nt-'+v).classList.add('on');
  if(v==='home'){
    document.getElementById('nt-ptg').style.display='none';
    document.getElementById('nt-elv').style.display='none';
    document.getElementById('nt-back').style.display='none';
  } else {
    document.getElementById('nt-ptg').style.display='';
    document.getElementById('nt-elv').style.display='';
    document.getElementById('nt-back').style.display='';
  }
  curView=v;
}
function goBO(bo){goView(bo)}
function goHome(){goView('home')}

// ── SUB-VIEWS (salas / resumo) ──
function ssv(bo,panel,btn){
  var prefix='sv-'+bo+'-';
  document.querySelectorAll('[id^="'+prefix+'"]').forEach(function(el){el.classList.remove('on')});
  var btns=btn.parentElement.querySelectorAll('.subtab');
  for(var i=0;i<btns.length;i++) btns[i].classList.remove('on');
  document.getElementById(prefix+panel).classList.add('on');
  btn.classList.add('on');
}

// ── RENDER SALAS ──
var UID=0;
function stLabel(s){
  return s==='ok'?'<span class="st-ok">✓ Na sala</span>'
        :s==='pend'?'<span class="st-pend">⏳ Em esterilização</span>'
        :'<span class="st-miss">✗ Não localizada</span>';
}
function mkRoom(r){
  var uid='u'+(UID++);
  var sc={ac:'ac',dl:'dl',cl:'cl',id:'id'}[r.st]||'id';
  var bc={ac:'bac',dl:'bdl',cl:'bcl',id:'bid'}[r.st]||'bid';
  var bt={ac:'Em cirurgia',dl:'Com atraso',cl:'Em limpeza',id:'Disponível'}[r.st]||'Disponível';
  var hdr='<div class="rc-hdr" onclick="tog(\''+uid+'\')">'
    +'<span class="rn">'+r.nm+'</span>'
    +'<span class="bdg '+bc+'">'+bt+'</span>';
  if(r.sp) hdr+='<span class="sp">'+r.sp+'</span>';
  else hdr+='<span style="flex:1"></span>';
  hdr+='<span style="font-size:11px;color:#9ca3af;max-width:260px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap">'+r.cg+'</span>'
    +'<span class="exp" id="ei-'+uid+'">▼</span></div>';
  var hasCirg=(r.st==='ac'||r.st==='dl');
  var hasClean=(r.st==='cl');
  var hasTeam=r.equipa&&r.equipa.length>0;
  var hasInst=r.instrumental&&r.instrumental.length>0;
  var body='<div class="rc-body" id="bd-'+uid+'">';
  var ct='<div class="ctabs">';
  if(hasCirg) ct+='<button class="ctab on" onclick="ctab(\''+uid+'\',\'tm\',this)">⏱ Tempo</button>';
  if(hasClean) ct+='<button class="ctab on" onclick="ctab(\''+uid+'\',\'lm\',this)">🧹 Limpeza</button>';
  if(hasTeam) ct+='<button class="ctab '+((!hasCirg&&!hasClean)?'on':'')+'" onclick="ctab(\''+uid+'\',\'eq\',this)">👥 Equipa</button>';
  if(hasInst) ct+='<button class="ctab" onclick="ctab(\''+uid+'\',\'in\',this)">📦 Instrumental</button>';
  ct+='</div>';
  body+=ct;
  if(hasCirg){
    var e=elp(r.ir),rm=rem2(r.ir,r.de);
    var at=r.ex||Math.max(0,e-r.de);
    var pct=Math.min(100,Math.round(e/r.de*100));
    var fc=pct>=100?'fd':pct>70?'fw':'fg';
    var rc2=rm===0?'rv-d':at>0?'rv-w':'rv-g';
    var ic2=r.ir>r.ip?'rv-w':'rv-g';
    body+='<div class="cpanel open" id="pn-'+uid+'-tm">'
      +'<div style="font-size:12px;color:#6b7280;margin-bottom:8px">🔪 '+r.cg+'</div>'
      +'<div class="rg">'
      +'<div><div class="ri-l">Início prog.</div><div class="ri-v rv-n">'+ft(r.ip)+'</div></div>'
      +'<div><div class="ri-l">Início real</div><div class="ri-v '+ic2+'">'+ft(r.ir)+'</div></div>'
      +'<div><div class="ri-l">Duração est.</div><div class="ri-v rv-n">'+r.de+' min</div></div>'
      +'<div><div class="ri-l">Decorrido</div><div class="ri-v rv-n">'+e+' min</div></div>'
      +'<div><div class="ri-l">Restante</div><div class="ri-v '+rc2+'">'+rm+' min</div></div>'
      +'</div>';
    if(at>0) body+='<div class="delay-tag">⚠ +'+at+' min acima do estimado</div>';
    body+='<div class="pbw"><div class="pbl"><span>Progresso</span><span>'+pct+'%</span></div>'
      +'<div class="pbg"><div class="pbf '+fc+'" style="width:'+pct+'%"></div></div></div>';
    if(r.sf) body+='<div class="safe-tag">✔ Cirurgia Segura — Checklist OMS completo</div>';
    body+='</div>';
  }
  if(hasClean){
    var ce=elp(r.cs),cr=Math.max(0,r.ce-ce),cp=Math.min(100,Math.round(ce/r.ce*100));
    body+='<div class="cpanel open" id="pn-'+uid+'-lm">'
      +'<div style="font-size:12px;color:#6b7280;margin-bottom:8px">🧹 '+r.cg+'</div>'
      +'<div class="rg" style="grid-template-columns:repeat(3,1fr)">'
      +'<div><div class="ri-l">Tempo estimado</div><div class="ri-v rv-n">'+r.ce+' min</div></div>'
      +'<div><div class="ri-l">Decorrido</div><div class="ri-v rv-w">'+ce+' min</div></div>'
      +'<div><div class="ri-l">Restante</div><div class="ri-v '+(cr<=3?'rv-g':'rv-n')+'">'+cr+' min</div></div>'
      +'</div>'
      +'<div class="pbw"><div class="pbl"><span>Limpeza</span><span>'+cp+'%</span></div>'
      +'<div class="pbg"><div class="pbf fw" style="width:'+cp+'%"></div></div></div>'
      +'</div>';
  }
  if(hasTeam){
    var tf=(!hasCirg&&!hasClean)?'open':'';
    body+='<div class="cpanel '+tf+'" id="pn-'+uid+'-eq"><div class="team-grid">';
    for(var i=0;i<r.equipa.length;i++){
      var m=r.equipa[i];
      body+='<div class="member"><div class="av '+m.av+'">'+m.ini+'</div>'
        +'<div><div class="m-name">'+m.nome+'</div><div class="m-role">'+m.papel+'</div></div></div>';
    }
    body+='</div></div>';
  }
  if(hasInst){
    body+='<div class="cpanel" id="pn-'+uid+'-in"><div class="inst-grid">';
    for(var k=0;k<r.instrumental.length;k++){
      var it=r.instrumental[k];
      body+='<div class="ibox"><div class="ibox-ico">'+it.ico+'</div>'
        +'<div class="ibox-info"><div class="ibox-name">'+it.nm+'</div>'
        +'<div class="ibox-detail">'+it.detalhe+'</div>'
        +'<div class="ibox-status">'+stLabel(it.st)+'</div>'
        +'</div></div>';
    }
    body+='</div>';
    if(r.instNota) body+='<div class="inst-note">📋 '+r.instNota+'</div>';
    body+='</div>';
  }
  if(r.st==='id') body+='<div style="padding:10px 0;font-size:12px;color:#9ca3af">📋 '+r.cg+'</div>';
  body+='</div>';
  var d=document.createElement('div');
  d.className='rc '+sc;
  d.innerHTML=hdr+body;
  return d;
}
function tog(uid){
  var bd=document.getElementById('bd-'+uid);
  var ei=document.getElementById('ei-'+uid);
  bd.classList.toggle('open');
  ei.classList.toggle('open',bd.classList.contains('open'));
}
function ctab(uid,panel,btn){
  var body=document.getElementById('bd-'+uid);
  body.querySelectorAll('.cpanel').forEach(function(p){p.classList.remove('open')});
  body.querySelectorAll('.ctab').forEach(function(b){b.classList.remove('on')});
  var pn=document.getElementById('pn-'+uid+'-'+panel);
  if(pn) pn.classList.add('open');
  btn.classList.add('on');
}
function buildRooms(rooms,id){
  var c=document.getElementById(id);c.innerHTML='';
  for(var i=0;i<rooms.length;i++) c.appendChild(mkRoom(rooms[i]));
}

// ── RESUMO ──
function buildTov(rows,id){
  var html='';
  for(var i=0;i<rows.length;i++){
    var row=rows[i];var pct=Math.round(row.r/35*100);
    var col=row.r>row.e?'#ef4444':'#10b981';
    var diff=row.r-row.e;
    var ds=diff>0?' (+'+diff+'min)':diff<0?' ('+diff+'min)':'';
    html+='<div class="tor"><span class="to-n">'+row.n+'</span>'
      +'<div class="to-b"><div class="to-f" style="width:'+pct+'%;background:'+col+'"></div></div>'
      +'<span class="to-v" style="color:'+col+'">'+row.r+' min'+ds+' <span style="color:#9ca3af;font-weight:400">est. '+row.e+'</span></span></div>';
  }
  document.getElementById(id).innerHTML=html;
}
function buildSpc(sp,id){
  var tot=0;for(var i=0;i<sp.length;i++) tot+=sp[i].v;
  var html='';
  for(var i=0;i<sp.length;i++){
    var s=sp[i];var pct=Math.round(s.v/tot*100);
    html+='<div class="sb"><span class="sb-n">'+s.n+'</span>'
      +'<div class="sb-b"><div class="sb-f" style="width:'+pct+'%;background:'+s.c+'"></div></div>'
      +'<span class="sb-v">'+s.v+' <span style="font-weight:400;color:#9ca3af;font-size:11px">('+pct+'%)</span></span></div>';
  }
  document.getElementById(id).innerHTML=html;
}
function buildCk(id){
  var sections=[
    {t:'Sign In — Antes da indução anestésica',items:['Identidade do doente confirmada (pulseira + voz)','Consentimento informado assinado e verificado','Local cirúrgico marcado pelo cirurgião','Verificação de equipamento e fármacos de anestesia','Oximetria de pulso colocada e funcionante','Alergias conhecidas — nenhuma identificada']},
    {t:'Time Out — Antes da incisão cirúrgica',items:['Toda a equipa se apresentou (nome e função)','Procedimento, local e lado confirmados verbalmente','Profilaxia antibiótica administrada há < 60 min','Antecipação de eventos críticos pela equipa','Imagiologia essencial disponível na sala','Contagem inicial de compressas e instrumentos']},
    {t:'Sign Out — Antes do doente sair da sala',items:['Procedimento cirúrgico realizado confirmado','Contagem final de compressas correcta','Contagem final de instrumentos correcta','Peças para anatomia patológica etiquetadas','Problemas de equipamento registados','Informação de recuperação comunicada à equipa']},
  ];
  var html='';
  for(var s=0;s<sections.length;s++){
    var sec=sections[s];
    html+='<div style="font-size:11px;font-weight:600;color:#6b7280;text-transform:uppercase;letter-spacing:.05em;margin:10px 0 4px;padding:5px 8px;background:#f9fafb;border-radius:6px">'+sec.t+'</div>';
    for(var i=0;i<sec.items.length;i++) html+='<div class="ck-item"><span class="ck-ok">✓</span>'+sec.items[i]+'</div>';
  }
  document.getElementById(id).innerHTML=html;
}

// ── RELÓGIO ──
function uck(){
  var d=new Date();
  document.getElementById('clk').textContent=p(d.getHours())+':'+p(d.getMinutes())+':'+p(d.getSeconds());
  document.getElementById('dt').textContent=d.toLocaleDateString('pt-PT',{weekday:'short',day:'numeric',month:'short',year:'numeric'});
}

// ── INIT ──
buildRooms(HR,'rh');
buildRooms(SR,'rs');
buildTov([
  {n:'S1',e:18,r:20},{n:'S2',e:18,r:15},{n:'S3',e:20,r:14}
],'tov-ptg');
buildTov([
  {n:'S1',e:15,r:12},{n:'S2',e:20,r:22},{n:'S3',e:18,r:8}
],'tov-elv');
buildSpc([
  {n:'Ortopedia',v:4,c:'#10b981'},{n:'Cirurgia Geral',v:3,c:'#3b82f6'},{n:'Urologia',v:2,c:'#f59e0b'}
],'spc-ptg');
buildSpc([
  {n:'Ginecologia',v:3,c:'#ec4899'},{n:'Neurocirurgia',v:2,c:'#8b5cf6'},{n:'Oftalmologia',v:2,c:'#06b6d4'}
],'spc-elv');
buildCk('ck-list-ptg');
buildCk('ck-list-elv');
uck();
setInterval(uck,1000);
setInterval(function(){buildRooms(HR,'rh');buildRooms(SR,'rs');},60000);
</script>
</body>
</html>
