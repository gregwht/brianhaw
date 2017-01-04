<html>
<head>
<title>The most basic form of geolocation</title>


<p>You may need to enable location services for your browser.
<br>On iPhone, ensure location services are enabled by going to Settings > Privacy > Location Services > Safari > While Using the App.</p>
<p id="demo"></p>

<script type="text/javascript">

var x = document.getElementById("demo");

function TestGeo()
    {
         if (navigator.geolocation) 
            {
              navigator.geolocation.watchPosition( TestMap, error, {maximumAge: 1000, timeout: 10000, enableHighAccuracy: true} );
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
