# Scala-Akka-Rest-API
- [Overview](#overview)
- [Resources](#paths)
  - [Restaurant](#restaurant_resource)
    - [Create Restaurant](#create_restaurant)
    - [Get all Restaurants](#get_restaurants)
    - [Get Restaurant by Id](#get_restaurant)
    - [Update Restaurant](#update_restaurant)
    - [Delete Restaurant](#delete_restaurant)
    - [Get Restaurants by latitude and logitude](#restaurants_by_lat_lon)
  - [Restaurant Types](#restaurant_type_resource)
    - [Get all restaurant types](#get_restaurant_types)
  - [Restaurant Address](#address_resource)
    - [Create Address](#create_address)
    - [Get Address](#get_address)
    - [Update Address](#update_address)
    - [Delete Address](#delete_address)
  - [Restaurant Images](#image_resource)
    - [Create Image](#create_image)
    - [Get all Images](#get_images)
    - [Get Image by Id](#get_image)
    - [Update Image](#update_image)
    - [Delete Image](#delete_image)
  - [Category](#category_resource)
    - [Create Category](#create_category)
    - [Get all Category](#get_category)
    - [Update Category](#update_category)
    - [Delete Category](#delete_category)
  - [Dish](#dish_resource)
    - [Create Dish](#create_dish)
    - [Get all Dishes](#get_dishes)
    - [Get Dish by Id](#get_dish)
    - [Get Dishes by Category](#get_dish_by_category)
    - [Update Dish](#update_dish)
    - [Delete Dish](#delete_dish)
  - [Dish Category](#dish_category_resource)
    - [Create Dish for given Category](#create_dish_category)
  - [Dish Ingredients](#ingredient_resource)
    - [Create Ingredient](#create_ingredient)
    - [Get all Ingredients](#get_ingredients)
    - [Get_Ingredient](#get_ingredient)
    - [Update Ingredients](#update_ingredient)
    - [Delete Ingredient](#delete_ingredient)
  - [Order](#order_resource)
    - [Create Order](#create_order)
    - [Get Orders](#get_orders)
    - [Get single Order](#get_order)
    - [Update Order](#update_order)
    - [Delete Order](#delete_order)
  - [Order Dishes](#order_dishes_resource)
    - [Create Order dishes](#create_order_dish)
    - [Get all Order Dishes](#get_order_dishes)
    - [Update Order Dish](#update_order_dish)
    - [Delete Order Dish](delete_order_dish)
  - [Review](#review_resource)
    - [Create review](#create_review)
    - [Get all Reviews](#get_reviews)
    - [Get Review](#get_review)
    - [Update Review](#update_review)
    - [Delete Review](#delete_review)
  - [Application Review](#app_review_resource)
    - [Create Application Review](#create_app_review)
    - [Get all Application Reviews](#get_app_reviews)
    - [Get Application Review](#get_app_review)
    - [Update Application Review](#update_app_review)
    - [Delete Application Review](#delete_app_review)  
  - [User](#user_resource)
    - [Create User](#create_user)
    - [Get all Users](#get_users)
    - [Get User by Id](#get_user)
    - [User Login](#user_login)
    - [Update User](#update_user)
    - [Delete User](#delete_user)
    
    
<a name="overview"></a>
## Overview
Taplicious API

<a name="paths"></a>
## Resources
### Base URL - Append all request url after base url
```
http://ec2-34-237-123-153.compute-1.amazonaws.com
```

<a name="restaurant_resource"></a>
### Restaurant

<a name="create_restaurant"></a>
#### Create Restaurant
```
POST /api/restaurants
```
##### Description
Create a new restaurant

##### Parameters
|Name|Description|Schema|
|---|---|---|
|**name** <br>*required*|**Example** : `"Indian Masala"`|String|
|**restaurantTypeId** <br>*required*|**Example** : `1`|Long|
|**image** <br>*optional*|**Example** : `"taplicious.jpg"`|String|
|**latitude** <br>*required*|**Example** : `3.4947`|Float|
|**longitude** <br>*required*|**Example** : `4.2343`|Float|
|**isTapliciousApp** <br>*required*|**Example** : `true`|Boolean|
|**phone** <br>*optional*|**Example** : `"1234567890"`|String|
|**email** <br>*optional*|**Example** : `"indianmasala@example.com"`|String|
###### Request body
```
{
    "name": "Indian Masala",
    "restaurantTypeId": 1,
    "image": "taplicious.jpg",
    "latitude": 3.4947,
    "longitude": 4.2343,
    "isTapliciousApp": true,
    "phone": "22222222222",
    "email": "indianmasala@example.com"
}
```
###### Response 201
```
{
    "id": 5,
    "name": "Indian Masala",
    "restaurantTypeId": 1,
    "image": "taplicious.jpg",
    "latitude": 3.4946999549865723,
    "longitude": 4.234300136566162,
    "isTapliciousApp": true,
    "phone": "22222222222",
    "email": "indianmasala@example.com",
    "createdAt": "2018-11-15 14:18:18.908",
    "updatedAt": "2018-11-15 14:18:18.908"
}
```

<a name="get_restaurants"></a>
#### Get All Restaurants
```
GET /api/restaurants
```

<a name="get_restaurant"></a>
#### Get Single Restaurant by Id
```
GET /api/restaurants/{restaurant_id}
```

<a name="update_restaurant"></a>
#### Update Restaurant
```
PUT /api/restaurants/{restaurant_id}
```
##### Description
Update restaurant information
##### Parameters
|Name|Description|Schema|
|---|---|---|
|**id** <br>*required*|**Example** : `5` |Long|
|**name** <br>*optional*|**Example** : `"Indian Masala"`|String|
|**restaurantTypeId** <br>*optional*|**Example** : `1`|Long|
|**image** <br>*optional*|**Example** : `"taplicious.jpg"`|String|
|**latitude** <br>*optional*|**Example** : `3.4947`|Float|
|**longitude** <br>*optional*|**Example** : `4.2343`|Float|
|**isTapliciousApp** <br>*optional*|**Example** : `true`|Boolean|
|**phone** <br>*optional*|**optional** : `"1234567890"`|String|
|**email** <br>*optional*|**optional** : `"indianmasala@example.com"`|String|

###### Request body
```
{
    "id": 5,
    "email": "indianmasala-test@example.com"
}
```
###### Response 200
```
{
    "id": 5,
    "name": "Indian Masala",
    "restaurantTypeId": 1,
    "image": "taplicious.jpg",
    "latitude": 3.4946999549865723,
    "longitude": 4.234300136566162,
    "isTapliciousApp": true,
    "phone": "22222222222",
    "email": "indianmasala-test@example.com",
    "createdAt": "2018-11-15 14:18:18.908",
    "updatedAt": "2018-11-15 14:38:56.827"
}
```

<a name="delete_restaurant"></a>
#### Delete Restaurant
```
DELETE /api/restaurants/{restaurant_id}
```

<a name="restaurants_by_lat_lon"></a>
#### Get Restaurant by Latitude and Longitude
```
GET /api/restaurants/{restaurant_id}?lat1={min_lat}&lon1={min_lon}&lat2={max_lat}&lon2={max_lon}
```

<a name="restaurant_type_resource"></a>
### Restaurant Types

<a name="get_restaurant_types"></a>
#### Get all Restaurant Types
```
GET /api/restaurant_types
```

<a name="address_resource"></a>
### Restaurant Address

<a name="create_address"></a>
#### Create Address
```
POST /api/restaurants/{restaurant_id}/address
```
##### Description
Create restaurant address

##### Parameters
|Name|Description|Schema|
|---|---|---|
|**restaurantId** <br>*required*|**Example** : `5`|Long|
|**addr1** <br>*required*|**Example** : `"500 S Oakland Blvd"`|String|
|**addr2** <br>*optional*|**Example** : `"Suite 200"`|String|
|**city** <br>*required*|**Example** : `"Oakland"`|String|
|**state** <br>*required*|**Example** : `"California"`|String|
|**zipcode** <br>*required*|**Example** : `12345`|Integer|
|**country** <br>*required*|**Example** : `"USA"`|String|
###### Request body
```
{
    "restaurantId": 5,
    "addr1": "500 S Oakland Blvd",
    "addr2": "Suite 200",
    "city": "Oakland",
    "state": "California",
    "zipcode": 12345,
    "country": "USA"
}
```
###### Response 201
```
{
    "id": 1,
    "restaurantId": 5,
    "addr1": "500 S Oakland Blvd",
    "addr2": "Suite 200",
    "city": "Oakland",
    "state": "California",
    "zipcode": 12345,
    "country": "USA"
    "createdAt": "2018-11-15 14:18:18.908",
    "updatedAt": "2018-11-15 14:18:18.908"
}
```

<a name="get_address"></a>
#### Get Address
```
GET /api/restaurants/{restaurant_id}/address
```

<a name="update_address"></a>
#### Update Restaurant
```
PUT /api/restaurants/{restaurant_id}/address/{address_id}
```

<a name="delete_address"></a>
#### Delete Restaurant
```
DELETE /api/restaurants/{restaurant_id}/address/{address_id}
```

<a name="image_resource"></a>
### Restaurant Images

<a name="create_image"></a>
#### Create Image

<a name="get_images"></a>
#### Get all Images

<a name="get_image"></a>
#### Get single Image

<a name="update_image"></a>
#### Update Image

<a name="delete_image"></a>
#### Delete Image

<a name="category_resource"></a>
### Restaurant Category for Dishes

<a name="create_category"></a>
#### Create Category

<a name="get_category"></a>
#### Get all Category

<a name="update_category"></a>
#### Update Category

<a name="delete_category"></a>
#### Delete Category

<a name="dish_resource"></a>
### Restaurant Dishes

<a name="create_dish"></a>
#### Create Dish

<a name="get_dishes"></a>
#### Get all Dishes

<a name="get_dish"></a>
#### Get single Dish

<a name="get_dish_by_category"></a>
#### Get all Dishes for given Category

<a name="update_dish"></a>
#### Update Dish

<a name="delete_dish"></a>
#### Delete Dish

<a name="ingredient_resource"></a>
### Dish Ingredients

<a name="create_ingredient"></a>
#### Create Ingredient

<a name="get_ingredients"></a>
#### Get all Ingredients

<a name="get_ingredient"></a>
#### Get single Ingredient

<a name="update_ingredient"></a>
#### Update Ingredient

<a name="delete_ingredient"></a>
#### Delete Ingredient

<a name="order_resource"></a>
### Restaurant Order

<a name="create_order"></a>
#### Create Order

<a name="get_orders"></a>
#### Get all Orders

<a name="get_order"></a>
#### Get single Order

<a name="update_order"></a>
#### Update Order

<a name="delete_order"></a>
#### Delete Order

<a name="order_dishes_resource"></a>
### Order Dishes

<a name="create_order_dish"></a>
#### Create Order Dishes

<a name="get_order_dishes"></a>
#### Get all Order Dishes

<a name="update_order_dish"></a>
#### Update Order Dish

<a name="delete_order_dish"></a>
#### Delete Order Dish

<a name="review_resource"></a>
### Restaurant Reviews

<a name="create_review"></a>
#### Create Review

<a name="get_reviews"></a>
#### Get all Reviews

<a name="get_review"></a>
#### Get single Review

<a name="update_review"></a>
#### Update Review

<a name="delete_review"></a>
#### Delete Review

<a name="app_review_resource"></a>
### Taplicious Application Review

<a name="create_app_review"></a>
#### Create Application Review

<a name="get_app_reviews"></a>
#### Get all Application Reviews

<a name="get_app_review"></a>
#### Get single Application Review

<a name="update_app_review"></a>
#### Update Application Review

<a name="delete_app_review"></a>
#### Delete Application Review

<a name="user_resource"></a>
### User

<a name="user_login"></a>
### User Login
