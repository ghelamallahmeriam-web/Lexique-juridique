# Lexique-juridique<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>⚖️ Glossaire Juridique</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;800&family=Source+Sans+3:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
<style>
:root {
  --navy: #1e3a5f;
  --navy-light: #2c5282;
  --gold: #c9a84c;
  --gold-light: #e0c068;
  --parchment: #f8f6f1;
  --parchment-dark: #ede8dc;
  --border: #d5cfc3;
  --text: #1a1a1a;
  --text-muted: #666;
  --white: #fff;
  --radius: 12px;
}

* { box-sizing: border-box; margin: 0; padding: 0; }
body {
  font-family: 'Source Sans 3', system-ui, sans-serif;
  background: linear-gradient(180deg, var(--parchment) 0%, var(--parchment-dark) 100%);
  color: var(--text);
  min-height: 100vh;
}

/* ─── HEADER ─── */
.header {
  background: linear-gradient(135deg, var(--navy) 0%, var(--navy-light) 100%);
  color: var(--white);
  padding: 28px 32px 24px;
  display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 16px;
}
.header h1 {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 28px; font-weight: 800; display: flex; align-items: center; gap: 12px;
}
.header .subtitle { opacity: .75; font-size: 14px; margin-top: 4px; }
.btn-add {
  display: flex; align-items: center; gap: 8px;
  padding: 11px 22px; background: linear-gradient(135deg, var(--gold), var(--gold-light));
  color: var(--text); border: none; border-radius: 10px; font-size: 15px; font-weight: 700;
  cursor: pointer; transition: all .2s; font-family: inherit;
}
.btn-add:hover { transform: translateY(-1px); box-shadow: 0 4px 14px rgba(201,168,76,.4); }

/* ─── NOTIFICATION ─── */
.notif {
  position: fixed; top: 20px; right: 20px; padding: 12px 22px; border-radius: 10px;
  font-size: 14px; font-weight: 600; z-index: 1000; box-shadow: 0 4px 16px rgba(0,0,0,.15);
  animation: slideDown .3s ease; pointer-events: none;
}
.notif.success { background: #d1fae5; color: #065f46; }
.notif.delete { background: #fee2e2; color: #991b1b; }
@keyframes slideDown { from { opacity:0; transform:translateY(-10px); } to { opacity:1; transform:translateY(0); } }

/* ─── CHIPS ─── */
.chips { display: flex; flex-wrap: wrap; gap: 8px; padding: 18px 32px 0; }
.chip {
  display: flex; align-items: center; gap: 6px; padding: 6px 14px;
  border: 1.5px solid; border-radius: 20px; font-size: 13px; font-weight: 600;
  cursor: pointer; transition: all .2s; background: var(--white);
}
.chip:hover { transform: translateY(-1px); }
.chip .count {
  background: rgba(0,0,0,.08); border-radius: 10px; padding: 1px 7px; font-size: 11px;
}
.chip.active { color: var(--white) !important; }

/* ─── FILTERS ─── */
.filters { padding: 16px 32px; display: flex; flex-direction: column; gap: 12px; }
.search-wrap { position: relative; display: flex; align-items: center; }
.search-wrap .icon { position: absolute; left: 14px; font-size: 16px; pointer-events: none; }
.search-input {
  width: 100%; padding: 12px 40px 12px 42px;
  border: 2px solid var(--border); border-radius: 10px; font-size: 15px;
  background: var(--white); font-family: inherit; outline: none; transition: border-color .2s;
}
.search-input:focus { border-color: var(--navy); }
.search-clear {
  position: absolute; right: 12px; background: none; border: none;
  font-size: 16px; cursor: pointer; color: #999;
}
.filter-row { display: flex; flex-wrap: wrap; gap: 10px; align-items: center; }
.filter-row select {
  padding: 8px 12px; border: 2px solid var(--border); border-radius: 8px;
  font-size: 14px; background: var(--white); cursor: pointer; font-family: inherit;
}
.filter-toggle {
  padding: 8px 16px; border: 2px solid var(--navy); border-radius: 8px;
  font-size: 13px; font-weight: 600; cursor: pointer; transition: all .2s;
  background: transparent; color: var(--navy); font-family: inherit;
}
.filter-toggle.active { background: var(--navy); color: var(--white); }

/* ─── EMPTY STATE ─── */
.empty { text-align: center; padding: 60px 32px; }
.empty .icon { font-size: 56px; margin-bottom: 12px; }
.empty h3 { font-family: 'Playfair Display', serif; font-size: 20px; color: var(--navy); margin-bottom: 8px; }
.empty p { color: var(--text-muted); font-size: 15px; }

/* ─── CARDS ─── */
.entries { padding: 8px 32px 40px; display: flex; flex-direction: column; gap: 12px; }
.card {
  background: var(--white); border-radius: 14px; border: 1px solid #e2ddd4;
  overflow: hidden; transition: all .25s; box-shadow: 0 1px 4px rgba(0,0,0,.04);
  animation: fadeIn .3s ease both;
}
.card.expanded { box-shadow: 0 4px 20px rgba(30,58,95,.12); border-color: #b8b0a0; }
@keyframes fadeIn { from { opacity:0; transform:translateY(6px); } to { opacity:1; transform:translateY(0); } }

.card-header {
  padding: 16px 20px; display: flex; justify-content: space-between;
  align-items: center; cursor: pointer; gap: 12px;
}
.card-title {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 17px; font-weight: 700; color: var(--navy); line-height: 1.3;
}
.card-ref { font-size: 13px; color: #888; font-family: 'Courier New', monospace; letter-spacing: .02em; }
.card-right { display: flex; align-items: center; gap: 10px; flex-shrink: 0; }
.badge-entreprise {
  font-size: 12px; padding: 4px 10px; background: #fef3c7; color: #92400e;
  border-radius: 6px; font-weight: 600; white-space: nowrap;
}
.arrow { font-size: 11px; color: #999; transition: transform .3s; }
.card.expanded .arrow { transform: rotate(180deg); }

.card-domains { padding: 0 20px 14px; display: flex; flex-wrap: wrap; gap: 6px; }
.domain-tag { font-size: 12px; padding: 3px 10px; border-radius: 6px; font-weight: 600; }
.custom-tag { font-size: 12px; padding: 3px 10px; border-radius: 6px; background: #f3f4f6; color: #4b5563; }

.card-body { padding: 4px 20px 20px; border-top: 1px solid #f0ece4; animation: fadeIn .25s ease; }
.section { margin-top: 18px; }
.section-title {
  margin-bottom: 8px; font-size: 12px; font-weight: 700; color: var(--navy);
  text-transform: uppercase; letter-spacing: .04em;
}
.legal-text {
  padding: 16px 20px; background: #fdfcf9; border: 1px solid #e8e3d9;
  border-left: 4px solid var(--gold); border-radius: 0 10px 10px 0;
  font-size: 14px; line-height: 1.75; white-space: pre-wrap; color: #333;
  font-family: Georgia, serif;
}
.explanation-text {
  padding: 16px 20px; background: #f0f9ff; border: 1px solid #bae6fd;
  border-radius: 10px; font-size: 14px; line-height: 1.75; white-space: pre-wrap; color: #0c4a6e;
}
.entreprise-text {
  padding: 16px 20px; background: #fffbeb; border: 1px solid #fde68a;
  border-radius: 10px; font-size: 14px; line-height: 1.75; white-space: pre-wrap; color: #78350f;
}
.links-wrap { display: flex; flex-direction: column; gap: 6px; }
.link-item {
  display: inline-flex; align-items: center; gap: 6px; padding: 8px 14px;
  background: var(--parchment); border-radius: 8px; color: var(--navy);
  font-size: 14px; text-decoration: none; transition: background .2s; word-break: break-all;
}
.link-item:hover { background: var(--parchment-dark); }

.card-footer {
  display: flex; justify-content: space-between; align-items: center;
  margin-top: 18px; padding-top: 14px; border-top: 1px solid #f0ece4;
  flex-wrap: wrap; gap: 10px;
}
.date-text { font-size: 12px; color: #999; }
.card-actions { display: flex; gap: 8px; align-items: center; }
.btn-edit {
  padding: 7px 16px; background: #e0e7ff; border: none; border-radius: 8px;
  font-size: 13px; cursor: pointer; color: #3730a3; font-weight: 600; font-family: inherit;
}
.btn-edit:hover { background: #c7d2fe; }
.btn-delete {
  padding: 7px 12px; background: #fee2e2; border: none; border-radius: 8px;
  font-size: 13px; cursor: pointer; font-family: inherit;
}
.btn-delete:hover { background: #fecaca; }
.confirm-wrap { display: flex; align-items: center; gap: 6px; }
.confirm-text { font-size: 13px; color: #dc2626; font-weight: 600; }
.btn-confirm-yes {
  padding: 4px 12px; background: #dc2626; color: var(--white); border: none;
  border-radius: 6px; font-size: 12px; cursor: pointer; font-weight: 600;
}
.btn-confirm-no {
  padding: 4px 12px; background: #e5e7eb; border: none; border-radius: 6px;
  font-size: 12px; cursor: pointer; font-weight: 600;
}

/* ─── MODAL / FORM ─── */
.modal-overlay {
  position: fixed; inset: 0; background: rgba(0,0,0,.5); z-index: 900;
  display: flex; align-items: flex-start; justify-content: center;
  padding: 30px 16px; overflow-y: auto; animation: fadeIn .2s ease;
}
.modal {
  background: var(--parchment); border-radius: 16px; width: 100%; max-width: 800px;
  box-shadow: 0 20px 60px rgba(0,0,0,.25); animation: slideDown .3s ease;
}
.modal-header {
  background: linear-gradient(135deg, var(--navy), var(--navy-light));
  color: var(--white); padding: 20px 28px; border-radius: 16px 16px 0 0;
  display: flex; justify-content: space-between; align-items: center;
}
.modal-header h2 {
  font-family: 'Playfair Display', serif; font-size: 22px; display: flex; align-items: center; gap: 10px;
}
.btn-back {
  padding: 8px 18px; background: rgba(255,255,255,.12); color: var(--white);
  border: 1px solid rgba(255,255,255,.25); border-radius: 8px; font-size: 14px;
  cursor: pointer; font-family: inherit;
}
.btn-back:hover { background: rgba(255,255,255,.2); }
.modal-body { padding: 24px 28px 32px; }

.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 22px; }
.form-field { margin-bottom: 22px; }
.form-field label { display: block; margin-bottom: 7px; font-size: 14px; font-weight: 700; color: var(--navy); }
.form-field label .hint { font-weight: 400; color: #999; font-size: 12px; }
.form-field input, .form-field textarea {
  width: 100%; padding: 11px 14px; border: 2px solid var(--border); border-radius: 8px;
  font-size: 15px; background: var(--white); font-family: inherit; outline: none;
  transition: border-color .2s;
}
.form-field input:focus, .form-field textarea:focus { border-color: var(--navy); }
.form-field textarea { min-height: 100px; resize: vertical; line-height: 1.65; }

.domains-grid { display: flex; flex-wrap: wrap; gap: 8px; }
.domain-btn {
  padding: 8px 15px; border: 2px solid; border-radius: 8px; font-size: 13px;
  font-weight: 600; cursor: pointer; transition: all .2s; font-family: inherit;
  background: var(--white);
}
.domain-btn.active { color: var(--white) !important; }

.check-row { display: flex; align-items: center; gap: 10px; margin-bottom: 10px; }
.checkbox-btn {
  width: 26px; height: 26px; border-radius: 6px; border: 2px solid var(--border);
  display: flex; align-items: center; justify-content: center; cursor: pointer;
  transition: all .2s; background: var(--white); font-size: 15px; font-weight: 700; color: var(--white);
}
.checkbox-btn.active { background: var(--navy); border-color: var(--navy); }

.lien-row { display: flex; gap: 10px; margin-bottom: 8px; align-items: center; }
.lien-row input { flex: 1; }
.lien-row input:first-child { flex: 2; }
.btn-remove-lien {
  width: 34px; height: 34px; border-radius: 6px; border: none; background: #fee2e2;
  color: #dc2626; font-size: 14px; cursor: pointer; flex-shrink: 0;
}
.btn-add-lien {
  padding: 8px 18px; background: transparent; border: 2px dashed var(--border);
  border-radius: 8px; font-size: 13px; color: #888; cursor: pointer; font-family: inherit;
}
.btn-add-lien:hover { border-color: var(--navy); color: var(--navy); }

.form-actions { display: flex; justify-content: flex-end; gap: 12px; margin-top: 12px; }
.btn-cancel {
  padding: 12px 24px; background: transparent; border: 2px solid var(--border);
  border-radius: 10px; font-size: 15px; cursor: pointer; color: var(--text-muted); font-family: inherit;
}
.btn-save {
  padding: 12px 28px; background: linear-gradient(135deg, var(--navy), var(--navy-light));
  color: var(--white); border: none; border-radius: 10px; font-size: 15px;
  font-weight: 700; cursor: pointer; transition: opacity .2s; font-family: inherit;
}
.btn-save:disabled { opacity: .45; cursor: default; }

/* ─── EXPORT BAR ─── */
.export-bar { padding: 0 32px 8px; display: flex; gap: 8px; flex-wrap: wrap; }
.btn-export {
  padding: 6px 14px; background: var(--white); border: 1.5px solid var(--border);
  border-radius: 8px; font-size: 12px; font-weight: 600; cursor: pointer;
  color: var(--navy); font-family: inherit; transition: all .2s;
}
.btn-export:hover { background: var(--parchment-dark); border-color: var(--navy); }

/* ─── RESPONSIVE ─── */
@media (max-width: 640px) {
  .header { padding: 20px; }
  .header h1 { font-size: 22px; }
  .filters, .chips, .entries, .export-bar { padding-left: 16px; padding-right: 16px; }
  .form-row { grid-template-columns: 1fr; }
  .modal-body { padding: 20px 16px; }
  .card-header { padding: 14px 16px; }
  .card-domains { padding: 0 16px 12px; }
  .card-body { padding: 4px 16px 16px; }
}
</style>
</head>
<body>

<div id="app"></div>

<script>
// ─── DATA ───
const DOMAINS = [
  { id:"travail", label:"Droit du travail", color:"#2563eb", bg:"#dbeafe", icon:"⚙️" },
  { id:"fiscal", label:"Droit fiscal", color:"#d97706", bg:"#fef3c7", icon:"💰" },
  { id:"commercial", label:"Droit commercial", color:"#059669", bg:"#d1fae5", icon:"🤝" },
  { id:"societes", label:"Droit des sociétés", color:"#7c3aed", bg:"#ede9fe", icon:"🏢" },
  { id:"social", label:"Droit social", color:"#dc2626", bg:"#fee2e2", icon:"👥" },
  { id:"civil", label:"Droit civil", color:"#0891b2", bg:"#cffafe", icon:"📜" },
  { id:"penal", label:"Droit pénal", color:"#be123c", bg:"#ffe4e6", icon:"⚖️" },
  { id:"administratif", label:"Droit administratif", color:"#4f46e5", bg:"#e0e7ff", icon:"🏛️" },
  { id:"europeen", label:"Droit européen", color:"#0369a1", bg:"#e0f2fe", icon:"🇪🇺" },
  { id:"autre", label:"Autre", color:"#6b7280", bg:"#f3f4f6", icon:"📂" },
];

const STORAGE_KEY = "glossaire-juridique-data";

function loadEntries() {
  try { return JSON.parse(localStorage.getItem(STORAGE_KEY)) || []; } catch { return []; }
}
function saveEntries(entries) {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(entries));
}
function genId() { return Date.now().toString(36) + Math.random().toString(36).slice(2,8); }
function esc(s) { const d=document.createElement('div'); d.textContent=s; return d.innerHTML; }
function formatDate(iso) {
  return new Date(iso).toLocaleDateString('fr-FR', { day:'numeric', month:'long', year:'numeric' });
}
function getDomain(id) { return DOMAINS.find(d=>d.id===id); }

// ─── STATE ───
let entries = loadEntries();
let search = "";
let filterDomain = "all";
let filterEntreprise = false;
let sortBy = "date";
let expandedId = null;
let confirmDeleteId = null;
let editingEntry = null;
let showModal = false;

// ─── NOTIFICATION ───
function showNotif(msg, type="success") {
  const el = document.createElement("div");
  el.className = "notif " + type;
  el.textContent = msg;
  document.body.appendChild(el);
  setTimeout(() => el.remove(), 2500);
}

// ─── RENDER ───
function render() {
  const app = document.getElementById("app");

  const filtered = entries
    .filter(e => {
      const q = search.toLowerCase();
      const mSearch = !q || e.titre.toLowerCase().includes(q) ||
        (e.reference||"").toLowerCase().includes(q) ||
        (e.texte||"").toLowerCase().includes(q) ||
        (e.explication||"").toLowerCase().includes(q) ||
        (e.tags||"").toLowerCase().includes(q);
      const mDomain = filterDomain === "all" || (e.domaines||[]).includes(filterDomain);
      const mEntr = !filterEntreprise || e.entreprise;
      return mSearch && mDomain && mEntr;
    })
    .sort((a,b) => {
      if (sortBy === "date") return new Date(b.updatedAt) - new Date(a.updatedAt);
      if (sortBy === "alpha") return (a.titre||"").localeCompare(b.titre||"", "fr");
      return 0;
    });

  const stats = DOMAINS.map(d => ({ ...d, count: entries.filter(e=>(e.domaines||[]).includes(d.id)).length }));

  let html = `
    <header class="header">
      <div>
        <h1><span style="font-size:30px">⚖️</span> Glossaire Juridique</h1>
        <div class="subtitle">${entries.length} article${entries.length!==1?'s':''} référencé${entries.length!==1?'s':''}</div>
      </div>
      <button class="btn-add" onclick="openForm()"><span style="font-size:18px">＋</span> Nouvel article</button>
    </header>
  `;

  // Chips
  const activeChips = stats.filter(d=>d.count>0);
  if (activeChips.length > 0) {
    html += `<div class="chips">`;
    activeChips.forEach(d => {
      const isActive = filterDomain === d.id;
      html += `<button class="chip${isActive?' active':''}" 
        style="border-color:${d.color}; ${isActive ? 'background:'+d.color+';color:#fff' : 'color:'+d.color}"
        onclick="toggleDomainFilter('${d.id}')">${d.icon} ${d.label} <span class="count">${d.count}</span></button>`;
    });
    if (filterDomain !== "all") {
      html += `<button class="chip" style="border-color:#ccc;color:#888" onclick="toggleDomainFilter('all')">✕ Réinitialiser</button>`;
    }
    html += `</div>`;
  }

  // Filters
  html += `
    <div class="filters">
      <div class="search-wrap">
        <span class="icon">🔍</span>
        <input class="search-input" placeholder="Rechercher par titre, référence, texte, tag…"
          value="${esc(search)}" oninput="search=this.value;render()">
        ${search ? '<button class="search-clear" onclick="search=\'\';render()">✕</button>' : ''}
      </div>
      <div class="filter-row">
        <select onchange="filterDomain=this.value;render()">
          <option value="all"${filterDomain==='all'?' selected':''}>Tous les domaines</option>
          ${DOMAINS.map(d=>`<option value="${d.id}"${filterDomain===d.id?' selected':''}>${d.icon} ${d.label}</option>`).join('')}
        </select>
        <select onchange="sortBy=this.value;render()">
          <option value="date"${sortBy==='date'?' selected':''}>Plus récent</option>
          <option value="alpha"${sortBy==='alpha'?' selected':''}>Alphabétique</option>
        </select>
        <button class="filter-toggle${filterEntreprise?' active':''}" onclick="filterEntreprise=!filterEntreprise;render()">🏢 Entreprise</button>
      </div>
    </div>
  `;

  // Export
  if (entries.length > 0) {
    html += `<div class="export-bar">
      <button class="btn-export" onclick="exportJSON()">📥 Exporter JSON</button>
      <button class="btn-export" onclick="document.getElementById('importFile').click()">📤 Importer JSON</button>
      <input type="file" id="importFile" accept=".json" style="display:none" onchange="importJSON(this)">
    </div>`;
  }

  // Entries
  if (filtered.length === 0) {
    html += `<div class="empty">
      <div class="icon">${entries.length===0?'📚':'🔎'}</div>
      <h3>${entries.length===0?'Votre glossaire est vide':'Aucun résultat'}</h3>
      <p>${entries.length===0?'Ajoutez votre premier texte de loi en cliquant sur « Nouvel article ».':'Essayez de modifier vos filtres ou votre recherche.'}</p>
    </div>`;
  } else {
    html += `<div class="entries">`;
    filtered.forEach((entry, idx) => {
      const isExp = expandedId === entry.id;
      html += `<article class="card${isExp?' expanded':''}" style="animation-delay:${idx*0.04}s">`;

      // Header
      html += `<div class="card-header" onclick="toggleExpand('${entry.id}')">
        <div>
          <div class="card-title">${esc(entry.titre||'Sans titre')}</div>
          ${entry.reference ? `<div class="card-ref">${esc(entry.reference)}</div>` : ''}
        </div>
        <div class="card-right">
          ${entry.entreprise ? '<span class="badge-entreprise">🏢 Entreprise</span>' : ''}
          <span class="arrow">▼</span>
        </div>
      </div>`;

      // Domain tags
      html += `<div class="card-domains">`;
      (entry.domaines||[]).forEach(dId => {
        const d = getDomain(dId);
        if (d) html += `<span class="domain-tag" style="background:${d.bg};color:${d.color}">${d.icon} ${d.label}</span>`;
      });
      if (entry.tags) {
        entry.tags.split(',').filter(t=>t.trim()).forEach(t => {
          html += `<span class="custom-tag">${esc(t.trim())}</span>`;
        });
      }
      html += `</div>`;

      // Body
      if (isExp) {
        html += `<div class="card-body">`;
        if (entry.texte) {
          html += `<div class="section"><div class="section-title">📜 Texte de loi</div><div class="legal-text">${esc(entry.texte)}</div></div>`;
        }
        if (entry.explication) {
          html += `<div class="section"><div class="section-title">💡 Explication</div><div class="explanation-text">${esc(entry.explication)}</div></div>`;
        }
        if (entry.entreprise && entry.noteEntreprise) {
          html += `<div class="section"><div class="section-title">🏢 Application en entreprise</div><div class="entreprise-text">${esc(entry.noteEntreprise)}</div></div>`;
        }
        const liens = (entry.liens||[]).filter(l=>l.url);
        if (liens.length > 0) {
          html += `<div class="section"><div class="section-title">🔗 Liens & Références</div><div class="links-wrap">`;
          liens.forEach(l => {
            html += `<a href="${esc(l.url)}" target="_blank" rel="noopener" class="link-item">${esc(l.label||l.url)} <span style="font-size:12px;opacity:.6">↗</span></a>`;
          });
          html += `</div></div>`;
        }

        // Footer
        html += `<div class="card-footer">
          <span class="date-text">Modifié le ${formatDate(entry.updatedAt)}</span>
          <div class="card-actions">
            <button class="btn-edit" onclick="event.stopPropagation();openEdit('${entry.id}')">✏️ Modifier</button>`;
        if (confirmDeleteId === entry.id) {
          html += `<span class="confirm-wrap">
            <span class="confirm-text">Supprimer ?</span>
            <button class="btn-confirm-yes" onclick="event.stopPropagation();deleteEntry('${entry.id}')">Oui</button>
            <button class="btn-confirm-no" onclick="event.stopPropagation();confirmDeleteId=null;render()">Non</button>
          </span>`;
        } else {
          html += `<button class="btn-delete" onclick="event.stopPropagation();confirmDeleteId='${entry.id}';render()">🗑️</button>`;
        }
        html += `</div></div></div>`;
      }

      html += `</article>`;
    });
    html += `</div>`;
  }

  // Modal
  if (showModal) {
    const e = editingEntry;
    html += `<div class="modal-overlay" onclick="if(event.target===this){closeForm()}">
      <div class="modal">
        <div class="modal-header">
          <h2>${e.id?'✏️ Modifier':'📝 Nouvel article'}</h2>
          <button class="btn-back" onclick="closeForm()">✕ Fermer</button>
        </div>
        <div class="modal-body">
          <div class="form-row">
            <div class="form-field">
              <label>Titre de l'article *</label>
              <input id="f-titre" value="${esc(e.titre)}" placeholder="Ex : Article L1234-1 du Code du travail">
            </div>
            <div class="form-field">
              <label>Référence légale</label>
              <input id="f-ref" value="${esc(e.reference||'')}" placeholder="Ex : Art. L1234-1 C. trav.">
            </div>
          </div>
          <div class="form-field">
            <label>📜 Texte de loi</label>
            <textarea id="f-texte" style="min-height:140px" placeholder="Collez ici le texte de loi original…">${esc(e.texte||'')}</textarea>
          </div>
          <div class="form-field">
            <label>💡 Explication / Résumé</label>
            <textarea id="f-explication" placeholder="Expliquez ce que signifie ce texte en termes simples…">${esc(e.explication||'')}</textarea>
          </div>
          <div class="form-field">
            <label>📁 Domaines juridiques</label>
            <div class="domains-grid">
              ${DOMAINS.map(d => {
                const active = (e.domaines||[]).includes(d.id);
                return `<button class="domain-btn${active?' active':''}" 
                  style="border-color:${d.color};${active?'background:'+d.color+';color:#fff':'color:'+d.color}"
                  onclick="toggleFormDomain('${d.id}')">${d.icon} ${d.label}</button>`;
              }).join('')}
            </div>
          </div>
          <div class="form-field">
            <div class="check-row">
              <button class="checkbox-btn${e.entreprise?' active':''}" onclick="editingEntry.entreprise=!editingEntry.entreprise;render()">${e.entreprise?'✓':''}</button>
              <label style="font-size:15px;font-weight:600;cursor:pointer" onclick="editingEntry.entreprise=!editingEntry.entreprise;render()">🏢 Relatif à l'entreprise</label>
            </div>
            ${e.entreprise ? `<textarea id="f-noteEntreprise" placeholder="En quoi ce texte s'applique-t-il à l'entreprise ?">${esc(e.noteEntreprise||'')}</textarea>` : ''}
          </div>
          <div class="form-field">
            <label>🔗 Liens & Références</label>
            ${(e.liens||[{url:'',label:''}]).map((l,i) => `
              <div class="lien-row">
                <input id="f-lien-url-${i}" value="${esc(l.url)}" placeholder="URL (https://…)">
                <input id="f-lien-label-${i}" value="${esc(l.label)}" placeholder="Libellé">
                ${(e.liens||[]).length > 1 ? `<button class="btn-remove-lien" onclick="removeFormLien(${i})">✕</button>` : ''}
              </div>
            `).join('')}
            <button class="btn-add-lien" onclick="addFormLien()">＋ Ajouter un lien</button>
          </div>
          <div class="form-field">
            <label>🏷️ Tags personnalisés <span class="hint">(séparés par des virgules)</span></label>
            <input id="f-tags" value="${esc(e.tags||'')}" placeholder="Ex : licenciement, indemnité, préavis">
          </div>
          <div class="form-actions">
            <button class="btn-cancel" onclick="closeForm()">Annuler</button>
            <button class="btn-save" onclick="saveForm()">${e.id?'💾 Enregistrer':'✅ Ajouter au glossaire'}</button>
          </div>
        </div>
      </div>
    </div>`;
  }

  app.innerHTML = html;
}

// ─── ACTIONS ───
function toggleDomainFilter(id) { filterDomain = filterDomain===id ? 'all' : id; render(); }
function toggleExpand(id) { expandedId = expandedId===id ? null : id; confirmDeleteId=null; render(); }
function openForm(entry) {
  editingEntry = entry || { id:'', titre:'', reference:'', texte:'', explication:'', domaines:[], entreprise:false, noteEntreprise:'', liens:[{url:'',label:''}], tags:'' };
  showModal = true; render();
}
function closeForm() { showModal = false; editingEntry = null; render(); }
function openEdit(id) {
  const e = entries.find(x=>x.id===id);
  if (e) openForm({...e, liens: (e.liens&&e.liens.length>0) ? [...e.liens] : [{url:'',label:''}]});
}
function toggleFormDomain(dId) {
  if (!editingEntry.domaines) editingEntry.domaines = [];
  const idx = editingEntry.domaines.indexOf(dId);
  if (idx >= 0) editingEntry.domaines.splice(idx,1);
  else editingEntry.domaines.push(dId);
  render();
}
function addFormLien() {
  syncFormFields();
  editingEntry.liens.push({url:'',label:''});
  render();
}
function removeFormLien(i) {
  syncFormFields();
  editingEntry.liens.splice(i,1);
  render();
}
function syncFormFields() {
  if (!editingEntry || !showModal) return;
  const v = id => { const el=document.getElementById(id); return el ? el.value : ''; };
  editingEntry.titre = v('f-titre');
  editingEntry.reference = v('f-ref');
  editingEntry.texte = v('f-texte');
  editingEntry.explication = v('f-explication');
  editingEntry.noteEntreprise = v('f-noteEntreprise');
  editingEntry.tags = v('f-tags');
  (editingEntry.liens||[]).forEach((l,i) => {
    l.url = v('f-lien-url-'+i);
    l.label = v('f-lien-label-'+i);
  });
}
function saveForm() {
  syncFormFields();
  if (!editingEntry.titre.trim()) return;
  const now = new Date().toISOString();
  if (editingEntry.id) {
    entries = entries.map(e => e.id===editingEntry.id ? {...editingEntry, updatedAt:now} : e);
    showNotif("Article mis à jour");
  } else {
    entries.unshift({...editingEntry, id:genId(), createdAt:now, updatedAt:now});
    showNotif("Article ajouté au glossaire");
  }
  saveEntries(entries);
  closeForm();
}
function deleteEntry(id) {
  entries = entries.filter(e=>e.id!==id);
  saveEntries(entries);
  confirmDeleteId = null; expandedId = null;
  showNotif("Article supprimé", "delete");
  render();
}

// ─── IMPORT / EXPORT ───
function exportJSON() {
  const blob = new Blob([JSON.stringify(entries, null, 2)], {type:'application/json'});
  const a = document.createElement('a');
  a.href = URL.createObjectURL(blob);
  a.download = 'glossaire-juridique-' + new Date().toISOString().slice(0,10) + '.json';
  a.click();
  showNotif("Glossaire exporté !");
}
function importJSON(input) {
  const file = input.files[0];
  if (!file) return;
  const reader = new FileReader();
  reader.onload = function(e) {
    try {
      const data = JSON.parse(e.target.result);
      if (Array.isArray(data)) {
        entries = [...data, ...entries];
        saveEntries(entries);
        showNotif(data.length + " article(s) importé(s)");
        render();
      }
    } catch { showNotif("Fichier invalide", "delete"); }
  };
  reader.readAsText(file);
  input.value = '';
}

// ─── INIT ───
render();
</script>
</body>
</html>
