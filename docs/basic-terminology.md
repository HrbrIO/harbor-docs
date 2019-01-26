Hrbr

# Basic Terminology
Here is a quick guide to terms we use at Hrbr.  We know it's a lot of nautical terms, but you can be happy we didn't call these guides Hrbr Docks.

|   |   |
| :--- | :--- |
| User       | It's starts with you.  You can use your Google ID, GitHub ID, or you e-mail to identify you as a user.|
|Organization| All Users must be part of an organization.  That way multiple members can create inputs, get insight or take action on that shared data.
|Application|Since Hrbr is designed with  the developer in mind, all of the functions are grouped by application.  That way you can see information pertinent to an application regardless of how many systems it's running on or our many other applications are running on that system.
|Beacon|A Beacon is anything that collects information from an application.  Generally Beacons can be implemented in one of three ways.
|Beacon Types|<ul><li>Code directly integrated in an application.  You can write calls to Hrbr directly into your app to start tracking what's going on inside of your application.<li>Install a pre-written Beacon as a package in your app.  Find a Beacon in the catalog that servers your purpose and follow the instructions to install it as a package/library into your existing application. Often these pre-written packages will allow you to more simply write calls to Hrbr into your existing application.<li>Stand-alone Beacons.  These Beacons will sit outside your application and can be useful for gathering system information or on third party apps such as databases.  A number fo these stand-alone Beacons are also available in the Catalog.</ol>
|Foghorn|Foghorns listen to streams of data from Hrbr Services in order to send an alert to humans are systems.  There are two basic implementations for a Foghorn.
|Foghorn Types|<ul><li>Internal Foghorns.  Use the Hrbr UI to create a simple Foghorn to start immediately being notified of changes in your applications performance.<li>External Foghorns.  Hrbr allows you to directly subscribe to streams of data from Hrbr to use in any system set alerts or actions.
|View|Charts and graphs to quickly visualize what's going on with the your data.  Grouped by application a View is a collection of any number of different types of charts.
|Tug|Similar to Foghorns, tugs grab streams of data and perform actions against that data as opposed to simply alerting on the data.  Internal Tugs are not implemented in the Alpha Version of Hrbr, but have it with your own code.  The possibilities are endless.
