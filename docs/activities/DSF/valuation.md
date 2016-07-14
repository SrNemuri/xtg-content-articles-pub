---
title: Valuation
keywords: activities, data structure, valuation
search: Activities - Data Structure - Valuation
sidebar: mydoc_sidebar
permalink: /docs/activities/DSF/valuation
---



### ValuationRQ Example

~~~xml
    <OTA_TourActivityBookRQ xmlns:xsi = "http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd = "http://www.w3.org/2001/XMLSchema" PrimaryLangID = "es">
      <BookingInfo>
        <BasicInfo Name = "Palma Aquarium" TourActivityID = "000200515"/>
        <Schedule StartPeriod = "2014-03-20T00:00:00" EndPeriod = "2014-03-21T00:00:00"/>
        <Pricing>
          <ParticipantCategory age = "30">
            <QualifierInfo>Adult</QualifierInfo>
            <Price Amount = "19.661" CurrencyCode = "EUR"/>
          </ParticipantCategory>
        </Pricing>
        <TPA_Extensions>
          <Seat>
            <Level id = "N1" description = "Nivel 1"/>
            <Area id = "A1" description = "Area 1"/>
            <Zone id = "A1_z1" description = "Parte Central"/>
            <Sector id = "A1_z1_b1" description = "Delantera Derecha"/>
            <UrlSitting>http://93.90.21.41/Janto/traveltino/public/janto/main.php?Nivel=Detalle_1_Sesion&Idioma=es&idSesion=0000000000000211&idZona=A1_z1&idBloque=A1_z1_b1&idConcesion=XXX&numEntradas=1&modo=IFRAME</UrlSitting>
          </Seat>
          <DynamicToken>pr1</DynamicToken>
          <Issue Mandatory = "false"/>
          <Attributes>
            <Attribute key = "availToken" value = "BpvkqOrfqU6ZpOqiJ0k21g=="/>
            <Attribute key = "modalityCode" value = "0#8"/>
            <Attribute key = "dateFrom" value = "20140320"/>
            <Attribute key = "dateTo" value = "20140320"/>
            <Attribute key = "limitAdult" value = "12"/>
            <Attribute key = "modeCode" value = "P"/>
          </Attributes>
        </TPA_Extensions>
      </BookingInfo>
    </OTA_TourActivityBookRQ>
~~~


### ValuationRQ Description




| **Element**				| **Number**	| **Type**	| **Description**				|
| ------------------------------------- | ------------- | ------------- | --------------------------------------------- |
| OTA_TourActivityBookRQ		| 1       	|		| Root node.					|
| @PrimaryLangID      			| 1  		| String	| Language code (ISO 3166-1 alpha-2) format.	|
| BookingInfo         			| 0..1     	|		| Information about specific ticket. 		|
| BookingInfo/BasicInfo			| 0..1     	|		| If need search by activity provider code.	|
| @Name               			| 0..1		| String	| Name of ticket.				|
| @TourActivityID     			| 0..1		| String	| Code of ticket, mandatory if need search by activity provider code. |
| BookingInfo/Schedule			| 1       	|		| Information about dates range on which you can enjoy the activity. |
| @StartPeriod        			| 1  		| Date		| Start date that you apply availability.	|
| @EndPeriod          			| 1  		| Date		| End date that you apply availability.		|
| BookingInfo/CategoryAndType		| 0..1     	|		| Category of Ticket.				|
| BookingInfo/CategoryAndType/Category	| 0..1     	|		| Category of Ticket.				|
| @Code               			| 0..1		| String	| A category code from a predefined list, if Extension = "Other" then will be provider code. |
| @Extension          			| 0..1		| String	| Enter a category here if you have selected "Other" from the pre-defined list. |
| ParticipantCategory 			| 0..n     	|		| Information about participant type, specifying age for each participant. |
| @Age                			| 1  		| Integer	| Age of participant.				|
| Pricing/ParticipantCategory/QualifierInfo | 0..1	| String	| Specifies participant type (Adult, Children or Baby). If value = Other then then is mandatory specify Extension provider type. |
| Pricing/ParticipantCategory/Price	| 1       	|		| Specific price for each participantCategory.	|
| @Amount             			| 1   		| String	| ParticipantCategory price.			|
| @CurrencyCode       			| 0..1		| String	| Currency code (ISO 4217).			|
| Pricing/ParticipantCategory/TPA_Extensions | 0..1     |		| Necessary information that we need send between calls. |
| Pricing/ParticipantCategory/TPA_Extensions/DynamicToken | 0..1 | String | Inform about the participant types to valuate (if more than one type, the participant Types must be separated by ";"). |
| Pricing/ParticipantCategory/TPA_Extensions/Issue | 0..1 |		| Contains information about ticket printing.	|
| @Mandatory          			| 0..1		| Boolean	| Specifies if the ticket should be printed by the client. |



### ValuationRS Example



~~~xml
    <OTA_TourActivityBookRS>
        <ReservationDetails>
            <BasicInfo
                Name = "PALMA AQUARIUM"
                TourActivityID = "000200515"/>
            <Schedule StartPeriod = "2014-02-26T00:00:00" EndPeriod = "2014-02-27T00:00:00"/>
             <PickupDropoff OtherInfo="El cliente puede canjear el bono en la oficina de billetes de La Reserva  en Predio Son Net s/n 07194 Puigpunyent
            Abierto todos los das del ao.
            Verano: de 10:00h a 19:00h
            Invierno: de 10:00h a 18:00h  

            El cliente no puede olvidar llevar su documento de identidad.

            En caso de emergencia, el cliente deber llamar al siguiente nmero: (+34) 902 430 419
             " />

            <!--Pricing. -->
            <Pricing>
                <Summary Amount = "19.660" CurrencyCode = "EUR">
                    <PricingType Extension = "PerTotal">Other_</PricingType>
                </Summary>
                <ParticipantCategory age = "30">
                    <QualifierInfo>Adult</QualifierInfo>
                    <Price
                        Amount = "19.660"
                        CurrencyCode = "EUR"/>
                </ParticipantCategory>
            </Pricing>  
        <TPA_Extensions>
              <Attributes>
                <Attribute key = "purchaseToken" value = ""> </Attribute>
                <Attribute key = "SPUI" value = ""> </Attribute>        
                <Attribute key = "limitAdult" value="16"> </Attribute>              
              </Attributes>
            </TPA_Extensions>           
        </ReservationDetails>
    </OTA_TourActivityBookRS>
~~~


### ValuationRS Description




| **Element**				| **Number**	| **Type**	| **Description**				|
| ------------------------------------- | ------------- | ------------- | --------------------------------------------- |
| @StartPeriod        			| 1 		| Date		| Start date that you apply availability.	|
| @EndPeriod          			| 1 		| Date		| End date that you apply availability.		|
| BookingInfo/CategoryAndType		| 0..1    	|		| Category of Ticket.				|
| BookingInfo/CategoryAndType/Category 	| 0..1    	|		| Category of Ticket.				|
| @Code               			| 0..1		| String	| A category code from a predefined list, if Extension = "Other" then will be provider code. |
| @Extension          			| 0..1		| String	1 Enter a category here if you have selected "Other" from the pre-defined list. |
| ReservationDetails/PickupDropoff	| 0..1    	|		| The pickup and/or dropoff information if transportation is provided to/ from the tour/activity location. |
| @OtherInfo          			| 0..1		| String	| Other instructions pertaining to the pickup/dropoff. |
| ParticipantCategory 			| 0..n    	|		| Information about participant type, specifying age for each participant. |
| @Age                			| 1 		| Integer	| Age of participant.				|
| Pricing/ParticipantCategory/QualifierInfo | 0..1	| String	| Specifies participant type (Adult, Children or Babie). If value = "Other_" then then is mandatory specify Extension provider type. |
| Pricing/ParticipantCategory/Price	| 1     	|		| Specific price for each participantCategory.	|
| @Amount             			| 1 		| String	| ParticipantCategory price.			|
| @CurrencyCode       			| 0..1		| String	| Currency code (ISO 4217).			|
| Pricing/ParticipantCategory/TPA_Extensions | 0..1     |		| Necessary information that we need send between calls. |
| Pricing/ParticipantCategory/TPA_Extensions/DynamicToken | 0..1 | String | Inform about the participant types to valuate (if more than one type, the participant Types must be separated by ";"). |
| Pricing/ParticipantCategory/TPA_Extensions/Issue | 0..1 |   		| Contains information about ticket printing. 	|
| @Mandatory          			| 0..1		| Boolean	| Specifies if the ticket should be printed by the client. |

