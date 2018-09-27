# Overview

Trivver is advertising platform that allows advertisers to place real branded assets as 3d models in various applications. It runs on various platforms. Each platform is supported via it's own SDK.  
Right now there are 3 SDK's:

* Unity SDK
* Android native SDK
* iOS native SDK  

Each SDK allows to support specified platform. For more details proceed to special section.

Here is quick overview of the system:

![Trivver main image](.gitbook/assets/trivver-main-diagram%20%281%29.png)

**Advertisers** provide [branded assets](xref:unity-branded-asset-term) i.e. 3d models that represent advertisable products, for example 3d model of branded TV or a car of some popular brand.

**Developers** using Trivver tools \(SDK\) display branded assets in their apps.

**Developer’s application** at runtime requests branded assets from the server and after successful download displays them to the users.

**Users** can see downloaded at runtime [branded assets](xref:unity-branded-asset-term) while using app. Trivver will collect branded assets viewability and engagement statistics and send it to the server. From this statistics system calculates advertiser’s charges and developer’s revenue.

**Server** stores [branded assets](xref:unity-branded-asset-term) and gives them to the app as it requests it.

**Trivver App** is an application that user can download from store and use it to see all collected data about all branded assets that were available while using developer's app.

