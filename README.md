# SMART-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Smart Solar Energy Management System</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
            background: #0f172a;
            color: #fff;
        }

        header {
            background: #020617;
            padding: 15px;
            text-align: center;
            font-size: 22px;
            font-weight: bold;
            letter-spacing: 1px;
        }

        .container {
            padding: 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
        }

        .card {
            background: #020617;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,255,255,0.1);
            text-align: center;
        }

        .card h3 {
            margin-bottom: 10px;
            font-size: 18px;
            color: #38bdf8;
        }

        .value {
            font-size: 28px;
            font-weight: bold;
            margin: 10px 0;
        }

        .status {
            padding: 8px;
            border-radius: 20px;
            display: inline-block;
            font-size: 14px;
            margin-top: 10px;
        }

        .on {
            background: #16a34a;
        }

        .off {
            background: #dc2626;
        }

        footer {
            text-align: center;
            padding: 10px;
            background: #020617;
            font-size: 14px;
            margin-top: 20px;
            color: #94a3b8;
        }
    </style>
</head>
<body>

<header>
    Smart Solar Energy Management System
</header>

<div class="container">

    <div class="card">
        <h3>Solar Voltage</h3>
        <div class="value" id="voltage">0 V</div>
    </div>

    <div class="card">
        <h3>Power Generated</h3>
        <div class="value" id="power">0 W</div>
    </div>

    <div class="card">
        <h3>Battery Level</h3>
        <div class="value" id="battery">0 %</div>
    </div>

    <div class="card">
        <h3>Load Consumption</h3>
        <div class="value" id="load">0 W</div>
    </div>

    <div class="card">
        <h3>System Status</h3>
        <div class="status on" id="status">ON</div>
    </div>

</div>

<footer>
    AI-Enabled Renewable Energy Monitoring Dashboard
</footer>

<script>
    // Simulated data (replace with real backend / Arduino data later)
    function updateData() {
        const voltage = (Math.random() * 5 + 18).toFixed(2);
        const power = (Math.random() * 200 + 300).toFixed(1);
        const battery = Math.floor(Math.random() * 40 + 60);
        const load = (Math.random() * 150 + 200).toFixed(1);

        document.getElementById("voltage").innerText = voltage + " V";
        document.getElementById("power").innerText = power + " W";
        document.getElementById("battery").innerText = battery + " %";
        document.getElementById("load").innerText = load + " W";

        const status = document.getElementById("status");
        if (battery < 30) {
            status.innerText = "OFF";
            status.className = "status off";
        } else {
            status.innerText = "ON";
            status.className = "status on";
        }
    }

    setInterval(updateData, 2000);
    updateData();
</script>

</body>
</html>
