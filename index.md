<!DOCTYPE html>
<html>
  <head>
    <title>Styled Map Types</title>
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no">
    <meta charset="utf-8">
	<meta name="viewport" content="width=device-width" />
    <style>
/* Always set the map height explicitly to define the size of the div
       * element that contains the map. */
      #map {
        height: 70%;
      }
	 
/* Optional: Makes the sample page fill the window. */
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>

<style>

/* Dropdown Button */
.dropbtn {
  background-color: #ffffff;
  color: black;
  margin-top:10px;
  margin-left:10px;
  padding: 6px;
  font-size: 25px;
  border: 2px solid #7b6662;
}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: #ddd;}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {display: block;}

/* Change the background color of the dropdown button when the dropdown content is shown */
.dropdown:hover .dropbtn {background-color: #3e8e41;}
.box{
    margin-top: 0px;
	margin-left:30%;
	padding:20px;
  padding-top:5px;
	width:420px;
	height:65px;
	border-top: 0px solid #7b6662;
	background:#f4f0e3;
	position: relative;
}
/* Button 1*/
.button1 {
  background-color: #dfd2ae;
  color: black;
  margin-top:-25px;
  margin-left:10px;
  padding: 6px;
  font-size: 25px;
  border: 2px solid #7b6662;
}
.button1 a{
  color: black;
  padding: 1px 1px;
  text-decoration: none;
  display: block;
}
.button1:active{
  background-color:#3e8e41;
}
.box2{
  margin-top: 0px;
	margin-left:30%;
	padding-left:70px;
	width:420px;
	height:60px;
	position: relative;
	background:none;
}
.bar{
  margin-top: -6px;
  margin-left:23%;
	width:610px;
	height:12px;
	position: relative;
	background: #7b6662;
}
</style>
<style>
      /* Optional: Makes the sample page fill the window. */
      html, body {
        height: 100%;
        margin: 0;
        padding: 0;
      }
      #description {
        font-family: Roboto;
        font-size: 15px;
        font-weight: 300;
      }

      #infowindow-content .title {
        font-weight: bold;
      }

      #infowindow-content {
        display: none;
      }

      #map #infowindow-content {
        display: inline;
      }

      .pac-card {
        margin: 10px 10px 0 0;
        border-radius: 2px 0 0 2px;
        box-sizing: border-box;
        -moz-box-sizing: border-box;
        outline: 10px solid black;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
        background-color: #fff;
        font-family: Roboto;
      }

      #pac-container {
        padding-bottom: 30px;
        margin-right: 30px;
      }

      .pac-controls {
        display: inline-block;
        padding: 5px 11px;
      }

      .pac-controls label {
        font-family: Roboto;
        font-size: 20px;
        font-weight: 300;
      }

      #pac-input {
        background-color: #f1f1f1;
        font-family: Roboto;
        font-size: 20px;
        font-weight: 300;
        margin-left: 12px;
        padding: 0 11px 0 13px;
        text-overflow: ellipsis;
        width: 400px;
        height:30px;
        border: 3px solid #7b6662;
      }

      #pac-input:focus {
        border-color: blue;
      }

      #title {
        color: #fff;
        background-color: #4d90fe;
        font-size: 25px;
        font-weight: 500;
        padding: 6px 12px;
      }
      #target {
        width: 345px;
      }
    </style>
  </head>
  <body>
<input id="pac-input" class="controls" type="text" placeholder="Search Box">
    <div id="map"></div>
<div class="bar">
</div>
<div class="box">
<div class="dropdown">
  <button class="dropbtn">Function</button>
  <div class="dropdown-content">
    <a href="#">Function 1</a>
    <a href="#">Function 2</a>
    <a href="#">Function 3</a>
  </div>
</div>
<div class="dropdown">
  <button class="dropbtn">Optional </button>
  <div class="dropdown-content">
    <a href="#">Option 1</a>
    <a href="#">Option 2</a>
    <a href="#">Option 3</a>
  </div>
</div>
  <div class="dropdown">
  <button class="dropbtn">Other Button</button>
  <div class="dropdown-content">
    <a href="#">Button 1</a>
    <a href="#">Button 2</a>
    <a href="#">Button 3</a>
  </div>
</div>
</div>
<div class="box2">
<div class="dropdown">
  <button class="button1"><a href="#">Refresh</a></button>
</div>
<div class="dropdown">
  <button class="button1"><a href="#">More research</a></button>
</div>
</div>
      
<script>

function myFunction() {
  document.getElementById("myDropdown").classList.toggle("show");
}

// Close the dropdown menu if the user clicks outside of it
window.onclick = function(event) {
  if (!event.target.matches('.dropbtn')) {
    var dropdowns = document.getElementsByClassName("dropdown-content");
    var i;
    for (i = 0; i < dropdowns.length; i++) {
      var openDropdown = dropdowns[i];
      if (openDropdown.classList.contains('show')) {
        openDropdown.classList.remove('show');
      }
    }
  }
}
</script>
<script>
      function initMap() {

        // Create a new StyledMapType object, passing it an array of styles,
        // and the name to be displayed on the map type control.
        var styledMapType = new google.maps.StyledMapType(
            [
              {elementType: 'geometry', stylers: [{color: '#ebe3cd'}]},
              {elementType: 'labels.text.fill', stylers: [{color: '#523735'}]},
              {elementType: 'labels.text.stroke', stylers: [{color: '#f5f1e6'}]},
              {
                featureType: 'administrative',
                elementType: 'geometry.stroke',
                stylers: [{color: '#c9b2a6'}]
              },
              {
                featureType: 'administrative.land_parcel',
                elementType: 'geometry.stroke',
                stylers: [{color: '#dcd2be'}]
              },
              {
                featureType: 'administrative.land_parcel',
                elementType: 'labels.text.fill',
                stylers: [{color: '#ae9e90'}]
              },
              {
                featureType: 'landscape.natural',
                elementType: 'geometry',
                stylers: [{color: '#dfd2ae'}]
              },
              {
                featureType: 'poi',
                elementType: 'geometry',
                stylers: [{color: '#dfd2ae'}]
              },
              {
                featureType: 'poi',
                elementType: 'labels.text.fill',
                stylers: [{color: '#93817c'}]
              },
              {
                featureType: 'poi.park',
                elementType: 'geometry.fill',
                stylers: [{color: '#a5b076'}]
              },
              {
                featureType: 'poi.park',
                elementType: 'labels.text.fill',
                stylers: [{color: '#447530'}]
              },
              {
                featureType: 'road',
                elementType: 'geometry',
                stylers: [{color: '#f5f1e6'}]
              },
              {
                featureType: 'road.arterial',
                elementType: 'geometry',
                stylers: [{color: '#fdfcf8'}]
              },
              {
                featureType: 'road.highway',
                elementType: 'geometry',
                stylers: [{color: '#f8c967'}]
              },
              {
                featureType: 'road.highway',
                elementType: 'geometry.stroke',
                stylers: [{color: '#e9bc62'}]
              },
              {
                featureType: 'road.highway.controlled_access',
                elementType: 'geometry',
                stylers: [{color: '#e98d58'}]
              },
              {
                featureType: 'road.highway.controlled_access',
                elementType: 'geometry.stroke',
                stylers: [{color: '#db8555'}]
              },
              {
                featureType: 'road.local',
                elementType: 'labels.text.fill',
                stylers: [{color: '#806b63'}]
              },
              {
                featureType: 'transit.line',
                elementType: 'geometry',
                stylers: [{color: '#dfd2ae'}]
              },
              {
                featureType: 'transit.line',
                elementType: 'labels.text.fill',
                stylers: [{color: '#8f7d77'}]
              },
              {
                featureType: 'transit.line',
                elementType: 'labels.text.stroke',
                stylers: [{color: '#ebe3cd'}]
              },
              {
                featureType: 'transit.station',
                elementType: 'geometry',
                stylers: [{color: '#dfd2ae'}]
              },
              {
                featureType: 'water',
                elementType: 'geometry.fill',
                stylers: [{color: '#b9d3c2'}]
              },
              {
                featureType: 'water',
                elementType: 'labels.text.fill',
                stylers: [{color: '#92998d'}]
              }
            ],
            {name: 'Styled Map'});

        // Create a map object, and include the MapTypeId to add
        // to the map type control.
        var map = new google.maps.Map(document.getElementById('map'), {
          center: {lat: 21.054836, lng: 105.820533},
          zoom: 13,
          mapTypeControlOptions: {
            mapTypeIds: ['roadmap', 'satellite', 'hybrid', 'terrain',
                    'styled_map']
          }
        });

        //Associate the styled map with the MapTypeId and set it to display.
        map.mapTypes.set('styled_map', styledMapType);
        map.setMapTypeId('styled_map');
		
var image = 'https://2.bp.blogspot.com/-q518vZnB7Rs/W-KsCgwsVPI/AAAAAAAAAZ8/gJ27kVMMZ9YSOVx4QWw_dHNcL4dLWiwlACLcBGAs/s1600/s40.png';

        var contentString = '<div id="content">'+
            '<div id="siteNotice">'+
            '</div>'+
            '<h3 id="firstHeading" class="firstHeading"> <span style="color: #bf005f">ADD GROUP</span></h3>'+
            '<div id="bodyContent">'+
            '<p><b><span style="color: #ff7f00">ACT</span> Apartment Map</b></br>The map will help you easily find a good place to live and invest in Vietnam </b>'
            '</div>';

        var infowindow = new google.maps.InfoWindow({
          content: contentString,
          maxWidth: 270
        });

        var marker = new google.maps.Marker({
          position: {lat: 21.054502, lng: 105.820617},
          map: map,
          icon: image,
          draggable: true,
          animation: google.maps.Animation.BOUNCE,
          title: 'Factory Map'
        });

          marker.addListener('click', function() {
          infowindow.open(map, marker);
        });
    var infowindow = new google.maps.InfoWindow({
        content: contentString,
		maxWidth: 170
    });

   //Create a marker pin to add to the map
   var marker;
   marker1 = new google.maps.Marker({
      position: new google.maps.LatLng(21.054836, -105.820533),//set the position of the pin
      map: map,
      title: "ADD Group",
      icon: "http://www.codeshare.co.uk/images/blue-pin.png", //if you comment this out or delete it you will get the default pin icon.
      animation:google.maps.Animation.DROP
   });

    marker1.addListener('click', function() {
        infowindow.open(map, marker1);
    });
	//-------START CLUSTER INFOWINDOW SETTING------

var infoWin = new google.maps.InfoWindow({content: location.info, maxWidth: 360});
var factoryimg = 'https://4.bp.blogspot.com/-NI_7HK9mcbA/W-KoaBBzn-I/AAAAAAAAAZQ/kNHeKbXkaHQGbvMN6fRrJT9WkyvQuO6NwCLcBGAs/s1600/x25.png';
var titles = 'Factory Level 2';
var factorymarkers = factory.map(function(location, i) {
          
          var factorymarkers = new google.maps.Marker({
    position: location,
    icon: factoryimg,
    Draggable: false,
    animation: google.maps.Animation.DROP,
    title: titles
  });
  google.maps.event.addListener(factorymarkers, 'click', function(evt) {
    infoWin.setContent(location.info);
    
    infoWin.open(map, factorymarkers);
  })
  return factorymarkers;
});
//------------------------------ CREATE SEARCH BOX and link it to the UI element.---------------------
        var input = document.getElementById('pac-input');
        var searchBox = new google.maps.places.SearchBox(input);
        map.controls[google.maps.ControlPosition.BOTTOM_CENTER].push(input);

        // Bias the SearchBox results towards current map's viewport.
        map.addListener('bounds_changed', function() {
          searchBox.setBounds(map.getBounds());
        });

        var markers = [];
        // Listen for the event fired when the user selects a prediction and retrieve
        // more details for that place.
        searchBox.addListener('places_changed', function() {
          var places = searchBox.getPlaces();

          if (places.length == 0) {
            return;
          }

          // Clear out the old markers.
          markers.forEach(function(marker) {
            marker.setMap(null);
          });
          markers = [];
          // For each place, get the icon, name and location.
          var bounds = new google.maps.LatLngBounds();
          places.forEach(function(place) {
            if (!place.geometry) {
              console.log("Returned place contains no geometry");
              return;
            }
            var icon = {
              url: place.icon,
              size: new google.maps.Size(71, 71),
              origin: new google.maps.Point(0, 0),
              anchor: new google.maps.Point(17, 34),
              scaledSize: new google.maps.Size(25, 25)
            };

            // Create a marker for each place.
            markers.push(new google.maps.Marker({
              map: map,
              icon: icon,
              title: place.name,
              position: place.geometry.location
            }));

            if (place.geometry.viewport) {
              // Only geocodes have viewport.
              bounds.union(place.geometry.viewport);
            } else {
              bounds.extend(place.geometry.location);
            }
          });
          map.fitBounds(bounds);
        });
//----------END SEARCH BOX SCRIPT--------------------------

//----------END CLUSTER INFOR---------
//----------------------------------------START VIGLACERA CLUSTER-------------------------------
var viglaimg = 'https://1.bp.blogspot.com/-iDUkh25mHlk/XqQIdASerFI/AAAAAAAAEbM/PjTG8R8QqZYs0KvTu8L5-fVGtGwS4bEpQCLcBGAsYHQ/s1600/Green4045.png';
var titles = 'Apartment Building';
var viglamarkers = vigla.map(function(location, i) {
          
          var viglamarkers = new google.maps.Marker({
    position: location,
    icon: viglaimg,
    Draggable: false,
    animation: google.maps.Animation.DROP,
    title: titles
  });
  google.maps.event.addListener(viglamarkers, 'click', function(evt) {
    infoWin.setContent(location.info);
    
    infoWin.open(map, viglamarkers);
  });
  return viglamarkers;
});

//---- Add a marker clusterer to manage the markers.-
//set style options for marker clusters (these are the default styles)
viglamcOptions = {styles: [{
height: 71,
url: "https://1.bp.blogspot.com/-ZlDKibOg5T4/XqPAy5MkBjI/AAAAAAAAEa0/k5QlOiMecSUgvlgKXcMWzMg1gAU8xUnwgCLcBGAsYHQ/s1600/orangedot40dddd.png",
width: 68
}]};
viglamcOptions1 = {styles: [{
height: 53,
url: "https://4.bp.blogspot.com/-7k6GkOO4VbI/XHNqzLop7PI/AAAAAAAAAoQ/ha9vFOkbUJAqx3jh7ZGNUKQa3Uz7H8BGgCLcBGAs/s1600/orangedot40.png",
width: 40
}]};
//init clusterer with your options
var viglamc = new MarkerClusterer(map, viglamarkers, {imagePath: 'https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/m'});
//------------------------------------END VIGLACERA CLUSTER-------------------------------
//--------------------------------- factory marker----------------------
viglamcOptions1 = {styles: [{
height: 53,
url: "https://3.bp.blogspot.com/-jOsaGS4hBMk/XHNrVxeNZJI/AAAAAAAAAoY/EUUY4NtyzE4s3IO5MnlSph5QR7gXr2KpgCLcBGAs/s1600/Bluedot%2B40.png",
width: 40
}]};

//init clusterer with your options
//--------------END Vigla---------
}
//-------------- START CLUSTER MARK Vigla again-------------

var vigla = [
        //////Apartment
        {lat:  21.050269, lng:  105.779182, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> An Binh City</font></p></a></b>"},
        {lat:  21.070436, lng:  105.791523, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/c1-c2-xuan-dinh style=text-decoration:none><p align=middle><font size=4> Chung Cu C1 - C2 Xuan Dinh  </font></p></a></b>"},
        {lat:  21.050844, lng:  105.786173, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/ct3-co-nhue style=text-decoration:none><p align=middle><font size=4> CT3 Co Nhue </font></p></a></b>"},
        {lat:  21.043421, lng:  105.767855, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/goldmark-city style=text-decoration:none><p align=middle><font size=4> Goldmark City </font></p></a> </b>"},
        {lat:  21.052203, lng:  105.780868, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/green-stars style=text-decoration:none><p align=middle><font size=4> Green Stars</font></p></a> </b>"},
        {lat: 21.047067, lng: 105.786543, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/hanhud-hoang-quoc-viet style=text-decoration:none><p align=middle><font size=4> Hanhud Hoang Quoc Viet </font></p></a></b>"},
        {lat: 21.051161, lng: 105.785054, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/kdtm-co-nhue style=text-decoration:none><p align=middle><font size=4> KDTM Co Nhue </font></p></a></b>"},
        {lat:  21.081145, lng:  105.791565, info: "<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/the-link style=text-decoration:none><p align=middle><font size=4> The LINK </font></p></a></b>"},
        {lat: 21.064551, lng: 105.782579, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/kdtm-resco style=text-decoration:none><p align=middle><font size=4> KDTM Resco </font></p></a></b>"},
        {lat: 21.063108, lng: 105.795617, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/ngoai-giao-doan style=text-decoration:none><p align=middle><font size=4> Ngoai Giao Doan </font></p></a></b>"},
        {lat: 21.057518, lng: 105.777450, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/nha-o-bo-cong-an style=text-decoration:none><p align=middle><font size=4> Nha O Bo Cong An  </font></p></a></b>"},
        {lat: 21.069553, lng: 105.796947, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/chung-cu-789-xuan-dinh style=text-decoration:none><p align=middle><font size=4> Chung Cu 789 Xuan Dinh </font></p></a></b>"},
        {lat: 21.086424, lng: 105.782230, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/ecohome-1 style=text-decoration:none><p align=middle><font size=4> Ecohome 1 </font></p></a></b>"},
        {lat: 21.083702, lng: 105.784339, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/ecohome-2 style=text-decoration:none><p align=middle><font size=4> Ecohome 2 </font></p></a></b>"},
        {lat: 21.041790, lng: 105.765374, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/scitech-tower style=text-decoration:none><p align=middle><font size=4> Scitech Tower </font></p></a></b>"},
        {lat: 21.041695, lng: 105.758952, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/toa-nha-intracom-2 style=text-decoration:none><p align=middle><font size=4> Toa Nha Intracom 2  </font></p></a></b>"},
        {lat: 21.050439, lng: 105.785330, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/ct2b-nam-cuong style=text-decoration:none><p align=middle><font size=4> CT2B Nam Cuong  </font></p></a></b>"},
        {lat: 21.047487, lng: 105.796702, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/chung-cu-238-hoang-quoc-viet style=text-decoration:none><p align=middle><font size=4> Chung Cu 238 Hoang Quoc Viet </font></p></a></b>"},
        {lat: 21.044920, lng: 105.767718, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/vc7-housing-complex style=text-decoration:none><p align=middle><font size=4> VC7 Housing Complex </font></p></a></b>"},
        {lat: 21.02975, lng: 105.821472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hanoi Golden Lake</font></p></a></b>"}, 
		{lat: 21.022917, lng: 105.814611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> C1 Thanh Cong</font></p></a></b>"}, 
		{lat: 21.030389, lng: 105.823639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Nui Truc Square</font></p></a></b>"}, 
		{lat: 21.027471999999999, lng: 105.822361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> C7 Giang Vo</font></p></a></b>"}, 
		{lat: 21.044694, lng: 105.845056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hanoi Aqua Central</font></p></a></b>"}, 
		{lat: 21.019110999999999, lng: 105.815917, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> BRG Grand Plaza</font></p></a></b>"}, 
		{lat: 21.020278000000001, lng: 105.81788899999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sun Grand City - 31 Lang Ha</font></p></a></b>"}, 
		{lat: 21.031749999999999, lng: 105.814944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes Metropolis - Lieu Giai</font></p></a></b>"}, 
		{lat: 21.038250000000001, lng: 105.813389, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> 379 Doi Can</font></p></a></b>"}, 
		{lat: 21.035333000000001, lng: 105.813806, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Lieu Giai Tower</font></p></a></b>"}, 
		{lat: 21.029693999999999, lng: 105.82130600000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Golden Armor</font></p></a></b>"}, 
		{lat: 21.041250000000002, lng: 105.81191699999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu So 6 Doi Nhan</font></p></a></b>"}, 
		{lat: 21.027722000000001, lng: 105.816694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Platinum Residences</font></p></a></b>"}, 
		{lat: 21.026, lng: 105.82216699999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu D2 Giang Vo</font></p></a></b>"}, 
		{lat: 21.040889, lng: 105.807694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hoa Binh Green Apartment</font></p></a></b>"}, 
		{lat: 21.036110999999998, lng: 105.78236099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Indochina Plaza Residences</font></p></a></b>"}, 
		{lat: 21.027083000000001, lng: 105.786056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sky Park Residence</font></p></a></b>"}, 
		{lat: 21.00525, lng: 105.798778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mandarin Garden</font></p></a></b>"}, 
		{lat: 21.004694000000001, lng: 105.793778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes D'Capitale</font></p></a></b>"}, 
		{lat: 21.025971999999999, lng: 105.791583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Luxury Park Views</font></p></a></b>"}, 
		{lat: 21.032167000000001, lng: 105.791944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Ha Do Parkside</font></p></a></b>"}, 
		{lat: 21.020111, lng: 105.791222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Central Field Trung Kinh</font></p></a></b>"}, 
		{lat: 21.019472, lng: 105.79427800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chelsea Residences</font></p></a></b>"}, 
		{lat: 21.026306000000002, lng: 105.78925, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Golden Park tower</font></p></a></b>"}, 
{lat: 21.044028000000001, lng: 105.80283300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Trang An Complex</font></p></a></b>"}, 
{lat: 21.027111000000001, lng: 105.79349999999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Ha Do Park View</font></p></a></b>"}, 
{lat: 21.016138999999999, lng: 105.79261099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Home City Trung Kính</font></p></a></b>"}, 
{lat: 21.005749999999999, lng: 105.798778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDT Dong Nam Tran Duy Hung</font></p></a></b>"}, 
{lat: 21.013611000000001, lng: 105.803472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Eurowindow Multi Complex</font></p></a></b>"}, 
{lat: 21.035610999999999, lng: 105.794083, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Discovery Complex</font></p></a></b>"}, 
{lat: 21.015999999999998, lng: 105.797056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Park View City</font></p></a></b>"}, 
{lat: 21.032222000000001, lng: 105.799694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Cau Giay Center Point</font></p></a></b>"}, 
{lat: 21.035806000000001, lng: 105.783778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Richland Southern</font></p></a></b>"}, 
{lat: 21.026083, lng: 105.799222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Lancaster Luminaire</font></p></a></b>"}, 
{lat: 21.018528, lng: 105.824333, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hoang Cau Skyline</font></p></a></b>"}, 
{lat: 21.019722000000002, lng: 105.821611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> TDC Hoang Cau</font></p></a></b>"}, 
{lat: 21.023444000000001, lng: 105.80919400000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes Nguyen Chi Thanh</font></p></a></b>"}, 
{lat: 21.019528000000001, lng: 105.82252800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> D'. Le Pont D'or Hoang Cau</font></p></a></b>"}, 
{lat: 21.001055999999998, lng: 105.837222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Capital Garden 102 Truong Chinh Kinh Do</font></p></a></b>"}, 
{lat: 21.013361, lng: 105.827639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Sunrise Tower - 187 Tay Son</font></p></a></b>"}, 
{lat: 21.014527999999999, lng: 105.81699999999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Song Hong Park View</font></p></a></b>"}, 
{lat: 21.021083000000001, lng: 105.828028, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> 170 De La Thanh - GP Building</font></p></a></b>"}, 
{lat: 21.020056, lng: 105.80875, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> M3 - M4 Nguyen Chi Thanh</font></p></a></b>"}, 
{lat: 21.027332999999999, lng: 105.803889, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hong Kong Tower</font></p></a></b>"}, 
{lat: 21.008389000000001, lng: 105.83452800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> B4 - B14 Kim Lien</font></p></a></b>"}, 
{lat: 21.005583000000001, lng: 105.823583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Toa Nha MIPEC Tay Son</font></p></a></b>"}, 
{lat: 20.980250000000002, lng: 105.784667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Booyoung</font></p></a></b>"}, 
{lat: 20.984110999999999, lng: 105.75775, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Mới Dương Nội - Anland Lakeview</font></p></a></b>"}, 
{lat: 20.976027999999999, lng: 105.761, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Mới Dương Nội - Anland Premium</font></p></a></b>"}, 
{lat: 20.983416999999999, lng: 105.754167, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Mới Dương Nội - Anland Complex</font></p></a></b>"}, 
{lat: 20.975667000000001, lng: 105.78063899999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tháp Doanh Nhân Tower</font></p></a></b>"}, 
{lat: 20.972916999999999, lng: 105.756889, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Terra An Hưng</font></p></a></b>"}, 
{lat: 20.960667000000001, lng: 105.742361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Xuân Mai Sparks Tower</font></p></a></b>"}, 
{lat: 20.959278000000001, lng: 105.76683300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDTM Văn Phú - The K Park</font></p></a></b>"}, 
{lat: 20.959944, lng: 105.7675, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDTM Văn Phú - The Victoria</font></p></a></b>"}, 
{lat: 20.957611, lng: 105.76983300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDTM Văn Phú - CT12 Văn Phú</font></p></a></b>"}, 
{lat: 20.958389, lng: 105.763139, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDTM Văn Phú - C10 - C11</font></p></a></b>"}, 
{lat: 20.961082999999999, lng: 105.794111, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Xa La</font></p></a></b>"}, 
{lat: 20.955249999999999, lng: 105.74422199999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Nhà Ơ BỘ Tư Lệnh Thủ đô Hà Nội</font></p></a></b>"}, 
{lat: 20.952639000000001, lng: 105.758194, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cư PCC1 Complex</font></p></a></b>"}, 
{lat: 20.982056, lng: 105.742833, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> ICID Complex</font></p></a></b>"}, 
{lat: 20.946306, lng: 105.755944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cư The Vesta</font></p></a></b>"}, 
{lat: 20.974610999999999, lng: 105.78788900000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Rainbow Văn Quán</font></p></a></b>"}, 
{lat: 20.951443999999999, lng: 105.790778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mipec City View</font></p></a></b>"}, 
{lat: 20.986889000000001, lng: 105.785083, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mulberry Lane</font></p></a></b>"}, 
{lat: 20.963722000000001, lng: 105.775972, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hyundai Hillstate</font></p></a></b>"}, 
{lat: 20.986694, lng: 105.782944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cư Euroland</font></p></a></b>"}, 
{lat: 20.987110999999999, lng: 105.786361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Seasons Avenue</font></p></a></b>"}, 
{lat: 20.972360999999999, lng: 105.757667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Pride</font></p></a></b>"}, 
{lat: 20.976721999999999, lng: 105.775306, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Goldsilk Complex</font></p></a></b>"}, 
{lat: 20.974556, lng: 105.76088900000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Usilk City</font></p></a></b>"}, 
{lat: 20.974944000000001, lng: 105.761444, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> BID Residence</font></p></a></b>"}, 
{lat: 20.982638999999999, lng: 105.789861, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Nhà Ở Bắc Hà</font></p></a></b>"}, 
{lat: 20.962278000000001, lng: 105.763944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> FLC Star Tower</font></p></a></b>"}, 
{lat: 20.964694000000001, lng: 105.764556, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cư An Lạc - Nam La Khê</font></p></a></b>"}, 
{lat: 20.973943999999999, lng: 105.77847199999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tòa tháp Thiên Niên Kỷ Hà Tây</font></p></a></b>"}, 
{lat: 20.953749999999999, lng: 105.788639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu đô thị Kiến Hưng</font></p></a></b>"}, 
{lat: 20.963861000000001, lng: 105.777778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Phú Thịnh Green Park</font></p></a></b>"}, 
{lat: 20.976472000000001, lng: 105.762722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HPC Landmark 105</font></p></a></b>"}, 
{lat: 20.959139, lng: 105.798361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cư Sails Tower</font></p></a></b>"}, 
{lat: 20.974917000000001, lng: 105.776639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Samsora Premier</font></p></a></b>"}, 
{lat: 20.972833000000001, lng: 105.76344400000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Văn Khê</font></p></a></b>"}, 
{lat: 20.938749999999999, lng: 105.78744399999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Đô Thị Thanh Hà Mường Thanh</font></p></a></b>"}, 
{lat: 20.979139, lng: 105.78536099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hồ Gươm Plaza</font></p></a></b>"}, 
{lat: 20.962889000000001, lng: 105.77333299999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Xuân Mai Park State</font></p></a></b>"}, 
{lat: 20.977333000000002, lng: 105.81055600000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Bea Sky</font></p></a></b>"}, 
{lat: 20.981472, lng: 105.880222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu X203 Linh Nam</font></p></a></b>"}, 
{lat: 20.973832999999999, lng: 105.842389, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinawaco Thinh Liet</font></p></a></b>"}, 
{lat: 20.988944, lng: 105.858417, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Panorama Hoang Van Thu</font></p></a></b>"}, 
{lat: 20.955749999999998, lng: 105.84486099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Athena Complex Phap Van</font></p></a></b>"}, 
{lat: 20.98075, lng: 105.81063899999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Athena Fulland</font></p></a></b>"}, 
{lat: 20.965083, lng: 105.84480600000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Green Park Tran Thu Do</font></p></a></b>"}, 
{lat: 20.984528000000001, lng: 105.835611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sky Central</font></p></a></b>"}, 
{lat: 20.974250000000001, lng: 105.84402799999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hong Ha Tower</font></p></a></b>"}, 
{lat: 20.984860999999999, lng: 105.833139, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> An Binh 1</font></p></a></b>"}, 
{lat: 20.9785, lng: 105.83627799999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Smile Building</font></p></a></b>"}, 
{lat: 20.972000000000001, lng: 105.879639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Zen Residence</font></p></a></b>"}, 
{lat: 20.973389000000001, lng: 105.83925000000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Eco Lake View</font></p></a></b>"}, 
{lat: 20.987138999999999, lng: 105.849722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HUD3 Nguyen Duc Canh</font></p></a></b>"}, 
{lat: 20.958528000000001, lng: 105.83886099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Osaka Complex</font></p></a></b>"}, 
{lat: 20.975639000000001, lng: 105.869722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Gelaxia Riverside</font></p></a></b>"}, 
{lat: 20.998916999999999, lng: 105.880444, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> T&T Riverview</font></p></a></b>"}, 
{lat: 20.964082999999999, lng: 105.823194, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> B1 - B2 Tay Nam Linh Dam</font></p></a></b>"}, 
{lat: 20.963971999999998, lng: 105.822444, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Rice City Linh Dam</font></p></a></b>"}, 
{lat: 20.967167, lng: 105.833139, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> VP6 Linh Dam</font></p></a></b>"}, 
{lat: 20.970611000000002, lng: 105.878111, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Two Residence - Gamuda Garden</font></p></a></b>"}, 
{lat: 20.984306, lng: 105.84733300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mandarin Garden 2</font></p></a></b>"}, 
{lat: 20.964666999999999, lng: 105.827361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HH2 Linh Dam</font></p></a></b>"}, 
{lat: 20.974972000000001, lng: 105.819889, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Thong Tan Xa Viet Nam</font></p></a></b>"}, 
{lat: 20.974694, lng: 105.82597199999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Nha O Xa Hoi Dong Mo</font></p></a></b>"}, 
{lat: 20.989833000000001, lng: 105.867861, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sunshine Palace</font></p></a></b>"}, 
{lat: 20.963305999999999, lng: 105.864694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hateco Hoang Mai</font></p></a></b>"}, 
{lat: 20.987749999999998, lng: 105.83502799999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> CT36 - Dream House</font></p></a></b>"}, 
{lat: 20.964110999999999, lng: 105.82599999999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HH1 Linh Dam</font></p></a></b>"}, 
{lat: 20.984249999999999, lng: 105.85247200000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu Nha O Quan Doi K35 Tan Mai</font></p></a></b>"}, 
{lat: 20.989417, lng: 105.866028, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> New Horizon City - 87 Linh Nam</font></p></a></b>"}, 
{lat: 20.986806000000001, lng: 105.849833, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hoa Phat 70 NDC Tower</font></p></a></b>"}, 
{lat: 20.995028000000001, lng: 105.863472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Helios Tower 75 Tam Trinh</font></p></a></b>"}, 
{lat: 20.981888999999999, lng: 105.87091700000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Dong Phat Park View Tower</font></p></a></b>"}, 
{lat: 20.9635, lng: 105.827611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HH3 Linh Dam</font></p></a></b>"}, 
{lat: 20.964361, lng: 105.825278, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> CT3 Tay Nam Linh Dam</font></p></a></b>"}, 
{lat: 20.963971999999998, lng: 105.824167, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Rainbow Linh Dam</font></p></a></b>"}, 
{lat: 20.981860999999999, lng: 105.87097199999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Đông Phát Tower</font></p></a></b>"}, 
{lat: 20.990639000000002, lng: 105.787639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Intracom 1 Trung Van</font></p></a></b>"}, 
{lat: 20.991167000000001, lng: 105.755278, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> FLC Garden City</font></p></a></b>"}, 
{lat: 21.006416999999999, lng: 105.769167, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> My Dinh Pearl</font></p></a></b>"}, 
{lat: 20.996389000000001, lng: 105.79305600000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tay Ha Tower</font></p></a></b>"}, 
{lat: 20.986556, lng: 105.78874999999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu An Lac - Phung Khoang</font></p></a></b>"}, 
{lat: 20.998166999999999, lng: 105.794444, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Viwaseen Tower</font></p></a></b>"}, 
{lat: 21.015639, lng: 105.779972, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Sun - Me Tri</font></p></a></b>"}, 
{lat: 21.035499999999999, lng: 105.76991700000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Zei My Dinh</font></p></a></b>"}, 
{lat: 21.00525, lng: 105.739222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes Smart City</font></p></a></b>"}, 
{lat: 21.027833000000001, lng: 105.769583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cu CT5 - CT6 Le Duc Tho</font></p></a></b>"}, 
{lat: 21.030722000000001, lng: 105.76125, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Florene My Dinh</font></p></a></b>"}, 
{lat: 20.985917000000001, lng: 105.76625, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Startup Tower</font></p></a></b>"}, 
{lat: 21.031444, lng: 105.759833, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Iris Garden</font></p></a></b>"}, 
{lat: 21.047471999999999, lng: 105.73527799999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hateco Xuan Phuong</font></p></a></b>"}, 
{lat: 21.017555999999999, lng: 105.773917, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Emerald</font></p></a></b>"}, 
{lat: 21.029471999999998, lng: 105.777056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> My Dinh Plaza 2</font></p></a></b>"}, 
{lat: 21.030028000000001, lng: 105.778583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sunshine Center</font></p></a></b>"}, 
{lat: 21.031082999999999, lng: 105.755583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> CT2 Xuan Phuong</font></p></a></b>"}, 
{lat: 21.035139000000001, lng: 105.765528, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Golden Field My Dinh</font></p></a></b>"}, 
{lat: 21.040861, lng: 105.735056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Athena Complex</font></p></a></b>"}, 
{lat: 20.993500000000001, lng: 105.78611100000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Ecolife Capitol</font></p></a></b>"}, 
{lat: 21.030166999999999, lng: 105.777111, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Garden Hill - 99 Tran Binh</font></p></a></b>"}, 
{lat: 20.994111, lng: 105.779222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Trung Van - Vinaconex 3</font></p></a></b>"}, 
{lat: 20.996389000000001, lng: 105.78405600000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> VOV Me Tri</font></p></a></b>"}, 
{lat: 21.034222, lng: 105.765, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> MD Complex My Dinh</font></p></a></b>"}, 
{lat: 21.027332999999999, lng: 105.778111, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> FLC Complex 36 Pham Hung</font></p></a></b>"}, 
{lat: 21.002777999999999, lng: 105.79275, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Thang Long Number One</font></p></a></b>"}, 
{lat: 21.030944000000002, lng: 105.775611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> My Dinh Plaza</font></p></a></b>"}, 
{lat: 21.011972, lng: 105.775333, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Golden Palace</font></p></a></b>"}, 
{lat: 21.029667, lng: 105.77625, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Dolphin Plaza</font></p></a></b>"}, 
{lat: 21.016667000000002, lng: 105.78375, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Keangnam Hanoi Landmark Tower</font></p></a></b>"}, 
{lat: 21.035610999999999, lng: 105.766694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mon City</font></p></a></b>"}, 
{lat: 21.035167000000001, lng: 105.761083, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes Gardenia</font></p></a></b>"}, 
{lat: 21.014610999999999, lng: 105.775722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Manor</font></p></a></b>"}, 
{lat: 21.033999999999999, lng: 105.770278, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Flc Landmark Tower</font></p></a></b>"}, 
{lat: 21.032499999999999, lng: 105.76991700000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sun Square</font></p></a></b>"}, 
{lat: 21.011417000000002, lng: 105.785472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes West point</font></p></a></b>"}, 
{lat: 21.019777999999999, lng: 105.781667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Vinhomes Skylake</font></p></a></b>"}, 
{lat: 20.99775, lng: 105.79508300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> HH2 - Bắc Hà</font></p></a></b>"}, 
{lat: 21.031555999999998, lng: 105.764278, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu đô thị Mỹ Đình I</font></p></a></b>"}, 
{lat: 21.033611000000001, lng: 105.765972, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu đô thị Mỹ Đình II</font></p></a></b>"}, 
{lat: 21.016472, lng: 105.779472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> KDT Mỹ Đình Sông Đà - Sudico</font></p></a></b>"}, 
{lat: 20.991167000000001, lng: 105.7885, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Trung Văn - Hancic</font></p></a></b>"}, 
{lat: 21.084278000000001, lng: 105.807389, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sunshine Golden River</font></p></a></b>"}, 
{lat: 21.064527999999999, lng: 105.808639, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> CT36 Xuan La</font></p></a></b>"}, 
{lat: 21.080832999999998, lng: 105.815944, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Pent Studio</font></p></a></b>"}, 
{lat: 21.079722, lng: 105.812583, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Udic Westlake</font></p></a></b>"}, 
{lat: 21.051278, lng: 105.799306, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> 6th Element</font></p></a></b>"}, 
{lat: 21.089306000000001, lng: 105.794667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tay Ho River view</font></p></a></b>"}, 
{lat: 21.070028000000001, lng: 105.81138900000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> D'EL Dorado</font></p></a></b>"}, 
{lat: 21.083832999999998, lng: 105.81225000000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sunshine Riverside</font></p></a></b>"}, 
{lat: 21.051528000000001, lng: 105.801389, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Ecolife Tay Ho</font></p></a></b>"}, 
{lat: 21.040832999999999, lng: 105.825722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sun Grand City</font></p></a></b>"}, 
{lat: 21.065249999999999, lng: 105.82730599999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> D'. Le Roi Soleil - Quang An</font></p></a></b>"}, 
{lat: 21.084083, lng: 105.8105, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Lac Hong Westlake</font></p></a></b>"}, 
{lat: 21.052, lng: 105.80927800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Oriental Westlake</font></p></a></b>"}, 
{lat: 21.086777999999999, lng: 105.814222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Packexim 2</font></p></a></b>"}, 
{lat: 21.055806, lng: 105.805306, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tay Ho Residence</font></p></a></b>"}, 
{lat: 21.042611000000001, lng: 105.820667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Five Star Westlake</font></p></a></b>"}, 
{lat: 20.970555999999998, lng: 105.822694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Galaxy Tower Nguyen Xien</font></p></a></b>"}, 
{lat: 20.980667, lng: 105.80713900000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Eco Dream Nguyen Xien</font></p></a></b>"}, 
{lat: 20.932888999999999, lng: 105.851361, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tecco Tu Hiep</font></p></a></b>"}, 
{lat: 20.982832999999999, lng: 105.80922200000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Housinco Grand Tower</font></p></a></b>"}, 
{lat: 20.981694000000001, lng: 105.87136099999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Dai Thanh</font></p></a></b>"}, 
{lat: 20.958611000000001, lng: 105.804694, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tabudec Plaza</font></p></a></b>"}, 
{lat: 20.952805999999999, lng: 105.852194, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tu Hiep Plaza</font></p></a></b>"}, 
{lat: 20.983582999999999, lng: 105.808722, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Eco Green City</font></p></a></b>"}, 
{lat: 20.968889000000001, lng: 105.792222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung Cu Vien 103</font></p></a></b>"}, 
{lat: 20.951360999999999, lng: 105.847222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Dragon Riverside Phap Van</font></p></a></b>"}, 
{lat: 20.998888999999998, lng: 105.805667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Bohemia Residence</font></p></a></b>"}, 
{lat: 21.004639000000001, lng: 105.802667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> C3 Tower - Golden Palace</font></p></a></b>"}, 
{lat: 20.995999999999999, lng: 105.802667, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư 282 Nguyễn Huy Tưởng</font></p></a></b>"}, 
{lat: 20.999806, lng: 105.79811100000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư Ban cơ yếu Chính phủ</font></p></a></b>"}, 
{lat: 20.980222000000001, lng: 105.82641700000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư C13 Bộ Quốc Phòng</font></p></a></b>"}, 
{lat: 21.002417000000001, lng: 105.802222, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư Golden West</font></p></a></b>"}, 
{lat: 20.985417000000002, lng: 105.798194, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư PCC1 Triều Khúc</font></p></a></b>"}, 
{lat: 21.000556, lng: 105.8045, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Chung cư The Legacy</font></p></a></b>"}, 
{lat: 21.005417000000001, lng: 105.80408300000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Diamond Flower Tower</font></p></a></b>"}, 
{lat: 21.001694000000001, lng: 105.820472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Fafilm - VNT Tower</font></p></a></b>"}, 
{lat: 20.985972, lng: 105.812556, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Five Star Kim Giang</font></p></a></b>"}, 
{lat: 20.993556000000002, lng: 105.807, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Golden Land</font></p></a></b>"}, 
{lat: 20.995056000000002, lng: 105.805306, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> GoldSeason</font></p></a></b>"}, 
{lat: 21.004722000000001, lng: 105.804778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hà Nội Center Point</font></p></a></b>"}, 
{lat: 21.003917000000001, lng: 105.803472, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Handi Resco Lê Văn Lương</font></p></a></b>"}, 
{lat: 21.000305999999998, lng: 105.807, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hapulico Complex</font></p></a></b>"}, 
{lat: 21.003111000000001, lng: 105.805556, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Hei Tower</font></p></a></b>"}, 
{lat: 20.997582999999999, lng: 105.803056, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Imperia Garden</font></p></a></b>"}, 
{lat: 20.985555999999999, lng: 105.84044400000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Imperial Plaza</font></p></a></b>"}, 
{lat: 20.996110999999999, lng: 105.805778, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Khu nhà ở 90 Nguyễn Tuân</font></p></a></b>"}, 
{lat: 20.999389000000001, lng: 105.801833, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Legend Tower 109 Nguyễn Tuân</font></p></a></b>"}, 
{lat: 20.998166999999999, lng: 105.80716700000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Mỹ Sơn Tower</font></p></a></b>"}, 
{lat: 20.985306000000001, lng: 105.8005, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Pandora 53 Triều Khúc</font></p></a></b>"}, 
{lat: 20.990860999999999, lng: 105.814139, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Riverside Garden</font></p></a></b>"}, 
{lat: 21.003, lng: 105.81527800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Royal City</font></p></a></b>"}, 
{lat: 20.994582999999999, lng: 105.81791699999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Star Tower 283 Khương Trung</font></p></a></b>"}, 
{lat: 21.000582999999999, lng: 105.803611, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Stellar Garden</font></p></a></b>"}, 
{lat: 21.001916999999999, lng: 105.822417, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Tân Hồng Hà Complex</font></p></a></b>"}, 
{lat: 21.000028, lng: 105.80500000000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Thanh Xuân Complex</font></p></a></b>"}, 
{lat: 20.999749999999999, lng: 105.82852800000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Artemis</font></p></a></b>"}, 
{lat: 21.007000000000001, lng: 105.80763899999999, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> The Golden Palm Lê Văn Lương</font></p></a></b>"}, 
{lat: 20.997056000000001, lng: 105.80494400000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Thống Nhất Complex</font></p></a></b>"}, 
{lat: 21.002889, lng: 105.80197200000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Times Tower - HACC1 Complex Building</font></p></a></b>"}, 
{lat: 20.999222, lng: 105.807833, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Rivera Park</font></p></a></b>"}, 
{lat: 20.997444000000002, lng: 105.809167, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Sakura Tower</font></p></a></b>"}, 
{lat: 20.999972, lng: 105.79986100000001, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=#><p align=middle><font size=4> Viet Duc Tower</font></p></a></b>"}, 


//      {lat: 21.051467, lng: 105.792779, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city><p align=middle><font size=4> Toa Nha Intracom 2 <br> 32,341,000vnd/sqm  </font></p></a></b>"},
//        {lat: 21.051467, lng: 105.792779, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city><p align=middle><font size=4> Toa Nha Intracom 2 <br> 32,341,000vnd/sqm  </font></p></a></b>"},
//        {lat: 21.051467, lng: 105.792779, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city><p align=middle><font size=4> Toa Nha Intracom 2 <br> 32,341,000vnd/sqm  </font></p></a></b>"},
//        {lat: 21.051467, lng: 105.792779, info: "<img src='https://haiphat.org/wp-content/uploads/bfi_thumb/khu-do-thi-thuan-thanh-370ahkztg4b01neokq57nu.jpg' height='200px' width='300px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city><p align=middle><font size=4> Toa Nha Intracom 2 <br> 32,341,000vnd/sqm  </font></p></a></b>"},


        {lat: 21.051467, lng: 105.792779, info: "<img src='https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'><br><b><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/kdtm-nghia-do style=text-decoration:none><p align=middle><font size=4> KDTM Nghia Do</font></p></a></b>"}       
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},
      
       
];
//-------------end location viglacera-----
var factory = [
     
//{lat:  ....., lng:  ....., info: "<h3> .....</h3><img src=' .....' height='200px' width='380px'><b>Description:</b><br><b>Address:</b>..... Province.<hr><b>Total Area:</b>...<hr><b>Price:</b> (updated ...).<br>- Rental fee: ...usd/sqm.<br>- Management fee: ...usd/sqm/year.<br>-Electricity fee:...<br>- Water fee: ...usd/m3.<br>- Wastewater fee: ...usd/m3.<hr><b>Worker Salary:</b> ...usd/person/month. <hr><b>Land Period:</b> .....<hr><b>Advantage</b><br>... <hr><b>Infrastructure</b><br>- Water treatment station with capacity of ...m3/day.<br>- Power is supplied from national grid ....<br>- Waste water treatment station with the capacity of ... m3/day. <br>- Telecommunication system..."},

]
    </script>




	<script src="https://developers.google.com/maps/documentation/javascript/examples/markerclusterer/markerclusterer.js">
    </script> 
  <script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBM89L8uNkaUpbRLJTibMZj4Kl9FMHPrc4&libraries=places&callback=initMap"
         async defer>
		 
		 </script>
  </body>
</html>
