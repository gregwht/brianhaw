<html>
<head>
<title>The most basic form of geolocation</title>

<p id="demo"></p>

<script type="text/javascript">

var x = document.getElementById("demo");

function TestGeo()
    {
         if (navigator.geolocation) 
            {
              navigator.geolocation.getCurrentPosition( TestMap, error, {maximumAge: 30000, timeout: 10000, enableHighAccuracy: true} );
        }
        else
        {
              x.innerHTML = "Geolocation is not supported by this browser."
        }
    }

function TestMap(position) {
	var latitude = position.coords.latitude;
	var longitude = position.coords.longitude;  
	 x.innerHTML = "Latitude: " + position.coords.latitude + 
	    "<br>Longitude: " + position.coords.longitude + 
	    "<br>Accuracy: " + position.coords.accuracy; 
	}
	
function error() {
		x.innerHTML = "Cannot locate user."
		}
</script>

</head>
<body onload="TestGeo();">

</body>
</html>
