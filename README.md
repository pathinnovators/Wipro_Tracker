<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Wipro Tracker - Fixed</title>

<style>
body { font-family: Arial; background:#f5f5f5; padding:20px; }
table { width:100%; border-collapse: collapse; background:white; margin-bottom:20px; }
th,td { border:1px solid #ddd; padding:8px; text-align:center; }
th { background:#067d28; color:white; }
input,select { width:100%; padding:5px; }

.section { margin-bottom:25px; }
</style>
</head>

<body>

<h2>📊 WIPRO TRACKER</h2>

<select id="monthDropdown" onchange="calculateSummary()">
<option>Mar 2026</option>
<option>Apr 2026</option>
<option>May 2026</option>
<option>Jun 2026</option>
</select>

<!-- SUMMARY -->
<div class="section">
<h3>📅 Monthly Summary</h3>
<table>
<tr><td>Total Candidates</td><td id="sum_candidates">0</td></tr>
<tr><td>Offer Released</td><td id="sum_offerReleased">0</td></tr>
<tr><td>Offer Pending</td><td id="sum_offerPending">0</td></tr>
<tr><td>Total Profile Payment</td><td id="sum_profilePayment">₹0</td></tr>
<tr><td>Total Advance</td><td id="sum_advance">₹0</td></tr>
<tr><td>Total Paid</td><td id="sum_paid">₹0</td></tr>
<tr><td>Pending</td><td id="sum_pending">₹0</td></tr>
</table>
</div>

<!-- CANDIDATES -->
<div class="section">
<h3>👥 Candidates</h3>
<table id="candidateTable">
<thead>
<tr>
<th>Name</th><th>Date</th><th>Status</th><th>Payment</th>
</tr>
</thead>
<tbody></tbody>
</table>
<button onclick="addCandidate()">Add Row</button>
</div>

<!-- ADVANCE -->
<div class="section">
<h3>💰 Advance</h3>
<table id="advanceTable">
<thead>
<tr>
<th>Amount</th><th>Date</th>
</tr>
</thead>
<tbody></tbody>
</table>
<button onclick="addAdvance()">Add Row</button>
</div>

<!-- PAYMENT -->
<div class="section">
<h3>💳 Payments</h3>
<table id="paymentTable">
<thead>
<tr>
<th>Amount</th><th>Date</th>
</tr>
</thead>
<tbody></tbody>
</table>
<button onclick="addPayment()">Add Row</button>
</div>

<script>

// SAFE NUMBER
function num(v){ return parseFloat(v)||0; }

// MONTH CHECK
function isSameMonth(dateStr, selectedMonth){
 if(!dateStr) return false;
 const d=new Date(dateStr);
 const m=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
 return `${m[d.getMonth()]} ${d.getFullYear()}`===selectedMonth;
}

// COLLECT DATA
function getCandidates(){
 let data=[];
 document.querySelectorAll("#candidateTable tbody tr").forEach(tr=>{
   let t=tr.querySelectorAll("input,select");
   data.push({
     date:t[1].value,
     status:t[2].value,
     pay:t[3].value
   });
 });
 return data;
}

function getAdvance(){
 let data=[];
 document.querySelectorAll("#advanceTable tbody tr").forEach(tr=>{
   let t=tr.querySelectorAll("input");
   data.push({ amt:t[0].value, date:t[1].value });
 });
 return data;
}

function getPayment(){
 let data=[];
 document.querySelectorAll("#paymentTable tbody tr").forEach(tr=>{
   let t=tr.querySelectorAll("input");
   data.push({ amt:t[0].value, date:t[1].value });
 });
 return data;
}

// MAIN CALCULATION
function calculateSummary(){

 let month=document.getElementById("monthDropdown").value;

 let candidates=getCandidates().filter(c=>isSameMonth(c.date,month));
 let advances=getAdvance().filter(a=>isSameMonth(a.date,month));
 let payments=getPayment().filter(p=>isSameMonth(p.date,month));

 let totalCandidates=candidates.length;

 let offerReleased=0, offerPending=0, profile=0;

 candidates.forEach(c=>{
   if(c.status==="Offer Released"){
     offerReleased++;
     profile+=num(c.pay);
   }
   if(c.status==="Offer Pending"){
     offerPending++;
   }
 });

 let advance=advances.reduce((s,a)=>s+num(a.amt),0);
 let paid=payments.reduce((s,p)=>s+num(p.amt),0);

 let pending=profile-paid;

 // UPDATE UI
 document.getElementById("sum_candidates").innerText=totalCandidates;
 document.getElementById("sum_offerReleased").innerText=offerReleased;
 document.getElementById("sum_offerPending").innerText=offerPending;
 document.getElementById("sum_profilePayment").innerText="₹"+profile;
 document.getElementById("sum_advance").innerText="₹"+advance;
 document.getElementById("sum_paid").innerText="₹"+paid;
 document.getElementById("sum_pending").innerText="₹"+pending;
}

// ADD ROWS
function addCandidate(){
 let tr=document.createElement("tr");
 tr.innerHTML=`
<td><input></td>
<td><input type="date" onchange="calculateSummary()"></td>
<td>
<select onchange="calculateSummary()">
<option>Offer Released</option>
<option>Offer Pending</option>
</select>
</td>
<td><input type="number" oninput="calculateSummary()"></td>`;
 document.querySelector("#candidateTable tbody").appendChild(tr);
}

function addAdvance(){
 let tr=document.createElement("tr");
 tr.innerHTML=`
<td><input type="number" oninput="calculateSummary()"></td>
<td><input type="date" onchange="calculateSummary()"></td>`;
 document.querySelector("#advanceTable tbody").appendChild(tr);
}

function addPayment(){
 let tr=document.createElement("tr");
 tr.innerHTML=`
<td><input type="number" oninput="calculateSummary()"></td>
<td><input type="date" onchange="calculateSummary()"></td>`;
 document.querySelector("#paymentTable tbody").appendChild(tr);
}

// INIT
addCandidate(); addCandidate();
addAdvance();
addPayment();

</script>

</body>
</html>
