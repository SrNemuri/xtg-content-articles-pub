---
title: MetaData
keywords: hotel, data structure, meta data
search: Hotel - Data Structure - Metadata
sidebar: mydoc_sidebar
permalink: /docs/hotel/DSF/MetaData
---

### Method Goals


This method provides information about the meta data of the
supplier so that it can be effectively configured.



### Request Format


The request does not require any elements - empty request.



### Response Format


The XML response contains many elements of the supplier's meta data: number of
hotels, number of cities and number of areas available, maximum number of
*roomcandidate*, maximum number of paxes in a *roomcandidate*, release days,
minimum stay, list of languages supported ...



### MetaDataRQ Example


~~~xml
    <MetaDataRQ>
    </MetaDataRQ>
~~~


### MetaDataRQ Description


  
| **Element**			| **Number**	| **Type**	| **Description**	|
| ----------------------------- | ------------- | ------------- | --------------------- |
| MetaDataRQ		| 1          	|		| Root node.		|

### MetaDataRS Example


~~~xml
    <MetaDataRS>
    <operationImplemented>true</operationImplemented>
    <Avail>
        <Destinations>
            <MaxNumberHotels reviewDate = "">0</MaxNumberHotels>
            <MaxNumberHotelsRecommended reviewDate = "">0</MaxNumberHotelsRecommended>
            <MaxNumberCities reviewDate = "">0</MaxNumberCities>
            <MaxNumberCitiesRecommended reviewDate = "">0</MaxNumberCitiesRecommended>
            <MaxNumberZones reviewDate = "">0</MaxNumberZones>
            <MaxNumberZonesRecommended reviewDate = "">0</MaxNumberZonesRecommended>
            <MaxNumberGeoCodes reviewDate = "">0</MaxNumberGeoCodes>
            <MaxNumberGeoCodesRecommended reviewDate = "">0</MaxNumberGeoCodesRecommended>
            <HotelSameDestinationRestriction reviewDate = "">false</HotelSameDestinationRestriction>
            <DestinationSameCountryRestriction reviewDate = "">false</DestinationSameCountryRestriction>
        </Destinations>
        <AllowsCurrency reviewDate = "">false</AllowsCurrency>
        <AllowsBusinessRules reviewDate = "">false</AllowsBusinessRules>
        <NumMarketsAllowed reviewDate = "">0</NumMarketsAllowed>
        <Release reviewDate = "">0</Release>
        <MinimumStay reviewDate = "">0</MinimumStay>
        <MaxStay reviewDate = "">0</MaxStay>
        <MaxNumberRoomCandidates reviewDate = "">0</MaxNumberRoomCandidates>
        <MaxPaxInRoomCandidates reviewDate = "">0</MaxPaxInRoomCandidates>
        <MaxPaxInAllRooms reviewDate = "">0</MaxPaxInAllRooms>
        <RequiredRoomWithSamePaxConfiguration>
            <SamePaxNumber reviewDate = "">false</SamePaxNumber>
            <SamePaxAge reviewDate = "">false</SamePaxAge>
        </RequiredRoomWithSamePaxConfiguration>
        <RateRules>
            <RateRule reviewDate = "">NonRefundable</RateRule>
            <RateRule reviewDate = "">largeFamily</RateRule>
        </RateRules>
        <Beds>
            <InformNumberOfUnits reviewDate = "">false</InformNumberOfUnits>
            <InformSharedBed reviewDate = "">false</InformSharedBed>
            <InformBedType reviewDate = "">false</InformBedType>
            <InformNumberOfBeds reviewDate = "">false</InformNumberOfBeds>
        </Beds>
        <InformBindingPrice reviewDate = "">false</InformBindingPrice>
        <InformCancelPolicies reviewDate = "">false</InformCancelPolicies>
        <InformRemarks reviewDate = "">false</InformRemarks>
        <PaymentTypes>
            <PaymentType reviewDate = "">MerchantPay</PaymentType>
            <PaymentType reviewDate = "">LaterPay</PaymentType>
        </PaymentTypes>
        <OptionTypes>
            <OptionType reviewDate = "">Hotel</OptionType>
        </OptionTypes>
        <Languages>
            <Language reviewDate = "">en</Language>
            <Language reviewDate = "">es</Language>
        </Languages>
        <InformDailyPrice reviewDate = "">false</InformDailyPrice>
        <InformDailyRatePlan reviewDate = "">false</InformDailyRatePlan>
        <InformOffers reviewDate = "">false</InformOffers>
        <InformNRFRateByRoom reviewDate = "">false</InformNRFRateByRoom>
        <AgeRange reviewDate = "11/11/2016">
            <Age min = "2" max = "5"/>
        </AgeRange>
        <InformFees reviewDate = "">false</InformFees>
    </Avail>
    <Valuation>
        <AllowsBlockOption reviewDate = "">false</AllowsBlockOption>
        <InformBindingPrice reviewDate = "">false</InformBindingPrice>
        <InformNRFRate reviewDate = "">false</InformNRFRate>
        <InformRemarks reviewDate = "">false</InformRemarks>
        <InformCancelPolicies reviewDate = "">false</InformCancelPolicies>
        <InformCancelPoliciesDescription reviewDate = "">false</InformCancelPoliciesDescription>
        <InformFees reviewDate = "">false</InformFees>
    </Valuation>
    <Reservation>
        <AllowsDeltaPrice reviewDate = "">false</AllowsDeltaPrice>
        <RequiredAllPassengers reviewDate = "">false</RequiredAllPassengers>
        <AllowsRemarks reviewDate = "">false</AllowsRemarks>
        <AllowsUrlCard reviewDate = "">false</AllowsUrlCard>
        <InformBillingSupplier reviewDate = "">false</InformBillingSupplier>
        <InformPrice reviewDate = "">false</InformPrice>
    </Reservation>
    <ReservationRead>
        <Implements reviewDate = "">false</Implements>
        <AllowsProvideLocator reviewDate = "">false</AllowsProvideLocator>
        <AllowsClientLocator reviewDate = "">false</AllowsClientLocator>
        <InformCancelPolicies reviewDate = "">false</InformCancelPolicies>
        <InformPriceCancel reviewDate = "">false</InformPriceCancel>
    </ReservationRead>
    <ReservationList>
        <Implements reviewDate = "">false</Implements>
        <AllowsCreationDate reviewDate = "">false</AllowsCreationDate>
        <AllowsCheckDate reviewDate = "">false</AllowsCheckDate>
        <InformCancelPolicies reviewDate = "">false</InformCancelPolicies>
        <InformPriceCancel reviewDate = "">false</InformPriceCancel>
    </ReservationList>
    <Cancel>
        <Implements reviewDate = "">false</Implements>
        <AllowsProvideLocator reviewDate = "">false</AllowsProvideLocator>
        <AllowsClientLocator reviewDate = "">false</AllowsClientLocator>
        <InformPriceCancel reviewDate = "">false</InformPriceCancel>
    </Cancel>
    <Batch>
        <InformExclusiveDeal reviewDate = "">false</InformExclusiveDeal>
        <HotelList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </HotelList>
        <DescriptiveInfo>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </DescriptiveInfo>
        <GeographicDestinationTree>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </GeographicDestinationTree>
        <AvailDestinationTree>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
            </Languages>
        </AvailDestinationTree>
        <RoomList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </RoomList>
        <MealPlanList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </MealPlanList>
        <CategoryList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </CategoryList>
        <DescriptiveInfoExtended>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </DescriptiveInfoExtended>
        <MarketList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </MarketList>
        <CurrencyList>
            <StaticType reviewDate = "">NotImplemented</StaticType>
            <Languages>
                <Language reviewDate = "">en</Language>
                <Language reviewDate = "">es</Language>
            </Languages>
        </CurrencyList>
    </Batch>
    <Generic>
        <RequiredNationality reviewDate = "">false</RequiredNationality>
        <AllowsOnRequest reviewDate = "">false</AllowsOnRequest>
    </Generic>
</MetaDataRS>
~~~

### MetaDataRS Description

| **Element**				| **Number**	| **Type**	| **Description**						|
| ------------------------------------- | ------------- | ------------- | ------------------------------------------------------------- |
| MetaDataRS			| 1        	|		| Root node.							|
| Avail			| 1        	| 	| Avail node.		|
| Avail/Destinations			| 1        	| 	| Contains information regarding the destinations for *AvailRQ*.		|
| Avail/Destinations/MaxNumberHotels			| 1        	| Integer	| Maximum number of hotels that can be requested. |
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberHotelsRecommended			| 1        	| Integer	| Maximum number of hotels recommended by the supplier.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberCities			| 1        	| Integer	| Maximum number of cities that can be requested.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberCitiesRecommended			| 1        	| Integer	| Maximum number of cities recommended by the supplier.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberZones			| 1        	| Integer	| Maximum number of zones that can be requested.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberZonesRecommended			| 1        	| Integer	| Maximum number of zones recommended by the supplier.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberGeoCodes			| 1        	| Integer	| Maximum number of GeoCodes that can be requested.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/MaxNumberGeoCodesRecommended			| 1        	| Integer	| Maximum number of GeoCodes recommended by the supplier.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/HotelSameDestinationRestriction			| 1        	| Boolean | If the supplier allows the availability for N hotels, this tag indicates whether those hotels must be within the same destination.			|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Destinations/DestinationSameCountryRestriction			| 1        	| Boolean | If the supplier allows the availability for N destinations, this tag indicates whether those destinations must be within the same country.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/AllowsCurrency			| 1        	| Boolean	| If true, it is possible to request the currency.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/AllowsBusinessRules			| 1        	| Boolean	| Specifies if this supplier allows *businessrules*.|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/NumMarketsAllowed			| 1        	| Integer	| Number of markets supported by the supplier in the same request. |
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Release			| 1        	| Integer	| Minimum days required in between booking date and checking date ( days in advance ). If the value is zero then there is no limitation.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/MinimumStay			| 1        	| Integer	| Minimum number of days required for booking. If the value is zero then there is no limitation.  |
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/MaxStay			| 1        	| Integer	| Maximum number of days allowed for booking.  |
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/MaxNumberRoomCandidates			| 1        	| Integer | Maximum number of room candidates that can be requested in the same avail request.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/MaxPaxInRoomCandidates			| 1        	| Integer | Maximum number paxs in same room that can be requested in the same avail request.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/MaxPaxInAllRooms			| 1        	| Integer | Total amount of paxs that can be requested in the same avail request.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/RequiredRoomWithSamePaxConfiguration			| 1        	| 	| Indicates whether all of the distributions must have the same configuration.		|
| Avail/RequiredRoomWithSamePaxConfiguration/SamePaxNumber			| 1        	| Boolean	| Indicates whether it is necessary that the number of guests be the same in all of the configurations.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/RequiredRoomWithSamePaxConfiguration/SamePaxAge			| 1        	| Boolean	| Indicates whether all of the guests in a particular distribution must be the same age.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/RateRules			| 1        	| 	| List of rate rule types.		|
| Avail/RateRules/RateRule			| 1..n        	| Enum	| Rate rules supported by the supplier (You can check these Rate conditions in our Avail section).		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Beds			| 1        	| 	| Information about beds.		|
| Avail/Beds/InformNumberOfUnits			| 1        	| Boolean | Indicates the number of units available per room.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Beds/InformSharedBed			| 1        	| Boolean | Informs in availability response if beds in the room are shared. |
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Beds/InformBedType			| 1        	| Boolean	| Informs if the supplier returns the beds types.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Beds/InformNumberOfBeds			| 1        	| Boolean 	| Informs if the supplier returns the number of beds for each room.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformBindingPrice			| 1        	| Boolean	| Supplier returns binding PVPs.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformCancelPolicies			| 1        	| Boolean	| Returns cancellation policies.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformRemarks			| 1        	| Boolean	| Space available for any remarks or comments aimed at the client.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/PaymentTypes			| 1        	| 	| List of payment types accepted by the supplier.		|
| Avail/PaymentTypes/PaymentType			| 1..n        	| 	| Indicates the types of payment (Merchant, Direct, ...).		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/OptionTypes			| 1        	| 	| List of option types accepted by the supplier.		|
| Avail/OptionTypes/OptionType			| 1..n        	| 	| Indicates the types of option.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/Languages			| 1        	| 	| List of languages.		|
| Avail/Languages/Language			| 1..n        	| String	| 	Language code. 		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformDailyPrice			| 1        	| Boolean	| Informs if the supplier returns the daily price. 		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformDailyRatePlan			| 1        	| Boolean	| Informs if the supplier returns the daily rate.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformOffers			| 1        	| Boolean	| If true, the supplier returns the offers applied. 		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/InformNRFRateByRoom			| 1        	| Boolean	| The supplier can inform in availability if the room is non-refundable. 		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/AgeRange			| 0..1        	| 	| The age range used by the supplier.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Avail/AgeRange/Age			| 1..n        	| 	| Age range.	|
| @min 			| 1   		| String	| Minimum age in range. |
| @max 			| 1		| String	|  Max age in range. |
| Avail/InformFees			| 1        	| Boolean 	| Informs if the supplier returns fees.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation			| 1        	| 	| Valuation node.		|
| Valuation/AllowsBlockOption			| 1        	| Boolean	| Informs if the supplier can block the option.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformBindingPrice			| 1        	| Boolean	| Informs if the price is binding in valuation response.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformNRFRate			| 1        	| Boolean	| The supplier can inform in valuation if the rate is non-refundable.	|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformRemarks			| 1        	| Boolean	| Returns remarks.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformCancelPolicies			| 1        	| Boolean 	| Informs cancellation policies.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformCancelPoliciesDescription			| 1        	| Boolean	| Specifies if the supplier informs the cancel policies in free text.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Valuation/InformFees			| 1        	| Boolean	| Informs if the supplier returns fees.		|
| @reviewDate 			| 1   		| String	| Informs of the date when the field was last reviewed. |
| Reservation			| 1        	| 	| Reservation node.		|
| ReservationRead			| 1        	| 	| ReservationRead node.		|
| ReservationList			| 1        	| 	| ReservationList node.		|
| Cancel			| 1        	| 	| Cancel node.		|
| Batch			| 1        	| 	| Batch node.		|
| Generic			| 1        	| 	| Generic node.		|
