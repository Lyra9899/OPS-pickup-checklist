# OPS-pickup-checklist
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="mobile-web-app-capable" content="yes">
<title>CSPADT Pickup Inspection Checklist</title>

<style>
*{box-sizing:border-box}

body{
  margin:0;
  background:#eef1f4;
  color:#18212b;
  font-family:Arial,Helvetica,sans-serif;
}

.wrap{
  max-width:980px;
  margin:16px auto;
  padding:10px;
}

.card{
  background:#fff;
  border:1px solid #d5dce2;
  border-radius:14px;
  box-shadow:0 3px 14px rgba(0,0,0,.08);
  overflow:hidden;
}

.header{
  text-align:center;
  padding:16px 12px 10px;
  border-bottom:1px solid #d9dfe4;
}

.logo{
  max-width:270px;
  max-height:90px;
  object-fit:contain;
  margin-bottom:8px;
}

h1{
  margin:5px 0 2px;
  font-size:23px;
  color:#17365d;
}

.subtitle{
  font-size:13px;
  color:#5b6570;
}

.section{
  padding:14px 16px;
  border-bottom:1px solid #e1e5e8;
}

.section-title{
  font-size:16px;
  font-weight:700;
  color:#17365d;
  margin-bottom:11px;
}

.grid{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:12px;
}

.field{
  display:flex;
  flex-direction:column;
  gap:5px;
}

label{
  font-size:13px;
  font-weight:700;
  color:#303b45;
}

input,
select,
textarea{
  width:100%;
  min-height:44px;
  padding:10px 11px;
  border:1px solid #bfc8d0;
  border-radius:8px;
  background:#fff;
  color:#17212b;
  font-size:16px;
  outline:none;
}

input:focus,
select:focus,
textarea:focus{
  border-color:#4677a8;
  box-shadow:0 0 0 2px rgba(70,119,168,.12);
}

input[readonly]{
  background:#f2f5f7;
}

textarea{
  min-height:80px;
  resize:vertical;
}

.required{
  color:#c62828;
}

.mileage-row{
  display:grid;
  grid-template-columns:1fr 1fr 1fr;
  gap:10px;
}

.mileage-box{
  border:1px solid #bfc8d0;
  border-radius:9px;
  padding:9px;
  background:#f8fafb;
}

.mileage-box label{
  display:block;
  margin-bottom:5px;
}

.mileage-result{
  background:#e9f5e9 !important;
  border:2px solid #4f8a4f !important;
  font-weight:700;
  color:#245c24 !important;
}

.warning{
  display:none;
  margin-top:10px;
  padding:10px 12px;
  border-radius:8px;
  background:#fff1f1;
  border:1px solid #d9534f;
  color:#a12622;
  font-weight:700;
  font-size:14px;
}

.success{
  display:none;
  margin-top:10px;
  padding:10px 12px;
  border-radius:8px;
  background:#edf8ed;
  border:1px solid #6ca66c;
  color:#286228;
  font-weight:700;
}

.lookup-row{
  display:grid;
  grid-template-columns:1fr auto;
  gap:8px;
  align-items:end;
}

.mobileLookup{
  display:none;
  min-height:44px;
}

.checklist{
  width:100%;
  border-collapse:collapse;
  font-size:13px;
}

.checklist th,
.checklist td{
  border:1px solid #cfd6dc;
  padding:8px;
  vertical-align:middle;
}

.checklist th{
  background:#edf2f6;
  color:#17365d;
  text-align:left;
}

.checklist td:first-child{
  width:62%;
}

.check-options{
  white-space:nowrap;
  text-align:center;
}

.check-options label{
  font-weight:normal;
  margin:0 7px 0 0;
  font-size:13px;
}

.check-options input{
  width:auto;
  min-height:auto;
  margin-right:3px;
  vertical-align:middle;
}

.actions{
  display:flex;
  flex-wrap:wrap;
  gap:9px;
  padding:15px 16px;
  background:#f7f9fa;
}

button{
  border:0;
  border-radius:8px;
  padding:11px 16px;
  min-height:44px;
  font-size:15px;
  font-weight:700;
  cursor:pointer;
  background:#17365d;
  color:white;
}

button.secondary{
  background:#64727e;
}

button.green{
  background:#357a38;
}

button.orange{
  background:#a86600;
}

button.red{
  background:#a52d2d;
}

.note{
  padding:10px 16px 15px;
  font-size:12px;
  color:#68737d;
  line-height:1.45;
}

.footer{
  text-align:center;
  padding:10px;
  font-size:11px;
  color:#7b858e;
}

.print-only{
  display:none;
}

@media(max-width:700px){

  .wrap{
    margin:0;
    padding:0;
  }

  .card{
    border-radius:0;
    border-left:0;
    border-right:0;
  }

  .header{
    padding:13px 10px 9px;
  }

  .logo{
    max-width:230px;
    max-height:75px;
  }

  h1{
    font-size:20px;
  }

  .section{
    padding:12px 10px;
  }

  .grid{
    grid-template-columns:1fr;
    gap:10px;
  }

  .lookup-row{
    grid-template-columns:1fr auto;
  }

  .mobileLookup{
    display:block;
  }

  .mileage-row{
    grid-template-columns:1fr;
    gap:9px;
  }

  input,
  select,
  textarea{
    min-height:48px;
    font-size:17px;
  }

  button{
    min-height:48px;
    flex:1 1 100%;
    font-size:16px;
  }

  .actions{
    padding:12px 10px;
  }

  .checklist{
    font-size:12px;
  }

  .checklist th,
  .checklist td{
    padding:6px;
  }

  .check-options label{
    margin-right:4px;
  }
}

@media print{

  @page{
    size:A4;
    margin:7mm;
  }

  body{
    background:#fff;
    font-size:9px;
  }

  .wrap{
    max-width:none;
    margin:0;
    padding:0;
  }

  .card{
    border:0;
    box-shadow:none;
    border-radius:0;
  }

  .header{
    padding:4px 0 5px;
  }

  .logo{
    max-width:170px;
    max-height:48px;
    margin-bottom:2px;
  }

  h1{
    font-size:15px;
    margin:2px 0;
  }

  .subtitle{
    font-size:8px;
  }

  .section{
    padding:5px 0;
    border-bottom:1px solid #aaa;
  }

  .section-title{
    font-size:10px;
    margin-bottom:4px;
  }

  .grid{
    gap:5px;
  }

  .field{
    gap:2px;
  }

  label{
    font-size:8px;
  }

  input,
  select,
  textarea{
    min-height:22px;
    padding:3px 5px;
    font-size:9px;
    border-radius:3px;
  }

  textarea{
    min-height:35px;
  }

  .mileage-row{
    grid-template-columns:1fr 1fr 1fr;
    gap:5px;
  }

  .mileage-box{
    padding:4px;
    border-radius:3px;
  }

  .mileage-box label{
    margin-bottom:2px;
  }

  .checklist{
    font-size:7.5px;
  }

  .checklist th,
  .checklist td{
    padding:3px;
  }

  .check-options label{
    font-size:7px;
  }

  .warning,
  .success{
    margin-top:4px;
    padding:4px 6px;
    font-size:8px;
  }

  .actions,
  .note{
    display:none !important;
  }

  .footer{
    padding:3px;
    font-size:7px;
  }

  .print-only{
    display:block;
  }

  input[type="radio"],
  input[type="checkbox"]{
    min-height:auto;
  }
}
</style>
</head>

<body>

<div class="wrap">

<div class="card">

<div class="header">

<!-- CSP TERMINAL LOGO -->
<img
class="logo"
alt="CSP Abu Dhabi Terminal"
src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAA..."
>

<h1>CSPADT Pickup Inspection Checklist</h1>
<div class="subtitle">
Terminal Operations – Pickup Vehicle Daily Inspection
</div>

</div>


<!-- STAFF DETAILS -->
<div class="section">

<div class="section-title">
1. Staff & Duty Details
</div>

<div class="grid">

<div class="field">

<label>
Employee ID <span class="required">*</span>
</label>

<div class="lookup-row">

<input
id="employeeId"
inputmode="numeric"
maxlength="3"
autocomplete="off"
autocapitalize="none"
placeholder="Enter / paste ID, e.g. 107"
oninput="lookupEmployee()"
onkeyup="lookupEmployee()"
onblur="lookupEmployee()"
>

<button
type="button"
class="secondary mobileLookup"
onclick="lookupEmployee(true)"
>
Fetch Name
</button>

</div>

</div>


<div class="field">

<label>
Employee Name
</label>

<input
id="employeeName"
readonly
placeholder="Name will appear automatically"
>

</div>


<div class="field">

<label>
Date <span class="required">*</span>
</label>

<input
id="date"
type="date"
>

</div>


<div class="field">

<label>
Shift <span class="required">*</span>
</label>

<select id="shift">

<option value="">Select Shift</option>
<option value="Day">Day</option>
<option value="Night">Night</option>

</select>

</div>

</div>

</div>


<!-- PICKUP DETAILS -->
<div class="section">

<div class="section-title">
2. Pickup Details
</div>

<div class="grid">

<div class="field">

<label>
Pickup Number <span class="required">*</span>
</label>

<select id="pickupNumber" onchange="toggleOtherPickup()">

<option value="">Select Pickup</option>
<option value="56436">56436 – OPS Pickup 1</option>
<option value="56434">56434 – OPS Pickup 2</option>
<option value="Other">Other – Replacement Pickup</option>

</select>

</div>


<div
class="field"
id="otherPickupField"
style="display:none"
>

<label>
Other / Replacement Pickup Number
</label>

<input
id="otherPickup"
inputmode="numeric"
placeholder="Enter pickup number"
>

</div>

</div>

</div>


<!-- MILEAGE -->
<div class="section">

<div class="section-title">
3. Mileage
</div>

<div class="mileage-row">

<div class="mileage-box">

<label>
Beginning Mileage (km) <span class="required">*</span>
</label>

<input
id="beginMileage"
type="number"
inputmode="decimal"
min="0"
step="0.1"
placeholder="e.g. 12353.0"
oninput="calculateMileage()"
onchange="calculateMileage()"
onblur="calculateMileage()"
>

</div>


<div class="mileage-box">

<label>
Ending Mileage (km) <span class="required">*</span>
</label>

<input
id="endMileage"
type="number"
inputmode="decimal"
min="0"
step="0.1"
placeholder="e.g. 12357.4"
oninput="calculateMileage()"
onchange="calculateMileage()"
onblur="calculateMileage()"
>

</div>


<div class="mileage-box">

<label>
Mileage Run (km)
</label>

<input
id="mileageRun"
class="mileage-result"
readonly
placeholder="Auto calculated"
>

</div>

</div>


<div
id="mileageWarning"
class="warning"
>
⚠️ Mileage run exceeds 100 km. Please verify the reading and inform the supervisor.
</div>

</div>


<!-- FUEL -->
<div class="section">

<div class="section-title">
4. Fuel Details
</div>

<div class="grid">

<div class="field">

<label>
Fuel Filled?
</label>

<select
id="fuelFilled"
onchange="toggleFuelQuantity()"
>

<option value="">Select</option>
<option value="No">No</option>
<option value="Yes">Yes</option>

</select>

</div>


<div
class="field"
id="fuelQuantityField"
style="display:none"
>

<label>
Fuel Quantity (L)
</label>

<input
id="fuelQuantity"
type="number"
inputmode="decimal"
min="0"
step="0.1"
placeholder="Enter quantity in litres"
>

</div>

</div>

</div>


<!-- INSPECTION -->
<div class="section">

<div class="section-title">
5. Pickup Inspection
</div>

<table class="checklist">

<thead>

<tr>

<th>Inspection Item</th>

<th>Condition</th>

</tr>

</thead>

<tbody>

<tr>
<td>Tyres – condition, pressure and visible damage</td>
<td class="check-options">
<label><input type="radio" name="q1" value="OK"> OK</label>
<label><input type="radio" name="q1" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Lights – headlights, brake lights and indicators</td>
<td class="check-options">
<label><input type="radio" name="q2" value="OK"> OK</label>
<label><input type="radio" name="q2" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Brakes – normal operation</td>
<td class="check-options">
<label><input type="radio" name="q3" value="OK"> OK</label>
<label><input type="radio" name="q3" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Horn – working condition</td>
<td class="check-options">
<label><input type="radio" name="q4" value="OK"> OK</label>
<label><input type="radio" name="q4" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Mirrors – clean and properly adjusted</td>
<td class="check-options">
<label><input type="radio" name="q5" value="OK"> OK</label>
<label><input type="radio" name="q5" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Seat belts – available and functioning</td>
<td class="check-options">
<label><input type="radio" name="q6" value="OK"> OK</label>
<label><input type="radio" name="q6" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Body / external condition – no new visible damage</td>
<td class="check-options">
<label><input type="radio" name="q7" value="OK"> OK</label>
<label><input type="radio" name="q7" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Windscreen / windows – clean and no visible damage</td>
<td class="check-options">
<label><input type="radio" name="q8" value="OK"> OK</label>
<label><input type="radio" name="q8" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>Warning lights / dashboard – no abnormal indication</td>
<td class="check-options">
<label><input type="radio" name="q9" value="OK"> OK</label>
<label><input type="radio" name="q9" value="Not OK"> Not OK</label>
</td>
</tr>

<tr>
<td>General vehicle condition – suitable for operation</td>
<td class="check-options">
<label><input type="radio" name="q10" value="OK"> OK</label>
<label><input type="radio" name="q10" value="Not OK"> Not OK</label>
</td>
</tr>

</tbody>

</table>

</div>


<!-- REMARKS -->
<div class="section">

<div class="section-title">
6. Remarks / Defects
</div>

<div class="field">

<textarea
id="remarks"
placeholder="Mention any defect, damage, abnormal condition or other remarks..."
></textarea>

</div>

</div>


<!-- ACKNOWLEDGEMENT -->
<div class="section">

<div class="section-title">
7. Driver Acknowledgement
</div>

<label
style="font-weight:normal;font-size:14px;display:flex;gap:8px;align-items:flex-start;"
>

<input
id="acknowledgement"
type="checkbox"
style="width:auto;min-height:auto;margin-top:3px;"
>

<span>
I confirm that the above pickup inspection has been completed and the information provided is correct.
</span>

</label>

<div
id="submitMessage"
class="success"
>
✓ Checklist is ready. Please use Print / Save PDF and send the completed file to Operations through WhatsApp.
</div>

</div>


<!-- ACTIONS -->
<div class="actions">

<button
type="button"
class="green"
onclick="submitChecklist()"
>
✓ Submit Checklist
</button>


<button
type="button"
onclick="window.print()"
>
📄 Print / Save PDF
</button>


<button
type="button"
class="secondary"
onclick="saveProgress()"
>
💾 Save Progress
</button>


<button
type="button"
class="secondary"
onclick="loadProgress()"
>
↩ Load Saved Progress
</button>


<button
type="button"
class="red"
onclick="clearForm()"
>
✕ Clear Form
</button>

</div>


<div class="note">

<strong>Note:</strong>
Complete the inspection before operating the pickup.
If any defect is identified, inform the supervisor and do not operate the vehicle until the issue is addressed.

</div>


<div class="footer">

CSP Abu Dhabi Terminal – Operations Department

</div>

</div>

</div>


<script>

const STAFF = {

"107":"Suresh Valiya Parambil Kumaran",
"116":"Mohammed Mansoor",
"099":"Sivan Pillai Lalu Sivan Pillai",
"100":"Mohandoss Athisekaran Athisekaran",
"156":"Sanalkumar Sreekantan Nair",
"031":"Yohanan Johnson John",
"209":"Mohamed Waheed Ghanem Alhashmi",
"082":"Muraleedharan Ramanezath Gopinathamenon",
"147":"Mohamad Hamoud Ahmed",
"045":"Thangamari Chandran"

};


function el(id){

return document.getElementById(id);

}


function lookupEmployee(showAlert){

const input = el("employeeId");

if(!input) return;

let id = input.value
.replace(/\s+/g,"")
.trim();

if(!id){

el("employeeName").value="";

return;

}

if(/^\d+$/.test(id)){

id = id.padStart(3,"0");

input.value = id;

}

const name = STAFF[id];

if(name){

el("employeeName").value = name;

}else{

el("employeeName").value = "";

if(showAlert){

alert(
"Employee ID not found.\nPlease check the ID and try again."
);

}

}

}


function calculateMileage(){

const begin = parseFloat(el("beginMileage").value);
const end = parseFloat(el("endMileage").value);
const result = el("mileageRun");
const warning = el("mileageWarning");

if(
Number.isFinite(begin) &&
Number.isFinite(end)
){

const run = end - begin;

if(run >= 0){

result.value = run.toFixed(1);

if(run > 100){

warning.style.display = "block";

}else{

warning.style.display = "none";

}

}else{

result.value = "";

warning.style.display = "none";

}

}else{

result.value = "";

warning.style.display = "none";

}

}


function toggleOtherPickup(){

const value = el("pickupNumber").value;
const field = el("otherPickupField");

if(value === "Other"){

field.style.display = "flex";

}else{

field.style.display = "none";
el("otherPickup").value = "";

}

}


function toggleFuelQuantity(){

const value = el("fuelFilled").value;
const field = el("fuelQuantityField");

if(value === "Yes"){

field.style.display = "flex";

}else{

field.style.display = "none";
el("fuelQuantity").value = "";

}

}


function submitChecklist(){

lookupEmployee(false);
calculateMileage();

const employeeId = el("employeeId").value.trim();
const employeeName = el("employeeName").value.trim();
const date = el("date").value;
const shift = el("shift").value;
const pickup = el("pickupNumber").value;
const begin = el("beginMileage").value;
const end = el("endMileage").value;
const ack = el("acknowledgement").checked;

if(!employeeId){

alert("Please enter Employee ID.");

el("employeeId").focus();

return;

}

if(!employeeName){

alert("Please enter a valid Employee ID.");

el("employeeId").focus();

return;

}

if(!date){

alert("Please select the date.");

return;

}

if(!shift){

alert("Please select the shift.");

return;

}

if(!pickup){

alert("Please select the pickup number.");

return;

}

if(pickup === "Other" &&
!el("otherPickup").value.trim()
){

alert("Please enter the replacement pickup number.");

el("otherPickup").focus();

return;

}

if(
begin === "" ||
end === ""
){

alert("Please enter beginning and ending mileage.");

return;

}

const beginValue = parseFloat(begin);
const endValue = parseFloat(end);

if(endValue < beginValue){

alert(
"Ending mileage cannot be less than beginning mileage."
);

return;

}

const radios = [
"q1","q2","q3","q4","q5",
"q6","q7","q8","q9","q10"
];

for(const q of radios){

if(!document.querySelector(
'input[name="'+q+'"]:checked'
)){

alert("Please complete all inspection items.");

return;

}

}

if(!ack){

alert(
"Please confirm the acknowledgement before submitting."
);

return;

}

el("submitMessage").style.display = "block";

window.scrollTo({
top:document.body.scrollHeight,
behavior:"smooth"
});

}


function saveProgress(){

const data = {};

document.querySelectorAll(
"input, select, textarea"
).forEach(function(field){

if(field.type === "radio"){

data[field.name] =
document.querySelector(
'input[name="'+field.name+'"]:checked'
)?.value || "";

}

else if(field.type === "checkbox"){

data[field.id] = field.checked;

}

else{

data[field.id] = field.value;

}

});

localStorage.setItem(
"CSPADT_Pickup_Checklist_V5",
JSON.stringify(data)
);

alert(
"Progress saved on this device."
);

}


function loadProgress(){

const saved = localStorage.getItem(
"CSPADT_Pickup_Checklist_V5"
);

if(!saved){

alert("No saved progress found on this device.");

return;

}

const data = JSON.parse(saved);

Object.keys(data).forEach(function(key){

const field = el(key);

if(!field) return;

if(field.type === "checkbox"){

field.checked = data[key];

}

else if(
field.tagName === "SELECT" ||
field.tagName === "INPUT" ||
field.tagName === "TEXTAREA"
){

field.value = data[key];

}

});


document.querySelectorAll(
'input[type="radio"]'
).forEach(function(radio){

const value = data[radio.name];

if(value){

radio.checked =
radio.value === value;

}

});


lookupEmployee(false);
toggleOtherPickup();
toggleFuelQuantity();
calculateMileage();

alert(
"Saved progress loaded."
);

}


function clearForm(){

if(!confirm(
"Clear all entered information?"
)){

return;

}

document.querySelectorAll(
"input, select, textarea"
).forEach(function(field){

if(field.type === "radio" ||
field.type === "checkbox"){

field.checked = false;

}else{

field.value = "";

}

});


el("otherPickupField").style.display = "none";
el("fuelQuantityField").style.display = "none";
el("mileageWarning").style.display = "none";
el("submitMessage").style.display = "none";

el("date").value =
new Date().toISOString().slice(0,10);

}


document.addEventListener(
"DOMContentLoaded",
function(){

el("date").value =
new Date().toISOString().slice(0,10);


el("employeeId").addEventListener(
"input",
function(){
lookupEmployee(false);
}
);


el("employeeId").addEventListener(
"change",
function(){
lookupEmployee(false);
}
);


el("employeeId").addEventListener(
"blur",
function(){
lookupEmployee(false);
}
);


[
"beginMileage",
"endMileage"
].forEach(function(id){

[
"input",
"change",
"blur",
"keyup"
].forEach(function(ev){

el(id).addEventListener(
ev,
calculateMileage
);

});

});

});

</script>

</body>
</html>
