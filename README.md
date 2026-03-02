<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <title>PK Rummy Game</title>
    <style>
        body { background-color: #1a472a; color: white; text-align: center; font-family: Arial, sans-serif; }
        .table { border: 5px solid #5d3a1a; border-radius: 50px; padding: 50px; margin: 20px; background: radial-gradient(#2a623d, #1a472a); }
        .card { background: white; color: black; padding: 10px; border-radius: 5px; display: inline-block; width: 50px; height: 70px; font-weight: bold; margin: 5px; border: 1px solid #000; }
        .red { color: red; }
    </style>
</head>
<body>
    <h1>PK Rummy में आपका स्वागत है</h1>
    <div class="table">
        <h3>आपकी पत्तियां (Your Hand)</h3>
        <div class="card">A ♠</div>
        <div class="card red">K ♥</div>
        <div class="card">Q ♣</div>
        <div class="card red">10 ♦</div>
        <p>गेम लोड हो रहा है...</p>
    </div>
    <button onclick="alert('खेल जल्द शुरू होगा!')">कार्ड उठाएं (Draw Card)</button>
</body>
</html>
