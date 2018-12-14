# API Docs

Welcomet to the Harbor API.  Today we only expose a couple of elements of our API during the alpha.  Everything in the system is accessible via the API (such as adding users, beacons, foghorns, etc.), but we won't be exposing those endpoints until the beta relase.  But for now you can do the two most important things on the system.  Send __beacon messages__ and connect to a __wss stream__ to view and manipulate those messages in your custom code.

If you want to quickly brush up on our terminology, feel free to take a quick refresher at the [Basic Terminology](basic-terminology.md).

Before you start using the API you will also need to set up your app in the [Harbor UI](https://cloud.hrbr.io/).  Click here for a [Quick Start Guide](quick-start-guide.md) for complete instructions on how to do that.

---
## Short Cut
Don't like reading docs.  Here is a quick Curl Example and a super easy Postman link to dive right in.

### Curl
```
curl -X POST \
https://harbor-stream.hrbr.io/beacon \
-H 'Content-Type: application/json' \
-H 'apiKey: YOUR_API_KEY' \
-H 'appVersionId: APP_VERSION_ID' \
-H 'beaconVersionId: BEACON_VERSION_ID' \
-H 'cache-control: no-cache' \
-d '{"Message": "Hello from curl and Harbor!"}'
```
### Postman

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/7f988710d5854865c0e5)

___
## What you need from cloud.hrbr.io

### Get your apiKey

Currently Harbor uses your apiKey to authenticate all requests.  You can find your apiKey under your avatar at [Harbor Cloud]("https://cloud.hrbr.io/#") by clicking your avatar in the upper right hand corner.  ![apiKey](img/api-docs/find-apikey.png)
App Harbor UUID__

### Get your appVersionId

You will have to have an app registered in the [Harbor UI](https://cloud.hrbr.io/#!/apps/list).  You can find the AppVersionId on the applications page.

!!! Warning
    You want to use the __AppVersionId__ not the __App Harbor UUID__.

![appVersionID](img/api-docs/app-version-id.png)

### Get your beaconVersionId

The beaconVersionId will also need to be registered for the related appVersionId.  You can find it by hitting the pencil icon on the app page.

![beaconVersionId](img/api-docs/beacon-version-id.png)

---
## Send Beacon messages

The basis of all that is Harbor. Send a boat load of messages.  Why not the first 5 million every month are free.  So let's start sending.

### Beacon Message Parameters

The basic format of a Beacon message is an `HTTPs` post with 7 header fields.

!!! info
    The url for sending a beacon is `https://harbor-stream.hrbr.io/beacon`

Paramater  |Value   |Paramater<br> Type   |Data<br> Type   |Req?|Description
:---|:---|:---|:---|:--|:---
Content-Type|`application/json`   |  header  |string   |__YES__|Lets us know we are getting JSON
apiKey  |`YOUR_API_KEY`   |header   |string   |__YES__|  Your API Key
beaconVersionId  |`BEACON_VERSION_ID`|heder   |string   |__YES__|The name of the beacon you are sending
appVersionId  |`APP_VERSION_ID`   |header|string   |__YES__|The ID of the app in Harbor you want this beacon to identify with
beaconInstanceId  |`UNIQUE_SYSTEM_ID`   |header|string   |__NO__|Takes an identifier suce as a `HOSTNAME` or `MAC address` so you can tell what system sent the beaon
beaconMessageType  |`TYPE_OF_MESSAGE`   |header   |string |__KIND_OF__|  This is a meta field that allows you to look at similar beacons from multiple beaconVersionId's.  While this field is not mandatory, most of the UI features in `cloud.hrbr.io` require a beaconMessageType.
dataTimestamp  |`TIME_STAMP_FROM_BEACON`   | header  |string   |__NO__   |  Harbor will put a timestamp on every message received at the time it is received.  If you are sending delayed messages or want the exact time something occured on your system you can add your own timestamp.

### Curl example

### Postman example

If you are a postman fan you can click here to get a template for you beacon message post.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/7f988710d5854865c0e5)


## Connect to Beacon stream

Connecting to a beacon stream is a little different than a standard https post or get as we send the streams down a web-socket.
