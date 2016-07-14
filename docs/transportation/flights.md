---
title: Flights Data Structure
keywords: transportation, flights data structure
search: Transportation - Flights Data Structure
sidebar: mydoc_sidebar
permalink: /docs/transportation/flights
---

The structure of the API specification follows a standard. This document
intends to explain every aspect of this structure and their fields.



The integration will have the following methods:



| **Method**			| **Input**			| **Output**			| **Required** | **Description**	|
| ----------------------------- | ----------------------------- | ----------------------------- | ------------ | ---------------------- |
| Availability  		| AvailabilityRQ 		| AvailabilityRS 		| Yes 	       | Makes a availability call |
| Valuation     		| ValuationRQ    		| ValuationRS    		| Yes 	       | Makes a pre-booking	|
| Reservation   		| ReservationRQ  		| ReservationRS  		| Yes 	       | Makes a booking	|
| RetrieveReservation		| RetrieveReservation RQ		| RetrieveReservation RS		| No 	       | Gets booking details	|
| RetrieveReservation List	| RetrieveReservation ListRQ	| RetrieveReservation ListRS	| No 	       | Gets booking list	|
| Cancellation  		| CancellationRQ 		| CancellationRS 		| No 	       | Cancels a booking	|



Each request sent to the **service url** requires a node called rqXML .
Inside this node travels the current method's Input object.



The data structure will always have common elements in all objects and
the specific objects related to the operation



**Data structure content:**

1. [Flights](/docs/transportation/flights)
2. [Avail](/docs/transportation/DSF/flights/avail)
3. [Valuation](/docs/transportation/DSF/flights/valuation)
4. [Reservation](/docs/transportation/DSF/flights/reservation)
5. [RetrieveReservation](/docs/transportation/DSF/flights/recover-reserve)
6. [RetrieveReservationList](/docs/transportation/DSF/flights/recover-reserve-list)
7. [Cancellation](/docs/transportation/DSF/flights/cancel)
