1. TO GET THE LIST OF HOTELS IN A STATE
METHOD: GET
URL: https://hotel-bookings-api.herokuapp.com/api/getByState/:statename

where :statename is the name of the state you require a hotel in.

2. TO GET THE LIST OF HOTELS IN A CITY
METHOD: GET
URL: https://hotel-bookings-api.herokuapp.com/api/getByCity/:city
where :city is the name of the city the hotel is needed.

3. TO GET THE DETAILS OF A PARTICULAR HOTEL
METHOD: GET
URL: https://hotel-bookings-api.herokuapp.com/api/getHotelDetails/:hotelId

where :hotelId is the hotel Id gotten from query 1 or 2

4. TO GET THE DETAILS OF THE ROOMS IN A HOTEL(This can be gotten using the other endpoint)
METHOD: GET
URL: https://hotel-bookings-api.herokuapp.com/api/getHotelRooms/:hotelId

5. TO GET THE KEY VALUE REQUIRED TO MAKE BOOKINGS IN A HOTEL
METHOD: POST
URL: https://hotel-bookings-api.herokuapp.com/api/getHotelBookingInfo

where data to be sent should be in this format
data = {
  "hotel_id": "hotelId",
  "checkin": "yyyy-mm-dd",   //check in date in yyyy-mm-dd format
  "checkout": "yyyy-mm-dd",  //check out date in yyyy-mm-dd format
  "booked_rooms": [{
    "id": "roomId",           // the ID of the room gotten from the data in  API 4
    "num": "number"           // the number of rooms to be booked
  }]
}



response = {
  "data": {
    "key": "22857d9c607da869b2158c57a9fe3c85",
    "total_price": 28000
  }
}


6. TO BOOK A HOTEL
URL = https://hotel-bookings-api.herokuapp.com/api/bookHotel
METHOD = POST

Sample data to be sent:

  var data = {
    "client_title": "Miss",
    "client_full_name": "User name",
    "country_id": "157",
    "email_address ": "User Email Address,
    "phone": "UsePhone Number",
    "key": key_from_getHotelBookingInfo_response
  }



Response:
  response.data = {
    "data": {
      "client_title": "Miss/Ms/Mrs/Mr",
      "client_full_name": "User name",
      "country_id": "157",
      "email_address": "Email Address",
      "phone": "Phone Number",
      "checkin": "yyyy-mm-dd 00:00:00",
      "checkout": "yyyy-mm-dd 00:00:00",
      "hotel_id": "hotelId",
      "total_price": price,
      "id": id
    }
  }


TODO:Merge the last 2 together


 {
      "id": "2093",
      "hotel_id": "99374",
      "name": "Executive Classic",
      "roomprice": "26400",
      "image_id": null,
      "description": "",
      "admin_description": "",
      "buying_rate": "23760",
      "selling_rate": "26400",
      "promo_rate": "0",
      "promo_rate_detail": "",
      "rate_expiry_date": "0000-00-00 00:00:00"
    },
