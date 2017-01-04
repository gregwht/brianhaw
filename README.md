<html>
<body>

<p>Watch Position: Automatically get location.</p>

<p id="demo"></p>

<script>
getLocation();
var x = document.getElementById("demo");

function getLocation() {
    if (navigator.geolocation) {
        navigator.geolocation.watchPosition(showPosition);
    } else {
        x.innerHTML = "Geolocation is not supported by this browser.";
    }
}
function showPosition(position) {
    x.innerHTML = "Latitude: " + position.coords.latitude + 
    "<br>Longitude: " + position.coords.longitude +
    "<br>Accuracy: " + position.coords.accuracy; 
}
</script>
</body>
</html>
