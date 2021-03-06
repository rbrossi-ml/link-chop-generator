# CHOP Link Generator CLI 

This app generates Links from CHOP Checkout APP based on a CSV file. 

It is a CLI (Command Line Input) tool that have two main options.

![plot](./images/cmd2.png)

## Pre-requirements

* node/10.16.0 installed 
* Darwing system (MAC/OS)
* Connected to MeLi VPN

**Note:** This version was not tested on a Windows Machine

## Installation process 

Select some place in your machine and them clone the repository application. 

using HTTPs:  
```kotlin 
    git clone https://github.com/rbrossi-ml/LinkCHOPGenerator.git
```
or using SSH: 
```kotlin 
    git clone git@github.com:rbrossi-ml/LinkCHOPGenerator.git
```
run npm install inside the product folder.

```kotlin 
    npm install
```
to link the application to your operational system, inside de application folder run. 

```kotlin 
    npm link
```

Now you can start use the CHOP Link Generator CLI

You also need to configure the <code>.env</code> file. Its imporntante to define the API url, the environment is configured as follows: 

1. Create the <code>.env</code> file into the app root folder.
2. Place the information bellow into it

## Example of a .env file 
```
NODE_TLS_REJECT_UNAUTHORIZED=0 
SSL_CERT_FILE="/usr/local/etc/openssl/cert.pem"
API_URL="https://internal-api.mercadopago.com/tlv-chop-checkout/api/checkout"
```
## How to? 

### Through a CSV file.
Select some folder were you can donwload your CSV File. 

The structure of this file have to follow the rules bellow in terms of hearder's name. 

| Field/Header name | Description | 
|-------------------|:------------| 
| Device_Name |        `Device name` 	|
| Device_ID	   |     `Device ID`
| Cupon Origen	|    `Cupon origim (Marketing tools)`|
| Cupon Link	|        `Cupon Link (Marketing tools)`|
| utm_campaign	 |   `Marketing campaign that this link will be associated`|
| utm_source      |    `Source of this link come from`	|
| utm_seller	  |      `Agency or EPS associated to it`|    
| Link	          |  `Empty field`  |  
| Short URL       |    `Empty field`|

Example of a Excel file, source of this tool inputs
![plot](./images/sample1.png)

Export it into a <code>CSV</code> file

and then run the command 

````
# link csv <src_folder>/<src_file>.csv <dest_folder>/<dest_file>.csv
````
The result is an CSV file (i.e. named with your output file name option) within fields <code>Link</code> and <code>Short URL</code> filled in.   

Based on a Google spreadsheets,  to import the results based on a csv file goes through the "File" and then "Import" options.

Select import in a new tab/spreadsheets and hit the import button.
![plot](./images/import.png)

Open the results. It will be present as follows: 

![plot](./images/result.png)


### For only one Link (chop option).

To run this tool to generate only one link, please do the follow 

````
# link chop <device_id> <cupon> <utm_coupon> <utm_campaign> <utm_source> <utm_seller> 
````
Mandatory parameters:

| Parameter name | Description | 
|-------------------|:------------| 
| device_id	   |     `Device ID`
| cupon	|    `Cupon origim (Marketing tools)`|
| utm_campaign	 |   `Marketing campaign that this link will be associated`|
| utm_source      |    `Source of this link come from`	|
| utm_seller	  |      `Agency or EPS associated to it`|    

The result will be the short url and long url displaied in your console client.

## This project strucutre

|Folder name| Description|
|-----------| :----------:|
|EXAMPLE| Example of CSV generation |
|images| Documentation's image repository| 


## In case of any doubt
pleade let us know 
ayuda-point-tlv@mecadolivre.com