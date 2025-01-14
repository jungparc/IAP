## Mobile Service > IAP > STEAM Console Guide

> This document describes how to register and integrate information from apps released with Steamworks with the [NHN Cloud IAP](https://docs.nhncloud.com/ko/Mobile%20Service/IAP/ko/Overview/) console.
For more information on releasing a Steam app, see the [Steamworks Guide](https://partner.steamgames.com/doc/home).


## Enter Basic Information

Make sure you enter the following three pieces of information correctly to connect to Steam

Information about the integration is generated by[Steamworks](https://partner.steamgames.com/).

For other topics not covered on this page, see the **Mobile Service > IAP > [Console Common User Guide](https://docs.alpha-nhncloud.com/ko/Mobile%20Service/IAP/ko/console-guide/)** page.


![NHN Cloud IAP App Settings](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_iap/console_steam/steam_console_app_01_kor.png)


### Steam App ID

* A unique identifier for your app that you receive after registering your product in Steamworks.
* Enter the App ID as shown in **Steamworks > App Admin >** (Project Name).

![STEAM App ID](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_iap/console_steam/steam_console_app_02_kor.png)


### Steam Web API Key

* This information is required to access the [ISteamMicroTxn Interface](https://partner.steamgames.com/doc/webapi/ISteamMicroTxn)(Steam Payment API).
* In **Steamworks > Users & Permissions**, enter the value of your newly created or existing issued key.
    * See [Steamworks Publisher Web API Key](https://partner.steamgames.com/doc/webapi_overview/auth) for more information.

![STEAM Web API Key](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_iap/console_steam/steam_console_app_03_kor.png)


### Steam Default Currency

* You can set a default value for the currency code applied to an item's price when a user attempts to make a purchase and enters the Steam Checkout overlay.
* If no currency code exists in the item information that matches the currency of the user's Steam Wallet, the price of the item is output in the default currency set in this item.
    * See **Enter country-specific sales item information** in the **Setting up sales items** section.


![STEAM Default Currency](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_iap/console_steam/steam_console_app_04_kor.png)



## Set up items for sale

NHN Cloud IAP supports the [Steam Microtransaction API](https://partner.steamgames.com/doc/features/microtransactions).

![Set up NHN Cloud IAP Items](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_iap/console_steam/steam_console_app_05_kor.png)



### Enter item basic information

- **Item name**: Enter a representative name for the item you manage through the IAP console.
- **Store Item ID**: Enter the item ID that your app manages.

> The Store Item ID for each item must be entered as a unique value and can only be of type `uint32`.
> Number between 0 and 4,294,967,295

- **Product Type**: Currently supports only consumable items`(CONSUMABLE`).


### Enter country-specific sales item information
Make sure when entering and editing the name and price of the item, as this is the information that will actually be charged to the user who attempts to make the purchase.

- **Language code**: Select the language code that corresponds to the item name that will appear in the checkout.
- **Country-specific item name**: Enter the name of the item that you want to sell in the selected currency code.
- **Currency code**: Select the currency code that corresponds to your sales price.
- **Selling price by currency**: Enter the price that corresponds to the selected currency code.


> The price information corresponding to the default currency code in your app's settings is required.
> If more than one price is entered, payment information is generated with the price that corresponds to the currency code of the item in the user's Steam Wallet.
> (If none of the item information entered corresponds to the currency code of the user's wallet, the payment information is generated in the default currency code). 