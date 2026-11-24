<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>COMPASION FOOTBALL 0.3 — Touchline Edition</title>
<style>
*{box-sizing:border-box}html,body{margin:0;width:100%;height:100%;overflow:hidden;background:#06100d;color:#fff;font-family:Arial,Helvetica,sans-serif}
#game{position:fixed;inset:0}
#loading{position:fixed;inset:0;z-index:9;display:grid;place-content:center;text-align:center;background:#06100d;color:#b8ffbe;font-weight:900;letter-spacing:2px}
#loading small{display:block;margin-top:12px;color:#b8c9bd;font-weight:400;letter-spacing:0}
#hud{position:fixed;inset:0;pointer-events:none}
.top{position:absolute;top:14px;left:50%;transform:translateX(-50%);display:flex;align-items:center;gap:20px;padding:11px 18px;background:#06100ddd;border:1px solid #ffffff30;border-radius:12px;box-shadow:0 8px 30px #0006;white-space:nowrap}
.brand{font-weight:900;letter-spacing:1.5px;color:#aaffad}.score{font-size:20px;font-weight:900}.clock{font-variant-numeric:tabular-nums;color:#d5e4d8}
.panel{position:absolute;bottom:14px;left:14px;padding:12px 14px;border-radius:11px;border:1px solid #ffffff2b;background:#06100ddd;font-size:12px;line-height:1.7}
.panel.right{left:auto;right:14px;text-align:right}
.key{display:inline-block;padding:0 6px;margin:0 1px;border:1px solid #66806b;border-radius:4px;background:#1b3324;color:#e5ffe6}
#message{position:absolute;top:23%;left:50%;transform:translateX(-50%);font-weight:1000;font-size:clamp(24px,4vw,46px);color:#c7ffc9;text-shadow:0 4px 18px #000;opacity:0;transition:opacity .25s}
#quality{position:absolute;right:14px;top:14px;font-size:10px;color:#d2e5d6;background:#06100dbb;padding:7px 9px;border-radius:7px}
@media(max-width:650px){.top{top:7px;gap:9px;padding:8px 10px;font-size:11px}.score{font-size:15px}.panel{font-size:10px;padding:8px;bottom:8px;left:8px}.panel.right{display:none}#quality{display:none}}

#mobileControls{display:none;position:fixed;inset:0;z-index:5;pointer-events:none;touch-action:none}
#joyBase{position:absolute;left:22px;bottom:28px;width:132px;height:132px;border-radius:50%;background:#d7ffe52a;border:2px solid #d7ffe588;pointer-events:auto;touch-action:none;box-shadow:0 4px 18px #0006}
#joyStick{position:absolute;left:39px;top:39px;width:50px;height:50px;border-radius:50%;background:#e8fff0dd;border:2px solid #fff;box-shadow:0 3px 12px #0008;transform:translate(0,0)}
#touchActions{position:absolute;right:22px;bottom:30px;display:flex;flex-direction:column;gap:13px;pointer-events:auto}
#touchActions button{width:82px;height:70px;border-radius:50%;border:2px solid #ffffffb0;background:#09271ddd;color:#fff;font-weight:900;letter-spacing:1px;box-shadow:0 4px 16px #0008;touch-action:none}
#touchActions #shootBtn{width:94px;height:94px;background:#a52d25e8;font-size:15px}
#touchHint{position:absolute;bottom:7px;left:50%;transform:translateX(-50%);font-size:10px;color:#fff;background:#06100dbb;padding:5px 9px;border-radius:8px;white-space:nowrap}
@media(max-width:850px),(pointer:coarse){#mobileControls{display:block}.panel{display:none}.top{top:7px;gap:8px;padding:7px 9px}.brand{font-size:10px}.score{font-size:14px}.clock{font-size:11px}#quality{display:none}}
@media(max-width:390px){#joyBase{width:112px;height:112px;left:14px;bottom:22px}#joyStick{left:31px;top:31px}#touchActions{right:14px;bottom:24px}#touchActions button{width:70px;height:62px}#touchActions #shootBtn{width:82px;height:82px}}
</style>
</head>
<body>
<div id="game"></div>
<div id="loading">COMPASION FOOTBALL 0.3<small>Loading the stadium, teams and player models…</small></div>
<div id="hud">
 <div class="top"><span class="brand">COMPASION FC</span><span class="score" id="score">HOME 0 — 0 AWAY</span><span class="clock" id="clock">00:00</span></div>
 <div id="quality">STADIUM EDITION · OPTIMIZED 3D</div>
 <div id="message"></div>
 <div class="panel"><b>CONTROLS</b><br><span class="key">W A S D</span> Move &nbsp; <span class="key">SHIFT</span> Sprint<br><span class="key">SPACE</span> Shoot &nbsp; <span class="key">C</span> Camera (3 views)<br><span style="color:#a9c9ad">Camera: <b id="camName">Broadcast</b></span></div>
 <div class="panel right"><b>COMPASSION SPACE TECHNOLOGIES</b><br>Human model detail · Large stadium<br>Ball physics · Goalkeeper reactions</div>
</div>
<div id="mobileControls" aria-label="Touch controls">
 <div id="joyBase"><div id="joyStick"></div></div>
 <div id="touchActions"><button id="cameraBtn" type="button">CAM</button><button id="sprintBtn" type="button">SPRINT</button><button id="shootBtn" type="button">SHOOT</button></div>
 <div id="touchHint">Drag the left pad to move · Tap SHOOT near the ball</div>
</div>
<script type="module">
import * as THREE from 'https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js';
import { GLTFLoader } from 'https://cdn.jsdelivr.net/npm/three@0.160.0/examples/jsm/loaders/GLTFLoader.js';

const host=document.querySelector('#game');
const scene=new THREE.Scene();
scene.background=new THREE.Color(0x819eb2);
scene.fog=new THREE.Fog(0x819eb2,105,235);
const renderer=new THREE.WebGLRenderer({antialias:false,powerPreference:'low-power'});
renderer.setPixelRatio(Math.min(devicePixelRatio,1.0));
renderer.setSize(innerWidth,innerHeight);
renderer.outputColorSpace=THREE.SRGBColorSpace;
renderer.toneMapping=THREE.ACESFilmicToneMapping;
renderer.toneMappingExposure=1.12;
host.appendChild(renderer.domElement);

const camera=new THREE.PerspectiveCamera(48,innerWidth/innerHeight,.1,400);
const hemi=new THREE.HemisphereLight(0xdceeff,0x273725,2.05);scene.add(hemi);
const sun=new THREE.DirectionalLight(0xfff0d7,2.3);sun.position.set(-55,95,55);scene.add(sun);
const fill=new THREE.DirectionalLight(0xc8e1ff,.65);fill.position.set(50,35,-65);scene.add(fill);

const mat=(color,rough=.78,metal=0)=>new THREE.MeshStandardMaterial({color,roughness:rough,metalness:metal});
const M={
 turf:mat(0x28783a),stripe1:mat(0x2c8740),stripe2:mat(0x246d35),line:mat(0xf4f3e8),
 concrete:mat(0x3d4850),concrete2:mat(0x59636a),roof:mat(0x172a35,.48,.55),
 seatBlue:mat(0x174767),seatRed:mat(0x872f3d),seatWhite:mat(0xc5cbd0),
 home:mat(0xe9eff1,.48),homeDark:mat(0x183e88,.55),away:mat(0xd8b52b,.5),awayDark:mat(0x24272c,.65),
 skin1:mat(0x9b6042),skin2:mat(0x75452f),skin3:mat(0xc48761),skin4:mat(0x573927),
 hair:mat(0x211b18),boot:mat(0x11171b,.38),sockHome:mat(0xe9eff1),sockAway:mat(0xd8b52b),
 glove:mat(0x202a35),ball:mat(0xf5f4ed,.35)
};
function mesh(geo,material,parent,pos=[0,0,0],rot=[0,0,0]){const o=new THREE.Mesh(geo,material);o.position.set(...pos);o.rotation.set(...rot);parent.add(o);return o}
function box(parent,w,h,d,material,pos,rot=[0,0,0]){return mesh(new THREE.BoxGeometry(w,h,d),material,parent,pos,rot)}
function cylinder(parent,r1,r2,h,material,pos,rot=[0,0,0],seg=10){return mesh(new THREE.CylinderGeometry(r1,r2,h,seg),material,parent,pos,rot)}
function capsule(parent,r,len,material,pos,rot=[0,0,0]){return mesh(new THREE.CapsuleGeometry(r,len,4,8),material,parent,pos,rot)}
function sphere(parent,r,material,pos,scale=[1,1,1],seg=12){const o=mesh(new THREE.SphereGeometry(r,seg,Math.max(8,seg-2)),material,parent,pos);o.scale.set(...scale);return o}
function tube(parent,pts,r,material){const curve=new THREE.CatmullRomCurve3(pts.map(p=>new THREE.Vector3(...p)));return mesh(new THREE.TubeGeometry(curve,Math.max(20,pts.length*6),r,6,false),material,parent)}
function plane(parent,w,h,material,pos,rot=[-Math.PI/2,0,0]){return mesh(new THREE.PlaneGeometry(w,h),material,parent,pos,rot)}

// Ground and detailed pitch
box(scene,205,.8,195,mat(0x202b2a),[0,-1.1,0]);
plane(scene,68,105,M.turf,[0,-.68,0]);
for(let i=0;i<14;i++)plane(scene,68,7.5,i%2?M.stripe1:M.stripe2,[0,-.665,-48.75+i*7.5]);
const pitchGroup=new THREE.Group();scene.add(pitchGroup);
function pitchLine(points,r=.055){tube(pitchGroup,points.map(([x,z])=>[x,-.62,z]),r,M.line)}
pitchLine([[-34,-52.5],[34,-52.5],[34,52.5],[-34,52.5],[-34,-52.5]]);
pitchLine([[0,-52.5],[0,52.5]]);
const circle=[];for(let i=0;i<=96;i++){let a=i*Math.PI*2/96;circle.push([9.15*Math.cos(a),9.15*Math.sin(a)])}pitchLine(circle);
pitchLine([[-34,-36],[34,-36],[34,36],[-34,36],[-34,-36]]);
pitchLine([[-20,-52.5],[20,-52.5],[20,-36],[-20,-36],[-20,-52.5]]);
pitchLine([[-20,52.5],[20,52.5],[20,36],[-20,36],[-20,52.5]]);
for(const z of [-42,0,42]){const d=new THREE.Mesh(new THREE.CircleGeometry(.2,16),M.line);d.rotation.x=-Math.PI/2;d.position.set(0,-.6,z);scene.add(d)}

// Stadium bowl: four curved-looking tiered banks, vomitory gaps, fascia bands and roof canopy
const standMats=[M.seatBlue,M.seatRed,M.seatWhite];
function standBank(side,tier){
 const y=3+tier*3.05, depth=9.5, height=3.0, spread=tier*2.1;
 if(side==='north'||side==='south'){
  const z=(side==='north'?-1:1)*(62+spread);
  box(scene,119,height,depth,M.concrete,[0,y,z]);
  box(scene,119,.42,depth,standMats[tier%3],[0,y+1.45,z]);
  box(scene,121,.8,1.2,M.concrete2,[0,y+2.0,z+(side==='north'?4.5:-4.5)]);
  for(let x=-56;x<=56;x+=4.2){
   const seatMat=standMats[(Math.floor((x+60)/4.2)+tier)%3];
   for(let row=0;row<3;row++)box(scene,.75,.55,.65,seatMat,[x,y-.55+row*.72,z+(row-1)*2.2]);
  }
 }else{
  const x=(side==='east'?1:-1)*(42+spread);
  box(scene,depth,height,121,M.concrete,[x,y,0]);
  box(scene,depth,.42,121,standMats[(tier+1)%3],[x,y+1.45,0]);
  box(scene,1.2,.8,123,M.concrete2,[x+(side==='east'?-4.5:4.5),y+2,0]);
  for(let z=-57;z<=57;z+=4.2){
   const seatMat=standMats[(Math.floor((z+60)/4.2)+tier+1)%3];
   for(let row=0;row<3;row++)box(scene,.65,.55,.75,seatMat,[x+(row-1)*2.2,y-.55+row*.72,z]);
  }
 }
}
for(let t=0;t<4;t++)for(const s of ['north','south','east','west'])standBank(s,t);
// Upper concourse and roof supports
for(const z of [-72,72]){
 box(scene,126,2.2,5,M.concrete2,[0,17,z]);
 box(scene,130,.65,5,M.roof,[0,18.3,z]);
}
for(const x of [-58,58]){
 box(scene,5,2.2,145,M.concrete2,[x,17,0]);
 box(scene,5,.65,150,M.roof,[x,18.3,0]);
}
// Roof canopy overhangs with underside ribs
for(const z of [-76,76]){
 box(scene,132,1.2,19,M.roof,[0,20.2,z]);
 for(let x=-60;x<=60;x+=12)cylinder(scene,.13,.13,19,M.concrete2,[x,19.4,z],[Math.PI/2,0,0],7);
}
for(const x of [-63,63]){
 box(scene,19,1.2,148,M.roof,[x,20.2,0]);
 for(let z=-65;z<=65;z+=13)cylinder(scene,.13,.13,19,M.concrete2,[x,19.4,z],[0,0,Math.PI/2],7);
}
// Crowd: compact instanced people silhouettes across stands
const crowdGeo=new THREE.CapsuleGeometry(.19,.42,2,5);
const crowdMat=new THREE.MeshStandardMaterial({color:0xffffff,roughness:1});
const crowd=new THREE.InstancedMesh(crowdGeo,crowdMat,3400);
const dummy=new THREE.Object3D();let n=0;
const crowdColors=[0x174767,0x872f3d,0xd7dce0,0x2c6945,0xb38b50,0x343c4d];
for(const side of ['north','south','east','west'])for(let i=0;i<850;i++){
 const tier=Math.floor(Math.random()*4), row=Math.floor(Math.random()*3), along=(Math.random()-.5)* (side==='north'||side==='south'?112:116);
 if(side==='north')dummy.position.set(along,3.2+tier*3.05+row*.7,-62-tier*2.1+row*1.5);
 if(side==='south')dummy.position.set(along,3.2+tier*3.05+row*.7,62+tier*2.1-row*1.5);
 if(side==='east')dummy.position.set(42+tier*2.1-row*1.5,3.2+tier*3.05+row*.7,along);
 if(side==='west')dummy.position.set(-42-tier*2.1+row*1.5,3.2+tier*3.05+row*.7,along);
 dummy.rotation.set(0,Math.random()*Math.PI*2,0);dummy.scale.set(.8+Math.random()*.5,.8+Math.random()*.6,.8+Math.random()*.5);dummy.updateMatrix();
 crowd.setMatrixAt(n,dummy.matrix);crowd.setColorAt(n,new THREE.Color(crowdColors[Math.floor(Math.random()*crowdColors.length)]));n++;
}
scene.add(crowd);
// Advertising boards
const boardMat=mat(0x071b25,.4,.2), glowMat=mat(0x8cff9c,.3,.1);
for(const z of [-54,54]){
 box(scene,70,1.05,.35,boardMat,[0,.65,z]);
 for(let x=-31;x<=31;x+=15)box(scene,12,.07,.08,glowMat,[x,.7,z+(z<0?-.2:.2)]);
}
for(const x of [-35,35])box(scene,.35,1.05,105,boardMat,[x,.65,0]);

// Goals with post frame, back net and net grid
function goal(z,dir){
 const frame=mat(0xf4f5ed,.3,.2), netmat=new THREE.LineBasicMaterial({color:0xd9e5e0,transparent:true,opacity:.42});
 for(const x of [-3.66,3.66])cylinder(scene,.12,.12,2.45,frame,[x,1.23,z],[0,0,0],12);
 cylinder(scene,.12,.12,7.45,frame,[0,2.46,z],[0,0,Math.PI/2],12);
 const pts=[];
 for(let x=-3.6;x<=3.61;x+=.6){pts.push([x,.05,z+dir*4.3],[x,2.4,z+dir*4.3]);}
 for(let y=.1;y<=2.41;y+=.4)pts.push([-3.6,y,z+dir*4.3],[3.6,y,z+dir*4.3]);
 const geo=new THREE.BufferGeometry().setFromPoints(pts.map(p=>new THREE.Vector3(...p)));
 scene.add(new THREE.LineSegments(geo,netmat));
 for(const x of [-3.6,3.6])tube(scene,[[x,0,z],[x,1.2,z+dir*2.2],[x,2.4,z+dir*4.3]],.035,frame);
}
goal(-52.5,-1);goal(52.5,1);

// Floodlight masts and luminous arrays
for(const x of [-73,73])for(const z of [-75,75]){
 cylinder(scene,.45,.75,27,M.concrete2,[x,13.5,z],[],8);
 box(scene,8,1.1,2,mat(0xe9f3ee,.35),[x,27,z]);
 const light=new THREE.PointLight(0xfff1d7,36,95,1.7);light.position.set(x,26,z);scene.add(light);
}

// Human player construction: layered torso, neck, shaped head, ears, hair, articulated limbs and boots
const skinMats=[M.skin1,M.skin2,M.skin3,M.skin4];
const jerseyNumberTexture=(num,color)=>{
 const c=document.createElement('canvas');c.width=128;c.height=128;const ctx=c.getContext('2d');
 ctx.clearRect(0,0,128,128);ctx.fillStyle=color;ctx.font='bold 88px Arial';ctx.textAlign='center';ctx.textBaseline='middle';ctx.fillText(String(num),64,68);
 const t=new THREE.CanvasTexture(c);t.colorSpace=THREE.SRGBColorSpace;return new THREE.MeshBasicMaterial({map:t,transparent:true,side:THREE.DoubleSide});
};
function createPlayer(team,num,x,z,keeper=false){
 const root=new THREE.Group();root.position.set(x,0,z);scene.add(root);const body=new THREE.Group();root.add(body);
 const home=team==='home', jersey=home?M.home:M.away, shorts=home?M.homeDark:M.awayDark, sock=home?M.sockHome:M.sockAway;
 const skin=skinMats[(num+(home?0:2))%skinMats.length], parts={};
 // Torso and shirt silhouette
 const torso=new THREE.Group();torso.position.y=1.38;body.add(torso);parts.torso=torso;
 const chest=sphere(torso,.48,jersey,[0,.18,0],[.88,1.18,.52],16);
 capsule(torso,.22,.12,skin,[0,.82,0]); // neck
 // Shoulder caps and sleeves
 for(const s of [-1,1]){
  sphere(torso,.23,jersey,[s*.43,.48,0],[1,.8,.9],12);
  capsule(torso,.145,.38,jersey,[s*.57,.25,0],[0,0,-s*.22]);
  sphere(torso,.105,skin,[s*.64,-.03,-.01],[1,1.1,1],10);
 }
 // Front number plate
 const numberMat=jerseyNumberTexture(num,home?'#17345b':'#27251b');
 const number=mesh(new THREE.PlaneGeometry(.32,.42),numberMat,torso,[0,.22,-.455]);number.rotation.y=0;
 // collar
 const collar=mesh(new THREE.TorusGeometry(.17,.035,6,16),home?M.homeDark:M.awayDark,torso,[0,.66,0]);collar.rotation.x=Math.PI/2;
 // Head and face
 const head=new THREE.Group();head.position.set(0,2.48,0);body.add(head);parts.head=head;
 sphere(head,.275,skin,[0,0,0],[.83,1.13,.82],16);
 sphere(head,.21,M.hair,[0,.205,.005],[1,.48,1],12);
 for(const s of [-1,1]){
  sphere(head,.055,skin,[s*.235,-.015,0],[.7,1,1],8);
  sphere(head,.035,mat(0xf4e9dc),[s*.095,.035,-.226],[1,.65,.5],8);
  sphere(head,.018,mat(0x241b18),[s*.095,.035,-.247],[1,1,1],8);
 }
 // Hair cap, side hair and subtle mouth
 sphere(head,.25,M.hair,[0,.17,.025],[1,.55,1],12);
 box(head,.08,.035,.018,mat(0x4c2924),[0,-.105,-.221]);
 // Shorts and waist
 const hips=sphere(body,.34,shorts,[0,.91,0],[1,.65,.75],12);parts.hips=hips;
 // Articulated legs with upper/lower segments and football socks
 parts.legs=[];
 for(const s of [-1,1]){
  const hip=new THREE.Group();hip.position.set(s*.19,.83,0);body.add(hip);
  capsule(hip,.16,.36,shorts,[0,-.22,0]);
  const knee=new THREE.Group();knee.position.set(0,-.43,0);hip.add(knee);
  capsule(knee,.105,.39,sock,[0,-.23,0]);
  cylinder(knee,.112,.112,.12,home?M.homeDark:M.awayDark,[0,-.36,0],[],10);
  const boot=new THREE.Group();boot.position.set(0,-.48,-.045);knee.add(boot);
  sphere(boot,.145,M.boot,[0,0,-.12],[.82,.55,1.45],12);
  // boot studs
  for(let i=-1;i<=1;i++)cylinder(boot,.025,.025,.035,M.boot,[i*.065,-.07,-.12],[0,0,0],6);
  parts.legs.push({hip,knee,boot,side:s});
 }
 // Arms articulated from shoulders
 parts.arms=[];
 for(const s of [-1,1]){
  const arm=new THREE.Group();arm.position.set(s*.48,1.83,0);body.add(arm);
  capsule(arm,.115,.32,jersey,[s*.04,-.19,0],[0,0,-s*.12]);
  const fore=new THREE.Group();fore.position.set(s*.07,-.39,0);arm.add(fore);
  capsule(fore,.085,.32,skin,[s*.015,-.18,-.015],[0,0,-s*.08]);
  sphere(fore,.09,skin,[s*.02,-.39,-.015],[.85,1,.65],8);
  parts.arms.push({arm,fore,side:s});
 }
 root.userData={team,num,keeper,homeX:x,homeZ:z,parts,phase:Math.random()*6,velocity:new THREE.Vector3(),diving:0,proceduralBody:body,realModel:null};
 return root;
}
const players=[];
const homePos=[[-18,-25],[-6,-28],[6,-28],[18,-25],[-25,-9],[-9,-8],[9,-8],[25,-9],[-12,7],[12,7],[0,-43]];
const awayPos=[[-18,25],[-6,28],[6,28],[18,25],[-25,9],[-9,8],[9,8],[25,9],[-12,-7],[12,-7],[0,43]];
homePos.forEach((p,i)=>players.push(createPlayer('home',i+1,p[0],p[1],i===10)));
awayPos.forEach((p,i)=>players.push(createPlayer('away',i+1,p[0],p[1],i===10)));
const controlled=players[5];
// CC0 textured soccer-player GLB used as close-range character detail. It is a static
// running-pose mesh (not rigged), so distant players use the lightweight animated LOD.
const playerAssetURL='https://files.innerscene.com/library/soccer-player-running-3d-person-team-sports-7293f9db/dd8a246944bd0fcd6213/professional-soccer-running.glb';
new GLTFLoader().load(playerAssetURL,gltf=>{
 const source=gltf.scene;source.scale.setScalar(1.0);
 for(const p of players){const model=source.clone(true);model.traverse(o=>{if(o.isMesh){o.castShadow=false;o.receiveShadow=false;o.frustumCulled=true;}});p.add(model);p.userData.realModel=model;p.userData.proceduralBody.visible=false;}
 announce('REALISTIC PLAYER MODELS LOADED');
},undefined,()=>{announce('PLAYER MODEL DOWNLOAD FAILED — USING BUILT-IN PLAYERS');});

// Ball with panel pattern
const ball=new THREE.Group();scene.add(ball);ball.position.set(0,.48,0);
sphere(ball,.43,M.ball,[0,0,0],[1,1,1],20);
const patchmat=mat(0x20272b,.55);
for(let i=0;i<5;i++){const a=i*Math.PI*2/5;const p=sphere(ball,.105,patchmat,[Math.cos(a)*.32,Math.sin(a*2)*.2,Math.sin(a)*.32],[1,.65,1],8);p.rotation.y=a}
const velocity=new THREE.Vector3();
let homeScore=0,awayScore=0,elapsed=0,camMode=0,last=performance.now(),spaceHeld=false;
const touchMove={x:0,y:0};let touchSprint=false;
const key={};
addEventListener('keydown',e=>{key[e.code]=true;if(['Space','ArrowUp','ArrowDown','ArrowLeft','ArrowRight'].includes(e.code))e.preventDefault();if(e.code==='KeyC'&&!e.repeat){camMode=(camMode+1)%3;document.querySelector('#camName').textContent=['Broadcast','Player view','Side view'][camMode];}});
addEventListener('keyup',e=>key[e.code]=false);
// Mobile virtual joystick and action buttons. Pointer events support touch, pen and mouse.
const joyBase=document.querySelector('#joyBase'),joyStick=document.querySelector('#joyStick');let joyPointer=null;
function setJoy(e){const r=joyBase.getBoundingClientRect(),cx=r.left+r.width/2,cy=r.top+r.height/2;let x=e.clientX-cx,y=e.clientY-cy;const max=42,len=Math.hypot(x,y)||1;if(len>max){x=x/len*max;y=y/len*max}touchMove.x=x/max;touchMove.y=y/max;joyStick.style.transform=`translate(${x}px,${y}px)`}
joyBase.addEventListener('pointerdown',e=>{joyPointer=e.pointerId;joyBase.setPointerCapture(joyPointer);setJoy(e)});
joyBase.addEventListener('pointermove',e=>{if(e.pointerId===joyPointer)setJoy(e)});
function releaseJoy(e){if(e.pointerId!==joyPointer)return;joyPointer=null;touchMove.x=0;touchMove.y=0;joyStick.style.transform='translate(0,0)'}
joyBase.addEventListener('pointerup',releaseJoy);joyBase.addEventListener('pointercancel',releaseJoy);
const shootBtn=document.querySelector('#shootBtn');shootBtn.addEventListener('pointerdown',e=>{e.preventDefault();key.Space=true});['pointerup','pointercancel','pointerleave'].forEach(ev=>shootBtn.addEventListener(ev,()=>key.Space=false));
document.querySelector('#cameraBtn').addEventListener('click',()=>{camMode=(camMode+1)%3;document.querySelector('#camName').textContent=['Broadcast','Player view','Side view'][camMode];announce(['BROADCAST CAMERA','PLAYER CAMERA','SIDE CAMERA'][camMode]);});
const sprintBtn=document.querySelector('#sprintBtn');sprintBtn.addEventListener('pointerdown',e=>{e.preventDefault();touchSprint=true});['pointerup','pointercancel','pointerleave'].forEach(ev=>sprintBtn.addEventListener(ev,()=>touchSprint=false));
function announce(s){const el=document.querySelector('#message');el.textContent=s;el.style.opacity=1;clearTimeout(announce.t);announce.t=setTimeout(()=>el.style.opacity=0,1600)}
function resetBall(){ball.position.set(0,.48,0);velocity.set(0,0,0)}
function shoot(){const dx=ball.position.x-controlled.position.x,dz=ball.position.z-controlled.position.z;if(Math.hypot(dx,dz)<3.2){const dir=new THREE.Vector3(0,0,-1).applyQuaternion(controlled.quaternion);velocity.set(dir.x*24,6,dir.z*24);announce('SHOT!')}}
function animatePlayer(p,dt,moving){
 const a=p.userData,parts=a.parts;a.phase+=dt*(moving?10:2);
 const swing=moving?Math.sin(a.phase)*.62:0;
 parts.legs.forEach((l,i)=>{l.hip.rotation.x=swing*(i===0?1:-1);l.knee.rotation.x=Math.max(0,-swing*(i===0?1:-1))*.9});
 parts.arms.forEach((arm,i)=>{arm.arm.rotation.x=-swing*(i===0?1:-1)*.45;arm.fore.rotation.x=-.18});
 parts.torso.rotation.z=moving?Math.sin(a.phase)*.035:0;
}
function update(dt){
 elapsed+=dt;document.querySelector('#clock').textContent=String(Math.floor(elapsed/60)).padStart(2,'0')+':'+String(Math.floor(elapsed%60)).padStart(2,'0');
 let dx=(key.KeyD?1:0)-(key.KeyA?1:0)+touchMove.x,dz=(key.KeyS?1:0)-(key.KeyW?1:0)+touchMove.y;
 const dir=new THREE.Vector3(dx,0,dz);
 if(dir.lengthSq()){dir.normalize();controlled.position.addScaledVector(dir,(key.ShiftLeft||key.ShiftRight||touchSprint?11.5:7.2)*dt);controlled.rotation.y=Math.atan2(-dir.x,-dir.z)}
 controlled.position.x=THREE.MathUtils.clamp(controlled.position.x,-32,32);controlled.position.z=THREE.MathUtils.clamp(controlled.position.z,-50,50);
 animatePlayer(controlled,dt,dir.lengthSq()>0);
 for(const p of players){if(p.userData.realModel){const near=p.position.distanceTo(controlled.position)<31;p.userData.realModel.visible=near;p.userData.proceduralBody.visible=!near;}}
 if(key.Space&&!spaceHeld)shoot();spaceHeld=!!key.Space;
 // Ball gravity, bounce and friction
 velocity.y-=17*dt;ball.position.addScaledVector(velocity,dt);
 if(ball.position.y<.44){ball.position.y=.44;if(velocity.y<0)velocity.y*=-.38;velocity.x*=.985;velocity.z*=.985}
 velocity.x*=Math.pow(.989,dt*60);velocity.z*=Math.pow(.989,dt*60);ball.rotation.x+=velocity.z*dt*1.8;ball.rotation.z-=velocity.x*dt*1.8;
 if(Math.abs(ball.position.x)>33){ball.position.x=Math.sign(ball.position.x)*33;velocity.x*=-.55}
 if(Math.abs(ball.position.z)>52){ball.position.z=Math.sign(ball.position.z)*52;velocity.z*=-.55}
 // Teammates hold their shape and nearby opponent players press toward the ball
 for(const p of players){if(p===controlled||p.userData.keeper)continue;const a=p.userData;
  if(a.team==='away'){const tx=THREE.MathUtils.clamp(a.homeX*.55+ball.position.x*.45,-29,29),tz=THREE.MathUtils.clamp(a.homeZ*.62+ball.position.z*.38,-48,48);p.position.x=THREE.MathUtils.damp(p.position.x,tx,.8,dt);p.position.z=THREE.MathUtils.damp(p.position.z,tz,.8,dt)}
  animatePlayer(p,dt,Math.abs(p.position.x-a.homeX)+Math.abs(p.position.z-a.homeZ)>.3);
 }
 // Goalkeepers track the ball and dive when a shot approaches their goal
 for(const gk of [players[10],players[21]]){
  const sign=gk.userData.team==='home'?-1:1,targetZ=sign*46.5;
  const targetX=THREE.MathUtils.clamp(ball.position.x,-3.25,3.25);
  gk.position.x=THREE.MathUtils.damp(gk.position.x,targetX,3.2,dt);
  gk.position.z=THREE.MathUtils.damp(gk.position.z,targetZ,2.2,dt);
  const incoming=(sign<0?velocity.z< -5:velocity.z>5)&&Math.abs(ball.position.z-targetZ)<12;
  if(incoming&&Math.abs(ball.position.x-gk.position.x)<6){gk.userData.diving= Math.sign(ball.position.x-gk.position.x||1);gk.rotation.z=THREE.MathUtils.damp(gk.rotation.z,-gk.userData.diving*.75,5,dt)}
  else {gk.rotation.z=THREE.MathUtils.damp(gk.rotation.z,0,3,dt)}
  animatePlayer(gk,dt,true);
 }
 // Basic player-ball contact: ball is nudged away from the controlled player
 const pd=ball.position.clone().sub(controlled.position);if(pd.length()<1.25&&ball.position.y<1.4){pd.y=0;pd.normalize();velocity.addScaledVector(pd,5*dt)}
 // Goal detection
 if(Math.abs(ball.position.z)>52.25&&Math.abs(ball.position.x)<3.65&&ball.position.y<2.45){
  if(ball.position.z<0)awayScore++;else homeScore++;
  document.querySelector('#score').textContent=`HOME ${homeScore} — ${awayScore} AWAY`;announce('GOAL!');resetBall();
 }
}
function updateCamera(){
 if(camMode===0){camera.position.lerp(new THREE.Vector3(0,61,86),.035);camera.lookAt(0,0,0)}
 else if(camMode===1){const offset=new THREE.Vector3(0,6.2,10.5).applyQuaternion(controlled.quaternion);camera.position.lerp(controlled.position.clone().add(offset),.11);camera.lookAt(controlled.position.clone().add(new THREE.Vector3(0,1.35,0)))}
 else {camera.position.lerp(new THREE.Vector3(94,18,0),.055);camera.lookAt(0,0,0)}
}
function loop(now){requestAnimationFrame(loop);const dt=Math.min((now-last)/1000,.033);last=now;update(dt);updateCamera();renderer.render(scene,camera)}
addEventListener('resize',()=>{camera.aspect=innerWidth/innerHeight;camera.updateProjectionMatrix();renderer.setSize(innerWidth,innerHeight);renderer.setPixelRatio(Math.min(devicePixelRatio,1.0))});
document.querySelector('#loading').style.display='none';announce('WELCOME TO COMPASION FOOTBALL');loop(performance.now());
</script>
</body>
</html>
