<!DOCTYPE html><html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Kalkulator Support & Resistance</title>
<style>
    body {
        background: #0d0d0d;
        color: #f5f5f5;
        font-family: Arial, sans-serif;
        padding: 20px;
    }
    .container {
        max-width: 350px;
        margin: auto;
        background: #1a1a1a;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(255,255,255,0.1);
    }
    input {
        width: 100%;
        padding: 10px;
        margin-top: 10px;
        background: #333;
        border: 1px solid #555;
        color: #fff;
        border-radius: 5px;
    }
    button {
        margin-top: 15px;
        width: 100%;
        padding: 10px;
        background: #b8860b;
        border: none;
        color: #fff;
        font-size: 16px;
        border-radius: 5px;
        cursor: pointer;
    }
    .result {
        margin-top: 20px;
        padding: 10px;
        background: #111;
        border-radius: 6px;
    }
</style>
</head>
<body>
<div class="container">
    <h2>Kalkulator Support & Resistance</h2><label>High:</label>
<input type="number" id="high" placeholder="Masukkan nilai tertinggi">

<label>Low:</label>
<input type="number" id="low" placeholder="Masukkan nilai terendah">

<button onclick="hitung()">Hitung</button>

<div class="result" id="output"></div>

</div><script>
function hitung() {
    let high = parseFloat(document.getElementById("high").value);
    let low = parseFloat(document.getElementById("low").value);

    if (isNaN(high) || isNaN(low)) {
        document.getElementById("output").innerHTML = "Masukkan angka yang valid";
        return;
    }

    let support = low + (high - low) * 0.25;
    let tengah = low + (high - low) * 0.5;
    let resistance = low + (high - low) * 0.75;

    document.getElementById("output").innerHTML = `
        <b>Support:</b> ${support.toFixed(2)}<br>
        <b>Zona Buy:</b> di bawah ${support.toFixed(2)}<br><br>
        <b>Zona Tengah (No Entry):</b> sekitar ${tengah.toFixed(2)}<br><br>
        <b>Zona Sell:</b> di atas ${resistance.toFixed(2)}<br>
        <b>Resistance:</b> ${resistance.toFixed(2)}
    `;
}
</script></body>
</html>
