# Travel

## Get Available Flights

```shell
curl -X GET
     -H "X-User-Email: demoapiuser@demo.com"
     -H "X-User-Token: 9xDx4rzx8YmqzPmUC8C4"
     -F "booking_type=O"
     -F "origin=MNL"
     -F "destination=CEB"
     -F "travel_date=03/04/2017"
     -F "class_type=E"
     -F "airline_codes=Z2"
     -F "no_of_adults=1"
     -F "no_of_childs=0"
     -F "no_of_infants=0"
     -F "phil_resident=1"
     -F "senior_citizen=0"
     -F "direct_access=0"
     -F "trans_fee_flag=1"
https://try.payswitch.net/api/v2/biyaheko/flights
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

uri = URI("https://try.payswitch.net/api/v2/biyaheko/flights")

params = {  
   booking_type:'O',
   origin:'MNL',
   destination:'CEB',
   travel_date:'02/03/2017',
   class_type:'E',
   airline_codes:'Z2',
   no_of_adults:1,
   no_of_childs:0,
   no_of_infants:0,
   phil_resident:1,
   senior_citizen:0,
   direct_access:0,
   trans_fee_flag:1
  }

uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(uri)
request["x-user-email"] = 'demoapiuser@demo.com'
request["x-user-token"] = '9xDx4rzx8YmqzPmUC8C4'

response = http.request(request)
puts response.read_body
```

```python
import requests 

URL = "https://try.payswitch.net/api/v2/biyaheko/flights"
HEADERS = {
    'X-User-Email' : 'demoapiuser@demo.com',
    'X-User-Token' : '9xDx4rzx8YmqzPmUC8C4'
} 
PARAMS = {  
   'booking_type' :'O',
   'origin' :'MNL',
   'destination' :'CEB',
   'travel_date' :'02/03/2017',
   'class_type' :'E',
   'airline_codes' :'Z2',
   'no_of_adults' :1,
   'no_of_childs' :0,
   'no_of_infants' :0,
   'phil_resident': 1,
   'senior_citizen' :0,
   'direct_access' :0,
   'trans_fee_flag' :1
  }

response = requests.get(URL, headers=HEADERS, data=PARAMS)
print(response.text)
```

> JSON response:

```json
{
  "success": true,
  "data": {
    "AvailableDetails": [
      {
        "SegmentDetails": {
          "FlightId": "101",
          "AirlineId": "Z2",
          "FlightNo": "771",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 19:30:00",
          "ArrivalDateTime": "04/03/2017 20:55:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "2",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "102",
          "AirlineId": "Z2",
          "FlightNo": "783",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 12:25:00",
          "ArrivalDateTime": "04/03/2017 13:55:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "8",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "103",
          "AirlineId": "Z2",
          "FlightNo": "767",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 18:15:00",
          "ArrivalDateTime": "04/03/2017 19:40:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "2",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "104",
          "AirlineId": "Z2",
          "FlightNo": "775",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 10:45:00",
          "ArrivalDateTime": "04/03/2017 12:10:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "10",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "105",
          "AirlineId": "Z2",
          "FlightNo": "773",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 07:15:00",
          "ArrivalDateTime": "04/03/2017 08:40:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "10",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "106",
          "AirlineId": "Z2",
          "FlightNo": "781",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 08:40:00",
          "ArrivalDateTime": "04/03/2017 10:05:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "10",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1125",
                "RBD": "Z",
                "FareBasis": "Z00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "335",
                "GrossAmount": "1500",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "Z",
                "FareBasis": "Z00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1460",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "107",
          "AirlineId": "Z2",
          "FlightNo": "763",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 06:00:00",
          "ArrivalDateTime": "04/03/2017 07:25:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "2",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1419",
                "RBD": "I",
                "FareBasis": "I00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "371",
                "GrossAmount": "1830",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "I",
                "FareBasis": "I00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1789.28",
                "Commission": null
              }
            ]
          }
        }
      },
      {
        "SegmentDetails": {
          "FlightId": "108",
          "AirlineId": "Z2",
          "FlightNo": "765",
          "AirCraftType": null,
          "Origin": "MNL",
          "Destination": "CEB",
          "DepartureDateTime": "04/03/2017 15:00:00",
          "ArrivalDateTime": "04/03/2017 16:25:00",
          "Duration": null,
          "NumberofStops": null,
          "StopOverCity": null,
          "CurrencyCode": "PHP",
          "FareDetails": {
            "ClassDescription": "Economy",
            "FewSeatIndicator": "8",
            "Item": [
              {
                "Pax": "Adult",
                "BasicAmount": "1419",
                "RBD": "I",
                "FareBasis": "I00H000 NonRefundable",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": "371",
                "GrossAmount": "1830",
                "Commission": null
              },
              {
                "Pax": "Child",
                "BasicAmount": null,
                "RBD": "I",
                "FareBasis": "I00H000",
                "FareType": null,
                "FuelSurcharge": null,
                "Others": null,
                "Vat": null,
                "TaxesAndOthers": null,
                "GrossAmount": "1789.28",
                "Commission": null
              }
            ]
          }
        }
      }
    ]
  },
  "session_id": "YRKSNMO97699909991877983968668964804728",
  "created_at": "2016-12-06T11:46:55.704+08:00"
}
```
Get all the available flights.

### HTTP REQUEST

`GET https://try.payswitch.net/api/v2/biyaheko/flights`

### HEADER PARAMETERS
Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token

### QUERY PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
booking_type   | String  | This requires the booking type either (O - for Oneway or R - for Roundtrip)
origin         | String  | Flight origin. (city code)
destination    | String  | Flight destination. (city code)
travel_date    | Date    | Departure date. (MM/DD/YYYY)
return_date    | Date    | Return date (MM/DD/YYYY). Required when booking_type is R - roundtrip.
class_type     | String  | Either E - for economy or B - for business.
airline_codes  | String<br>(optional)  | Pass an empty value to search for all airlines (Default); incase of searching for specific airline. Just pass airline code(IATA code) with suffix "," (Comma). (i.e. PR,5J,Z2).
no_of_adults   | Integer | No of adult passenger
no_of_childs   | Integer | Number of Child passenger. (2-11 years old)
no_of_infants  | Integer | Number of infant passenger. (0-23 months old)
senior_citizen | Integer | 0 - for non-senior citizen passenger<br/>1 - for senior citizen passenger
phil_resident  | Integer | 0 - for non-filipino resident<br/>1 - for filipino resident
direct_access  | Integer | Direct access from the host.<br/>(0 - Not Direct Access<br/> 1 - Direct Access)
trans_fee_flag | Integer | 0 - w/o transaction fee<br/>1 - with transaction fee 

###Airline Codes / IATA codes
   PR - Philippine Airline,<br/> 5J - Cebu Pacific, <br/>Z2 - Zest Air,<br/> DG - Cebgo,<br/> M8 - SkyJet


## Get Fare Rule

```shell
curl -X GET
     -H "X-User-Email: demoapiuser@demo.com"
     -H "X-User-Token: 9xDx4rzx8YmqzPmUC8C4"    
     -F "session_id=YRKSNMO97699909991877983968668964804728"
     -F "airline_id=Z2"
     -F "flight_id=101"
     -F "rbd=Z"
https://try.payswitch.net/api/v2/biyaheko/farerule
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

uri = URI("https://try.payswitch.net/api/v2/biyaheko/farerule")

params = {
  session_id:'YRKSNMO97699909991877983968668964804728',
  airline_id:'Z2',
  flight_id:101,
  rbd:'Z'
}

uri.query = URI.encode_www_form(params)

http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(uri)
request["x-user-email"] = 'demoapiuser@demo.com'
request["x-user-token"] = '9xDx4rzx8YmqzPmUC8C4'

response = http.request(request)
puts response.read_body
```

```python
import requests 

URL = "https://try.payswitch.net/api/v2/biyaheko/farerule"
HEADERS = {
    'X-User-Email' : 'demoapiuser@demo.com',
    'X-User-Token' : '9xDx4rzx8YmqzPmUC8C4'
} 
PARAMS = {
  'session_id' : 'YRKSNMO97699909991877983968668964804728',
  'airline_id' : 'Z2',
  'flight_id' : '101',
  'rbd' : 'Z'
}

response = requests.get(URL, headers=HEADERS, data=PARAMS)
print(response.text)
```

> JSON response: 

```json
{
  "success": true,
  "data": "# ECONOMY\nBooking purchased under this fare type: \n\n\n\n# \tis ALLOWED to do a flight change up to 48 hours prior to the scheduled departure time subject to a change fee chargeable per passenger per sector, plus any fare difference applicable.\n\n\n# \tis NOT ALLOWED to do a name change.\n\n\n# \tis capacity controlled and limited and hence, may not be available on all flights.\n\n\n# \tis always subject to our General Terms and Conditions of Carriage & Fee Schedule (if applicable). \n\n\n"
}
```
Get fare rule for specific airline.

### HTTP REQUEST

`GET https://try.payswitch.net/api/v2/biyaheko/farerule`

### HEADER PARAMETERS
Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


### QUERY PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
session_id | String  | Unique session from Get Available Flights response.
airline_id | String  | Airline code / IATA code. 
flight_id  | Integer | Flight id from Get Available Flights response.
rbd        | String  | Class code; RBD from Get Available Flights response.


## Get Tax

```shell
curl -X GET
     -H "X-User-Email: demoapiuser@demo.com"
     -H "X-User-Token: 9xDx4rzx8YmqzPmUC8C4"    
     -F "major_airline_id=Z2"
     -F "flights[][airline_id]=Z2"
     -F "flights[][flight_id]=101"
     -F "flights[][rbd]=Z"
     -F "flights[][eticket_flag]=1"
     -F "flights[][basic_amount]=1125"
     -F "trans_fee_flag=0"
     -F "senior_citizen=0"
https://try.payswitch.net/api/v2/biyaheko/tax/YRKSNMO97699909991877983968668964804728
```

```ruby
require 'net/http'
require 'uri'
require 'openssl'


uri = URI("https://try.payswitch.net/api/v2/biyaheko/tax/YRKSNMO97699909991877983968668964804728")

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(uri)
request["X-User-Email"] = "demoapiuser@demo.com"
request["X-User-Token"] = "9xDx4rzx8YmqzPmUC8C4"

request.set_form_data(
  "major_airline_id" => "Z2",
  "flights[][airline_id]" => "Z2",
  "flights[][flight_id]" => "101",
  "flights[][rbd]" => "Z",
  "flights[][eticket_flag]" => "1",
  "flights[][basic_amount]" => "1125",
  "trans_fee_flag" => "0",
  "senior_citizen" => "0"
)

response = http.request(request)
puts response.read_body
```

```python
import requests

URL = 'https://try.payswitch.net/api/v2/biyaheko/tax/YRKSNMO97699909991877983968668964804728'

HEADERS = {
    'X-User-Email': 'demoapiuser@demo.com',
    'X-User-Token': '9xDx4rzx8YmqzPmUC8C4',
}

PARAMS = {
    'major_airline_id': 'Z2',
    'flights[][airline_id]': 'Z2',
    'flights[][flight_id]': 101,
    'flights[][rbd]': 'Z',
    'flights[][eticket_flag]': 1,
    'flights[][basic_amount]': 1125,
    'trans_fee_flag': 0,
    'senior_citizen': 0
}

response = requests.get(URL, headers=HEADERS, data=PARAMS)
print(response.text)
```
> JSON response:

```json
{
  "success": true,
  "data": {
    "ResultCode": {
      "Status": "1"
    },
    "FlightDetails": {
      "Item": {
        "FlightId": "101",
        "Adult": {
          "CurrencyCode": "PHP",
          "BasicAmount": "1125",
          "Tax": {
            "Item": {
              "Description": "Total AdultTax",
              "Amount": "335"
            }
          },
          "GrossAmount": "1460",
          "Others": {
            "Item": {
              "Description": "Transaction Fee",
              "Amount": "40"
            }
          },
          "Commission": null
        },
        "Child": {
          "CurrencyCode": "PHP",
          "BasicAmount": "1125",
          "Tax": {
            "Item": {
              "Description": "Total ChildTax",
              "Amount": "335"
            }
          },
          "GrossAmount": "1460",
          "Others": {
            "Item": {
              "Description": "Transaction Fee",
              "Amount": "40"
            }
          },
          "Commission": null
        },
        "Infant": {
          "CurrencyCode": "PHP",
          "BasicAmount": null,
          "Tax": {
            "Item": {
              "Description": null,
              "Amount": null
            }
          },
          "GrossAmount": null,
          "Others": {
            "Item": [
              {
                "Description": null,
                "Amount": null
              },
              {
                "Description": null,
                "Amount": null
              }
            ]
          },
          "Commission": "0.0"
        }
      }
    },
    "RequiredFieldsForBooking": {
      "Age": "N",
      "IdProof": "N",
      "PassportNumber": "N",
      "Sex": "Y",
      "DateOfBirth": "Y",
      "PassportExpiryDate": "N",
      "PassportIssuingCountry": "N",
      "Nationality": "N"
    },
    "BaggageDetails": {
      "Item": [
        {
          "Code": "PBA0",
          "Description": "No Baggages",
          "Amount": "0.00"
        },
        {
          "Code": "PBAB",
          "Description": "Upto 20Kg",
          "Amount": "320"
        },
        {
          "Code": "PBAC",
          "Description": "Upto 25Kg",
          "Amount": "580"
        },
        {
          "Code": "PBAD",
          "Description": "Upto 30Kg",
          "Amount": "900"
        },
        {
          "Code": "PBAF",
          "Description": "Upto 40Kg",
          "Amount": "1700"
        }
      ]
    },
    "MealsDetails": {
      "Item": [
        {
          "Code": "PML0",
          "Description": "No Meals",
          "Amount": "0",
          "PaxTypeCode": "1"
        },
        {
          "Code": "PACB",
          "Description": "Maan's Pas",
          "Amount": "180",
          "PaxTypeCode": "1"
        },
        {
          "Code": "NLCB",
          "Description": "Pak Nasser",
          "Amount": "180",
          "PaxTypeCode": "1"
        },
        {
          "Code": "CSCB",
          "Description": "Assorted S",
          "Amount": "180",
          "PaxTypeCode": "1"
        },
        {
          "Code": "CRCB",
          "Description": "Uncle Chin",
          "Amount": "180",
          "PaxTypeCode": "1"
        },
        {
          "Code": "CACB",
          "Description": "Chicken Ad",
          "Amount": "180",
          "PaxTypeCode": "1"
        },
        {
          "Code": "BDCB",
          "Description": "Beef Calde",
          "Amount": "180",
          "PaxTypeCode": "1"
        }
      ]
    }
  }
}
```
Get tax for flight.

### HTTP REQUEST

`GET https://try.payswitch.net/api/v2/biyaheko/tax/<session_id>` 

### HEADER PARAMETERS
Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


### QUERY PARAMETERS

Parameter | Type | Description
--------- | ------- | -----------
major_airline_id | String  | Airline code / IATA code from Get Available Flights response.   
airline_id       | String  | Airline id from Get Available Flights response.
flight_id        | Integer | Flight id from Get Available Flights response.
rbd              | String  | RBD from Get Available Flights response.
eticket_flag     | Integer | 0 - without eticket<br/>1 - with eticket
basic_amount     | Double  | Basic fare for each passenger; Basic amount from Get Available Flights response.
trans_fee_flag   | Integer<br/>(optional)| 0 - w/o transaction fee<br/>1 - with transaction fee
senior_citizen   | Integer | 0 - for non-senior citizen passenger<br/>1 - for senior citizen passenger

## Create New Travel Transaction

```shell
curl -X POST
     -H "X-User-Email: demoapiuser@demo.com"
     -H "X-User-Token: 9xDx4rzx8YmqzPmUC8C4" 
     -F "sku=FLIGHT"
     -F "session_id=YRKSNMO97699909991877983968668964804728"
     -F "payload[title]=Ms"
     -F "payload[booked_by]=Kristine"
     -F "payload[country_id]=63"
     -F "payload[contact_no]=9057852992"
     -F "payload[city]=Valenzuela"
     -F "payload[zip]=1440"
     -F "payload[email]=kristineglazegallardo@gmail.com"
     -F "payload[send_mail]=1"
     -F "payload[send_sms]=1"
     -F "payload[no_of_adults]=1"
     -F "payload[no_of_childs]=0"
     -F "payload[no_of_infants]=0"
     -F "payload[senior_citizen]=0"
     -F "payload[booking_type]=O"
     -F "payload[total_amount]=4380"
     -F "payload[bookings][][airline_id]=Z2"
     -F "payload[bookings][][currency]=PHP"
     -F "payload[bookings][][amount]=4380"
     -F "payload[bookings][][passengers][][passenger_type]=Adult"
     -F "payload[bookings][][passengers][][title]=Mr"
     -F "payload[bookings][][passengers][][fname]=Juan"
     -F "payload[bookings][][passengers][][lname]=Dela Cruz"
     -F "payload[bookings][][passengers][][gender]=M"
     -F "payload[bookings][][passengers][][dob]=03/15/1993"
     -F "payload[bookings][][passengers][][nationality]=Filipino"
     -F "payload[bookings][][passengers][][segments][][flight_id]=101"
     -F "payload[bookings][][passengers][][segments][][rbd]=Z"
     -F "payload[bookings][][passengers][][segments][][baggage_code]=PBAB"
     -F "payload[bookings][][passengers][][segments][][baggage_description]=Upto 20Kg"
     -F "payload[bookings][][passengers][][segments][][baggage_amount]=320"
     -F "payload[bookings][][passengers][][segments][][meal_code]=NLCB"
     -F "payload[bookings][][passengers][][segments][][meal_description]=Pak Nasser"
     -F "payload[bookings][][passengers][][segments][][meal_amount]=180"
     -F "cost=4380"
https://try.payswitch.net/api/transactions
```

```ruby
require 'net/http'
require 'uri'

uri = URI.parse("http://localhost:3000/api/transactions")
request = Net::HTTP::Post.new(uri)

request["X-User-Email"] = "branch@demomerchant.com"
request["X-User-Token"] = "-27yj5xgePPfC9azbyAs"

request.set_form_data(
  "sku" => "FLIGHT",
  "session_id" => "YRKSNMO97699909991877983968668964804728",
  "payload[title]" => "Ms.",
  "payload[booked_by]" => "Kris",
  "payload[country_id]" => "63",
  "payload[contact_no]" => "9334378851",
  "payload[city]" => "Valenzuela",
  "payload[zip]" => "1440",
  "payload[email]" => "example@example.com",
  "payload[send_mail]" => "1",
  "payload[send_sms]" => "1",
  "payload[no_of_adults]" => "1",
  "payload[no_of_childs]" => "0",
  "payload[no_of_infants]" => "0",
  "payload[senior_citizen]" => "0",
  "payload[booking_type]" => "O",
  "payload[total_amount]" => "2000",
  "payload[bookings][][airline_id]" => "Z2",
  "payload[bookings][][currency]" => "PHP",
  "payload[bookings][][amount]" => "2000",
  "payload[bookings][][passengers][][passenger_type]" => "Adult",
  "payload[bookings][][passengers][][title]" => "Ms.",
  "payload[bookings][][passengers][][fname]" => "Kristine",
  "payload[bookings][][passengers][][lname]" => "Park",
  "payload[bookings][][passengers][][gender]" => "M",
  "payload[bookings][][passengers][][dob]" => "12/25/1995",
  "payload[bookings][][passengers][][nationality]" => "Filipino",
  "payload[bookings][][passengers][][segments][][flight_id]" => "101",
  "payload[bookings][][passengers][][segments][][rbd]" => "Z",
  "payload[bookings][][passengers][][segments][][baggage_code]" => "PBAB",
  "payload[bookings][][passengers][][segments][][baggage_description]" => "Upto 20Kg",
  "payload[bookings][][passengers][][segments][][baggage_amount]" => "320",
  "payload[bookings][][passengers][][segments][][meal_code]" => "NLCB",
  "payload[bookings][][passengers][][segments][][meal_description]" => "Pak Nasser",
  "payload[bookings][][passengers][][segments][][meal_amount]" => "180",
  "cost" => "2000"
)

response = Net::HTTP.start(uri.hostname, uri.port, use_ssl: uri.scheme == "https") do |http|
  http.request(request)
end

puts response.read_body
```

```python
import requests

URL = 'http://localhost:3000/api/transactions'

HEADERS = {
    'X-User-Email': 'branch@demomerchant.com',
    'X-User-Token': '-27yj5xgePPfC9azbyAs',
}

PARAMS = {
  'sku' : 'FLIGHT',
  'session_id' : 'YRKSNMO97699909991877983968668964804728',
  'payload[title]' : 'Ms.',
  'payload[booked_by]' : 'Kris',
  'payload[country_id]' : 63,
  'payload[contact_no]' : 9334378851,
  'payload[city]' : 'Valenzuela',
  'payload[zip]' : 1440,
  'payload[email]' : 'example@example.com',
  'payload[send_mail]' : 1,
  'payload[send_sms]' : 1,
  'payload[no_of_adults]' : 1,
  'payload[no_of_childs]' : 0,
  'payload[no_of_infants]' : 0,
  'payload[senior_citizen]' : 0,
  'payload[booking_type]' : 'O',
  'payload[total_amount]' : 2000,
  'payload[bookings][][airline_id]' : 'Z2',
  'payload[bookings][][currency]' : 'PHP',
  'payload[bookings][][amount]' : 2000,
  'payload[bookings][][passengers][][passenger_type]' : 'Adult',
  'payload[bookings][][passengers][][title]' : 'Ms.',
  'payload[bookings][][passengers][][fname]' : 'Kristine',
  'payload[bookings][][passengers][][lname]' : 'Park',
  'payload[bookings][][passengers][][gender]' : 'M',
  'payload[bookings][][passengers][][dob]' : '12/25/1995',
  'payload[bookings][][passengers][][nationality]' : 'Filipino',
  'payload[bookings][][passengers][][segments][][flight_id]' : 101,
  'payload[bookings][][passengers][][segments][][rbd]' : 'Z',
  'payload[bookings][][passengers][][segments][][baggage_code]' : 'PBAB',
  'payload[bookings][][passengers][][segments][][baggage_description]' : 'Upto 20Kg',
  'payload[bookings][][passengers][][segments][][baggage_amount]' : 320,
  'payload[bookings][][passengers][][segments][][meal_code]' : 'NLCB',
  'payload[bookings][][passengers][][segments][][meal_description]' : 'Pak Nasser',
  'payload[bookings][][passengers][][segments][][meal_amount]' : 180,
  'cost' : 2000
}

response = requests.post(URL, headers=HEADERS, data=PARAMS)
print(response.text)
```
> JSON response:

```json
{
  "id": 725,
  "payload": {
    "session_id": "YRKSNMO97699909991877983968668964804728",
    "title": "Ms",
    "booked_by": "Kristine",
    "country_id": "63",
    "contact_no": "9334378851",
    "city": "Valenzuela",
    "zip": "1440",
    "email": "example@example.com",
    "send_mail": "0",
    "send_sms": "0",
    "no_of_adults": "1",
    "no_of_childs": "0",
    "no_of_infants": "0",
    "senior_citizen": "0",
    "booking_type": "O",
    "total_amount": "2000",
    "bookings": [
      {
        "airline_id": "Z2",
        "currency": "PHP",
        "amount": "2000",
        "passengers": [
          {
            "passenger_type": "Adult",
            "title": "Ms",
            "fname": "Kristine",
            "lname": "Park",
            "gender": "F",
            "dob": "12/25/1995",
            "nationality": "Filipino",
            "segments": [
              {
                "flight_id": "101",
                "rbd": "Z",
                "baggage_code": "PBAB",
                "baggage_description": "Upto 20Kg",
                "baggage_amount": "320",
                "meal_code": "NLCB",
                "meal_description": "Pak Nasser",
                "meal_amount": "180"
              }
            ]
          }
        ]
      }
    ]
  },
  "cost": "2000.0",
  "created_at": "2016-12-07T15:49:46.000+08:00",
  "provider_refno": "YRKSNMO97699909991877983968668964804728",
  "convenience_fee": null,
  "service_fee": "50.0",
  "rebates": "50.0",
  "provider_message": {
    "code": null,
    "message": "Transaction successful."
  },
  "computed_cost": 2050,
  "total_transaction_cost": "2050.0",
  "transaction_status": {
    "code": "00",
    "name": "Successful",
    "description": "Transaction has been successful"
  },
  "user": {
    "id": 2,
    "type": "Branch",
    "name": "Demo Branch",
    "merchant": {
      "id": 1,
      "name": "Demo Merchant"
    }
  },
  "provider_product": {
    "id": 486,
    "product_category_root_id": 36,
    "product": {
      "id": 477,
      "sku": "FLIGHT",
      "name": "Flight Booking"
    }
  }
}
```


### HTTP REQUEST

`POST https://try.payswitch.net/api/transactions`

### HEADER PARAMETERS
Parameter | Type | Description
--------- | ------- | -----------
X-User-Email | string<br/>(required) | The user's email address
X-User-Token | string<br/>(required) | The user's authentication token


### QUERY PARAMETERS
Parameter | Type | Description
--------- | ------- | -----------
sku                 |  String   | 
session_id          |  String   | Unique session id from Get Available Flights.
title               |  String   | Either Mr. / Mrs.
booked_by           |  String   | Agent / Customer name.
country_id          |  Integer  | Requires country id. (63) for Philippines
contact_no          |  Integer  | Booker' contact number.
city                |  String   | Booker' city.
zip                 |  Integer  | Booker' zipcode.
email               |  String   | Booker' email address.
send_mail           |  Integer  | This requires whether to notify your booking via Email.<br/>(0 - No Need to Notify<br/>1 - Notify)
send_sms            |  Integer  | This requires whether to notify your booking via SMS.<br/>(0 - No Need to Notify<br/>1 - Notify)
no_of_adults        |  Integer  | Number of adult passenger.
no_of_childs        |  Integer  | Number of child passenger.
no_of_infants       |  Integer  | Number of infant passenger.
senior_citizen      |  Integer  | 0 - for non-senior citizen passenger<br/>1 - for senior citizen passenger
booking_type        |  String   | Either O - for oneway or R - for roundtrip.
total_amount        |  Double   | Total fare amount for return flight and/or departure flight.
airline_id          |  String   | Airline code / IATA code.
currency            |  String   | Currency; PHP for Philippine peso.
amount              |  Double   | Amount to be paid for the flight.
passenger_type      |  String   | If the passenger is an Adult, Child or Infant.
title               |  String   | Whether Mr., Mrs. or Inft for an infant passenger.
fname               |  String   | Passenger' first name.
lname               |  String   | Passenger' last name.
gender              |  String   | Passenger' gender.
dob                 |  Date     | Passenger' date of birth.
nationality         |  String   | Passenger' nationality.
flight_id           |  Integer  | Flight id from Get Available Flights response.
rbd                 |  String   | Class code ; RBD from Get Available Flights Flights response.
baggage_code        |  String   | Baggage code from Get Tax response.
baggage_description |  String   | Baggage description from Get Tax response.
baggage_amount      |  Double   | Baggage amount from Get Tax response.
meal_code           |  String   | Meal code from Get Tax response. 
meal_description    |  String   | Meal description from Get Tax response.
meal_amount         |  Double   | Meal amount from Get Tax response.
cost                |  Double   | Total cost.