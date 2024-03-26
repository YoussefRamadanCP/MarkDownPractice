# FSC-GetCoCRecordByMemberShipID
## Introduction
The objective of this document is to present API specification (between API clients and Apigee) including methods, URLs, request/response body formats, etc

## Security
So in order to make the proxy more secure we have created an OauthV2 Bearer token API and added Bearer Authentication to all proxies, you have to send the Token Api called **OAuth-Generate-Token** a request in order to get back a valid bearer token to use for the API’s Bearer Authentication.

## Proxy Configuration
#### Target Servers
[Target Servers Environment URL](https://edgeui-preprod.rega.gov.sa/platform/rega/environments/development/target-servers).

###### Target Server Configuration 
  
```xml
<TargetServer name="GSB">
 <IsEnabled>true</IsEnabled>
 <Host>192.168.12.34</Host>
 <Port>80</Port>
 <SSLInfo/>
</TargetServer>
```

Dillinger is a cloud-enabled, mobile-ready, offline-storage compatible,
AngularJS-powered HTML5 Markdown editor.

- Type some Markdown on the left
- See HTML in the right
- ✨Magic ✨

## Mediation

##### Query Parameters (Client Request to Proxy)

```
* Means Query parameter is required

Name: cocMemberChamberCity *
Type: integer

Name: cocMemberId
Type: string
```
##### Proxy Request to Backend
```xml
           <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:tem="http://tempuri.org/">
                <soapenv:Header/>
                <soapenv:Body>
                    <tem:GetCoCRecordByMemberShipID>
                        <tem:cocMemberChamberCity>301</tem:cocMemberChamberCity>
                        <tem:cocMemberId>5</tem:cocMemberId>
                    </tem:GetCoCRecordByMemberShipID>
                </soapenv:Body>
            </soapenv:Envelope>
```

##### Backend Response To Proxy
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<soapenv:Envelope
	xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
	xmlns:tem="http://tempuri.org/">
	<soapenv:Header/>
	<soapenv:Body>
		<GetCoCRecordByMemberShipIDResponse>
			<tem:GetCoCRecordByMemberShipIDResult>
				<tem:CoCMembershipDetails>
					<tem:CoCMembershipID>5</tem:CoCMembershipID>
					<tem:CoCMembershipChamberCity>301</tem:CoCMembershipChamberCity>
					<tem:CoCMemberMembershipClass>0</tem:CoCMemberMembershipClass>
					<tem:CoCMemberSubscriptionToChamberDate>
						<tem:GregorianDate>2024-03-14</tem:GregorianDate>
						<tem:HijriDate>string</tem:HijriDate>
					</tem:CoCMemberSubscriptionToChamberDate>
					<tem:CoCMemberSubscriptionExpiryDate>
						<tem:GregorianDate>2024-03-14</tem:GregorianDate>
						<tem:HijriDate>string</tem:HijriDate>
					</tem:CoCMemberSubscriptionExpiryDate>
				</tem:CoCMembershipDetails>
				<tem:CoCMemberEst>
					<tem:CoCMemberEstNameAR>string</tem:CoCMemberEstNameAR>
					<tem:CoCMemberEstJuridicalFormAR>string</tem:CoCMemberEstJuridicalFormAR>
					<tem:CoCMemberEstNationalityAR>string</tem:CoCMemberEstNationalityAR>
					<tem:CoCMemberEstNumberOfBranches>0</tem:CoCMemberEstNumberOfBranches>
				</tem:CoCMemberEst>
				<tem:CoCMemberSijil>
					<tem:CoCMemberSijilNumber>string</tem:CoCMemberSijilNumber>
					<tem:CoCMemberSijilType>string</tem:CoCMemberSijilType>
					<tem:CoCMemberSijilSourceAR>string</tem:CoCMemberSijilSourceAR>
					<tem:CoCMemberSijilDate>
						<GregorianDate>2024-03-14</GregorianDate>
						<HijriDate>string</HijriDate>
					</tem:CoCMemberSijilDate>
					<tem:CoCMemberSijilExpiryDate>
						<GregorianDate>2024-03-14</GregorianDate>
						<HijriDate>string</HijriDate>
					</tem:CoCMemberSijilExpiryDate>
				</tem:CoCMemberSijil>
				<tem:CoCActivityType>
					<tem:CoCMemberMainActivityAR>string</tem:CoCMemberMainActivityAR>
					<tem:CoCMemberSecondaryActivityAR>string</tem:CoCMemberSecondaryActivityAR>
				</tem:CoCActivityType>
				<tem:CoCMemberOwner>
					<tem:CoCMemberOwnerNameAR>string</tem:CoCMemberOwnerNameAR>
					<tem:CoCMemberOwnerPrefixAR>string</tem:CoCMemberOwnerPrefixAR>
					<tem:CoCMemberOwnerGender>string</tem:CoCMemberOwnerGender>
					<tem:CoCMemberOwnerNationalityAR>string</tem:CoCMemberOwnerNationalityAR>
					<tem:CoCMemberOwnerPositionAR>string</tem:CoCMemberOwnerPositionAR>
				</tem:CoCMemberOwner>
				<tem:CoCMemberAddress>
					<tem:CoCMemberAddressPOBox>string</tem:CoCMemberAddressPOBox>
					<tem:CoCMemberAddressPostalCode>string</tem:CoCMemberAddressPostalCode>
					<tem:CoCMemberAddressStreetNameAR>string</tem:CoCMemberAddressStreetNameAR>
					<tem:CoCMemberAddressDistrictNameAR>string</tem:CoCMemberAddressDistrictNameAR>
					<tem:CoCMemberAddressDistrictNameEN>string</tem:CoCMemberAddressDistrictNameEN>
					<tem:CoCMemberAddressCityNameAR>string</tem:CoCMemberAddressCityNameAR>
					<tem:CoCMemberAddressRegionNameAR>string</tem:CoCMemberAddressRegionNameAR>
					<tem:CoCMemberAddressLocationInfo>string</tem:CoCMemberAddressLocationInfo>
					<tem:CoCMemberAddressWasselInfo>string</tem:CoCMemberAddressWasselInfo>
				</tem:CoCMemberAddress>
				<tem:CoCMemberPhone>
					<tem:CoCMemberPhoneNumber1>string</tem:CoCMemberPhoneNumber1>
					<tem:CoCMemberPhoneNumber2>string</tem:CoCMemberPhoneNumber2>
					<tem:CoCMemberPhoneNumber3>string</tem:CoCMemberPhoneNumber3>
					<tem:CoCMemberPhoneNumber4>string</tem:CoCMemberPhoneNumber4>
				</tem:CoCMemberPhone>
				<tem:CoCMemberFax>
					<tem:CoCMemberFaxNumber1>string</tem:CoCMemberFaxNumber1>
					<tem:CoCMemberFaxNumber2>string</tem:CoCMemberFaxNumber2>
					<tem:CoCMemberFaxNumber3>string</tem:CoCMemberFaxNumber3>
					<tem:CoCMemberFaxNumber4>string</tem:CoCMemberFaxNumber4>
				</tem:CoCMemberFax>
				<tem:CoCMemberMobile>
					<tem:CoCMemberMobileNumber1>string</tem:CoCMemberMobileNumber1>
					<tem:CoCMemberMobileNumber2>string</tem:CoCMemberMobileNumber2>
					<tem:CoCMemberMobileNumber3>string</tem:CoCMemberMobileNumber3>
					<tem:CoCMemberMobileNumber4>string</tem:CoCMemberMobileNumber4>
				</tem:CoCMemberMobile>
				<tem:CoCMemberEmail>
					<tem:CoCMemberEmail1>string</tem:CoCMemberEmail1>
					<tem:CoCMemberEmail2>string</tem:CoCMemberEmail2>
					<tem:CoCMemberEmail3>string</tem:CoCMemberEmail3>
					<tem:CoCMemberEmail4>string</tem:CoCMemberEmail4>
				</tem:CoCMemberEmail>
				<tem:CoCMemberWebSite>
					<tem:CoCMemberWebSite1>string</tem:CoCMemberWebSite1>
					<tem:CoCMemberWebSite2>string</tem:CoCMemberWebSite2>
					<tem:CoCMemberWebSite3>string</tem:CoCMemberWebSite3>
					<tem:CoCMemberWebSite4>string</tem:CoCMemberWebSite4>
				</tem:CoCMemberWebSite>
				<tem:CoCCapitalDetails>
					<tem:CoCMemberAnnouncedCapital>string</tem:CoCMemberAnnouncedCapital>
					<tem:CoCMemberPaidCapital>string</tem:CoCMemberPaidCapital>
					<tem:CoCMemberRateOfNationalCapital>string</tem:CoCMemberRateOfNationalCapital>
					<tem:CoCMemberRateOfForeignCapital>string</tem:CoCMemberRateOfForeignCapital>
					<tem:CoCMemberAllowedShares>string</tem:CoCMemberAllowedShares>
					<tem:CoCMemberPaidShares>string</tem:CoCMemberPaidShares>
					<tem:CoCMemberNumberOfSaudisMale>string</tem:CoCMemberNumberOfSaudisMale>
					<tem:CoCMemberNumberOfSaudisFemale>string</tem:CoCMemberNumberOfSaudisFemale>
					<tem:CoCMemberNumberOfNonSaudisMale>string</tem:CoCMemberNumberOfNonSaudisMale>
					<tem:CoCMemberNumberOfNonSaudisFemale>string</tem:CoCMemberNumberOfNonSaudisFemale>
				</tem:CoCCapitalDetails>
			</tem:GetCoCRecordByMemberShipIDResult>
		</tem:GetCoCRecordByMemberShipIDResponse>
	</soapenv:Body>
</soapenv:Envelope>

```
##### Proxy Response To Client
```json
{
  "GetCoCRecordByMemberShipIDResult": {
    "CoCMembershipDetails": {
      "CoCMembershipID": "string",
      "CoCMembershipChamberCity": 0,
      "CoCMemberMembershipClass": 0,
      "CoCMemberSubscriptionToChamberDate": {
        "GregorianDate": "2024-03-14",
        "HijriDate": "string"
      },
      "CoCMemberSubscriptionExpiryDate": {
        "GregorianDate": "2024-03-14",
        "HijriDate": "string"
      }
    },
    "CoCMemberEst": {
      "CoCMemberEstNameAR": "string",
      "CoCMemberEstJuridicalFormAR": "string",
      "CoCMemberEstNationalityAR": "string",
      "CoCMemberEstNumberOfBranches": 0
    },
    "CoCMemberSijil": {
      "CoCMemberSijilNumber": "string",
      "CoCMemberSijilType": "string",
      "CoCMemberSijilSourceAR": "string",
      "CoCMemberSijilDate": {
        "GregorianDate": "2024-03-14",
        "HijriDate": "string"
      },
      "CoCMemberSijilExpiryDate": {
        "GregorianDate": "2024-03-14",
        "HijriDate": "string"
      }
    },
    "CoCActivityType": {
      "CoCMemberMainActivityAR": "string",
      "CoCMemberSecondaryActivityAR": "string"
    },
    "CoCMemberOwner": {
      "CoCMemberOwnerNameAR": "string",
      "CoCMemberOwnerPrefixAR": "string",
      "CoCMemberOwnerGender": "string",
      "CoCMemberOwnerNationalityAR": "string",
      "CoCMemberOwnerPositionAR": "string"
    },
    "CoCMemberAddress": {
      "CoCMemberAddressPOBox": "string",
      "CoCMemberAddressPostalCode": "string",
      "CoCMemberAddressStreetNameAR": "string",
      "CoCMemberAddressDistrictNameAR": "string",
      "CoCMemberAddressDistrictNameEN": "string",
      "CoCMemberAddressCityNameAR": "string",
      "CoCMemberAddressRegionNameAR": "string",
      "CoCMemberAddressLocationInfo": "string",
      "CoCMemberAddressWasselInfo": "string"
    },
    "CoCMemberPhone": {
      "CoCMemberPhoneNumber1": "string",
      "CoCMemberPhoneNumber2": "string",
      "CoCMemberPhoneNumber3": "string",
      "CoCMemberPhoneNumber4": "string"
    },
    "CoCMemberFax": {
      "CoCMemberFaxNumber1": "string",
      "CoCMemberFaxNumber2": "string",
      "CoCMemberFaxNumber3": "string",
      "CoCMemberFaxNumber4": "string"
    },
    "CoCMemberMobile": {
      "CoCMemberMobileNumber1": "string",
      "CoCMemberMobileNumber2": "string",
      "CoCMemberMobileNumber3": "string",
      "CoCMemberMobileNumber4": "string"
    },
    "CoCMemberEmail": {
      "CoCMemberEmail1": "string",
      "CoCMemberEmail2": "string",
      "CoCMemberEmail3": "string",
      "CoCMemberEmail4": "string"
    },
    "CoCMemberWebSite": {
      "CoCMemberWebSite1": "string",
      "CoCMemberWebSite2": "string",
      "CoCMemberWebSite3": "string",
      "CoCMemberWebSite4": "string"
    },
    "CoCCapitalDetails": {
      "CoCMemberAnnouncedCapital": "string",
      "CoCMemberPaidCapital": "string",
      "CoCMemberRateOfNationalCapital": "string",
      "CoCMemberRateOfForeignCapital": "string",
      "CoCMemberAllowedShares": "string",
      "CoCMemberPaidShares": "string",
      "CoCMemberNumberOfSaudisMale": "string",
      "CoCMemberNumberOfSaudisFemale": "string",
      "CoCMemberNumberOfNonSaudisMale": "string",
      "CoCMemberNumberOfNonSaudisFemale": "string"
    }
  }
}

```

Markdown is a lightweight markup language based on the formatting conventions
that people naturally use in email.
As [John Gruber] writes on the [Markdown site][df1]

> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually- written in Markdown! To get a feel
for Markdown's syntax, type some text into the left window and
watch the results in the right.

## Tech

Dillinger uses a number of open source projects to work properly:

- [AngularJS] - HTML enhanced for web apps!
- [Ace Editor] - awesome web-based text editor
- [markdown-it] - Markdown parser done right. Fast and easy to extend.
- [Twitter Bootstrap] - great UI boilerplate for modern web apps
- [node.js] - evented I/O for the backend
- [Express] - fast node.js network app framework [@tjholowaychuk]
- [Gulp] - the streaming build system
- [Breakdance](https://breakdance.github.io/breakdance/) - HTML
to Markdown converter
- [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

## Installation

Dillinger requires [Node.js](https://nodejs.org/) v10+ to run.

Install the dependencies and devDependencies and start the server.

```sh
cd dillinger
npm i
node app
```

For production environments...

```sh
npm install --production
NODE_ENV=production node app
```

## Plugins

Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:

```sh
node app
```

Second Tab:

```sh
gulp watch
```

(optional) Third:

```sh
karma test
```

#### Building for source

For production release:

```sh
gulp build --prod
```

Generating pre-built zip archives for distribution:

```sh
gulp build dist --prod
```

## Docker

Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the
Dockerfile if necessary. When ready, simply use the Dockerfile to
build the image.

```sh
cd dillinger
docker build -t <youruser>/dillinger:${package.json.version} .
```

This will create the dillinger image and pull in the necessary dependencies.
Be sure to swap out `${package.json.version}` with the actual
version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on
your host. In this example, we simply map port 8000 of the host to
port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart=always --cap-add=SYS_ADMIN --name=dillinger <youruser>/dillinger:${package.json.version}
```

> Note: `--capt-add=SYS-ADMIN` is required for PDF rendering.

Verify the deployment by navigating to your server address in
your preferred browser.

```sh
127.0.0.1:8000
```

## License

MIT

**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
