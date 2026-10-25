<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="utf-8">
<title>Savings Goals</title>
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Savings">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<meta name="theme-color" content="#f4f6f3">
<style>
:root{--bg:#f4f6f3;--card:#f9fbf8;--ink:#1b241f;--mute:#667068;--line:#e1e6df;--lime:#ccee62;--pur:#8b7cf0;--grn:#2bb673;--red:#e5484d;--ph:#d3d9d9;color-scheme:light}
@media (prefers-color-scheme:dark){:root:not([data-theme=light]){--bg:#141816;--card:#1d231f;--ink:#eef2ee;--mute:#9aa49c;--line:#2c352f;--ph:#2a3330;color-scheme:dark}}
:root[data-theme=dark]{--bg:#141816;--card:#1d231f;--ink:#eef2ee;--mute:#9aa49c;--line:#2c352f;--ph:#2a3330;color-scheme:dark}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{margin:0;height:100%;background:var(--bg);color:var(--ink);font-family:-apple-system,system-ui,"Sarabun","Noto Sans Thai",sans-serif;overscroll-behavior:none}
:root{padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
button{font:inherit;color:inherit;border:0;background:none;cursor:pointer;touch-action:manipulation}
#app{max-width:520px;margin:0 auto;padding:12px 16px 40px}
.bar{display:flex;align-items:center;gap:6px;height:48px}
.bar .sp{flex:1}
.ib{width:44px;height:44px;border-radius:22px;display:grid;place-items:center;font-size:22px}
.ib:active{background:var(--line)}
.pur{color:var(--pur)}
.card{background:var(--card);border:1px solid var(--line);border-radius:28px;overflow:hidden;margin:14px 0}
.cover{height:190px;background:linear-gradient(135deg,var(--ph),#e6eae8);display:grid;place-items:center;background-size:cover;background-position:center}
.cover svg{width:72px;height:72px;opacity:.55}
.cb{padding:16px 20px 18px}
.row{display:flex;justify-content:space-between;align-items:baseline;gap:10px}
.nm{font-size:22px;font-weight:700;word-break:break-word}
.pct{color:var(--mute);font-size:17px}
.pb{height:10px;border-radius:5px;background:var(--line);margin:12px 0;overflow:hidden}
.pb i{display:block;height:100%;background:var(--grn);border-radius:5px;transition:width .4s}
.sm{color:var(--mute);font-size:15px}
.add{display:block;margin:10px 0 0 auto;color:var(--pur);font-size:17px;padding:8px 4px}
.badge{display:inline-block;background:var(--grn);color:#fff;border-radius:10px;font-size:12px;padding:2px 8px;margin-left:8px;vertical-align:middle}
.info{border:1px solid var(--line);background:var(--card);border-radius:24px;padding:16px 20px;display:grid;gap:12px;margin:14px 0}
.info b{margin-left:8px}
h3{font-size:22px;margin:26px 2px 10px}
.tx{background:var(--card);border-radius:20px;padding:14px 18px;display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;gap:10px}
.tx small{display:block;color:var(--mute);margin-top:2px}
.tx .a{font-size:20px;font-weight:600}.tx .a.w{color:var(--red)}
.tx .x{color:var(--mute);font-size:18px;padding:6px}
.done{width:100%;border:2px solid var(--grn);color:var(--grn);border-radius:28px;height:56px;font-size:18px;font-weight:600;margin-top:22px}
.empty{text-align:center;color:var(--mute);padding:50px 20px}
#ov{position:fixed;inset:0;background:rgba(0,0,0,.4);display:none;z-index:20}
#sh{position:fixed;left:0;right:0;bottom:0;max-height:92%;overflow-y:auto;background:var(--bg);border-radius:28px 28px 0 0;padding:16px 16px calc(24px + env(safe-area-inset-bottom,0px));display:none;z-index:21;max-width:520px;margin:0 auto;-webkit-overflow-scrolling:touch}
.on{display:block!important}
.sh-h{display:flex;align-items:center;justify-content:space-between;margin-bottom:6px}
.sh-h h2{margin:0;font-size:20px;flex:1;text-align:center}
label{display:block;font-weight:700;font-size:18px;margin:16px 2px 8px}
input,select,textarea{width:100%;font:inherit;font-size:16px;color:var(--ink);background:var(--card);border:1.5px solid var(--ink);border-radius:22px;padding:14px 18px;outline:0;-webkit-appearance:none;appearance:none}
input.big{font-size:30px;font-weight:600}
input.soft,select{border-color:var(--line)}
textarea{min-height:100px;resize:none}
.chips{display:flex;gap:8px;margin-top:12px;flex-wrap:wrap}
.chip{border:1.5px solid var(--line);background:var(--card);border-radius:24px;padding:12px 18px;font-size:17px;font-weight:600}
.chip.sel{background:var(--red);color:#fff;border-color:var(--red)}
.btn{width:100%;height:56px;border-radius:28px;background:var(--lime);color:#1b241f;font-size:19px;font-weight:700;margin-top:22px}
.btn.g{background:none;color:var(--red);border:1.5px solid var(--red);margin-top:12px}
.btn.s{background:var(--card);color:var(--ink);border:1.5px solid var(--line);margin-top:12px;height:48px;font-size:16px}
.two{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.prev{height:110px;border-radius:20px;background:var(--ph) center/cover;margin-top:6px}
#toast{position:fixed;left:50%;bottom:calc(30px + env(safe-area-inset-bottom,0px));transform:translateX(-50%);background:var(--ink);color:var(--bg);padding:10px 18px;border-radius:20px;font-size:15px;opacity:0;pointer-events:none;transition:opacity .25s;z-index:40}
</style>
</head>
<body>
<div id="app"></div>
<div id="ov"></div><div id="sh"></div><div id="toast"></div>
<script>
(function(){
var KEY="savings_v1",S={goals:[]},view=null,sortMode=0,compact=false;
try{var r=localStorage.getItem(KEY);if(r)S=JSON.parse(r)||S;if(!S.goals)S.goals=[]}catch(e){}
function save(){try{localStorage.setItem(KEY,JSON.stringify(S))}catch(e){toast("บันทึกไม่ได้ พื้นที่เต็ม")}}
function $(id){return document.getElementById(id)}
function esc(s){return String(s==null?"":s).replace(/[&<>"']/g,function(c){return{"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]})}
function money(n){return "฿"+Number(n||0).toLocaleString("en-US",{minimumFractionDigits:2,maximumFractionDigits:2})}
function saved(g){return (g.txs||[]).reduce(function(a,t){return a+t.amt},0)}
function pct(g){return g.target>0?Math.max(0,Math.min(100,saved(g)/g.target*100)):0}
function today(){var d=new Date();return d.getFullYear()+"-"+String(d.getMonth()+1).padStart(2,"0")+"-"+String(d.getDate()).padStart(2,"0")}
function fdate(s){var p=s.split("-");return new Date(+p[0],+p[1]-1,+p[2]).toLocaleDateString("en-US",{month:"short",day:"numeric",year:"numeric"})}
function uid(){return Date.now().toString(36)+Math.random().toString(36).slice(2,6)}
function toast(m){var t=$("toast");t.textContent=m;t.style.opacity=1;clearTimeout(toast.t);toast.t=setTimeout(function(){t.style.opacity=0},1800)}
var SHIELD='<svg viewBox="0 0 24 24" fill="#5d6b73"><path d="M12 2 4 5v6c0 5 3.4 9.4 8 11 4.6-1.6 8-6 8-11V5l-8-3zm1 15a5 5 0 0 1-3-9 4 4 0 0 0 5 5 5 5 0 0 1-2 4z"/></svg>';
var FREQ={none:"ไม่กำหนด",daily:"Daily",weekly:"Weekly",monthly:"Monthly"};
function cover(g){return g.img?'<div class="cover" style="background-image:url('+g.img+')"></div>':'<div class="cover">'+SHIELD+'</div>'}
function find(id){return S.goals.filter(function(g){return g.id===id})[0]}

function render(){
  var g=view&&find(view);if(view&&!g)view=null;
  $("app").innerHTML=g?detail(g):home();
  window.scrollTo(0,0)
}
function home(){
  var list=S.goals.slice();
  if(sortMode===1)list.sort(function(a,b){return pct(b)-pct(a)});
  if(sortMode===2)list.sort(function(a,b){return a.name.localeCompare(b.name)});
  var h='<div class="bar"><button class="ib" data-a="settings">⚙︎</button><button class="ib" data-a="sort">⇅</button><button class="ib" data-a="compact">▭</button><span class="sp"></span><button class="ib pur" data-a="newgoal">＋</button></div>';
  if(!list.length)h+='<div class="empty">ยังไม่มีเป้าหมาย<br>กด ＋ เพื่อเริ่มออม</div>';
  list.forEach(function(x){
    h+='<div class="card" data-open="'+x.id+'">'+(compact?'':cover(x))+'<div class="cb"><div class="row"><span class="nm">'+esc(x.name)+(x.done?'<span class="badge">✓</span>':'')+'</span><span class="pct">'+Math.floor(pct(x))+'%</span></div><div class="pb"><i style="width:'+pct(x)+'%"></i></div><div class="row sm"><span>'+money(saved(x))+' saved</span><span>'+money(x.target)+' target</span></div>'+(x.done?'':'<button class="add" data-add="'+x.id+'">＋ Add</button>')+'</div></div>'
  });
  return h
}
function detail(g){
  var h='<div class="bar"><button class="ib" data-a="back">←</button><span class="sp"></span><button class="ib" data-edit="'+g.id+'">✎</button><button class="ib pur" data-add="'+g.id+'">＋</button></div>';
  h+='<div class="card">'+cover(g)+'<div class="cb"><div class="row"><span class="nm">'+esc(g.name)+(g.done?'<span class="badge">Completed</span>':'')+'</span><span class="pct">'+Math.floor(pct(g))+'%</span></div><div class="pb"><i style="width:'+pct(g)+'%"></i></div><div class="row sm"><span>'+money(saved(g))+' saved</span><span>'+money(g.target)+' target</span></div></div></div>';
  h+='<div class="info"><div class="sm">📅 Savings frequency <b style="color:var(--ink)">'+FREQ[g.freq||"none"]+'</b></div><div class="sm">🔔 Reminder <b style="color:var(--ink)">'+(g.remind?esc(g.remind):"ปิด")+'</b></div></div>';
  h+='<div class="row" style="align-items:center"><h3>Recent contributions</h3>'+(g.done?'':'<button class="pur" style="font-size:17px;padding:8px" data-add="'+g.id+'">＋ Add</button>')+'</div>';
  var tx=(g.txs||[]).slice().sort(function(a,b){return b.date.localeCompare(a.date)||b.id.localeCompare(a.id)});
  if(!tx.length)h+='<div class="empty" style="padding:24px">ยังไม่มีรายการ</div>';
  tx.forEach(function(t){h+='<div class="tx"><div><div>'+(t.amt<0?"Withdrawal":"Contribution")+'</div><small>'+fdate(t.date)+(t.note?' · '+esc(t.note):'')+'</small></div><div style="display:flex;align-items:center;gap:6px"><span class="a'+(t.amt<0?' w':'')+'">'+(t.amt<0?'−':'')+money(Math.abs(t.amt))+'</span><button class="x" data-del="'+t.id+'">✕</button></div></div>'});
  h+='<button class="done" data-a="toggledone">'+(g.done?'↺ Reopen goal':'✓ Mark as completed')+'</button>';
  return h
}
function openSheet(html){$("sh").innerHTML=html;$("ov").style.display="block";$("sh").classList.add("on")}
function closeSheet(){$("ov").style.display="none";$("sh").classList.remove("on");$("sh").innerHTML=""}
$("ov").addEventListener("click",closeSheet);

var wd=false;
function addSheet(id){
  wd=false;
  var g=find(id);
  openSheet('<div class="sh-h"><button class="ib" data-s="close">✕</button><h2>Add to '+esc(g.name)+'</h2><span style="width:44px"></span></div><label>Amount</label><input id="amt" class="big" type="text" inputmode="decimal" placeholder="0" autocomplete="off"><div class="chips"><button class="chip" data-q="10">+฿10</button><button class="chip" data-q="50">+฿50</button><button class="chip" data-q="100">+฿100</button><button class="chip" id="wdb" data-s="wd">Withdraw</button></div><label>Date</label><input id="dt" class="soft" type="date" value="'+today()+'"><label>Note (optional)</label><textarea id="nt" class="soft" placeholder="e.g. Birthday money"></textarea><button class="btn" data-s="savetx" data-id="'+id+'">Save</button>')
}
function goalSheet(id){
  var g=id?find(id):{name:"",target:"",freq:"daily",remind:"19:00",img:""};
  openSheet('<div class="sh-h"><button class="ib" data-s="close">✕</button><h2>'+(id?"Edit goal":"New goal")+'</h2><span style="width:44px"></span></div><label>ชื่อเป้าหมาย</label><input id="gn" value="'+esc(g.name)+'" placeholder="เช่น เที่ยวญี่ปุ่น"><label>เป้าหมาย (฿)</label><input id="gt" type="text" inputmode="decimal" value="'+esc(g.target)+'" placeholder="100000"><div class="two"><div><label>Frequency</label><select id="gf">'+Object.keys(FREQ).map(function(k){return'<option value="'+k+'"'+(g.freq===k?' selected':'')+'>'+FREQ[k]+'</option>'}).join("")+'</select></div><div><label>Reminder</label><input id="gr" class="soft" type="time" value="'+esc(g.remind||"")+'"></div></div><label>รูปปก</label><div class="prev" id="pv" style="'+(g.img?'background-image:url('+g.img+')':'')+'"></div><input id="gi" type="file" accept="image/*" style="display:none"><div class="two"><button class="btn s" data-s="pick">เลือกรูป</button><button class="btn s" data-s="noimg">ลบรูป</button></div><button class="btn" data-s="savegoal" data-id="'+(id||"")+'">Save</button>'+(id?'<button class="btn g" data-s="delgoal" data-id="'+id+'">ลบเป้าหมายนี้</button>':''));
  var cur=g.img||"";window._img=cur;
  $("gi").onchange=function(e){
    var f=e.target.files[0];if(!f)return;
    var fr=new FileReader();
    fr.onload=function(){var im=new Image();im.onload=function(){
      var s=Math.min(1,800/Math.max(im.width,im.height)),c=document.createElement("canvas");
      c.width=Math.round(im.width*s);c.height=Math.round(im.height*s);
      c.getContext("2d").drawImage(im,0,0,c.width,c.height);
      window._img=c.toDataURL("image/jpeg",.78);$("pv").style.backgroundImage="url("+window._img+")"};im.src=fr.result};
    fr.readAsDataURL(f)
  }
}
function num(v){var n=parseFloat(String(v).replace(/,/g,""));return isFinite(n)?n:0}

document.addEventListener("click",function(e){
  var t=e.target.closest("[data-a],[data-open],[data-add],[data-edit],[data-del],[data-s],[data-q]");if(!t)return;
  var d=t.dataset;
  if(d.add){e.stopPropagation();addSheet(d.add);return}
  if(d.edit){goalSheet(d.edit);return}
  if(d.del){var g=find(view);if(g&&confirm("ลบรายการนี้?")){g.txs=g.txs.filter(function(x){return x.id!==d.del});save();render()}return}
  if(d.open){view=d.open;history.pushState({v:1},"");render();return}
  if(d.q){var i=$("amt");i.value=String(num(i.value)+num(d.q));return}
  if(d.a){
    if(d.a==="back"){history.back()}
    if(d.a==="newgoal")goalSheet(null);
    if(d.a==="sort"){sortMode=(sortMode+1)%3;render();toast(["เรียงตามที่สร้าง","เรียงตามความคืบหน้า","เรียงตามชื่อ"][sortMode])}
    if(d.a==="compact"){compact=!compact;render()}
    if(d.a==="toggledone"){var g2=find(view);g2.done=!g2.done;save();render()}
    if(d.a==="settings")openSheet('<div class="sh-h"><button class="ib" data-s="close">✕</button><h2>Settings</h2><span style="width:44px"></span></div><label>สำรอง / กู้คืนข้อมูล</label><textarea id="bk" class="soft" style="min-height:140px;font-size:13px">'+esc(JSON.stringify(S))+'</textarea><button class="btn s" data-s="copy">คัดลอกข้อมูลสำรอง</button><button class="btn s" data-s="import">กู้คืนจากข้อความด้านบน</button><p class="sm" style="padding:0 4px">ข้อมูลเก็บในเครื่องนี้เท่านั้น ควรคัดลอกเก็บไว้เป็นระยะ</p>');
    return
  }
  if(d.s){
    var s=d.s;
    if(s==="close")closeSheet();
    if(s==="wd"){wd=!wd;t.classList.toggle("sel",wd)}
    if(s==="savetx"){
      var a=num($("amt").value);if(a<=0){toast("ใส่จำนวนเงินก่อน");return}
      var g3=find(d.id);g3.txs.push({id:uid(),amt:wd?-a:a,date:$("dt").value||today(),note:$("nt").value.trim()});
      save();closeSheet();render();toast(wd?"ถอนแล้ว":"บันทึกแล้ว")
    }
    if(s==="pick")$("gi").click();
    if(s==="noimg"){window._img="";$("pv").style.backgroundImage="none"}
    if(s==="savegoal"){
      var n=$("gn").value.trim(),tg=num($("gt").value);
      if(!n){toast("ใส่ชื่อเป้าหมาย");return}
      if(tg<=0){toast("ใส่จำนวนเป้าหมาย");return}
      var o=d.id?find(d.id):{id:uid(),txs:[],done:false};
      o.name=n;o.target=tg;o.freq=$("gf").value;o.remind=$("gr").value;o.img=window._img||"";
      if(!d.id)S.goals.push(o);
      save();closeSheet();render()
    }
    if(s==="delgoal"&&confirm("ลบเป้าหมายและรายการทั้งหมด?")){S.goals=S.goals.filter(function(x){return x.id!==d.id});save();closeSheet();if(view){view=null;history.back()}render()}
    if(s==="copy"){var ta=$("bk");ta.select();try{navigator.clipboard.writeText(ta.value)}catch(x){document.execCommand("copy")}toast("คัดลอกแล้ว")}
    if(s==="import"){try{var j=JSON.parse($("bk").value);if(!j.goals)throw 0;S=j;save();closeSheet();view=null;render();toast("กู้คืนแล้ว")}catch(x){toast("ข้อมูลไม่ถูกต้อง")}}
  }
});
window.addEventListener("popstate",function(){if($("sh").classList.contains("on"))closeSheet();view=null;render()});
render();
})();
</script>
</body>
</html>