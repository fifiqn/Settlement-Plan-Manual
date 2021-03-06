<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>Settlement Layout Using OSM Data and QGISManual</title>
</head>

<body style="font-family: Helvettica,Arial,sans-serif; background-color:rgb(255, 255, 255);">

<header>
  <h1 style=" width: 80%;font-size: 2em; background-color: green; color: #ffffff; margin-left: auto; margin-right: auto; padding: 5px;">A guide for Lesotho Planners to Digitize using Qgisand OSM data</h1>
</header>
 
<section style="width: 80%; background-color: white; margin-right: auto; margin-left: auto;">

<article>

<h1 style="width: 60%; font-size:2em; background-color: blue; color: #ffffff; marign-left: auto; margin-right: auto; padding: 5px;"></h1>
<h2 style="width: 80%; color: blue; font-size: 1.3;">Here is what you will need</h2>
<ul>
  <li>PgAdmin3 Application</li>
  <li>Qgis Application</li>
  <li>osm2ogsql</li>
  <li>osm data file</li>
  <li>The style File</li>
</ul>

<h2 style="width: 80%;font-size: 1.6; color: blue;">PgAdmin3</h2>
<figure>
  <img src="/Settlement_Plan_Manual.zip/img/thJ1YQOA0L.jpg" />
</figure>


<h3 style="color: blue; font-size: 1.3;">how to install PostgreSQL</h3>
<br>here, you are going to learn how to install PostgreSQL in windows.<br>

<br>here are 3steps to complete the PostgreSQL installation:<br><br>
<ol>
  <li>Download PostgreSQL installer for Windows</li>
  <li>Install PostgreSQL</li>
  <li>Verify the installation</li>
</ol>

<br>Download PostgreSQL Installer for Windows<br><br>

<p style="margin: 10px;">You need to download the installer <a href="http://www.postgresql.org/download/windows/">here</a>.<br>
<br>
Click on the download installer from EnterpriseDB
Choose the latest version to download. It takes few minutes to complete the download.</p>

<h3 style="color: blue; font-size: 1.3;">How to Install PostgreSQL step by step</h3>

<p style="margin: 10px;">Double click on the installer file, an installation wizard will appear and guide you through multiple steps where you can choose different options that you would like to have 
in PostgreSQL.<br>
<br>
The following illustrates each step and its options for installation. If you have a different version, you may get additional steps.</p>


<h4 style="font-size: 1.2; color: blue;">Install PostgreSQL Step 1</h4>
<figure>
  <img src="Install-PostgreSQL-Step-2-1.png" alt="a picture of PgAdmin installation wizard">
  <figcaption>click next</figcaption>
</figure>

<p style="margin: 10px;">Specify installation folder, choose your own or keep the default folder suggested by PostgreSQL installer.</p>

<h4 style="fot-size: 1.2; color: blue;">Install PostgreSQL step2</h4>
<figure>
  <img src="Install-PostgreSQL-Step-3-1.png" alt="a picture of PgAdmin installation wizard">
  <figcaption>Enter the password of your own choice and make sure to remeber it.</figcaption>
</figure>

<h4 style="fot-size: 1.2; color: blue;">Install PostgreSQL Step 3</h4>

<figure>
  <img src="Install-PostgreSQL-Step-4-1.png" alt="a picture of PgAdmin installation wizard">
<figcaption>Enter the port for PostgreSQL.For some people it may P5433.</figcaption>
</figure>


<h4 style="fot-size: 1.2; color: blue;">Install PostgreSQL Step 5</h4>
<figure>
  <img src="Install-PostgreSQL-Step-5-1.png" alt="a picture of PgAdmin installation wizard">
  <figcaption>Choose the default locale and Click the Next button to install PostgreSQL</figcaption>
</figure>


<h4 style="fot-size: 1.2; color: blue;">Install PostgreSQL Step 7</h4>
<figure>
  <img src="Install-PostgreSQL-Step-7-1.png" alt="a picture of PgAdmin installation wizard">
</figure>

<br>now you can wait for the installation to run<br>

<h4 style="fot-size: 1.2; color: blue;">Install PostgreSQL Step 8</h4>
<figure>
  <img src="Install-PostgreSQL-Step-8.png" alt="a picture of PgAdmin installation wizard">
  <figcaption>Click Finish to complete the PostgreSQL installation.</figcaption>
</figure>


<h3 style="color: blue; font-size: 1.3;">How to Verify the Installation</h3>

<p style="margin: 10px;">This can be done through the pgAdmin application. First, go to your Local 
Disk C:. Now go to Program FilesX86, navigate the list to find postgresql 
and doubleclick on it. Open the 9.3 folder. do the samething for bin. Now,
if you scroll down the list, you will find pgadmin3. Rightclick on it, go
to create shortcut and click yes to create a desktop shortcut. now go to 
the desktop and doubleclick on the shortcut you have just created and 
pgadmin will be launched.</p>


<p style="margin: 10px;">second,Connect to PostgreSQL Server<br><br>this is done by simply doubleclicking on the server marked with the red x</p>
<figure>
  <img src="Connect-to-PostgreSQL-Server.jpg" alt="a picture of a launched PgAdmin application">
  <figcaption>now it is time to use the password you entered in step2 and check the store password box</figcaption>
</figure>


<p style="margin: 10px;">Third, if everything is fine, the pgAdmin will display all the objects that belong to the server.<p>
<figure>
  <img src="PostgreSQL-Objects.jpg" alt="a picture of a launched PgAdmin application">
</figure>
</article>

<article>
<h2 style=" width: 80%;font-size: 1.6; color: blue;">Quantum GIS (Qgis)</h2>
<figure>
  <img src="th.jpg" alt="Qgis logo">
</figure>
 <h3 style="color: blue; font-size: 1;3;">How to install Qgis</h3>

<p style="margin: 10px;">Here, you learn a step by step the installation of the actual version (2.18) of QGIS.<br><br> 

First, you need to download the software from 
<a href="http://www.qgis.org/">here</a>. Double click on the downloaded 
.exe file to install. Accept the install defaults to complete the process and
launch</p>
</article>

<aside style="width: 80%; margin-right: auto; font-size: 1em; background: #eeff99; padding: 20px; border: 1px solid #696; border-radius: 20px;">Congratulation! you’ve successfully installed PostgreSQL database server in your and Qgis PC.</aside> 


<article>
<h2 style=" width: 80%;font-size: 1.6; color: blue; ">osm2pgsql</h2>

<p style="margin: 10px;">In the previous article we saw how to set up Postgresql with PostGIS in Windows and how to set up a database and load it with shapefile data. In order to get OpenStreetMap data into a database, you could get the data in shapefile format and use the shapefile loader, but this may leave you without all the data that you want. In this chapter we will learn how to use osm2pgsql, a command-line program for loading raw OSM data into a PostGIS database.
We will go through the steps to set up osm2pgsql on Windows, though the steps should be roughly the same on another operating system, assuming you have set up your PostGIS database(s) correctly.</P>

<h3 style="color: blue; font-size: 1.3;">How to get OSM2PGSQL</h3>

<p style="margin: 10px;">Osm2pgsql in my opinion is short or Open Street Map to(2) Post GIS Structured Querybased Language. Which means that you are getting raw osm data and loading it into postgis using sql</P>
Click here to download the windows version of osm2pgsql<br>
<br><a href="http://wiki.openstreetmap.org/wiki/Osm2pgsql#Windows">osm2pgsql</a><br>
<br>
<ul>
  <li>Download the file named osm2pgsql.zip</li>
  <li>Right click on it and unzip the file on your system</li>
  <li>You should move the unzipped folder to the osm folder you have created in local disk C</li> 
  <li>In local disk C will be the unzipped file called osm2pgsql.exe</li>
</ul>
 
<p style="margin: 10px;">This is a program that we will run to import the data, but in order for Windows to find it, we need to add its location to the system path.</p>
</article>

<article>
<h2 style="font-size: 1.6; color: blue; padding-left: 10px;">System Path</h2>
<h3 style="color: blue; font-size: 1.3;">How to Create a System Path</h3>

<ul>
  <li>Go to the control panel and there, search system path</li>
</ul>


<figure>
 <img src="www.pic-ttp1.png" alt="A picture showing how to find a system path">
</figure>

<ul>
  <li>Click on an option called “Edit the system environment variables. That looks like this:
 </ul>

<figure>
 <img src="pic.ttp2.png" alt="This picture shows what the edit system environment variables button looks like">
</figure>

<ul>
  <li>Click on the “Environment Variables” button</li>
</ul>

<figure>
 <img src="pic.ttp3.png" alt="This picture shows the environment variables tab">
</figure>
 
<ul>
<li>Scroll to the bottom and find the variable named “Path”, highlight it and click “Edit…”</li>
</ul>

<figure>
 <img src="pic.ttp4.png" alt="This picture shows where to find the variable path">
</figure>
 
<ul>
  <li>This is how you must add the directory where osm2pgsql.exe is located to the end of the Path variable.</li>
</ul>
<p>Be careful not to erase anything as this will be highlighted


<figure>
  <img src="pic.ttp5.png" alt="A picture displaying an edit system variable window">
</figure>

<ul>
  <li>Add a semicolon to the end of the previous directory and then type in the full directory path of osm2pgsql.exe. In our case, since our osm2pgsql extract is in local disk C inside the osm folder, the directory path would be:
 ;C:\osm\osm2pgsql\x64; if you are using a 62bit operating system or   ;C:\osm\osm2pgsql\x32; if you are using 32bit operating system</li> 
  <li>Click OK several times to save the new settings</li>
</ul>

<h3 style="color: blue; font-size: 1.3;">How to test if osm2pgsql functions</h3>

<ul>
  <li>Run the Windows Command Prompt as an administrator. You can do this by clicking on the Start Menu and searching “cmd”. The Command Prompt application will come up. You can rightclick on it and run as an administrator</li>
</ul>

<figure> 
  <img src="pic.ttp6.png" alt="A picture showing how to find a command prompt application">
</figure>
 

<p style="margin: 10px;">In the black command window that opens, type:</P>
<p style="width: 80%; padding-left: 5px; background-color: lightgrey;">osm2pgsql.exe</p>
<p style="margin: 10px;">If everything is working right, you should get a message like this:</p>

<figure>
  <img src="pic.ttp7.png" alt="A picture of a message expected to be returned by a command">
</figure>
 
<ul>
  <li>If you don’t see an error message like this, and it says that it cannot find the application osm2pgsql, then you may have entered the Path variable incorrectly</li>
</ul>
</article>

<article>
<h2 style="color: blue; font-size: 1.6;">Raw OSM Data</h2>
<h3 style="color: blue; font-size: 1.3;">Getting Raw OSM Data</h3>

<p style="margin: 10px;">Before we can use osm2pgsql we need to have some raw OSM data to import into a database you can download osm data from this website. <br>
<br><a href="http://download.geofabrik.de">http://download.geofabrik.de</a><br><br>.In the list of continents displayed, scroll to Africa. Then, in the list of African 
Countries displayed, find Lesotho and click on it. Then in the list of the download links of the lesotho-latest.osm formats displayed, click on the lesotho-latest.osm.pbf<br>
<br>There are two ways in which you can download this:<br>
<br>

<ol>
  <li>Just click on the link and it will automatically download to the downloads folder. Now you can find it, cut it and paste it into the osm folder in local disk C</li>
  <li>Rightclick on the link, save as and navigate to the osm folder in the local disk C, then save</li>
</ol><br>
<br>
<p style="margin: 10px;">Now you can rename to the date of the download. For example, if the download was made on the 29th of September you can edit the name it to 2909-lesotho-latest.osm.pbf. this is just to avoid confusion should there be other numerous downlodas to follow.
PBF files are compressed versions of the normal .osm files. You can use any of the extract services listed in the chapter on getting data, if you’d like the raw data.</P>
</article>

<article>
<h2 style="color: blue; font-size: 1.6;">The Style File</h2>
<h3 style="color: blue; font-size: 1.3;">How To Get The Style File</h3>
<p style="margin: 10px;">Our work goes on. In order for osm2pgsql to define which osm tags must be included in the database during import, it will require the use of a custom style file. You can download the default style file <a href="http://learnosm.org/files/default.style">here</a></P>
</article>

<article>
<h3 style="color: blue; font-size: 1.3;">How to import OSM data</h3>

<p style="margin: 10px;">Open PgAdmin III and create a new database named lesotho, just as you did in the previous chapter. In order to import osm data, we will have to run the osm2pgsql program using the command line.</p>

<ul>
  <li>Run the command prompt as an administrator by clicking on the start button</li>
  <li>Search for cmd</li>
  <li>Right click on it</li>
  <li>Run as administrator</li>
</ul>

<figure>
  <img src="pic.ttp8.png" alt="A picture of an open command prompt window">
</figure>

<p style="margin: 10px;">Here is a list of several options we will use to run the application osm2pgsql.We need at least to supply it with:</p>

<ul>
  <li>The location of the following;</li>
  <li>The lesotho-latest.osm.pbf File</li>
  <li>The name of the database, and the database username</li>
  <li>The style file which defines which OSM tags will be imported to the database</li>
</ul>

<p>We have placed our OSM file into the osm folder in disk C:\ directory to make this easier.<br>
<br>
Type the following command</p>
<p style="width: 80%; padding-left: 5px; background-color: lightgrey;">Cd C:\osm<br>
<br>osm2pgsql -c -d lesotho -U postgres -K -H localhost –P 5432 –S default.style lesotho-latest.osm.pbf</P>  
<p>Press Enter. If all goes well, the process should begin running. It may take a few minutes for all of the data to load into the database depending on the size of the data.</p>


<figure>
  <img src="pic.ttp9.png" alt="A picture of what a successful command line should return">
</figure>

<p style="margin: 10px;">If your raw OSM file is large, you may need to add additional memory to the osm2pgsql import process. To do this, add the following to the command:</p>
<p style="width: 80%; background-color: lightgrey;">--cache</P><br>
OR
<br><p style="width: 80%; background-color: lightgrey;">--slim</P>
</article>

<article>
<h2 style="color: blue; font-size: 1.6;">QGIS</h2>
<h3 style="color: blue; font-size: 1.3;">how to use QGIS and Raw OSM data</h3>

<p style="margin: 10px;">We can test that the import was successful and view the data loaded in our Post GIS database using QGIS.
<ul>
  <li>Open QGIS and click on the “Add PostGIS Layers” button</li> 
  <li>Under “Connections” at the top, click “New”</li>
  <li>Give the new connection a name. Under database type lesotho (the name of your database)</li>
  <li>Enter the username postgres and your password credentials, same as the one entered when installing PG Admin below</li>
</ul>

<figure>
  <img src="pic.ttp10.png" alt="A picture displaying a connect a new database window">
</figure>

<ul>
  <li>Click OK to save the connection settings. Then click “Connect” to connect to your PostgreSQL server</li>
  <li>Click on the + sign next to “public” to expand all of the layers (tables) in your database. Notice that osm2pgsql creates a separate table for different object types - points, lines, and polygons. It also creates a roads table, which contains only major roads.</li>
</ul>

<figure>
  <img src="pic.ttp11.png" alt="A picture showing a list of all the tables/layers of our database">
</figure>

<ul>
  <li>Select one or more of the layers and click “Add.” If asked, choose WGS84 as the CRS</li>
  <li>If everything is successful, you will see the layers you selected displayed in QGIS</li>
</ul>

<figure>
  <img src="pic.ttp12.png" alt="A picture displaying a view of data when tables/layers are added in QGIS">
</figure>

<aside style="width: 80%; margin-right: auto; font-size: 1em; background: #eeff99; padding: 20px; border: 1px solid #696; border-radius: 20px;">
NB
<p style="margin: 10px;">When you want to import OpenStreetMap data into your own database, osm2pgsql is a great tool which can be extremely useful when you need to be able to get the most up-to-date OSM data. We have already seen another great tool called IMPOSM used harness osm data and use it in QGIS.
For more infor, see; http://wiki.openstreetmap.org/wiki/Osm2pgsql</p>
</aside>
</article>

<article>

<h2 style="color: blue;">Digitizing</h2>
<h3 style="color: blue; font-size: 1.3;">How to draw a settlement layout using Qgis</h3>

<p style="margin: 10px;">A huge thanks to all of the MapLesotho users because Lesotho now has a basemap. this means that, data is available in abundance for you to utilize. you have seen in the previous 
topics how you can access and store this specific data locally on our PCs and even convert it to postgis layer/tables. you have seen also how to add it as postgis tables in Qgis. In order to draw a perfect settlement layout, you may need the following:</p>
<ul>
  <li>offline satellite images</li>
  <li>landuses around the planning area</li>
  <li>fieldpapers for field verification</li>
  <li>to create your own shapefiles</li>
</ul>
<p>This is where utilization of #MapLesotho osm data comes in handy. If you take a moment to think about what tags were applied when drawing landuses, such as forests, farmlands, 
residential areas,wetlands e.t.c, you will realise that we used tags like</p><p style="width: 40%; background-color: lightgrey;"> "natural" IN ('wood','water','scrub','scree','shrub').</p> <p>Also, tags such as</p><p style="width: 25%; background-color: lightgrey"> "landuse" IN ('residential','farmland')</p><p> were also applied. For the mobility part of your about to be proposed settlement layout, you can think of the</p><p style="width: 25%; background-color: lightgrey"> 'highway' tag</p><p> and for the green infrastructure you may 
need tags like</p><p style="width: 25%; background-color: lightgrey;"> 'waterway' In ("river", "stream", "weir")</p> <p>as well as</p><p style="width: 25%; background-color: lightgrey"> "water" IN ('wetland','pond','lake').</p><p> There are whole lot more that are not mentioned in this article but eventually, 
this is the data available for us to use. The trick is to add this data first before you add your offline maps in order for this two to overlap onto each other. This article 
will guide you through all of that. This topic's images are not of good quality compared to that of the previous topics.</p>

<h3 style="color: blue; font-size: 1.3;">How to add osm data into qgis</h3>
<p style="margin: 10px;"> we have already seen this in the previous topic. however, this time, you are going to learn how to filter through the entire osm planet for the specific data you need. 
For example, if you need only the primary and the secondary roads. right after converting osm data into postgis tables, you will realise that, we will be having planet_osm_line, 
planet_osm_polygon and planet_osm_point. planet_osm_line contains evrything that was mapped as a line, an example of this could be roads, rivers and powerlines. in our case,
planet means the entire country. the samething goes for plane_osm_point and polygon. So, if you want to add primary and secondary roads to your map in qgis, first consider which table it will
fall under. Remeber, roads are drawn as lines, and this means that, it will fall under planet_osm_line.</p>
<figure>
  <img src="chuz.jpg" alt="A picture showing a list of postgis tables to choose from in Qgis">
  <figcaption>select planet_osm_line and the click the filter button</figcaption>
</figure>
<p style="margin: 10px;">now will be a good time to apply the "where clause" of SQL if you have already learned it. But if not yet, then you can quickly google this: <a href="http://rustyb.github.io/lesotho_manual">rustyb.github.io/lesotho_manual</a> because you will need
it.</p>
<figure>
  <img src="whereclause.jpg" alt="A picture showing where to add your where clause">
  <figcaption>in the list above, navigate to highway and doubleclick on it, click on the IN button in the operator panel, insert brackets, make sure that highway is 
highlighted and click the all values button, scroll to find primary, doubleclick on it, insert a comma, then doubleclick on secondary. make sure though that primary and
secondary are inside the brackets. you will have a "where clause" like this<p style="width: 25%; background-color: lightgrey"> 'highway' IN ("primary","secondary").</p> Click ok.</figcaption>
</figure>
<p style="margin: 10px;">click ok again. this will only add primary and secondary roads only instead of the entire planet_osm_line</p>

<h3 style="color: blue; font-size: 1.3;">How to add offline sattellite images</h3>

<p style="margin: 10px;">you have now learned how to add and filter through osm data, now you will learn how to add offline sattellite images. Adding offline sattelite images is as simple as this:</p>
<ul>
  <li>go to add raster layer</li>
  <li>click browse and browse to where you have stored them on your PC</li>
  <li>select them</li>
  <li>click ok/add</li>
</ul>

<h3 style="color: blue; font-size: 1.3;">How to create a shapefile</h3>
shapefiles are exactly what you need in order to digitize in Qgis.

<figure>
  <img src="createlayer.png" alt="A picture showing how to create a shapefile">
</figure>

<figure>
  <img src=![shapefile.png](https://user-images.githubusercontent.com/17254752/29928611-294667de-8e05-11e7-8dc3-c54c88232b08.jpg)alt="A picture displaying what a create a new shapefile window looks like ">
  <figcaption>If it is a polygon you want, you can select it, then enter your name field (it could be something like existing or proposed). Select text data for type in this case.
click the add to field list button and then ok. your shapefifle will be created and will prompt you to save as. Then, it will be added to the layers panel in Qgis.</figcaption>
</figure>
 <aside style="width: 80%; margin-right: auto; font-size: 1em; background: #eeff99; padding: 20px; border: 1px solid #696; border-radius: 20px;">That will be all for this
 article, but for further instructions on how to digitize a settlemet layout, applying planning standards (urban design), please visit my blog post at:
<a href="https://www.maplesotho.com/blog/2017/03/16/bye-bye-arcgis/">https://www.maplesotho.com/blog/2017/03/16/bye-bye-arcgis/</a></aside>

</article>
</section>

<footer style="width: 100%; background-color: green; color: white; margin-right: auto; margin-left: auto; height:50px; padding-bottom: 50px;">

<small style="font-size: 1.3;">Article by Refiloe Semethe and Inspired by:</small>
 <a href="https://www.maplesotho.com/"><figure style="margin-right:auto; margin-left: auto;">
  <img src="maplesotho-logo-pos.png" alt="#Maplesotho logo">
</figure></a>

</footer>
</body>
</html>
