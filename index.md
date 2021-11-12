# Welcome to the locator.stanford.edu Geocoder
## Introduction
The Stanford Geospatial Center has been developing our internal geocoding infrastructure. This is our ALPHA Geocoding Server, based upon Esri's ArcGIS Server technology. The server currently provides geocoding services for:
* **US Street Addresses**
* **Street Addresses**, **Place Names**, **Administrative Units**, and more, for _**North and South America**_
* **Reverse Geocoding**

## NEWS!!
A replacement server for locator.stanford.edu is currently being developed and should bring expanded Global Geocoding Services, as well as performance and stability improvements to our geocoding services. This project is being implemented in a partnership between Stanford Library's [Digital Library Systems & Services Division](https://library.stanford.edu/department/digital-library-systems-and-services-dlss), and the newly formed [Research Data Services Division](https://library.stanford.edu/data-services).

The following are components of the project:

* **Global Geocoding, Gazetteering and Reverse Geocoding** Services
* Scalable and sustainable Linux-based multi-server architecture providing **support for multiple simultaneous and sustained bulk geocoding requests**
* **Service Level Agreement** (SLA) with uptime, performance and security commitments and protocols
* **A Service Use Agreement**, detailing the responsibilities of researchers using locator.stanford.edu services with regards to **Data Use & security, Publication, Sharing and Data Risk Levels & Privacy Issues**
* **Expanded support offerings**, including new Support Documentation, Workshops, and Python & R Notebooks for getting started


### Some important points about the current service:

* The service **should not be used** with **PHI, Protected Health Information (PHI), or other types of [High Risk data](https://uit.stanford.edu/guide/riskclassifications). Users wishing to work with data related to human subject should consult with IRB for policies concerning de-identification of data and other privacy issues.
* The locator.stanford.edu service uses **https**
* The locator.stanford.edu service **does not** log geocodes made against the service
* Data passed to the service for augmentation **is not retained**
* The locator.stanford.edu geocoding service is **hosted on Stanford hardware within the Stanford Network**.
* This service is meant to be used for bulk geocoding of **thousands to millions of placenames and/or addresses**
* The service is provided **for use by Stanford researchers**, but is in ALPHA, currently, and **does not carry any Service Level Agreement, or guarantees of performance or uptime**
* The service is in development, and may be inaccessible at some times. When maintenance  requires the services to be turned off, we will post messaging for users to our [stanfordgis@lists.stanford.edu list](https://mailman.stanford.edu/mailman/listinfo/stanfordgis), as well as our Slack, which you can join at https://stanford-geospatial.slack.com

## Signing into locator.stanford.edu Services  

Because the locator.stanford.edu services use Windows Group authentication, it is necessary to use the Windows Domain before you SUNetID, in order to authenticate, like so:  

`WIN\put_your_SUNetID_here`

**Please be careful when using your credentials in code, and never put them in repositories that sync to public views.**

## Accessing locator.stanford.edu services
### Using Esri Desktop clients
#### ArcGIS Desktop
- In ArcCatalog, or the Catalog Panel in ArcMap, expand the GIS Servers item
- Double-click the Add ArcGIS Server item
- Leave the default "Use GIS Services" option, click Next
- For the 'Server URL' use: https://locator.stanford.edu/arcgis
- For 'User Name' use your SUNetID (prefixed with the 'WIN\' domain) as WIN\SUNetID
- Enter the password associated with your SUNetID and check the option to Save Username/Password
- Click Finish


#### ArcGIS Pro

- When ArcGIS Pro launches, use the ArcGISOnline login at the top right of the software to login to our Stanford ArcGIS Portal, (using our organizational url:**stanford.maps.arcgis.com**, and using your typical Single Sign-on credentials (_WITHOUT_ ```WIN\```, _this time_).
- Once logged into stanford.maps.arcgis.com, through ArcGIS Pro, you should see the Stanford **Latin America and North America Geocoders** & the Stanford **US Streets Locator** as options in your Catalog>Locators panel

#### ArcGIS Online

### Accessing through the REST API

You can login to locator.stanford.edu services at https://locator.stanford.edu/arcgis/ using WebAuth, and the ```WIN\your_SUNetID_here``` format described, above.

#### Service Endpoints are as follows (all endpoints require authentication):
* [US Street Addresses](https://locator.stanford.edu/arcgis/rest/services/geocode/USA_StreetAddress/GeocodeServer) - https://locator.stanford.edu/arcgis/rest/services/geocode/USA_StreetAddress/GeocodeServer
* [Latin America Composite](https://locator.stanford.edu/arcgis/rest/services/beta_geocoders/LatinAmerica/GeocodeServer) (Street Addresses, Place Names, Administrative Units, and Reverse Geocoding) - https://locator.stanford.edu/arcgis/rest/services/beta_geocoders/LatinAmerica/GeocodeServer
* [North America Composite](https://locator.stanford.edu/arcgis/rest/services/beta_geocoders/NorthAmerica/GeocodeServer) (Street Addresses, Place Names, Administrative Units, and Reverse Geocoding) - https://locator.stanford.edu/arcgis/rest/services/beta_geocoders/NorthAmerica/GeocodeServer


#### R & RStudio

Our colleague, [Claudia Engel](https://profiles.stanford.edu/claudia-engel), from [The Center for Interdisciplinary Digital Research](https://library.stanford.edu/research/cidr), has created a repository with support materials for accessing the locator.stanford.edu services, from R and RStudio:

* [cengel's ArcGIS_geocoding for R Repo on Github](https://github.com/cengel/ArcGIS_geocoding)

#### Python
You can access the locator.stanford.edu services, directly, using the ArcGIS REST API. The use of the API is well documented in the [ArcGIS REST API Services Reference](https://developers.arcgis.com/rest/services-reference/enterprise/get-started-with-the-services-directory.htm), and in particular the following sections:  
* [Geocode Service](https://developers.arcgis.com/rest/services-reference/enterprise/geocode-service.htm)
* [Geocoding Tools](https://developers.arcgis.com/rest/services-reference/enterprise/batch-geocode.htm)
* [Generating Tokens](https://developers.arcgis.com/rest/services-reference/enterprise/generate-token.htm)

The Stanford Geospatial Center has a Github repository that contains some resources for accessing the locator.stanford.edu services, using Python:

* [StanfordGeospatialCenter's SGC-Python-Geocoder repository on Github](https://github.com/StanfordGeospatialCenter/SGC-Python-Geocoder)

### More Information

[Esri's "Introducing Geocoding" documentation][b0c35cd8]

  [b0c35cd8]: https://desktop.arcgis.com/en/arcmap/10.3/guide-books/geocoding/what-is-geocoding.htm "Esri's Introducing Geocoding documentation"
