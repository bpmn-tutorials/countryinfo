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
