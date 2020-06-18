<html>
<head>
  <meta charset="utf-8" />
  <title>APARTMENT MAP</title>
  <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />

  <!-- Load Leaflet from CDN -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.6.0/dist/leaflet.css"
  integrity="sha512-xwE/Az9zrjBIphAcBb3F6JVqxf46+CDLwfLMHloNu6KEQCAWi6HcDUbeOfBIptF7tcCzusKFjFw2yuvEpDL9wQ=="
  crossorigin=""/>
  <script src="https://unpkg.com/leaflet@1.6.0/dist/leaflet.js"
  integrity="sha512-gZwIG9x3wUXg2hdXF6+rVkLF/0Vi9U8D2Ntg4Ga5I5BZpVkVxlJWbSQtXPSiUTtC0TjtGOmxa1AJPuV0CPthew=="
  crossorigin=""></script>


  <!-- Load Esri Leaflet from CDN -->
  <script src="https://unpkg.com/esri-leaflet@2.3.3/dist/esri-leaflet.js"
  integrity="sha512-cMQ5e58BDuu1pr9BQ/eGRn6HaR6Olh0ofcHFWe5XesdCITVuSBiBZZbhCijBe5ya238f/zMMRYIMIIg1jxv4sQ=="
  crossorigin=""></script>




  <!-- Load Leaflet MarkerCluster and Esri Leaflet Cluster from CDN -->
  <link rel="stylesheet" type="text/css"
    href="https://unpkg.com/leaflet.markercluster@1.4.1/dist/MarkerCluster.Default.css"
    integrity="sha512-BBToHPBStgMiw0lD4AtkRIZmdndhB6aQbXpX7omcrXeG2PauGBl2lzq2xUZTxaLxYz5IDHlmneCZ1IJ+P3kYtQ=="
    crossorigin="">
  <link rel="stylesheet" type="text/css" href="https://unpkg.com/leaflet.markercluster@1.4.1/dist/MarkerCluster.css"
    integrity="sha512-RLEjtaFGdC4iQMJDbMzim/dOvAu+8Qp9sw7QE4wIMYcg2goVoivzwgSZq9CsIxp4xKAZPKh5J2f2lOko2Ze6FQ=="
    crossorigin="">
  <script src="https://unpkg.com/leaflet.markercluster@1.4.1/dist/leaflet.markercluster.js"
    integrity="sha512-MQlyPV+ol2lp4KodaU/Xmrn+txc1TP15pOBF/2Sfre7MRsA/pB4Vy58bEqe9u7a7DczMLtU5wT8n7OblJepKbg=="
    crossorigin=""></script>
  <script src="https://unpkg.com/esri-leaflet-cluster@2.0.1/dist/esri-leaflet-cluster.js"
    integrity="sha512-2/Nwrks+A2omjKeWrF4TKFLIrUbAhSl8EDEm6xunuwXXYqMoJI71PZtlW0/vqt9d3DOyP1md/bzAnNH2KuAhaQ=="
    crossorigin=""></script>

  <style>
    body { margin:0; padding:0; }
    #map { position: absolute; top:0; bottom:0; right:0; left:0; }
	
  </style>
</head>
<body>

<style>

  .cluster {
    background: #2d84c8;
    border-radius: 50%;
    text-align: center;
    color: white;
    font-weight: 700;
    border: 1px solid #2d84c8;
    font-family: monospace;
  }

  .cluster:before {
    content: ' ';
    position: absolute;
    border-radius: 50%;
    z-index: -1;
    top: 1px;
    left: 1px;
    right: 1px;
    bottom: 1px;
    border: 1px solid white;
  }

  .digits-1 {
    font-size: 14px;
    height: 28px;
    width: 28px;
    line-height: 28px;
    margin-top: -14px;
    margin-left: -14px;
  }

  .digits-2 {
    font-size: 16px;
    height: 34px;
    width: 34px;
    line-height: 35px;
    margin-top: -17px;
    margin-left: -17px;
  }

  .digits-2:before {
    border-width: 2px;
  }

  .digits-3 {
    font-size: 18px;
    height: 48px;
    width: 47px;
    line-height: 47px;
    border-width: 3px;
    margin-top: -24px;
    margin-left: -24px;
  }

  .digits-3:before {
    border-width: 3px;
  }

  .digits-4 {
    font-size: 18px;
    height: 58px;
    width: 58px;
    line-height: 57px;
    border-width: 4px;
    margin-top: -29px;
    margin-left: -29px;
  }

  .digits-4:before {
    border-width: 4px;
  }
  
.custom-popup, .leaflet-popup-tip {
    background: #e7e7e7;
    border: none;
    box-shadow: none;
    }

.leaflet-popup-content-wrapper {
   background: #64758E;
   border-radius: 0px;
   }

.leaflet-popup {
    position: absolute;
    text-align: center;
    }

.leaflet-popup-content {
    margin-top: 0px;
    margin-right: 0px;
    padding-right: 0px;
	margin-left: 0px;
    padding-left: 0px;
    min-width: 100 px !important;
    max-height: 270px;
    }
.leaflet-popup-content p, h3{
    margin-top: 0;
    margin-bottom: 0;
    color: #D6E8FF;
    text-align: middle;
    font-family: 'Adobe Fan Heiti Std B';
    font-size: 14px
}

</style>
<div class='custom-popup' id='map'></div>


    <script>
var markers = [
  {
    "name": "<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city><p align=middle><font size=4> An Binh City <br> 32,341,000vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"GKA",
    "icao":"AYGA",
    "lat":21.050269,
    "lng":105.779182,
    "alt":5282,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Chung Cu C1 - C2 Xuan Dinh <br> 24,644,153vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.070436,
    "lng":105.791523,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> CT3 Co Nhue <br> 28,743,158vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.050844,
    "lng":105.786173,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Goldmark City <br> 27,653,527vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.043421,
    "lng":105.767855,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Green Stars <br> 28,144,265vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.052203,
    "lng":105.780868,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Hanhud Hoang Quoc Viet <br> 26,732,857vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.047067,
    "lng":105.786543,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> KDTM Co Nhue <br> 28,843,024vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.051161,
    "lng":105.785054,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> The LINK <br> 30,103,193vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.081145,
    "lng":105.791565,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> KDTM Resco <br> 20,412,161vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.064551,
    "lng":105.782579,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Ngoai Giao Doan <br> 32,341,000vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.063108,
    "lng":105.795617,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Nha O Bo Cong An <br> 32,194,145vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.057518,
    "lng":105.777450,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Chung Cu 789 Xuan Dinh <br> 31,371,048vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.069553,
    "lng":105.796947,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Ecohome 1 <br> 18,824,463vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.086424,
    "lng":105.782230,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Ecohome 2 <br> 20,237,524vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.083702,
    "lng":105.784339,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Scitech Tower <br> 21,980,639vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.041790,
    "lng":105.765374,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Toa Nha Intracom 2 <br> 32,341,000vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.041695,
    "lng":105.758952,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
    },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> CT2B Nam Cuong <br> 29,020,162vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.050439,
    "lng":105.785330,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
 },{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> Chung Cu 238 Hoang Quoc Viet <br> 32,341,000vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.047487,
    "lng":105.796702,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
},{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> VC7 Housing Complex <br> 24,810,416vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.044920,
    "lng":105.767718,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
},{
    "name":"<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> KDTM Nghia Do <br> 33,372,880vnd/sqm  </font></p></a></div>",
	 
    "city":"Hanoi, Viet Nam",
    "iata_faa":"MAG",
    "icao":"AYMD",
    "lat":21.051467,
    "lng":105.792779,
    "alt":20,
    "tz":"Pacific/Port_Moresby"
  }
];
</script>

<script>

var map = L.map( 'map', {
  center: [21.052203, 105.780868],
  minZoom: 2,
  zoom: 13
});
//api key and map style here 
L.tileLayer( 'https://api.maptiler.com/maps/streets/{z}/{x}/{y}.png?key=XDzNX0JCRQPYWEUXDDxM', {
 attribution: '&copy; <a href=”<a href="https://www.maptiler.com/copyright/" target="_blank">&copy; MapTiler</a> <a href="https://www.openstreetmap.org/copyright" target="_blank">&copy; OpenStreetMap contributors</a>”>OpenStreetMap</a> contributors',
 subdomains: ['a','b','c']
}).addTo( map );
 
var imageUrl ='https://1.bp.blogspot.com/-DFAqs0MwFWU/Xp_siW6JzXI/AAAAAAAAEYY/gCWlHeF9RtolXagTylBgQGmgP6961AxxACLcBGAsYHQ/s1600/blue4045.png';

var myIcon = L.icon({
  iconUrl: imageUrl,
  iconRetinaUrl: imageUrl,
  iconSize: [33, 37],
  iconAnchor: [9, 21],
  popupAnchor: [0, -14]
});
var markerClusters = L.markerClusterGroup();
 
for ( var i = 0; i < markers.length; ++i )
{
  var popup = '<img src="https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png" height="230px" width="300px"/>'+ markers[i].name;
 
  var m = L.marker( [markers[i].lat, markers[i].lng], {icon: myIcon} )
                  .bindPopup(popup);
  markerClusters.addLayer( m );
}
 
map.addLayer( markerClusters );
</script>
  </body>
</html>
