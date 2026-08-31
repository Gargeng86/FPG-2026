<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Consultancy Concept — Working Dashboard</title>
<style>
:root{--bg:#EDE8DD;--surface:#FBF9F4;--ink:#1B2A4A;--ink-soft:#5B6472;--gold:#B5822E;--clay:#8C4A2F;--line:#D8D0BF;--green:#3F6B4A}
*{box-sizing:border-box}html,body{margin:0;padding:0;background:var(--bg);color:var(--ink);font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif}body{min-height:100vh}.shell{display:flex;min-height:100vh}nav.rail{width:210px;flex:0 0 210px;background:var(--ink);color:#EDE8DD;padding:28px 18px;position:sticky;top:0;height:100vh;overflow-y:auto}.rail-status{margin-top:32px;padding-top:16px;border-top:1px solid rgba(255,255,255,.15);font-size:12px;color:#93A0B8;line-height:1.5}.rail-status .dot{display:inline-block;width:6px;height:6px;border-radius:50%;background:var(--green);margin-right:6px}main{flex:1;padding:40px 48px 90px;max-width:900px}header.top{margin-bottom:38px}.kicker{font-size:13px;color:var(--clay);margin-bottom:8px}h1{font-family:Georgia,"Times New Roman",serif;font-size:32px;line-height:1.2;margin:0 0 10px;font-weight:600}.subtitle{font-size:16px;color:var(--ink-soft);max-width:640px;line-height:1.5}[contenteditable="true"]{outline:none;border-bottom:1px dashed transparent;transition:border-color .15s}

\[contenteditable="true"]:hover{border-bottom-color:var(--line)}

\[contenteditable="true"]:focus{border-bottom-color:var(--gold);background:rgba(181,130,46,.06)}section{margin-bottom:52px;scroll-margin-top:24px}section h2{font-family:Georgia,"Times New Roman",serif;font-size:22px;font-weight:600;margin:0 0 4px;border-bottom:1px solid var(--line);padding-bottom:10px}section .lede{font-size:14px;color:var(--ink-soft);margin:8px 0 20px;max-width:620px;line-height:1.5}.founders{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}.founder-card{background:var(--surface);border:1px solid var(--line);border-radius:6px;padding:16px 18px}.founder-card .role{font-size:12px;color:var(--clay);margin-bottom:6px}.founder-card .name{font-size:15px;font-weight:600;margin-bottom:4px}.founder-card .desc{font-size:13px;color:var(--ink-soft);line-height:1.45}.stepper{display:flex;align-items:flex-start;margin-bottom:8px}.step{flex:1;position:relative;padding-right:16px}.step:not(:last-child)::after{content:"";position:absolute;top:15px;right:0;width:100%;height:1px;background:var(--line)}.step .marker{width:30px;height:30px;border-radius:50%;background:var(--ink);color:#fff;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:600;position:relative;z-index:1;margin-bottom:10px}.step .label{font-size:13px;color:var(--ink-soft);text-transform:none}.step .when{font-size:12px;color:var(--gold);margin-top:2px}.phase-card{background:var(--surface);border:1px solid var(--line);border-left:3px solid var(--gold);border-radius:4px;padding:18px 20px;margin-bottom:14px}.phase-card h3{font-size:16px;margin:0 0 10px;font-family:Georgia,serif}.phase-card ul{margin:0;padding-left:18px}.phase-card li{font-size:14px;line-height:1.6;color:var(--ink-soft);margin-bottom:4px}.phase-card li::marker{color:var(--gold)}.pillars{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}.pillar{background:var(--surface);border:1px solid var(--line);border-radius:6px;padding:18px 20px}.pillar .num{font-size:12px;color:var(--clay);margin-bottom:8px}.pillar h3{font-size:16px;margin:0 0 8px;font-family:Georgia,serif}.pillar p{font-size:13.5px;color:var(--ink-soft);line-height:1.55;margin:0}table{width:100%;border-collapse:collapse;background:var(--surface);border:1px solid var(--line);border-radius:6px;overflow:hidden;font-size:13.5px}th,td{padding:11px 14px;text-align:left;vertical-align:top;border-bottom:1px solid var(--line);line-height:1.5}th{background:var(--ink);color:#EDE8DD;font-weight:600;font-size:13px}tr:last-child td{border-bottom:none}td:first-child{font-weight:600;color:var(--ink);width:110px}.positioning{list-style:none;margin:0;padding:0;display:grid;gap:10px}.positioning li{background:var(--surface);border:1px solid var(--line);border-left:3px solid var(--ink);padding:12px 16px;border-radius:4px;font-size:14px;color:var(--ink-soft);line-height:1.5}.risk{display:flex;gap:12px;align-items:flex-start;background:var(--surface);border:1px solid var(--line);border-radius:6px;padding:14px 16px;margin-bottom:10px}.risk select{border:1px solid var(--line);background:#fff;border-radius:4px;font-size:12px;padding:4px 6px;color:var(--ink);flex:0 0 auto}.risk .body{flex:1;font-size:13.5px;color:var(--ink-soft);line-height:1.55}.risk .body b{color:var(--ink)}.checklist{display:grid;gap:8px}.task{display:flex;align-items:flex-start;gap:10px;background:var(--surface);border:1px solid var(--line);border-radius:5px;padding:11px 14px}.task input[type=checkbox]{margin-top:3px;width:15px;height:15px;accent-color:var(--gold);flex:0 0 auto}.task .txt{font-size:14px;line-height:1.5;flex:1}.task.done .txt{color:#9aa1ab;text-decoration:line-through}.toolbar{position:fixed;bottom:0;left:210px;right:0;background:var(--ink);color:#EDE8DD;padding:12px 32px;display:flex;align-items:center;justify-content:space-between;font-size:13px;z-index:5}.toolbar .save-state{color:#93A0B8}.toolbar button{background:var(--gold);color:#1B2A4A;border:none;border-radius:4px;padding:8px 16px;font-size:13px;font-weight:600;cursor:pointer}.toolbar button:hover{background:#c99a48}.toolbar .btns{display:flex;gap:10px}.toolbar button.secondary{background:transparent;color:#EDE8DD;border:1px solid rgba(255,255,255,.3)}@media (max-width:820px){.shell{flex-direction:column}nav.rail{width:100%;flex:none;height:auto;position:relative;padding:18px}nav.rail ul{display:flex;flex-wrap:wrap;gap:4px;margin-top:14px}main{padding:24px 20px 100px}.founders,.pillars{grid-template-columns:1fr}.stepper{flex-direction:column;gap:14px}.step::after{display:none}.toolbar{left:0;flex-direction:column;gap:8px;align-items:flex-start}}
</style>
</head>
<body>
<div class="shell">
  <nav class="rail">
    <div class="brand">Working concept<strong>Multi-Sector Expert Consultancy</strong></div>
    <ul>
      <li><a href="#founders" class="navlink">Founders</a></li>
      <li><a href="#phases" class="navlink">Growth phases</a></li>
      <li><a href="#pillars" class="navlink">Operating model</a></li>
      <li><a href="#comparison" class="navlink">Benchmark</a></li>
      <li><a href="#positioning" class="navlink">Positioning</a></li>
      <li><a href="#risks" class="navlink">Stress-test</a></li>
      <li><a href="#nextsteps" class="navlink">Next 90 days</a></li>
    </ul>
    <div class="rail-status"><span class="dot"></span><span id="statusText">Loading…</span></div>
  </nav>

  <main>
    <header class="top">
      <div class="kicker">Founding partner working draft</div>
      <h1 contenteditable="true" id="title">A Phased Model for a Multi-Sector Expert Consultancy</h1>
      <div class="subtitle" contenteditable="true" id="subtitle">Drawing on DAI and Tetra Tech's roster-and-capture mechanism, scaled to what three founders can realistically run — and grown in stages from there. Click any text to edit; changes are shared with everyone who opens this link.</div>
    </header>

    <section id="founders">
      <h2>Founders &amp; roles</h2>
      <div class="lede">Fill in names and which pillar each of you is anchoring — this is the first decision the note calls out as unresolved.</div>
      <div class="founders" id="founderGrid"></div>
    </section>

    <section id="phases">
      <h2>Growth phases — crawl, walk, run</h2>
      <div class="lede">The roster and the pipeline are meant to grow together, not sequentially.</div>
      <div class="stepper">
        <div class="step"><div class="marker">1</div><div class="label">Foundation</div><div class="when">Months 0–9</div></div>
        <div class="step"><div class="marker">2</div><div class="label">Expansion</div><div class="when">Months 9–24</div></div>
        <div class="step"><div class="marker">3</div><div class="label">Scale</div><div class="when">Year 2+</div></div>
      </div>
      <div id="phaseCards"></div>
    </section>

    <section id="pillars">
      <h2>Operating model — three pillars</h2>
      <div class="lede">Everything else is built on top of these.</div>
      <div class="pillars" id="pillarGrid"></div>
    </section>

    <section id="comparison">
      <h2>Benchmark — how the behemoths run it</h2>
      <div class="lede">Same mechanism, different scale. Reference only — not meant to be edited away.</div>
      <table>
        <thead><tr><th></th><th>DAI</th><th>Tetra Tech</th><th>Us (target)</th></tr></thead>
        <tbody>
          <tr><td>Talent base</td><td>250,000+ vetted profiles, standing sector rosters</td><td>Global talent network, continuous "Call for Experts"</td><td>40–60 vetted profiles across 8 sectors by month 9</td></tr>
          <tr><td>Business development</td><td>Dedicated BD unit: bid managers, recon missions, EOI coordination</td><td>Regional hubs sited near donor offices</td><td>One founder on standing-watch of opportunity boards</td></tr>
          <tr><td>Positioning</td><td>"Trusted broker" across govt, donors, civil society, private sector</td><td>Decades-long FCDO/EIB/KfW delivery relationships</td><td>African-owned, sector-broad, rapporteuring track record</td></tr>
          <tr><td>Incentive structure</td><td>Employee-owned, 80%+ staff equity</td><td>Public company</td><td>To be defined — revisit at Phase 3</td></tr>
        </tbody>
      </table>
    </section>

    <section id="positioning">
      <h2>Positioning — why clients choose us</h2>
      <ul class="positioning" id="positioningList"></ul>
    </section>

    <section id="risks">
      <h2>Stress-test — where this is weakest</h2>
      <div class="lede">Named plainly, with a status each of you can update as it's addressed.</div>
      <div id="riskList"></div>
    </section>

    <section id="nextsteps">
      <h2>Next 90 days</h2>
      <div class="checklist" id="taskList"></div>
    </section>
  </main>
</div>

<div class="toolbar">
  <div class="save-state" id="saveState">Synced</div>
  <div class="btns">
    <button class="secondary" id="resetBtn">Reset to original</button>
    <button id="copyBtn">Copy as text</button>
  </div>
</div>

<script>
/*
  CLIENT SCRIPT
  - Default: localStorage persistence
  - Optional shared persistence: set SERVER_BASE to your server URL (no trailing slash)
*/
const STORAGE_KEY = 'concept-dashboard-v1';
const SERVER_BASE = ''; // leave empty for GitHub Pages local-only persistence
const API_LOAD = SERVER_BASE ? (SERVER_BASE + '/load') : '/api/load';
const API_SAVE = SERVER_BASE ? (SERVER_BASE + '/save') : '/api/save';

const DEFAULT_STATE = {
  title: 'A Phased Model for a Multi-Sector Expert Consultancy',
  subtitle: "Drawing on DAI and Tetra Tech's roster-and-capture mechanism, scaled to what three founders can realistically run — and grown in stages from there. Click any text to edit; changes are shared with everyone who opens this link.",
  founders: [
    {role:'Roster &amp; quality lead', name:'Founder 1', desc:'Owns intake, vetting, and the performance record for each consultant on the bench.'},
    {role:'Capture &amp; BD lead', name:'Founder 2', desc:'Owns the standing watch on donor portals and the opportunity pipeline tracker.'},
    {role:'Delivery &amp; ops lead', name:'Founder 3', desc:'Owns onboarding briefs, client relationships, and post-assignment feedback loops.'}
  ],
  phases: [
    {title:'Phase 1 — Foundation (Months 0–9)', items:[
      'Register the entity and agree the founder time commitment against each pillar',
      'Build the first 40–60 vetted profiles from existing networks, sector by sector',
      'Revenue: subcontract margin under an established prime, plus direct rapporteuring/facilitation fees',
      'Run on a shared spreadsheet/CRM — no custom platform yet'
    ]},
    {title:'Phase 2 — Expansion (Months 9–24)', items:[
      'Add a placement/staffing commission model for clients who come directly to the roster',
      'Begin responding to RFIs/APS/EOIs directly, not only as a subcontractor',
      'Move to a lightweight searchable digital roster once volume outgrows the spreadsheet',
      'Grow sector coverage through referral incentives to existing roster members'
    ]},
    {title:'Phase 3 — Scale (Year 2+)', items:[
      'Pursue framework-style, multi-year agreements with two or three repeat clients or primes',
      'Consider a prime-management fee model, leading consortiums rather than only subcontracting',
      'Formalize an equity or profit-share structure now that the roster is a real asset',
      'Explore adjacent revenue lines — training products, thought leadership, data/analytics services'
    ]}
  ],
  pillars: [
    {title:'1. The Roster', desc:'Segmented from day one: Environmental, Programs/PM, Legal, Tax, Investment, Events, Technical Facilitation, Rapporteuring. Each sector carries its own minimum vetting bar — CV, 2–3 references, certifications, documented past performance.'},
    {title:'2. Capture &amp; BD', desc:'One founder owns continuous monitoring of UNGM, Devex, dgMarket, AfDB/AUDA-NEPAD procurement, FCDO\\'s supplier portal, Global Affairs Canada, DFAT, and regional RFI/APS channels, with a simple go/no-go tracker.'},
    {title:'3. Delivery &amp; QA', desc:'A standard onboarding brief for every matched consultant, a short post-assignment client feedback loop, and a running performance record per roster member — the cheapest insurance against a bad early match.'}
  ],
  positioning: [
    'African-owned, African-led — aligned with the donor sector\\'s own localization push, which DAI and Tetra Tech must partner their way into and we start with natively',
    'Sector breadth without sector shallowness — the founding trio already spans multiple technical competencies, closer to DAI\\'s "whole-of-society" model than a niche boutique',
    'Demonstrated delivery credibility, not just claimed expertise — three consecutive editions of Devolution Conference rapporteuring plus the Peoples Dialogue Festival partnership'
  ],
  risks: [
    {status:'open', text:'<b>Bandwidth:</b> each founder already carries independent consulting work and other commitments (in one case, a separate US-focused directorship in a different sector). The capture function needs a specific weekly time commitment from each of us, not "when convenient."'},
    {status:'open', text:'<b>Cold roster risk:</b> building 40–60 profiles before there\\'s a live pipeline behind them risks a stalled database. Roster-building and opportunity-tracking need to run in parallel from week one.'},
    {status:'open', text:'<b>Framing for Phase 1:</b> this is about getting into DAI\\'s and Tetra Tech\\'s supply chains as a subcontractor first, not competing with them for prime awards — that framing needs to be shared clearly with early partners.'},
    {status:'open', text:'<b>Data protection:</b> Kenya\\'s Data Protection Act, 2019 applies the moment CVs and contact details are collected — a basic consent and data-handling policy needs to exist before roster-building begins in earnest.'}
  ],
  tasks: [
    {done:false, text:'Agree founder roles against the three pillars and a realistic weekly time commitment from each'},
    {done:false, text:'Draft the sector-segmented intake template and begin populating the roster from existing networks'},
    {done:false, text:'Stand up a shared opportunity tracker and assign standing-watch responsibility for the donor portals'},
    {done:false, text:'Identify 2–3 target primes for subcontracting entry and map their current open EOI/roster calls'},
    {done:false, text:'Draft a one-page capability statement anchored on the rapporteuring track record'}
  ]
};

let state = null;
let saveTimer = null;

function setStatus(text){ document.getElementById('statusText').textContent = text; }
function setSaveState(text){ document.getElementById('saveState').textContent = text; }

/* Load: try server first if configured, fallback to localStorage */
async function loadState(){
  setStatus('Loading…');
  if (SERVER_BASE) {
    try {
      const res = await fetch(API_LOAD);
      if (res.ok) {
        const json = await res.json();
        if (json && json.state) {
          state = json.state;
          setStatus('Shared — live (server)');
          render();
          return;
        }
      }
    } catch (e) {
      // fall through to local
    }
  }
  try {
    const raw = localStorage.getItem(STORAGE_KEY);
    state = raw ? JSON.parse(raw) : structuredClone(DEFAULT_STATE);
    setStatus(SERVER_BASE ? 'Local fallback — server unreachable' : 'Local — edits saved to this browser');
  } catch (e) {
    state = structuredClone(DEFAULT_STATE);
    setStatus('Local — edits saved to this browser');
  }
  render();
}

/* Persist: try server save if configured, else localStorage */
async function persist(){
  setSaveState('Saving…');
  if (SERVER_BASE) {
    try {
      const res = await fetch(API_SAVE, {
        method: 'POST',
        headers: {'Content-Type':'application/json'},
        body: JSON.stringify({ state })
      });
      if (res.ok) { setSaveState('Synced (server)'); return; }
    } catch (e) {
      // fall back
    }
  }
  try {
    localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
    setSaveState('Synced (local)');
  } catch (e) {
    setSaveState('Could not save');
  }
}

function queueSave(){
  clearTimeout(saveTimer);
  setSaveState('Editing…');
  saveTimer = setTimeout(persist, 700);
}

/* Rendering and handlers (kept same as original) */
function render(){
  document.getElementById('title').textContent = state.title;
  document.getElementById('subtitle').textContent = state.subtitle;

  const fg = document.getElementById('founderGrid'); fg.innerHTML = '';
  state.founders.forEach((f,i)=>{
    const card = document.createElement('div'); card.className='founder-card';
    card.innerHTML = `<div class="role" contenteditable="true" data-path="founders.${i}.role">${f.role}</div>
      <div class="name" contenteditable="true" data-path="founders.${i}.name">${f.name}</div>
      <div class="desc" contenteditable="true" data-path="founders.${i}.desc">${f.desc}</div>`;
    fg.appendChild(card);
  });

  const pc = document.getElementById('phaseCards'); pc.innerHTML = '';
  state.phases.forEach((ph,i)=>{
    const div = document.createElement('div'); div.className='phase-card';
    div.innerHTML = `<h3 contenteditable="true" data-path="phases.${i}.title">${ph.title}</h3>
      <ul>${ph.items.map((it,j)=>`<li contenteditable="true" data-path="phases.${i}.items.${j}">${it}</li>`).join('')}</ul>`;
    pc.appendChild(div);
  });

  const pg = document.getElementById('pillarGrid'); pg.innerHTML = '';
  state.pillars.forEach((p,i)=>{
    const div = document.createElement('div'); div.className='pillar';
    div.innerHTML = `<div class="num">Pillar ${i+1}</div>
      <h3 contenteditable="true" data-path="pillars.${i}.title">${p.title}</h3>
      <p contenteditable="true" data-path="pillars.${i}.desc">${p.desc}</p>`;
    pg.appendChild(div);
  });

  const posList = document.getElementById('positioningList'); posList.innerHTML = '';
  state.positioning.forEach((t,i)=>{
    const li = document.createElement('li'); li.contentEditable='true';
    li.setAttribute('data-path', `positioning.${i}`); li.innerHTML = t; posList.appendChild(li);
  });

  const riskList = document.getElementById('riskList'); riskList.innerHTML = '';
  state.risks.forEach((r,i)=>{
    const div = document.createElement('div'); div.className='risk';
    div.innerHTML = `<select data-idx="${i}" class="riskStatus">
      <option value="open" ${r.status==='open'?'selected':''}>Open</option>
      <option value="in progress" ${r.status==='in progress'?'selected':''}>In progress</option>
      <option value="resolved" ${r.status==='resolved'?'selected':''}>Resolved</option>
    </select>
    <div class="body" contenteditable="true" data-path="risks.${i}.text">${r.text}</div>`;
    riskList.appendChild(div);
  });

  const taskList = document.getElementById('taskList'); taskList.innerHTML = '';
  state.tasks.forEach((t,i)=>{
    const div = document.createElement('div'); div.className = 'task' + (t.done ? ' done' : '');
    div.innerHTML = `<input type="checkbox" data-idx="${i}" ${t.done?'checked':''}>
      <div class="txt" contenteditable="true" data-path="tasks.${i}.text">${t.text}</div>`;
    taskList.appendChild(div);
  });

  attachHandlers();
}

function setByPath(obj, path, value){
  const parts = path.split('.');
  let cur = obj;
  for(let i=0;i<parts.length-1;i++){
    cur = cur[isFinite(parts[i]) ? parseInt(parts[i]) : parts[i]];
  }
  const last = parts[parts.length-1];
  cur[isFinite(last) ? parseInt(last) : last] = value;
}

function attachHandlers(){
  document.querySelectorAll('[data-path]').forEach(el=>{
    el.addEventListener('input', ()=>{
      setByPath(state, el.getAttribute('data-path'), el.innerHTML);
      queueSave();
    });
    el.addEventListener('blur', ()=>{
      setByPath(state, el.getAttribute('data-path'), el.innerHTML);
      queueSave();
    });
  });

  document.querySelectorAll('.riskStatus').forEach(sel=>{
    sel.addEventListener('change', ()=>{
      state.risks[parseInt(sel.getAttribute('data-idx'))].status = sel.value;
      queueSave();
    });
  });

  document.querySelectorAll('.task input[type=checkbox]').forEach(cb=>{
    cb.addEventListener('change', ()=>{
      const idx = parseInt(cb.getAttribute('data-idx'));
      state.tasks[idx].done = cb.checked;
      render();
      queueSave();
    });
  });
}

document.getElementById('title').addEventListener('input', e=>{
  state.title = e.target.textContent; queueSave();
});
document.getElementById('subtitle').addEventListener('input', e=>{
  state.subtitle = e.target.textContent; queueSave();
});

document.getElementById('resetBtn').addEventListener('click', async ()=>{
  if(!confirm('Reset the whole dashboard back to the original draft? This clears everyone\\'s edits.')) return;
  state = structuredClone(DEFAULT_STATE);
  render();
  await persist();
});

document.getElementById('copyBtn').addEventListener('click', ()=>{
  let out = `${document.getElementById('title').textContent}\n${document.getElementById('subtitle').textContent}\n\n`;
  out += 'FOUNDERS\n' + state.founders.map(f=>`- ${f.role.replace(/<[^>]+>/g,'')}: ${f.name.replace(/<[^>]+>/g,'')} — ${f.desc.replace(/<[^>]+>/g,'')}`).join('\n') + '\n\n';
  state.phases.forEach(ph=>{
    out += ph.title.replace(/<[^>]+>/g,'') + '\n' + ph.items.map(i=>`- ${i.replace(/<[^>]+>/g,'')}`).join('\n') + '\n\n';
  });
  out += 'PILLARS\n' + state.pillars.map(p=>`- ${p.title.replace(/<[^>]+>/g,'')}: ${p.desc.replace(/<[^>]+>/g,'')}`).join('\n') + '\n\n';
  out += 'POSITIONING\n' + state.positioning.map(p=>`- ${p.replace(/<[^>]+>/g,'')}`).join('\n') + '\n\n';
  out += 'STRESS-TEST\n' + state.risks.map(r=>`- [${r.status}] ${r.text.replace(/<[^>]+>/g,'')}`).join('\n') + '\n\n';
  out += 'NEXT 90 DAYS\n' + state.tasks.map(t=>`- [${t.done?'x':' '}] ${t.text.replace(/<[^>]+>/g,'')}`).join('\n');
  navigator.clipboard.writeText(out).then(()=>{
    const btn = document.getElementById('copyBtn'); const orig = btn.textContent;
    btn.textContent = 'Copied'; setTimeout(()=>btn.textContent = orig, 1500);
  });
});

// scroll spy
const sections = document.querySelectorAll('main section');
const navlinks = document.querySelectorAll('.navlink');
window.addEventListener('scroll', ()=>{
  let current = '';
  sections.forEach(s=>{ if(window.scrollY >= s.offsetTop - 80) current = s.id; });
  navlinks.forEach(l=>{ l.classList.toggle('active', l.getAttribute('href') === '#'+current); });
});

loadState();
</script>
</body>
</html>
