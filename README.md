# Countrinfo soap web service

## Build

mvn clean install

## Run

mvn spring-boot:run

## Sample request

Save following to lets say request.xml

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:gs="http://countryinfo.org/springsoap/gen">
    <soapenv:Header />
    <soapenv:Body>
        <gs:getCountryRequest>
            <gs:name>Spain</gs:name>
        </gs:getCountryRequest>
    </soapenv:Body>
</soapenv:Envelope>
```

And use curl to send the soap request:

```
curl --header "content-type: text/xml" -d @request.xml http://localhost:8082/ws
```

You should get response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header />
   <SOAP-ENV:Body>
      <ns2:getCountryResponse xmlns:ns2="http://countryinfo.org/springsoap/gen">
         <ns2:country>
            <ns2:name>Spain</ns2:name>
            <ns2:population>46704314</ns2:population>
            <ns2:capital>Madrid</ns2:capital>
            <ns2:currency>EUR</ns2:currency>
         </ns2:country>
      </ns2:getCountryResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

(not formatted tho ;) )

## How to get the WSDL?

When your app is running you can get the wsdl from:

```
http://localhost:8082/ws/countries.wsdl
```
