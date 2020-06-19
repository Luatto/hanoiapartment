<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<title>Create and style clusters</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />
<script src="https://api.mapbox.com/mapbox-gl-js/v1.9.1/mapbox-gl.js"></script>
<link href="https://api.mapbox.com/mapbox-gl-js/v1.9.1/mapbox-gl.css" rel="stylesheet" />
<style>
	body { margin: 0; padding: 0;}
	#map { position: absolute; top: 0; bottom: 0; width: 100%; margin-left: -0% }
.mapboxgl-popup-content-wrapper{
    padding-top: 0px;
    margin-right: 0px;
    padding-right: 0px;
	margin-left: 0px;
    padding-left: 0px;
}
.mapboxgl-popup {
margin-top: 0px;

	min-width: 330px;
	min-height: 200px;
	font: 8px/15px 'Open Sans', sans-serif;
	text-color: white;
	border-radius: 0px;
}
.mapboxgl-popup-content {
	background: #c6c8ee; 
    margin-top: 0px;
	padding-top: 0px;
    margin-right: 0px;
    padding-right: 0px;
	margin-left: 0px;
    padding-left: 0px;
	max-height: 260px;
}	


.cluster {
  background-image: url('https://1.bp.blogspot.com/-WlfHJed1Tlc/XqAKCGO1CtI/AAAAAAAAEaE/K6OH_iDzsuszo6m5WhOwIfHT0flqoxOtQCLcBGAsYHQ/s1600/dot40.png');
  background-size: cover;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
</head>
<body>

<div id="map"></div>

<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoibHVjYXNsdWF0IiwiYSI6ImNrOTdiOThodjB0ajQzcGwyczkwZ2Fnc3kifQ.vQ83gWW5CBR3af1_Xzo6Vw';
    var map = new mapboxgl.Map({
        container: 'map',
        style: 'mapbox://styles/mapbox/streets-v10',
        center: [105.820358, 21.054403],
        zoom: 10
    });

    map.on('load', function() {
        // Add a new source from our GeoJSON data and
        // set the 'cluster' option to true. GL-JS will
        // add the point_count property to your source data.
        map.addSource('earthquakes', {
            type: 'geojson',
            // Point to GeoJSON data. This example visualizes all M1.0+ earthquakes
            // from 12/22/15 to 1/21/16 as logged by USGS' Earthquake hazards program.
            data:
                {
"type": "FeatureCollection",
"crs": { "type": "name", "properties": { "name": "urn:ogc:def:crs:OGC:1.3:CRS84" } },
"features": [
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Southern Industrial Park Yen Bai Province<br> 7,1usd/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 104.9418057, 21.6756925, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Lương Sơn Industrial Park<br> 82USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.5484642, 20.8822227, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> kcn bắc thăng long<br> 90USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.77810220000001, 21.124536899999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Binh Luc Industry Zone<br> 46USD/sqm/44years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.03811090000001, 20.4753334, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Yen Phong IP<br> 76USD/ m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0042073, 21.192171699999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Van Trung Industry Zone<br> 75USD/sqm/45years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1295336, 21.245377000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Minh Duc Industry Zone<br> 60USD/sqm/50 years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.12901340000001, 20.9161143, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Song Tra Industry Zone<br> 2.5USD/sqm/montn  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.32404990000001, 20.477980200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Lai Vu<br> 55USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.39315120000001, 20.9803076, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Pho Noi A Industry Zone<br> 80USD/sqm/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.02551819999999, 20.956930400000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Yen Binh Industry Zone<br> 60USD/sqm/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.90052350000001, 21.430857199999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Diem Thuy Industry Zone<br> 48USD/sqm/40years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.891971, 21.474341800000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dong Van IV Industry Zone<br> 57USD/sqm/50 years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8955658, 20.638668899999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Nam Thăng Long Industrial Park<br> 120USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.761769, 21.082578600000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN PHÚ NGHĨA<br> 5 ha  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7403123, 20.954691400000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Lại Dụ<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.704435, 20.977982900000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Lại Yên Industry zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7182385, 21.022824, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN VSIP<br> 85USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9762884, 21.077036400000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Đại Đồng<br> 65USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.99809500000001, 21.1052058, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Trục chính KCN Tiên Sơn<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9977748, 21.1257433, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Yen Phong Industrial Zone 2<br> 76USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.95335009999999, 21.204578099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Thạch Thất<br> 85USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6310474, 21.006475699999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cum Công Nghiệp Trường An Xã An Khánh Hoài Đức Hà Nội<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7263128, 20.997368099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp xã kim bình<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.918595, 20.573345499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tay Bac Cu Chi Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4840413, 10.9830763, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dong Nam Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.6210686, 10.969378300000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Phu Trung Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.53524659999999, 10.921779600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Khai Quang<br> 63USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6333236, 21.3079027, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Thang Long II<br> 90-95USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.061348, 20.9146848, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Quế Võ Industrial Zone<br> 64USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1133033, 21.153963099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Pho Noi B Textile and Garment Industrial Park<br> 70- 75USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0575056, 20.924525800000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công nghiệp đông thọ<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.94637419999999, 21.1795911, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công Nghiệp Ngọc Hồi<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8515451, 20.9132201, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Thanh Oai Industrial Area<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.80114279999999, 20.8720426, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Quang Minh Industrial Zone<br> 120USD/m2/ 50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.77925209999999, 21.1856191, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Nam Cầu Kiền<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.63354959999999, 20.914779200000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Bá Thiện 1<br> 45USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6797689, 21.326165199999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Khai Sơn Thuận Thành<br> 52USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.05898620000001, 21.036857300000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phúc Điền Industrial Park<br> 55USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2040769, 20.930793000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phu Hung Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9902281, 20.968720600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Yên Phong Mở Rộng<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0005295, 21.2216375, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp an dương<br> 65USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.5796113, 20.873230199999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Ecological Zone Cuisine Vinh Hung<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.877388, 20.993811000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hai Ha Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.74881670000001, 21.3657714, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp DEEP C HP II<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.77959730000001, 20.803984700000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Vsip Hai Duong Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1732444, 20.928766199999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Thoi Hiep Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.6307187, 10.8850243, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Binh Chieu Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7307943, 10.883324200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Trang Due Industrial Park<br> 60USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.5715707, 20.857410699999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Truong Industrial Zone<br> 54- 57USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2270607, 20.935504600000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phuc Khanh Industrial Zone<br> 30USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.31265980000001, 20.4414804, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hạp Lĩnh Nam Sơn Industrial Zone<br> 60USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0956465, 21.130895200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Khánh Phú<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0225859, 20.232081300000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Yen My II Industrial Zone<br> 80usd/m2/50년  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0435813, 20.877169599999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Lộc Son<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.83702049999999, 11.5188276, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Hoà Phú<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9702104, 21.234251400000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Nam Dinh Vu non-tariff and industrial park (zone 1)<br> 70- 120USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.81154960000001, 20.815795399999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cai Lan Industrial Zone<br> 60USD/m2/Years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.0448962, 20.972393, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Thụy Vân Industrial Park<br> 30USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.3526452, 21.343331200000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Bình Xuyên 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.67926749999999, 21.303257500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Nội Hoàng<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1689138, 21.244645500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> công ti asia khu công nghiệp song khê<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1766047, 21.2435002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Fugiang Vân Trung<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.144429, 21.250619700000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Chau Son Industrial Park Henan<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8976869, 20.5196857, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KHU CÔNG NGHIỆP BÌNH XUYÊN<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.65512270000001, 21.280358100000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Đồ Sơn<br> 85usd- 97usd/m2/50년  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7606923, 20.739311900000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp VSIP<br> 80-90USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.702825, 20.904087499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Tam Hiệp<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.62446199999999, 21.082094699999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Phúc Sơn<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9861619, 20.216262799999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Đình Trám Industrial Zone<br> 45USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.12694500000001, 21.254740000000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công nghiệp xã Chiềng Châu<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.0751174, 20.638599899999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Lạc Thịnh<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.5967236, 20.4008295, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công Nghiệp Đồng Hướng<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.10126510000001, 20.0962736, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công Nghiệp Đồng Phong<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7322502, 20.320522400000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm Công nghiệp Đồng Tu<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2040454, 20.595583600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Nguyễn Đức Cảnh<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3293252, 20.4471621, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Cầu Nghìn<br> 50USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4352464, 20.655644899999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Bau Xeo Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.0308742, 10.957122099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phu My I Industrial Zone<br> 65  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.0480556, 10.5905556, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Song May Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.9540283, 10.9713461, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Honai Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.93857869999999, 10.950114299999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Amata Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.8909948, 10.939308499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Lễ Môn<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8128851, 19.7817981, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Tây Bắc Ga<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7659269, 19.826537299999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Rạng Đông<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1803625, 19.986333900000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hoa Khanh Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.12876249999999, 16.0833431, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> An Don Industrial Zone Danang<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.2323111, 16.0777517, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Da Nang Industrial Park (Khu công nghiệp Đà Nẵng)<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.23718959999999, 16.0775611, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Hoà Cầm<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.18818469999999, 16.004451400000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hoang Mai Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.72491960000001, 19.298073500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công Nghiệp Tri Lễ<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.1563747, 18.947284799999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Nam Cam Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6667367, 18.8261182, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Xóm 4 Nghi Phú<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.67826239999999, 18.7263096, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cổng Khu công nghiệp VSIP Nghệ An<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6319649, 18.704521700000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp vàng bạc đá quý<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.5986283, 18.689282800000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Bim Son Industrial Park<br> 30USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8466638, 20.109590399999998, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Phú Vinh<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.39840409999999, 18.012982000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Northwest Industrial Park in Dong Hoi<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.583641, 17.488457199999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Quán Ngang<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.08124410000001, 16.8904143, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Nam Đông Hà<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.11366630000001, 16.789783799999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm công nghiệp Diên Sanh<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.2559605, 16.68083, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dac Loc industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 109.16199109999999, 12.3012961, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Quang Ngai VSIP Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.7892724, 15.215720900000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tinh Phong Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.7988366, 15.1988612, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Quang Phu industrial zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.7671053, 15.118623400000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Phú Tài<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 109.1448314, 13.782018900000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> An Phuoc Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.9618341, 10.853688, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phu An Thanh Industrial Park<br> 119-135,  144-160 USD  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4516149, 10.6813024, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Long Duc<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.9785175, 10.842186099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Ninh Thủy<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 109.2466924, 12.504872600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Suoi Dau Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 109.0681374, 12.1487763, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Binh Industrial Zone (Tanimex)<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.623893, 10.8152115, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> An Ha Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.5109631, 10.811871200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Tao Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.5902876, 10.7460816, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Le Minh Xuan Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.54235799999999, 10.7418662, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phong Phu Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.6433966, 10.6983537, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hiep Phuoc Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7466009, 10.638517, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Robustness port Hiep Phuoc Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7347827, 10.6528358, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Trung An industrial cluster<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.332888, 10.3476658, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hoa Phu Industrial Park<br> 60 USD  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.93197480000001, 10.1730071, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Binh Minh Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.82423780000001, 10.037643299999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Chau Duc Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.1706398, 10.58925, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Da Bac Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.2757864, 10.5789048, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Đất Đỏ 1<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.30223839999999, 10.504759999999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Long Sơn<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.08916670000001, 10.452500000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dong Xuyen Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.11637380000001, 10.399841, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Giao Long Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4001846, 10.2981146, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tra Noc Industrial Zone in Can Tho<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.7152609, 10.1006312, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Xẻo Rô<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.11680339999999, 9.8504684000000005, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu CN Khánh An<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.0577457, 9.2279234999999993, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Thạnh Lộc<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.13189819999999, 9.9899632999999994, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Binh Long Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.249289, 10.567171500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Binh Hoa Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.3418949, 10.4544572, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Song Hau Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.5985542, 10.2499033, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Linh Trung 3 Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3943622, 11.013886599999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Trang Bang Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3949516, 11.0214242, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Bourbon An Hoa TransAsia Industrial Garden (Khu công nghiệp Xuyên Á Bourbon An Hòa)<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3278052, 11.034349000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Thành Thành Công<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3192514, 11.021049, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phuoc Dong Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.3191905, 11.1370942, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Chà Là<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2058837, 11.295595499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Tam Thăng<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.4684354, 15.619972199999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Hòa Bình<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.9891252, 14.3234467, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Trà Đa<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 108.03171, 14.019297, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Đông Mai<br> 55usd/m2/50년  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.84121020000001, 21.0060763, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Thanh Bình<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.8040965, 21.933755099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Long Binh Industrial Park - An, Tuyen Quang<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.24653669999999, 21.731650200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Thai Hoa Industrial Park<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4744537, 10.9283622, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cụm công nghiệp Bạch Hạc<br> 0,43USD/m2/years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.44409709999999, 21.2832878, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Kcn Đồng Lạng<br> 25USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.3504611, 21.385528000000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Đại An<br> 55-68USD/m2/Years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2669247, 20.9297632, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> VSIP<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9653268, 21.0940358, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> 꽝밍공업단지<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.77925209999999, 21.1856191, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Thuận Thành 2<br> 32USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.09585079999999, 21.056609999999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Thuan Thanh III Industrial Park<br> 58USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0583468, 21.047789999999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Hanaka Industrial Park<br> 39USD/m2/years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9582372, 21.124624600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu CN Bình Vàng<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 104.9768543, 22.713180099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dong Van I industrial Zone<br> 50-55USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9218913, 20.6364418, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Dong Van II Industrial Park<br> 58USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.91757680000001, 20.665318500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Việt Hòa-Kenmark<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2871315, 20.939228799999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> IZ Lai Cach<br> 55USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2516315, 20.934606200000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tien Hai Industrial Park<br> 25USD/m2?50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.52158129999999, 20.391947099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công nghiệp Hải Yên - Viglacera<br> 30USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 107.91613630000001, 21.541309800000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Que Vo III Industrial Park<br> 65USD/m2/years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.17879600000001, 21.138383300000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Que Vo Industrial Park 2<br> 64USD/m2/50years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2220739, 21.128552500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Phú Thái<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.51456020000001, 20.962667100000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN CỘNG HOÀ CHÍ LINH HẢI DƯƠNG<br> 50USD/m2/years  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4217838, 21.129179499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Luong Son Cluster Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2952591, 21.401541099999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Tan Hung Cluster Industrial Zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.2916431, 21.351537, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Ba Thien II Industrial Zone<br> 70-75usd/sqm  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.6750613, 21.338784499999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Gia Lễ<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.35668099999999, 20.503223500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu Công Nghiệp Tân Liên<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.4915608, 20.703779600000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Hòa xá<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1461747, 20.417607199999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khu công nghiệp Mỹ Trung<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1930152, 20.452692500000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Bao Minh Industrial Zone Management Board<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.1031586, 20.344221399999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Ý Yên II Industrial zone<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.95436340000001, 20.405581999999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Khánh Phú Industrial Zone<br> 35-40 Usd/sqm/year  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.0303645, 20.244480500000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> HANSSIP<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9147741, 20.708827500000002, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Phu nghia 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.671415, 20.929724799999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN Hiệp Phước 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7515861, 10.641088399999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCX Linh Trung 1<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.768351, 10.8686091, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN QUANG MINH<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.74798319999999, 21.206851, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN HÀ NỘI - ĐÀI TƯ<br> 10 ha  </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.9263243, 21.026779399999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Bien Hoa 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.87755249999999, 10.928039399999999, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Cat Lai 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7726538, 10.764358, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCN KCX TÂN THUẬN<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.72983619999999, 10.752447800000001, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> KCX Linh Trung 2<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7240779, 10.8906212, 105.5 ] } }, 
{ "type": "Feature", "properties": { "id": "ak16994519", "mag": "<div align='center'><a href=# style=text-decoration:none><p align=middle><font size=4> Long Hậu<br>   </font></p></a></div>", "time": 1507425289659, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 106.7143665, 10.6385048, 105.5 ] } }, 




{ "type": "Feature", "properties": { "id": "hv61900626", "mag": "<div align='center'><a href=https://sites.google.com/add-group.net/hotels-services/hotel-apartment/google-map/an-binh-city style=text-decoration:none><p align=middle><font size=4> KDTM Nghia Do <br> 33,372,880vnd/sqm  </font></p></a></div>", "time": 1504833891990, "felt": null, "tsunami": 0 }, "geometry": { "type": "Point", "coordinates": [ 105.792779, 21.051467, 2.609 ] } }
]
},
            cluster: true,
            clusterMaxZoom: 14, // Max zoom to cluster points on
            clusterRadius: 50 // Radius of each cluster when clustering points (defaults to 50)
        });

        map.addLayer({
            id: 'clusters',
            type: 'circle',
            source: 'earthquakes',
			style: 'cluster',
            filter: ['has', 'point_count'],
            paint: {
                // Use step expressions (https://docs.mapbox.com/mapbox-gl-js/style-spec/#expressions-step)
                // with three steps to implement three types of circles:
                //   * Blue, 20px circles when point count is less than 100
                //   * Yellow, 30px circles when point count is between 100 and 750
                //   * Pink, 40px circles when point count is greater than or equal to 750
                'circle-color': [
                    'step',
                    ['get', 'point_count'],
                    '#ff7800',
                    100,
                    '#f1f075',
                    750,
                    '#f28cb1'
                ],
				'circle-stroke-color': [
                    'step',
                    ['get', 'point_count'],
                    '#ffae00',
                    100,
                    '#ffae00',
                    750,
                    '#ffae00'
                ],
				'circle-stroke-width': 8,
                'circle-radius': [
                    'step',
                    ['get', 'point_count'],
                    10,
                    100,
                    15,
                    750,
                    20
                ]
            }
        });

        map.addLayer({
            id: 'cluster-count',
            type: 'symbol',
            source: 'earthquakes',
            filter: ['has', 'point_count'],
            layout: {
                'text-field': '{point_count_abbreviated}',
                'text-font': ['DIN Offc Pro Medium', 'Arial Unicode MS Bold'],
                'text-size': 12
            }
        });

        map.addLayer({
            id: 'unclustered-point',
            type: 'circle',
            source: 'earthquakes',
            filter: ['!', ['has', 'point_count']],
            paint: {
                'circle-color': 'Blue',
                'circle-radius': 4,
                'circle-stroke-width': 8,
                'circle-stroke-color': '#7678b5'
            }
        });

        // inspect a cluster on click
        map.on('click', 'clusters', function(e) {
            var features = map.queryRenderedFeatures(e.point, {
                layers: ['clusters']
            });
            var clusterId = features[0].properties.cluster_id;
            map.getSource('earthquakes').getClusterExpansionZoom(
                clusterId,
                function(err, zoom) {
                    if (err) return;

                    map.easeTo({
                        center: features[0].geometry.coordinates,
                        zoom: zoom
                    });
                }
            );
        });
        
        // When a click event occurs on a feature in
        // the unclustered-point layer, open a popup at
        // the location of the feature, with
        // description HTML from its properties.
        map.on('click', 'unclustered-point', function(e) {

            var coordinates = e.features[0].geometry.coordinates.slice();
            var mag = e.features[0].properties.mag;
            new mapboxgl.Popup({className: 'mapboxgl'})
                .setLngLat(coordinates)
                .setHTML("<img src=' https://1.bp.blogspot.com/-fdwl_Rnt7Rw/XpliSz2kqiI/AAAAAAAAES8/WH63iZyZXCsFDjYy-r502qod93cmgClFwCLcBGAsYHQ/s1600/ADD.png' height='220px' width='330px'>"  + mag )
                .addTo(map);
        });

        map.on('mouseenter', 'clusters', function() {
            map.getCanvas().style.cursor = 'pointer';
        });
        map.on('mouseleave', 'clusters', function() {
            map.getCanvas().style.cursor = '';
        });
    });
</script>

</body>
</html>
