# Unit-5-archaeology-review
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Unit 5 Archaeology — Interactive Review</title>
<style>
  :root{
    --accent:#1f6f6a;
    --muted:#f6fbfb;
    --card:#ffffff;
    --text:#073b3a;
    --accent-2:#2b8f8a;
  }
  body{font-family:Inter,system-ui,Arial,sans-serif;background:linear-gradient(180deg,#f0fbfa,#ffffff);color:var(--text);margin:0;padding:18px}
  header{display:flex;align-items:center;gap:12px;margin-bottom:14px}
  h1{font-size:20px;margin:0}
  .layout{display:grid;grid-template-columns:1fr 360px;gap:16px}
  .panel{background:var(--card);border-radius:10px;padding:12px;box-shadow:0 6px 18px rgba(7,59,58,0.06)}
  .stations{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
  .station{background:var(--muted);padding:10px;border-radius:8px;min-height:170px;display:flex;flex-direction:column;gap:8px}
  .station strong{display:block}
  button{background:var(--accent);color:#fff;border:0;padding:8px 10px;border-radius:8px;cursor:pointer}
  .small{font-size:13px;padding:6px 8px;border-radius:6px}
  .row{display:flex;gap:8px;align-items:center}
  .draggable{padding:8px;background:#fff;border-radius:6px;border:1px solid #d6f0ef;cursor:grab;margin:6px 0}
  .slot{min-height:40px;padding:6px;border-radius:6px;background:#fff;border:2px dashed #cfecec;margin:6px 0}
  .card{background:#fff;padding:8px;border-radius:8px;border-left:4px solid var(--accent)}
  input[type="text"], textarea, select{width:100%;padding:8px;border-radius:6px;border:1px solid #dfeff0}
  textarea{min-height:64px}
  .hidden{display:none}
  .badge{background:var(--accent-2);color:#fff;padding:4px 8px;border-radius:999px;font-size:12px}
  footer{font-size:13px;color:#2f6b6a;margin-top:12px}
  .flex-col{display:flex;flex-direction:column;gap:8px}
  .mini{font-size:13px;color:#0b6b67}
  .result{padding:8px;border-radius:6px;background:#e6fffb;border:1px solid #bfeee8}
  .timeline-pieces{display:flex;flex-direction:column;gap:6px}
  .gallery-list{display:flex;flex-direction:column;gap:6px}
  .rank-grid{display:grid;grid-template-columns:1fr 60px;gap:6px;align-items:center}
  .quiz-area{display:flex;flex-direction:column;gap:8px}
  .center{text-align:center}
  .note{font-size:12px;color:#2f6b6a}
  .source{font-size:12px;color:#0b6b67;margin-top:10px;background:#f0fffb;padding:8px;border-radius:6px}
  @media (max-width:900px){ .layout{grid-template-columns:1fr} .stations{grid-template-columns:1fr} aside{order:-1} }
</style>
</head>
<body>

<header>
  <div>
    <h1>Unit 5 Interactive Review — Stations</h1>
    <div class="mini">6 short activities • No long reading • Work solo or in small groups</div>
  </div>
  <div style="margin-left:auto" class="center">
    <div class="badge">Shareable URL</div>
  </div>
</header>

<div class="layout">
  <main class="panel">
    <h3 style="margin-top:0">Stations (rotate every 8 minutes)</h3>
    <div class="stations">

      <!-- Station 1: Fossil Lab -->
      <div class="station" id="s1">
        <strong>Station 1 — Fossil Lab (simulate)</strong>
        <div class="mini">Adjust conditions → create a fossil preview</div>
        <label>Burial speed</label>
        <input id="s1_burial" type="range" min="1" max="5" value="3" />
        <label>Environment</label>
        <select id="s1_env">
          <option value="sediment">Sediment</option>
          <option value="amber">Amber</option>
          <option value="tar">Tar pit</option>
          <option value="freeze">Freezing</option>
        </select>
        <div class="row">
          <button id="s1_make">Create</button>
          <div id="s1_msg" class="mini"></div>
        </div>
        <div id="s1_preview" class="card hidden"></div>
        <div class="note">Deliverable: Save one screenshot or type 3 labels (mold, cast, impression).</div>
      </div>

      <!-- Station 2: Timeline Drag -->
      <div class="station" id="s2">
        <strong>Station 2 — Timeline Puzzle (drag & drop)</strong>
        <div class="mini">Drag species into slots from earliest → latest</div>
        <div class="slot" id="slotA">Slot 1 (earliest)</div>
        <div class="slot" id="slotB">Slot 2</div>
        <div class="slot" id="slotC">Slot 3</div>
        <div class="slot" id="slotD">Slot 4</div>
        <div class="slot" id="slotE">Slot 5 (latest)</div>

        <div class="timeline-pieces card" id="pieces">
          <div draggable="true" class="draggable" data-id="Ardipithecus">Ardipithecus ramidus</div>
          <div draggable="true" class="draggable" data-id="Australopithecus">Australopithecus afarensis (Lucy)</div>
          <div draggable="true" class="draggable" data-id="HomoHabilis">Homo habilis</div>
          <div draggable="true" class="draggable" data-id="HomoErectus">Homo erectus</div>
          <div draggable="true" class="draggable" data-id="HomoSapiens">Homo sapiens sapiens</div>
        </div>

        <div class="row">
          <button id="s2_check">Check</button>
          <div id="s2_feedback" class="result hidden"></div>
        </div>
      </div>

      <!-- Station 3: Detective -->
      <div class="station" id="s3">
        <strong>Station 3 — Fossil Detective</strong>
        <div class="mini">Pick 3 clues, write a 3‑sentence profile (diet, job, cause of death)</div>
        <div class="gallery-list card" id="clues">
          <label><input type="checkbox" value="bones" /> Bone with healed fracture</label>
          <label><input type="checkbox" value="tools" /> Stone tool flakes nearby</label>
          <label><input type="checkbox" value="pollen" /> Grass pollen in soil</label>
          <label><input type="checkbox" value="isotope" /> Carbon isotope: high meat</label>
          <label><input type="checkbox" value="parasite" /> Parasite eggs in coprolite</label>
        </div>
        <textarea id="s3_text" placeholder="3 short sentences: diet. job. cause of death."></textarea>
        <div class="row">
          <button id="s3_submit">Submit</button>
          <div id="s3_result" class="result hidden"></div>
        </div>
      </div>

      <!-- Station 4: Oddities Gallery -->
      <div class="station" id="s4">
        <strong>Station 4 — Oddities Gallery Walk</strong>
        <div class="mini">Read cards → post one surprising fact + one question</div>
        <div class="card">Neanderthals — lived 200k–30k years ago</div>
        <div class="card">Denisovans — DNA found in modern people</div>
        <div class="card">Flores hobbit — very small hominins</div>

        <input id="s4_fact" type="text" placeholder="One surprising fact" />
        <input id="s4_q" type="text" placeholder="One question this raises" />
        <div class="row">
          <button id="s4_post">Post</button>
          <button id="s4_clear" style="background:#9bbfbf">Clear</button>
        </div>
        <div id="s4_board" class="card" style="min-height:48px"></div>
      </div>

      <!-- Station 5: Holes Challenge -->
      <div class="station" id="s5">
        <strong>Station 5 — Holes in the Record (rank)</strong>
        <div class="mini">Rank preservation scenarios 1 (best) → 5 (worst)</div>
        <div class="rank-grid card">
          <div>Amber</div><input class="rank" type="number" min="1" max="5" value="1" />
          <div>Rapid burial in sediment</div><input class="rank" type="number" min="1" max="5" value="2" />
          <div>Freezing</div><input class="rank" type="number" min="1" max="5" value="3" />
          <div>Tar pit</div><input class="rank" type="number" min="1" max="5" value="4" />
          <div>Slow surface burial</div><input class="rank" type="number" min="1" max="5" value="5" />
        </div>
        <div class="row">
          <button id="s5_submit">Submit Ranking</button>
          <div id="s5_result" class="result hidden"></div>
        </div>
      </div>

      <!-- Station 6: Rapid Quiz Relay -->
      <div class="station" id="s6">
        <strong>Station 6 — Rapid Fire Quiz</strong>
        <div class="mini">Click Next → choose answer. Fast pace.</div>
        <div id="q_card" class="card center">Press Next</div>
        <div class="row" id="q_choices" style="display:none">
          <button class="small" data-choice="A">A</button>
          <button class="small" data-choice="B">B</button>
          <button class="small" data-choice="C">C</button>
          <button class="small" data-choice="D">D</button>
        </div>
        <div class="row">
          <button id="q_next">Next</button>
          <div id="q_score" class="mini">Score: 0</div>
        </div>
      </div>

    </div>
  </main>

  <aside class="panel">
    <h3 style="margin-top:0">Teacher / Wrap</h3>

    <div class="card">
      <div class="row">
        <button id="startTimer" class="small">Start 8‑min Timer</button>
        <button id="stopTimer" class="small" style="background:#9bbfbf">Stop</button>
      </div>
      <div style="margin-top:8px" class="center">
        <div id="timerDisplay" style="font-weight:700;color:var(--accent)">08:00</div>
      </div>
      <div style="margin-top:8px">
        <strong>Exit ticket</strong>
        <textarea id="exit" placeholder="One sentence: One thing fossils tell us about people is..."></textarea>
        <div class="row" style="margin-top:8px">
          <button id="exit_submit">Submit</button>
          <div id="exit_result" class="result hidden"></div>
        </div>
      </div>
    </div>

    <div class="card" style="margin-top:12px">
      <strong>Quick controls</strong>
      <div style="margin-top:8px" class="row">
        <button id="reveal_timeline" class="small">Reveal Timeline Answer</button>
        <button id="clear_posts" class="small" style="background:#9bbfbf">Clear Posts</button>
      </div>
      <div class="note" style="margin-top:8px">Encourage 30‑second verbal shares after each rotation.</div>
    </div>

    <div class="source">
      <strong>From Unit 5 (source notes)</strong>
      <div style="margin-top:6px">A fossil is the remains of anything that was once alive. The fossil record is made up of all of the fossils ever discovered as well as those still buried beneath the earth.</div>
    </div>

    <footer>Share this single HTML file with students. No long passages — activities only.</footer>
  </aside>
</div>

<script>
/* ---------- Station 1 ---------- */
document.getElementById('s1_make').addEventListener('click',()=>{
  const burial = +document.getElementById('s1_burial').value;
  const env = document.getElementById('s1_env').value;
  let result = '';
  if(env==='amber') result = 'Amber preservation — small organisms preserved whole.';
  else if(env==='tar') result = 'Tar pit — rapid trapping, good for bones.';
  else if(env==='freeze') result = 'Freezing — soft tissue possible.';
  else result = burial>=4 ? 'Rapid burial → cast/mold likely.' : 'Slow burial → low preservation chance.';
  const preview = document.getElementById('s1_preview');
  preview.classList.remove('hidden');
  preview.textContent = result;
  document.getElementById('s1_msg').textContent = 'Preview ready';
  setTimeout(()=>document.getElementById('s1_msg').textContent='',1200);
});

/* ---------- Station 2 Drag & Drop ---------- */
const draggables = document.querySelectorAll('.draggable');
const slots = ['slotA','slotB','slotC','slotD','slotE'].map(id=>document.getElementById(id));
draggables.forEach(d=>{
  d.addEventListener('dragstart', e => e.dataTransfer.setData('text/plain', d.dataset.id));
});
slots.forEach(s=>{
  s.addEventListener('dragover', e => e.preventDefault());
  s.addEventListener('drop', e => {
    e.preventDefault();
    const id = e.dataTransfer.getData('text/plain');
    const el = [...draggables].find(x=>x.dataset.id===id);
    if(!el) return;
    // clear previous parent text if placeholder
    if(s.textContent.trim().startsWith('Slot')) s.innerHTML = '';
    s.appendChild(el);
  });
});
document.getElementById('s2_check').addEventListener('click',()=>{
  const order = slots.map(s=>s.querySelector('.draggable')?.dataset.id || '');
  const correct = ['Ardipithecus','Australopithecus','HomoHabilis','HomoErectus','HomoSapiens'];
  const ok = order.every((v,i)=>v===correct[i]);
  const fb = document.getElementById('s2_feedback');
  fb.classList.remove('hidden');
  fb.textContent = ok ? 'Correct — great!' : 'Not quite — swap pieces and try again.';
});

/* ---------- Station 3 Detective ---------- */
document.getElementById('s3_submit').addEventListener('click',()=>{
  const checked = [...document.querySelectorAll('#clues input:checked')].map(i=>i.value);
  const text = document.getElementById('s3_text').value.trim();
  const res = document.getElementById('s3_result');
  if(checked.length < 1 || text.split('.').filter(s=>s.trim()).length < 1){
    res.classList.remove('hidden'); res.textContent = 'Pick at least one clue and write a short profile.';
    return;
  }
  res.classList.remove('hidden');
  res.textContent = `Saved. Evidence: ${checked.join(', ')}.`;
});

/* ---------- Station 4 Gallery ---------- */
document.getElementById('s4_post').addEventListener('click',()=>{
  const fact = document.getElementById('s4_fact').value.trim();
  const q = document.getElementById('s4_q').value.trim();
  if(!fact && !q) return;
  const board = document.getElementById('s4_board');
  const el = document.createElement('div'); el.className='card';
  el.textContent = `Fact: ${fact || '—'}  |  Q: ${q || '—'}`;
  board.prepend(el);
  document.getElementById('s4_fact').value=''; document.getElementById('s4_q').value='';
});
document.getElementById('s4_clear').addEventListener('click',()=>document.getElementById('s4_board').innerHTML='');

/* ---------- Station 5 Ranking ---------- */
document.getElementById('s5_submit').addEventListener('click',()=>{
  const rows = [...document.querySelectorAll('#s5 .rank')];
  const items = ['Amber','Rapid burial in sediment','Freezing','Tar pit','Slow surface burial'];
  const pairs = rows.map((r,i)=>({name:items[i], val:+r.value}));
  const dup = pairs.map(p=>p.val).some((v,i,a)=>a.indexOf(v)!==i);
  const res = document.getElementById('s5_result');
  if(dup){ res.classList.remove('hidden'); res.textContent='Each rank 1–5 must be unique.'; return; }
  pairs.sort((a,b)=>a.val-b.val);
  res.classList.remove('hidden');
  res.textContent = 'Top 3: ' + pairs.slice(0,3).map(p=>p.name).join('; ');
});

/* ---------- Station 6 Quiz ---------- */
const questions = [
  {q:'Body vs trace fossil: which is a footprint?', a:'B', choices:{A:'Bone',B:'Footprint',C:'Leaf',D:'Amber'}},
  {q:'Who is "Ardi"?', a:'C', choices:{A:'Lucy',B:'Peking Man',C:'Ardipithecus ramidus',D:'Denisovan'}},
  {q:'Which preserves soft tissue best?', a:'D', choices:{A:'Slow burial',B:'Erosion',C:'Sediment with worms',D:'Freezing/amber'}},
  {q:'Which species left tools ~2.5 mya?', a:'A', choices:{A:'Homo habilis',B:'Neanderthal',C:'Denisovan',D:'Flores hobbit'}},
  {q:'Peking Man is a type of?', a:'C', choices:{A:'Australopithecus',B:'Homo sapiens',C:'Homo erectus',D:'Denisovan'}}
];
let qIndex = -1, score = 0;
function showNextQ(){
  qIndex++; if(qIndex>=questions.length) qIndex=0;
  const q = questions[qIndex];
  document.getElementById('q_card').textContent = q.q + '  (choose A–D)';
  const choicesDiv = document.getElementById('q_choices');
  choicesDiv.style.display='flex';
  const btns = choicesDiv.querySelectorAll('button');
  btns.forEach(b=>{ b.disabled=false; b.textContent = b.dataset.choice + ': ' + q.choices[b.dataset.choice]; });
}
document.getElementById('q_next').addEventListener('click', showNextQ);
document.querySelectorAll('#q_choices button').forEach(b=>{
  b.addEventListener('click', ()=>{
    const chosen = b.dataset.choice;
    const correct = questions[qIndex].a;
    if(chosen===correct){ score++; document.getElementById('q_score').textContent = 'Score: ' + score; b.style.background='#2b8f8a'; }
    else { b.style.background='#c66'; }
    // disable until next
    document.querySelectorAll('#q_choices button').forEach(x=>x.disabled=true);
  });
});

/* ---------- Timer (8 minutes) ---------- */
let timerInterval = null;
function startTimer(seconds){
  clearInterval(timerInterval);
  let t = seconds;
  const disp = document.getElementById('timerDisplay');
  function tick(){
    const mm = String(Math.floor(t/60)).padStart(2,'0');
    const ss = String(t%60).padStart(2,'0');
    disp.textContent = mm + ':' + ss;
    if(t<=0){ clearInterval(timerInterval); alert('Station time up! Rotate.'); }
    t--;
  }
  tick();
  timerInterval = setInterval(tick,1000);
}
document.getElementById('startTimer').addEventListener('click', ()=>startTimer(8*60));
document.getElementById('stopTimer').addEventListener('click', ()=>clearInterval(timerInterval));

/* ---------- Exit ticket ---------- */
document.getElementById('exit_submit').addEventListener('click',()=>{
  const text = document.getElementById('exit').value.trim();
  const res = document.getElementById('exit_result');
  if(!text){ res.classList.remove('hidden'); res.textContent='Write one sentence.'; return; }
  res.classList.remove('hidden'); res.textContent = 'Exit ticket saved.';
});

/* ---------- Quick controls ---------- */
document.getElementById('reveal_timeline').addEventListener('click', ()=>{
  alert('Correct order (earliest→latest): Ardipithecus → Australopithecus → Homo habilis → Homo erectus → Homo sapiens sapiens');
});
document.getElementById('clear_posts').addEventListener('click', ()=>{
  document.getElementById('s4_board').innerHTML=''; document.getElementById('s3_result').classList.add('hidden');
});

/* ---------- Small UX polish: allow Enter to post oddity ---------- */
document.getElementById('s4_q').addEventListener('keydown', (e)=>{ if(e.key==='Enter'){ e.preventDefault(); document.getElementById('s4_post').click(); } });

/* ---------- Prevent accidental form submits ---------- */
document.addEventListener('keydown', (e)=>{ if(e.key==='Enter' && e.target.tagName==='INPUT') e.preventDefault(); });

</script>
</body>
