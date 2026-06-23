# SS-DYNAMIC-CARGO-FULL-COMPLETE-CARCULATOR
SS DYNAMIC CARGO FULL COMPLETE CARCULATOR
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SS DYNAMIC CARGO - China To Malaysia Logistics Calculator</title><style>
body{
margin:0;
font-family:Arial,sans-serif;
background:linear-gradient(rgba(0,0,0,.85),rgba(0,0,0,.85)),
url('china-malaysia-flags.jpg');
background-size:cover;
color:#fff;
}
header{
background:#111;
padding:25px;
text-align:center;
border-bottom:3px solid red;
}
h1{color:#ff0000;}
.container{
max-width:1200px;
margin:auto;
padding:20px;
}
.card{
background:#111;
padding:20px;
margin-bottom:20px;
border-radius:10px;
border:1px solid #333;
}
input,select{
width:100%;
padding:12px;
margin:8px 0;
background:#222;
border:none;
color:#fff;
border-radius:5px;
}
button{
width:100%;
padding:14px;
background:red;
color:white;
border:none;
font-weight:bold;
cursor:pointer;
}
.result{
margin-top:15px;
padding:15px;
background:#000;
color:#00ff88;
font-weight:bold;
}
</style></head>
<body><header>
<h1>SS DYNAMIC CARGO</h1>
<h3>Your Logistics Partner Cargo Forwarder China To Malaysia</h3>
<h2>🇨🇳 CHINA ➜ 🇲🇾 MALAYSIA</h2>
</header><div class="container"><div class="card">
<h2>Customer Information</h2><input id="name" placeholder="Name">
<input id="phone" placeholder="WhatsApp Number">
<input id="email" placeholder="Email">
<input id="address" placeholder="Address"><select id="destination">
<option value="WEST MALAYSIA">WEST MALAYSIA</option>
<option value="EAST MALAYSIA">EAST MALAYSIA</option>
</select>
</div><div class="card">
<h2>Dimension Converter</h2><input id="cm" type="number" placeholder="CM"><button onclick="convertCM()">Convert</button>

<div class="result" id="cmResult"></div>
</div><div class="card">
<h2>CBM Calculator</h2><input id="length" type="number" placeholder="Length (CM)">
<input id="width" type="number" placeholder="Width (CM)">
<input id="height" type="number" placeholder="Height (CM)"><button onclick="calculateCBM()">Calculate CBM</button>

<div class="result" id="cbmResult"></div>
</div><div class="card">
<h2>Volumetric Weight Calculator</h2><input id="vlength" type="number" placeholder="Length (CM)">
<input id="vwidth" type="number" placeholder="Width (CM)">
<input id="vheight" type="number" placeholder="Height (CM)"><button onclick="calculateVolumetric()">Calculate</button>

<div class="result" id="volResult"></div>
</div><div class="card">
<h2>Air Freight Calculator</h2><input id="airKg" type="number" placeholder="Weight KG"><select id="airType">
<option value="29">West Normal RM29/KG</option>
<option value="39">West Sensitive RM39/KG</option>
<option value="49">East Normal RM49/KG</option>
<option value="59">East Sensitive RM59/KG</option>
</select><button onclick="calculateAir()">Calculate Air Freight</button>

<div class="result" id="airResult"></div>
</div><div class="card">
<h2>Sea Freight Calculator</h2><input id="seaCBM" type="number" step="0.001" placeholder="CBM"><select id="seaRate">
<option value="399">West Normal RM399/CBM</option>
<option value="450">West Sensitive RM450/CBM</option>
<option value="599">East Normal RM599/CBM</option>
<option value="650">East Sensitive RM650/CBM</option>
</select><button onclick="calculateSea()">Calculate Sea Freight</button>

<div class="result" id="seaResult"></div>
</div><div class="card">
<h2>RMB ➜ MYR Converter</h2><input id="rmb" type="number" placeholder="RMB Amount"><button onclick="convertRMB()">Convert</button>

<div class="result" id="rmbResult"></div>
</div><div class="card">
<h2>Shipping Cost Quotation Generator</h2><button onclick="generateQuote()">Generate Quotation</button>

<div class="result" id="quote"></div><button onclick="sendWhatsApp()">Send To WhatsApp</button>

</div></div><script>

let latestQuote="";

function convertCM(){
let cm=parseFloat(document.getElementById("cm").value)||0;
let m=cm/100;
let mm=cm*10;

document.getElementById("cmResult").innerHTML=
cm+" CM<br>"+m.toFixed(3)+" M<br>"+mm+" MM";
}

function calculateCBM(){
let l=document.getElementById("length").value;
let w=document.getElementById("width").value;
let h=document.getElementById("height").value;

let cbm=(l*w*h)/1000000;

document.getElementById("cbmResult").innerHTML=
cbm.toFixed(3)+" CBM";
}

function calculateVolumetric(){
let l=document.getElementById("vlength").value;
let w=document.getElementById("vwidth").value;
let h=document.getElementById("vheight").value;

let vol=(l*w*h)/6000;

document.getElementById("volResult").innerHTML=
vol.toFixed(2)+" KG";
}

function calculateAir(){
let kg=document.getElementById("airKg").value;
let rate=document.getElementById("airType").value;

let total=kg*rate;

document.getElementById("airResult").innerHTML=
"RM "+total.toFixed(2);
}

function calculateSea(){
let cbm=document.getElementById("seaCBM").value;
let rate=document.getElementById("seaRate").value;

let total=cbm*rate;

document.getElementById("seaResult").innerHTML=
"RM "+total.toFixed(2);
}

function convertRMB(){
let rmb=document.getElementById("rmb").value;

let rate=0.65;

let myr=rmb*rate;

document.getElementById("rmbResult").innerHTML=
"RM "+myr.toFixed(2);
}

function generateQuote(){

let name=document.getElementById("name").value;
let destination=document.getElementById("destination").value;

latestQuote=
"SS DYNAMIC CARGO\n"+
"Customer: "+name+"\n"+
"Destination: "+destination;

document.getElementById("quote").innerHTML=
latestQuote.replace(/\n/g,"<br>");
}

function sendWhatsApp(){

let phone="601151453147";

window.open(
"https://wa.me/"+phone+"?text="+encodeURIComponent(latestQuote)
);

}

</script></body>
