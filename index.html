<script>
/* === AI IMAGES via Pollinations.ai (robust, no broken-image "?" on mobile) === */
const encode = p => encodeURIComponent(p);
const pollUrl = (prompt, w=1920, h=1080, seed=42) =>
  `https://image.pollinations.ai/prompt/${encode(prompt)}?width=${w}&height=${h}&seed=${seed}&nologo=true&enhance=true`;

const introBg = pollUrl(
  'romantic night sky with golden stars, dark deep space, soft nebula clouds, ultra cinematic, moody atmospheric, dark purple and black tones, minimal, elegant, 8k',
  1920, 1080, 101
);
const poemBg = pollUrl(
  'single gold glowing rose floating in dark space, bokeh background, dark romantic night, deep black background, ultra cinematic lighting, ethereal, minimal, fine art photography',
  1920, 1080, 202
);
const secretBgUrl = pollUrl(
  'romantic golden light bokeh, dark elegant background, soft candlelight glow, cinematic, moody, luxury fine art',
  1920, 1080, 303
);
const roseCorner = pollUrl(
  'single white rose with gold tones corner decoration, dark background, ultra detailed, transparent background, fine art',
  600, 600, 404
);

/* Helper: preload image, then apply (prevents iOS "?" placeholders) */
function preload(url, { onload, onerror } = {}) {
  const img = new Image();
  img.onload = () => onload && onload(url);
  img.onerror = () => onerror && onerror(url);
  img.src = url;
  return img;
}

/* Intro BG + Loadbar */
const lb = document.getElementById('loadBar');
const aiBg = document.getElementById('aiBg');
lb.style.width = '60%';

preload(introBg, {
  onload: (url) => {
    aiBg.style.backgroundImage = `url(${url})`;
    aiBg.style.opacity = '1';
    lb.style.width = '100%';
    setTimeout(() => lb.style.opacity = '0', 500);
  },
  onerror: () => {
    // keep site usable even if image host fails
    aiBg.style.opacity = '1';
    lb.style.opacity = '0';
  }
});

/* Poem BG preload */
const poemBgImg = document.getElementById('poemBgImg');
preload(poemBg, {
  onload: (url) => (poemBgImg.style.backgroundImage = `url(${url})`),
  onerror: () => (poemBgImg.style.backgroundImage = '')
});

/* Secret BG preload */
const sBg = document.getElementById('secretBg');
preload(secretBgUrl, {
  onload: (url) => (sBg.style.backgroundImage = `url(${url})`),
  onerror: () => (sBg.style.backgroundImage = '')
});

/* Rose corners: hide first, show only when loaded (NO "?" icons) */
function loadCornerImg(id, url) {
  const el = document.getElementById(id);
  if (!el) return;

  // Hide immediately (prevents placeholder on slow/failed loads)
  el.style.display = 'none';
  el.removeAttribute('src');

  preload(url, {
    onload: (u) => {
      el.src = u;
      el.style.display = ''; // back to default
    },
    onerror: () => {
      // keep hidden forever (no ?)
      el.style.display = 'none';
    }
  });
}
['aiRoseTL','aiRoseTR','aiRoseBL','aiRoseBR'].forEach(id => loadCornerImg(id, roseCorner));

/* === CURSOR === */
const cur = document.getElementById('cur'), curR = document.getElementById('curR');
let mx = 0, my = 0, rx = 0, ry = 0;

document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cur.style.left = mx + 'px';
  cur.style.top = my + 'px';
});
(function loopCursor(){
  rx += (mx - rx) * .12;
  ry += (my - ry) * .12;
  curR.style.left = rx + 'px';
  curR.style.top = ry + 'px';
  requestAnimationFrame(loopCursor);
})();

document.querySelectorAll('button,.cstar').forEach(el => {
  el.addEventListener('mouseenter', () => {
    cur.style.width = '12px'; cur.style.height = '12px';
    curR.style.width = '40px'; curR.style.height = '40px';
  });
  el.addEventListener('mouseleave', () => {
    cur.style.width = '7px'; cur.style.height = '7px';
    curR.style.width = '26px'; curR.style.height = '26px';
  });
});

/* === STARFIELD === */
const cv = document.getElementById('bgC'), cx = cv.getContext('2d');
let W, H, bgs = [];

function rsz(){
  W = cv.width = innerWidth;
  H = cv.height = innerHeight;
  bgs = Array.from({length:220}, () => ({
    x: Math.random() * W,
    y: Math.random() * H,
    r: Math.random() * .8 + .1,
    ph: Math.random() * Math.PI * 2,
    sp: Math.random() * .006 + .002,
    mx: Math.random() * .45 + .06
  }));
}
rsz();
window.addEventListener('resize', rsz);

(function starLoop(t){
  cx.clearRect(0,0,W,H);
  bgs.forEach(s => {
    const a = s.mx * (.5 + .5 * Math.sin(t * s.sp + s.ph));
    cx.beginPath();
    cx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    cx.fillStyle = `rgba(255,255,255,${a})`;
    cx.fill();
  });
  requestAnimationFrame(starLoop);
})(0);

/* === SHOOTING STARS === */
const sc = document.getElementById('shootC'), sx = sc.getContext('2d');
sc.width = innerWidth; sc.height = innerHeight;
window.addEventListener('resize', () => { sc.width = innerWidth; sc.height = innerHeight; });

let shoots = [];
setInterval(() => shoots.push({
  x: Math.random() * innerWidth * .7,
  y: Math.random() * innerHeight * .3,
  vx: 4 + Math.random() * 5,
  vy: 2 + Math.random() * 3,
  len: 90 + Math.random() * 130,
  life: 1,
  alpha: 0
}), 3000);

(function shootLoop(){
  sx.clearRect(0,0,sc.width,sc.height);
  shoots = shoots.filter(s => s.life > 0);
  shoots.forEach(s => {
    s.alpha = Math.min(1, s.alpha + .055);
    s.life -= .022;
    const g = sx.createLinearGradient(s.x, s.y, s.x - s.len, s.y - s.len * .5);
    g.addColorStop(0, `rgba(232,208,144,${s.alpha*s.life})`);
    g.addColorStop(1, 'rgba(232,208,144,0)');
    sx.beginPath();
    sx.moveTo(s.x, s.y);
    sx.lineTo(s.x - s.len, s.y - s.len * .5);
    sx.strokeStyle = g;
    sx.lineWidth = 1.4;
    sx.stroke();
    s.x += s.vx; s.y += s.vy;
  });
  requestAnimationFrame(shootLoop);
})();

/* === MOUSE TRAIL === */
const tc = document.getElementById('trailC'), tx = tc.getContext('2d');
tc.width = innerWidth; tc.height = innerHeight;
window.addEventListener('resize', () => { tc.width = innerWidth; tc.height = innerHeight; });

let trails = [];
document.addEventListener('mousemove', e => {
  if (Math.random() > .6) trails.push({
    x: e.clientX, y: e.clientY,
    r: Math.random() * 1.8 + .4,
    life: 1,
    vx: (Math.random() - .5) * .6,
    vy: -Math.random() * .6 - .2
  });
});

(function trailLoop(){
  tx.clearRect(0,0,tc.width,tc.height);
  trails = trails.filter(t => t.life > 0);
  trails.forEach(t => {
    t.life -= .038;
    t.x += t.vx; t.y += t.vy;
    tx.beginPath();
    tx.arc(t.x, t.y, t.r * t.life, 0, Math.PI * 2);
    tx.fillStyle = `rgba(200,160,80,${t.life * .4})`;
    tx.fill();
  });
  requestAnimationFrame(trailLoop);
})();

/* === CLICK FX === */
document.addEventListener('click', e => {
  const sp = document.createElement('div');
  sp.className = 'sp';
  sp.textContent = ['✦','✧','⭑','·'][Math.floor(Math.random()*4)];
  sp.style.cssText = `left:${e.clientX}px;top:${e.clientY}px;font-size:${.7+Math.random()*.5}rem;color:rgba(200,160,80,.8)`;
  document.body.appendChild(sp);
  setTimeout(() => sp.remove(), 950);

  const rp = document.createElement('div');
  rp.className = 'ripple';
  rp.style.cssText = `left:${e.clientX}px;top:${e.clientY}px;width:0;height:0`;
  document.body.appendChild(rp);
  setTimeout(() => rp.remove(), 900);

  if (Math.random() > .65) {
    for (let i=0;i<3;i++) setTimeout(() => {
      const h = document.createElement('div');
      h.className = 'hpop';
      h.textContent = ['✦','🤍','·'][Math.floor(Math.random()*3)];
      const dx = (Math.random() - .5) * 55;
      h.style.cssText = `left:${e.clientX}px;top:${e.clientY}px;--dx:${dx}px;color:rgba(200,160,80,.7)`;
      document.body.appendChild(h);
      setTimeout(() => h.remove(), 1300);
    }, i*110);
  }
});

/* === PETALS === */
const pL = ['✿','❀','·','⋆','∘'];
function mkP(){
  const el = document.createElement('div');
  el.className = 'petal';
  el.textContent = pL[Math.floor(Math.random()*pL.length)];
  const d = 12 + Math.random() * 18;
  el.style.cssText =
    `left:${Math.random()*100}vw;font-size:${.4+Math.random()*.8}rem;animation-duration:${d}s;animation-delay:${Math.random()*6}s;color:rgba(200,160,80,${.1+Math.random()*.25});opacity:0`;
  document.body.appendChild(el);
  setTimeout(() => el.remove(), (d+6)*1000);
}
for (let i=0;i<5;i++) setTimeout(mkP, i*500);
setInterval(mkP, 2200);

/* === CLICKABLE STARS === */
const msgs = [
  {t:"Ти така красива,\nщо навіть через екран це видно.",s:"щиро"},
  {t:"Мені подобається,\nяк ти говориш.",s:"кожне слово"},
  {t:"Ти — одна з тих людей,\nяких зустрічаєш раз у житті.",s:"і це добре"},
  {t:"З тобою легко.\nЦе рідкість.",s:"правда"},
  {t:"Твоя усмішка —\nмоя улюблена річ.",s:"навіть здалеку"},
];

const pop = document.getElementById('starPop');
let popT = null;

document.querySelectorAll('.cstar').forEach((el,i) => {
  el.addEventListener('click', e => {
    e.stopPropagation();
    document.getElementById('spT').textContent = msgs[i].t;
    document.getElementById('spS').textContent = msgs[i].s;

    const r = el.getBoundingClientRect();
    let lx = r.left + r.width/2, ly = r.top - 14;
    if (lx > innerWidth - 130) lx = innerWidth - 130;
    if (lx < 115) lx = 115;
    if (ly < 90) ly = r.bottom + 14;

    pop.style.cssText = `left:${lx}px;top:${ly}px;transform:translate(-50%,-100%)`;
    pop.classList.add('vis');
    clearTimeout(popT);

    for (let j=0;j<5;j++) setTimeout(() => {
      const h = document.createElement('div');
      h.className = 'hpop';
      h.textContent = '✦';
      const dx = (Math.random() - .5) * 70;
      h.style.cssText = `left:${r.left+r.width/2}px;top:${r.top}px;--dx:${dx}px;color:rgba(200,160,80,.8)`;
      document.body.appendChild(h);
      setTimeout(() => h.remove(), 1300);
    }, j*75);

    popT = setTimeout(() => pop.classList.remove('vis'), 4000);
  });
});
document.addEventListener('click', () => { clearTimeout(popT); pop.classList.remove('vis'); });

/* === PIANO === */
let actx = null, musicOn = false, pianoT = null;
const fr = {'A2':110,'C3':130.81,'E3':164.81,'F2':87.31,'E2':82.41,'A4':440,'B4':493.88,'C5':523.25,'D5':587.33,'E5':659.25,'F5':698.46,'G5':783.99,'A5':880};
const mel = [['A4',.0,.5],['C5',.5,.4],['E5',1,.4],['A5',1.5,.6],['G5',2.5,.4],['E5',3,.4],['C5',3.5,.4],['A4',4,.6],['B4',5,.4],['C5',5.5,.4],['E5',6,.4],['G5',6.5,.5],['F5',7.5,.4],['E5',8,.4],['D5',8.5,.4],['C5',9,.7],['A4',10,.4],['C5',10.5,.4],['E5',11,.4],['A5',11.5,.6],['G5',12.5,.4],['E5',13,.4],['C5',13.5,.4],['A4',14,.7],['F5',15,.4],['G5',15.5,.3],['A5',16,.5],['E5',17,.4],['C5',17.5,.4],['A4',18,.9]];
const bas = [['A2',.0,2],['E2',2.5,2],['F2',5,2],['C3',7.5,2],['A2',10,2],['E2',12.5,2],['F2',15,2],['A2',17.5,1.5]];
const BT = 60/54, LOOP = 18.5*BT;

function pNote(f, t, d, v=.15, isBass=false){
  if(!actx) return;
  const o = actx.createOscillator(), g = actx.createGain(), flt = actx.createBiquadFilter();
  const irL = actx.sampleRate * 2, ir = actx.createBuffer(2, irL, actx.sampleRate);
  for(let c=0;c<2;c++){
    const data = ir.getChannelData(c);
    for(let i=0;i<irL;i++) data[i] = (Math.random()*2-1)*Math.pow(1-i/irL,2.5);
  }
  const rev = actx.createConvolver(); rev.buffer = ir;

  o.type = isBass ? 'sine' : 'triangle';
  o.frequency.setValueAtTime(f, t);

  flt.type='lowpass';
  flt.frequency.value = isBass ? 450 : 3800;
  flt.Q.value = .7;

  g.gain.setValueAtTime(0, t);
  g.gain.linearRampToValueAtTime(v, t+.012);
  g.gain.exponentialRampToValueAtTime(v*.28, t+.14);
  g.gain.exponentialRampToValueAtTime(.0001, t+d+1.3);

  const dry = actx.createGain(), wet = actx.createGain();
  dry.gain.value = .72; wet.gain.value = .28;

  o.connect(flt); flt.connect(g);
  g.connect(dry); dry.connect(actx.destination);
  g.connect(rev); rev.connect(wet); wet.connect(actx.destination);

  o.start(t); o.stop(t+d+1.6);
}
function schedLoop(off){
  mel.forEach(([n,b,d]) => pNote(fr[n], off+b*BT, d*BT, .14, false));
  bas.forEach(([n,b,d]) => pNote(fr[n], off+b*BT, d*BT, .075, true));
}
function startLoop(){
  if(!actx || !musicOn) return;
  schedLoop(actx.currentTime);
  pianoT = setTimeout(startLoop, (LOOP-.35)*1000);
}
async function toggleMusic(){
  if(!musicOn){
    if(!actx) actx = new (window.AudioContext||window.webkitAudioContext)();
    if(actx.state==='suspended') await actx.resume();
    musicOn = true;
    document.getElementById('mLabel').textContent='стоп';
    document.getElementById('mNote').textContent='♫';
    startLoop();
  }else{
    musicOn = false;
    clearTimeout(pianoT);
    document.getElementById('mLabel').textContent='музика';
    document.getElementById('mNote').textContent='♪';
    if(actx) actx.suspend();
  }
}

/* === POEM REVEAL === */
function openPoem(){
  document.getElementById('intro').style.display='none';
  document.getElementById('poemWrap').style.display='flex';

  poemBgImg.style.opacity='.9';
  aiBg.style.opacity='.3';

  setTimeout(() => {
    document.getElementById('roseL').classList.add('show');
    document.getElementById('roseR').classList.add('show');
  }, 600);

  // Keep your original behavior: show corners during poem.
  // Corners will only appear if loaded (no ?).
  setTimeout(() => {
    ['aiRoseTL','aiRoseTR','aiRoseBL','aiRoseBR'].forEach(id => {
      const el = document.getElementById(id);
      if(el && el.getAttribute('src')) el.style.display = '';
    });
  }, 1200);

  for(let i=0;i<10;i++) setTimeout(() => {
    const h = document.createElement('div'); h.className='hpop';
    h.textContent = ['✦','🤍','⭑'][Math.floor(Math.random()*3)];
    const dx = (Math.random()-.5)*200;
    h.style.cssText = `left:${innerWidth/2}px;top:${innerHeight/2}px;--dx:${dx}px;font-size:${.7+Math.random()*.6}rem;color:rgba(200,160,80,.65)`;
    document.body.appendChild(h);
    setTimeout(() => h.remove(), 1400);
  }, i*80);

  const seq=[['p0','aFade',400],['p1','aUp',900],['d1','aFade',2100],['p2','aUp',2600],['d2','aFade',4100],['p3','aUp',4600],['p4','aFade',6100],['p5','aFade',7100],['p6','aFade',7900]];
  seq.forEach(([id,cls,ms]) => setTimeout(() => document.getElementById(id).classList.add(cls), ms));
}

function goBack(){
  document.getElementById('poemWrap').style.display='none';
  poemBgImg.style.opacity='0';
  aiBg.style.opacity='1';

  document.getElementById('roseL').classList.remove('show');
  document.getElementById('roseR').classList.remove('show');

  // hide corners again (still no ?)
  ['aiRoseTL','aiRoseTR','aiRoseBL','aiRoseBR'].forEach(id => {
    const el = document.getElementById(id);
    if(el) el.style.display = 'none';
  });

  ['p0','p1','d1','p2','d2','p3','p4','p5','p6'].forEach(id => {
    const el = document.getElementById(id);
    el.classList.remove('aUp','aFade');
    el.style.opacity = '0';
  });

  const intro = document.getElementById('intro');
  intro.style.display='flex';
  intro.style.animation='none';
  intro.offsetHeight;
  intro.style.animation='';
}

function openSecret(){
  document.getElementById('secret').classList.add('open');
  setTimeout(()=>document.getElementById('secretBg').style.opacity='1',100);
}
function closeSecret(){
  document.getElementById('secret').classList.remove('open');
  document.getElementById('secretBg').style.opacity='0';
}
</script>
