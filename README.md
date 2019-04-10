# Banka-API
Documentation for Banka API v0.0.0
url: https://banka-ch-api.herokuapp.com
Root: /api/v1/


- [Account](#account)
	- [Create account](#create-account)
	- [Delete account](#delete-account)
	- [Retrieve account](#retrieve-account)
	- [Retrieve accounts](#retrieve-accounts)
	- [Update account](#update-account)
	
- [Auth](#auth)
	- [Authenticate Signup](#authenticate-signup)
	- [Authenticate Signin](#authenticate-signin)
	
- [User](#user)
	- [Create user](#create-user)
	- [Delete user](#delete-user)
	- [Retrieve user](#retrieve-user)
	- [Retrieve users](#retrieve-users)

- [Transaction](#transaction)
	- [Credit account](#credit-account)
	- [Debit account](#debit-account)
	


# Account

## Create Account



	POST /accounts


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| firstName			| String			|  <p>user first name.</p>							|
| lastName			| 			|  <p>user last name</p>							|
| dob			| ISO Date(1995-05-25)			|  <p>user date of birth.</p>							|
|sex			|String				|<p>user sex</p>|
|email			|				|<p>user email</p>|
|phone			|				|<p>user phone</p>|
|type			|				|<p>'current' or 'savings'</p>|
|currency		|				|<p>'Naira' or 'Dollar'</p>|
|address		|				|<p>user address</p>|

## Delete account



	DELETE /accounts/:account-number


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| account-number			| Integer			|  <p>Account number to be deleted</p>							|

## Retrieve account



	GET /accounts/:account-number


## Retrieve accounts



	GET /accounts


## Update account



	PATCH /accounts/:account-number


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| status			| String			|  <p>Status to patch; 'active' or 'dormant'</p>							|


# Auth

## Authenticate Signup



	POST /auth/signup

### Headers

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization			| String			|  <p>Basic authorization with email and password.</p>							|

### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| access_token			| String			|  <p>JWT token</p>							|


## Authenticate Signin

	POST /auth/signin

### Headers

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization			| String			|  <p>Basic authorization with email and password.</p>							|

### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| access_token			| String			|  <p>JWT token</p>							|



# User

## Create user



	POST /users


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| firstName			| String			|  <p>user first name.</p>							|
| lastName			| 			|  <p>user last name</p>							|
| email			| 			|  <p>user email</p>							|
|password			|String				|<p>user password</p>|
|confirmPassword			|				|				|

## Delete user



	DELETE /users/:id


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| id			| Integer			|  <p>User id.</p>							|



## Retrieve user



	GET /users/:id


## Retrieve users



	GET /users


### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| id			| Integer			|  <p>User id.</p>							|



#Transaction

##Credit Account

POST /transaction/:account-number/credit
### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| amount			| Integer			|  <p>Amount to Credit</p>							|
| transactionType			| String			|  <p>'Credit' or 'Debit'</p>							|


##Debit Account

POST /transaction/:account-number/debit
### Parameters

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| amount			| Integer			|  <p>Amount to debit</p>							|
| transactionType			| String			|  <p>'Credit' or 'Debit'</p>							|
