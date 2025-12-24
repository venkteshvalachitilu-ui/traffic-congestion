# traffic-congestion
urban area traffic congestion
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Smart Traffic Management System</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <!-- Leaflet Map CSS -->
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f4f6f8;
            margin: 0;
            padding: 0;
        }

        header {
            background: #1e88e5;
            color: white;
            padding: 15px;
            text-align: center;
        }

        .container {
            padding: 15px;
        }

        .info-box {
            background: white;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        label {
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            margin-bottom: 10px;
        }

        button {
            width: 100%;
            padding: 10px;
            background: #43a047;
            color: white;
            border: none;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background: #388e3c;
        }

        #map {
            height: 350px;
            border-radius: 8px;
        }

        .traffic-status {
            font-size: 16px;
            margin-top: 10px;
        }

        .red { color: red; }
        .yellow { color: orange; }
        .green { color: green; }
    </style>
</head>

<body>

<header>
    🚦 Smart Traffic Management System
</header>
<p>Visit the Echo Traffic Pulse app here:</p>
    <a href="https://echo-traffic-pulse.lovable.app" target="_blank" rel="noopener noreferrer">
        https://echo-traffic-pulse.lovable.app
    </a>
<div class="container">

    <div class="info-box">
        <label>📍 Current Location</label>
        <input type="text" value="Srikakulam" readonly>

        <label>🎯 Destination</label>
        <input type="text" value="Srikakulam Junction" readonly>

        <button onclick="showTraffic()">Show Traffic Status</button>

        <div class="traffic-status" id="status"></div>
    </div>

    <div class="info-box">
        <h3>🗺 Live Traffic Map</h3>
        <div id="map"></div>
    </div>

</div>

<!-- Leaflet JS -->
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<script>
    // Initialize map (Srikakulam coordinates)
    var map = L.map('map').setView([18.2969, 83.8968], 13);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '© OpenStreetMap'
    }).addTo(map);

    // Marker for current location
    L.marker([18.2969, 83.8968])
        .addTo(map)
        .bindPopup("Current Location: Srikakulam")
        .openPopup();

    // Marker for destination
    L.marker([18.3005, 83.8976])
        .addTo(map)
        .bindPopup("Destination: Srikakulam Junction");

    function showTraffic() {
        document.getElementById("status").innerHTML =
            "🚦 Traffic Status: <span class='yellow'>Moderate Traffic (Yellow Zone)</span><br>" +
            "⏱ Estimated Travel Time: 15 Minutes<br>" +
            "🛣 Number of Routes: 1 Main Route Available";
    }
</script>

</body>
</html>
