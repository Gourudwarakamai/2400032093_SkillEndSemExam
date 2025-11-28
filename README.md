# 2400032093_SkillEndSemExam
<html><body>
<h3>Notes</h3>
<input id="t"><br><br>
<textarea id="c"></textarea><br><br>
<button onclick="s()">Save</button>
<ul id="l"></ul>

<script>
let n=JSON.parse(localStorage.n||"[]"),e=-1;

function d(){
 l.innerHTML="";
 n.map((x,i)=>l.innerHTML+=`<li><b>${x.t}</b>:${x.c}
 <button onclick="E(${i})">Edit</button>
 <button onclick="R(${i})">Del</button></li>`);
}

function s(){
 let t=t.value,c=c.value;
 e>-1?n[e]={t,c}:n.push({t,c});
 e=-1; localStorage.n=JSON.stringify(n);
 t.value=c.value=""; d();
}

function E(i){ e=i; t.value=n[i].t; c.value=n[i].c; }
function R(i){ n.splice(i,1); localStorage.n=JSON.stringify(n); d(); }

d();
</script>
</body></html>
