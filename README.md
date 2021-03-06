# Exploring Armenia's Energy and Water Resources

[Link to the story map](https://usaid.maps.arcgis.com/apps/MapJournal/index.html?appid=7d94bc889b3c4ff5bc892de734498dd0#map)

![](https://github.com/chongzhiyang/essay/blob/master/img/overview.png)

## Introduction

The story map talks about the energy and water resources in Armenia in Asia, especially the production of electricity. Armenia has three main sources to produce electricity to power all over the country, thermal, nuclear, and hydropower, around 43% of total electricity production in Armenia are produced by nuclear power plants. Moreover, the story map has multiple maps showing the location of major infrastructure to Armenia’s power grid. More importantly, the renewable sources to produce electricity in a sustainable way to solve the increasing demand of electricity in Armenia. Audiences of this story map can be everyone around the world, and people who interested in the usage of resources and electricity production in Armenia.

## Major function

* Understanding the production of electricity with renewable and nonrenewable sources to solve the increasing demand.
* Explaining distribution and amount of water resources in Armenia. Also, the potential water problems in overuse water resources.
* Types of renewable and nonrenewable sources were used to produce electricity.

  Renewable | Nonrenewable
  ------------ | -------------
  Wind | Thermal
  Solar | Nuclear
  Hydropower |

## Author

The story map is created by GeoCenter in United States Agency for International Development (USAID). USAID is an independent agency, nonmilitary, that responsible for helping foreign countries and providing development, economic assistance. All programs in USAID are authorized by the Foreign Assistance Act that signed by former President John F. Kennedy in November 3, 1961. Africa, Asia, Latin America, the Middle East, and Eastern Europe are the focus of USAID. (Wikipedia)

## System architecture

According to the lecture material in week 2, the system architecture of this story map has two major components, external internet and internal network. The external internet is the web client, the web browser I used to access the story map. And the internal network has several servers to store the data of the story map. For example, js.arcgis.com stores the JavaScript functions were used in the story map, and the story map retrieved data from that server to make the functions working properly. Moreover, only the administrator can edit the story map to prevent other users to change the contents of the map.

## Libraries

Unlike the leaflet libraries we used in class project, this story map mainly used ArcGIS libraries, JavaScript and CSS style sheet. These libraries bring multiple functions in the story map, such as legend, locator, and labels. Also, `https://js.arcgis.com/3.32/esri/dijit/BasemapGallery.js` provides base maps for the website.

![](https://github.com/chongzhiyang/essay/blob/master/img/library.png)

## Codes
```html
<div id="esri.Map_0_root" class="esriMapContainer" style="width: 400px; height: 850px; direction: ltr;">
<div id="esri.Map_0_container" class="esriMapContainer" style="position: absolute; cursor: default; touch-action: none; clip: auto;">
<div id="esri.Map_0_layers" class="esriMapLayers" style="left: 0px; top: 0px;"><div id="esri.Map_0_World_Light_Gray_Base_1486" style="position: absolute; width: 400px; height: 850px; overflow: visible; transform: translate(0px, 0px); display: block;">
<div style="position: absolute; width: 400px; height: 850px; overflow: visible; transition: -webkit-transform 500ms ease 0s;">
<img id="esri.Map_0_World_Light_Gray_Base_1486_tile_12_0_0" alt="" class="layerTile" src="https://server.arcgisonline.com/ArcGIS/rest/services/Canvas/World_Light_Gray_Base/MapServer/tile/12/1547/2549" style="width: 256px; height: 256px; visibility: inherit; transform: translate(-121px, -227px);">
```
When the client accesses the story map, the codes will receive the base map from ArcGIS server and insert the base map into the story map with some changes according to the codes above. The code also includes the size and position of the base map. Also, the sources tag in the DevTools shows more details of the base map files. As the image below shows that multiple small parts of the map combined to compose a whole base map.

![](https://github.com/chongzhiyang/essay/blob/master/img/sources.png)

```JavaScript
function defineDojoConfig()
{
	var path1 = location.pathname.replace(/\/[^/]+$/, '/');

	window.dojoConfig = {
		parseOnLoad: true,
		isDebug: false,
		useDeferredInstrumentation: true,
		async: !app.isProduction,
	  has: { "esri-webgl-max-contexts": -1 },
```
The part of codes above, `function defineDojoConfig()` is the configurations parameter for the dojo loader and parser. Dojo loader loads the JavaScript files synchronously or asynchronously, and dojo parser is the function that covert HTML codes into dojo widgets. Within the fucntion, `isDebug` sets the debug level, in this case, false is the input, which means the debug function is off. And `parseOnLoad` is true, then dojo parser parses HTML document and converts them to dojo widgets automatically. Finally, `async` decides the javascript modules should load synchronously or asynchronously.

Furthermore, the toggle device toolbar functions in the Google chrome DevTools, it shows that the story map supports responsive design, and mobile. However, in mobile devices, the website only can show limited information, in order to view more detail of the map, users need to click some bottoms. Overall, using computer to visit the story map has the most features and more details, it is better for users to understand the story.

## Base map

In this story map, it uses some base maps from ArcGIS to show different types of data, such as thermal map, satellite image map, topographic map, and light grey map. Each map has a different function, for example, a light grey base map is perfect to show the Armenia’s power grid, without any distraction from the base map. On the other hand, satellite image map can show the overview of the Metsamor Nuclear Power Plant with details. Finally, the thermal map can represent the wind speed in different area, give audiences an idea that the best place to be a wind farm.

## Map element

Each map has a legend that explains the content of each map, except the satellite image map. Also, all the maps have a home bottom to return to the default zoom level, zoom in and zoom out functions, if users want to see more information in a certain area, such as the name of the city. Some of the maps have a popup function that includes a detailed description of each marker. However, there are no scale bar and north arrow to indicate the directions.

![](https://github.com/chongzhiyang/essay/blob/master/img/mapelement.png)

## Strength and Weakness

The story map has lots of contents that explain the production of electricity, and each page has a map that shows some data relate to the topic. Giving audiences an overview of the electricity production and water resources in Armenia. The map includes the power grid to show the distribution of infrastructure, the choice of location, and how electricity transfer across the country to meet the increasing demand.  In the wind power section, the information includes a diagram to explain how wind power can produce electricity, and it is beneficial for audiences that did not know wind power before. More importantly, the global warming problem brings lots of attention to develop or find the renewable, sustainable resources, so the renewable and sustainable method to produce electricity will be more popular. There is a navigation bar that allows users to skip several pages to reach the page they want to read. Legends and popups give more information and visualization about the topic of each page.

However, the story map does not include in depth knowledge or information, only some basic ideas to introduce each topic. If some audiences want to know more about the topic, they need to do some research by themselves. The story map has total 18 pages, and 17 pages have a map that has different data, which is 17 maps. In my opinion, it is good to have a visualization, but too much of visualization, maps, will create confusion because most of the maps look familiar, many of them are light grey base map. There are many data included for each marker, then users will spend most of the time to read all of markers, and some data do not tell what they are representing. Also, the dots in the navigation bar are too small, users will often misclick to other pages. I think a horizontal navigation bar on the top of the page is better because there is more space in the horizontal direction, then more space between each dot on the navigation bar.

## Thoughts

As I mentioned before, global warming is a huge issue that relates to everyone in the world. Therefore, renewable sources and sustainability become more popular in these days because renewable and sustainable sources can provide power while without damaging the environment. In this story map, it talked a lot about renewable sources for electricity, such as solar, wind, and hydropower, these sources could provide a long-term efficient power. Gasoline is still the main fuel for most of the cars on the streets, but in these days, we see more and more electric cars and other transportation tools powered by electricity on the streets. Gasoline is a limited resource, and it is one of the main sources that produce carbon dioxide. There are growing concerns about the impact of global warming during the recent decades, many car companies developed and began to manufacture electric cars because electricity can produce from renewable and sustainable sources, as the story map talked about. Also, electricity is much cheaper than gasoline, thus electric cars become more popular nowadays. In my opinion, developing a new type of source of power is difficult, it is better to use what we have now, but use it in a new way that is sustainable and renewable. The impacts of global warming are already causing lots of problems. In 2019, due to the increasing temperature in Australia, the wildfire already burned acres of lands, destroyed the home of wildlife, threatened the lives of residents. We should keep working on the way to prevent further damage to our environment because we only have one Earth.

## References

https://usaid.maps.arcgis.com/apps/MapJournal/index.html?appid=7d94bc889b3c4ff5bc892de734498dd0#map

https://en.wikipedia.org/wiki/United_States_Agency_for_International_Development

https://dojotoolkit.org/
