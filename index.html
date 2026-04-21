<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta charset="UTF-8">
<title>Wipro Tracker - Fixed Version</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">

<script src="https://cdn.sheetjs.com/xlsx-0.20.2/package/dist/xlsx.full.min.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-database-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-auth-compat.js"></script>

<style>
body { font-family: Poppins; background:#f5f6fa; padding:20px;}
h1{text-align:center;}
table{width:100%;border-collapse:collapse;margin-top:20px;background:#fff;}
th,td{border:1px solid #ddd;padding:8px;text-align:center;}
th{background:#2ecc71;color:white;}
button{padding:8px 15px;margin:5px;cursor:pointer;}
</style>
</head>

<body>

<h1>📊 Wipro Tracker (Fixed)</h1>

<select id="monthDropdown"></select>

<div>
<button onclick="addRow()">Add Row</button>
<button onclick="saveData()">Save</button>
<button onclick="exportExcel()">Export Excel</button>
</div>

<table>
<thead>
<tr>
<th>#</th>
<th>Name</th>
<th>Date</th>
<th>Payment</th>
</tr>
</thead>

<tbody id="tbody"></tbody>

<tfoot>
<tr>
<td colspan="3"><b>Total</b></td>
<td id="total">0</td>
</tr>
</tfoot>

</table>

<script>
// ================= FIREBASE =================
const firebaseConfig = {
apiKey: "AIzaSyA0ze6n4ERhn4Bi6_PT6bA3z3h9NOEc_5M",
authDomain: "wipro-tracker-bdc7d.firebaseapp.com",
databaseURL: "https://wipro-tracker-bdc7d-default-rtdb.asia-southeast1.firebasedatabase.app/",
projectId: "wipro-tracker-bdc7d",
};

firebase.initializeApp(firebaseConfig);
const db = firebase.database();

// ================= GLOBAL =================
let currentMonth = "";
let data = [];

// ================= MONTH =================
function loadMonths(){
const months = ["Mar 2026","Apr 2026","May 2026","Jun 2026"];
const dd = document.getElementById("monthDropdown");

dd.innerHTML = months.map(m=>`<option>${m}</option>`).join("");
currentMonth = months[0];
loadData();
}

document.getElementById("monthDropdown").onchange = function(){
currentMonth = this.value;
loadData();
};

// ================= TABLE =================
function render(){
const tb = document.getElementById("tbody");
tb.innerHTML = "";

data.forEach((row,i)=>{
const tr = document.createElement("tr");

tr.innerHTML = `
<td>${i+1}</td>
<td><input value="${row.name}" onchange="update(${i},'name',this.value)"></td>
<td><input type="date" value="${row.date}" onchange="update(${i},'date',this.value)"></td>
<td><input type="number" value="${row.payment}" onchange="update(${i},'payment',this.value)"></td>
`;

tb.appendChild(tr);
});

calcTotal();
}

function update(i,key,val){
data[i][key]=val;
calcTotal();
}

function calcTotal(){
let t=0;
data.forEach(r=> t += Number(r.payment||0));
document.getElementById("total").innerText = t;
}

// ================= CRUD =================
function addRow(){
data.push({name:"",date:"",payment:0});
render();
}

function saveData(){
db.ref("tracker/"+currentMonth).set(data);
localStorage.setItem(currentMonth,JSON.stringify(data));
alert("Saved!");
}

async function loadData(){
let local = localStorage.getItem(currentMonth);

if(local){
data = JSON.parse(local);
render();
}else{
const snap = await db.ref("tracker/"+currentMonth).once("value");
data = snap.val() || [];
render();
}
}

// ================= EXPORT =================
function exportExcel(){
const ws = XLSX.utils.json_to_sheet(data);
const wb = XLSX.utils.book_new();
XLSX.utils.book_append_sheet(wb,ws,"Sheet1");
XLSX.writeFile(wb,"tracker.xlsx");
}

// ================= INIT =================
loadMonths();
</script>

</body>
</html>
