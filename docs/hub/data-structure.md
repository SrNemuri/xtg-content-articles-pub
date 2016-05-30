---
title: Data Structure
keywords: intro
sidebar: mydoc_sidebar
permalink: /docs/hub/data-structure
---

There is a common XML API structure that is used for all integration
services.

The API structure has common elements and inside the body there are
specific XML elements depending integration type.

For information about the specific XML elements that travel inside the
requests and response objects please check the documentation by required
API:



-   [Hotel API](/docs/hotel/index)
-   [Transportation API](/docs/transportation/index)
-   [Car API](/docs/car/index)
-   [Transfers API](/docs/transfers/index)
-   [Tour Activity API](/docs/activities/index) 



All XML details must be checked, at each stage, by the client system and
by the end traveller. XML Travelgate does not take any responsibility
for any changes in details that are not noticed, since this can
sometimes be caused by the supplier.



- **Availability Calls**


Availability calls supports 1 or more (1..n) providers requests in a
single availability call.

All the supplier requests will be sent to each supplier in parallel and
the responses will be aggregated into one single response. If the
timeout time is reached and the supplier has not responded on time an
empty response will be returned for this specific supplier.

Please, check Hub Quotas for some limitations to requests.



### Availability RQ Example




    <soapenv:Envelope xmlns:soapenv = "http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns = "http://schemas.xmltravelgate.com/hub/2012/06" xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
        <soapenv:Header>
            <wsse:Security>
                <wsse:UsernameToken>
                    <wsse:Username>user</wsse:Username>
                    <wsse:Password>password</wsse:Password>
                </wsse:UsernameToken>
            </wsse:Security>
        </soapenv:Header>
      <soapenv:Body>
            <ns:Disponibilidad> <!-- Specific by API -->
                <ns:disponibilidadRQ> <!-- Specific by API -->
                    <ns:timeoutMilliseconds>60000</ns:timeoutMilliseconds>  
                    <ns:version>1</ns:version>
                    <ns:providerRQs>
                        <ns:ProviderRQ>
                            <ns:code>AXI</ns:code>
                            <ns:id>1</ns:id>
                            <ns:rqXML>
                                     <!-- XML RQ Specific by API -->                       
                            </ns:rqXML>
                        </ns:ProviderRQ>
                        <ns:ProviderRQ>
                            <ns:code>TEST</ns:code>
                            <ns:id>2</ns:id>
                            <ns:rqXML>
                                   <!-- XML RQ Specific by API --> 
                            </ns:rqXML>
                        </ns:ProviderRQ>
                    </ns:providerRQs>
                </ns:disponibilidadRQ>
            </ns:Disponibilidad>
        </soapenv:Body>
    </soapenv:Envelope>



### Availability RQ Description




| **Element**                   | **Number**  | **Type** | **Description** |
| ------------                  | ----------- | -------- | --------------- |
| Envelope                      |   1         |          | Root Node       |
| Header/Security/UserNameToken | 1           |          | Web Services Security UsernameToken Profile 1.0 |
| Body                          | 1           |          | Request Body    |
| timeoutMilliseconds           | 1           | Integer  | Maximum timeout (in milliseconds) to wait for all possible responses |
| version                       | 1           | String   | API specification version. (1) |
| providersRQs/ProviderRQ       | 1..n        |          | Provider to request |
| providersRQs/ProviderRQ/code  | 1           | String   | Provider code to request |
| providersRQs/ProviderRQ/id    | 1           | String   | Id to correlate requests with responses |
| providersRQs/ProviderRQ/rqXML | 1           | String   | API specific XML to request |

 


### Availability RS Example




    <s:Envelope xmlns:s = "http://schemas.xmlsoap.org/soap/envelope/" xmlns:u = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
        <s:Header>
            <o:Security s:mustUnderstand = "1" xmlns:o = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
                <u:Timestamp u:Id = "_0">
                    <u:Created>2013-12-04T10:58:28.709Z</u:Created>
                    <u:Expires>2013-12-04T11:03:28.709Z</u:Expires>
                </u:Timestamp>
            </o:Security>
        </s:Header>
        <s:Body>
            <DisponibilidadResponse xmlns = "http://schemas.xmltravelgate.com/hub/2012/06">  <!-- Specific by API -->
                <DisponibilidadResult xmlns:i = "http://www.w3.org/2001/XMLSchema-instance">  <!-- Specific by API -->
                    <hubStatus>
                        <code>1</code>
                        <warnings i:nil = "true"/>
                        <exceptionString i:nil = "true"/>
                        <roleInstanceId>HubFrontendWebRole_IN_0</roleInstanceId>
                        <channelId i:nil = "true"/>
                        <messageWebRoleStats>
                            <startAtUtc>2013-12-04T10:58:28.6785009Z</startAtUtc>
                            <endAtUtc>2013-12-04T10:58:28.7097417Z</endAtUtc>
                            <execution>PT0.0312408S</execution>
                            <messageExpiresAtUtc>2013-12-04T10:58:38.6785009Z</messageExpiresAtUtc>
                            <getValidationConfiguration>PT0S</getValidationConfiguration>
                            <buildHubMessageRQ>PT0S</buildHubMessageRQ>
                            <buildBrokeredMessageRQ>PT0S</buildBrokeredMessageRQ>
                            <sendBrokeredMessageRQ>PT0S</sendBrokeredMessageRQ>
                            <acceptMessageSession>0001-01-01T00:00:00</acceptMessageSession>
                            <acceptMessageSessionTimeSpan>PT0S</acceptMessageSessionTimeSpan>
                        </messageWebRoleStats>
                    </hubStatus>
                    <providerRSs>
                        <ProviderRS>
                            <hubProviderStatus>
                                <channelId>http://100.86.16.44:10101/ServiceHotel</channelId>
                                <code>1</code>
                                <exceptionString i:nil = "true"/>
                                <hubProviderError i:nil = "true"/>
                                <invocationWorkerRoleStats>
                                    <startAtUtc>2013-12-04T10:58:28.7999649Z</startAtUtc>
                                    <receiveBrokeredMessageRQ>2013-12-04T10:58:28.7999649Z</receiveBrokeredMessageRQ>
                                    <buildAssembly>PT0S</buildAssembly>
                                    <buildInvokeRQ>PT0S</buildInvokeRQ>
                                    <invoke>PT0S</invoke>
                                    <invokeProvider>PT0S</invokeProvider>
                                    <buildInvokeRS>PT0S</buildInvokeRS>
                                    <buildBrokeredMessageRS>PT0S</buildBrokeredMessageRS>
                                </invocationWorkerRoleStats>
                                <roleInstanceId>HubProcessTravelHotelWorkerRole_IN_0</roleInstanceId>
                            </hubProviderStatus>
                            <refId>1</refId>
                            <rsXML>
                                             <!-- XML RS Specific by API -->
                            </rsXML>
                        </ProviderRS>
                           <ProviderRS>
                            <hubProviderStatus>
                                <channelId>http://100.86.16.44:10101/ServiceHotel</channelId>
                                <code>1</code>
                                <exceptionString i:nil = "true"/>
                                <hubProviderError i:nil = "true"/>
                                <invocationWorkerRoleStats>
                                    <startAtUtc>2013-12-04T10:58:28.7999649Z</startAtUtc>
                                    <receiveBrokeredMessageRQ>2013-12-04T10:58:28.7999649Z</receiveBrokeredMessageRQ>
                                    <buildAssembly>PT0S</buildAssembly>
                                    <buildInvokeRQ>PT0S</buildInvokeRQ>
                                    <invoke>PT0S</invoke>
                                    <invokeProvider>PT0S</invokeProvider>
                                    <buildInvokeRS>PT0S</buildInvokeRS>
                                    <buildBrokeredMessageRS>PT0S</buildBrokeredMessageRS>
                                </invocationWorkerRoleStats>
                                <roleInstanceId>HubProcessTravelHotelWorkerRole_IN_0</roleInstanceId>
                            </hubProviderStatus>
                            <refId>2</refId>
                            <rsXML>
                                      <!-- XML RS Specific by API -->
                            </rsXML>
                        </ProviderRS>
                    </providerRSs>
                </DisponibilidadResult>
            </DisponibilidadResponse>
        </s:Body>
    </s:Envelope>



### Availability RS Description




| **Element**                                | **Number**  | **Type** | **Description** |
| ------------                               | ----------- | -------- | --------------- |
| Envelope                                   | 1           |          | Root Node       |
| Header/Security                            | 1           |          | Auto generated by SOAP framework based on Web Services Security UsernameToken Profile 1.0 |
| Body                                       | 1           |          | Responde Body    |
| hubStatus                                  | 1           |          | Trace information only for XMLTravelgate purposes |
| providersRSs/ProviderRS                    | 1..n        |          | Provider to request |
| providersRSs/ProviderRS/hubProviderStatus  | 1           |          | Trace information only for XMLTravelgate purposes |
| providersRSs/ProviderRS/refId              | 1           | String   | Id to correlate responses with requests. It is a reference to id filled in request |
| providersRSs/ProviderRS/rsXML              | 1           | String   | API specific XML to response |



### Other Calls


All other API calls only support one provider per transaction.

Provider response will be responded when timeout limit is reached or
when provider has responded.

**Common structures are same used in availability calls but only
allowing 1 element of type Provider per Request/Response.**

