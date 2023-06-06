### Base URL
The base address of Web API is https://api.spotify.com.
***
### Requests
##### GET – RETRIEVES RESOURCE
##### POST–CREATE RESOURCES
##### PUT– CHANGE AND/OR REPLACE RESOURCES OR COLLECTIONS
##### DELETE– DELETE RESOURCES
***
### RESPONSE STATUS CODE:
+ 200 OK - The request has succeeded. The client can read the result of the request in the body and the headers of the response.

+ 201 Created - The request has been fulfilled and resulted in a new resource being created.

+ 202 Accepted - The request has been accepted for processing, but the processing has not been completed.

+ 204 No Content - The request has succeeded but returns no message body.

+ 304 Not Modified. See Conditional requests.

+ 400 Bad Request - The request could not be understood by the server due to malformed syntax. The message body will contain more information

+ 401 Unauthorized - The request requires user authentication or, if the request included authorization credentials, authorization has been refused for those credentials.

+ 403 Forbidden - The server understood the request, but is refusing to fulfill it.

+ 404 Not Found - The requested resource could not be found. This error can be due to a temporary or permanent condition.

+ 429 Too Many Requests - Rate limiting has been applied.

+ 500 Internal Server Error. You should never receive this error because our clever coders catch them all ... but if you are unlucky enough to get one, please report it to us through a comment at the bottom of this page.
+ 502 Bad Gateway - The server was acting as a gateway or proxy and received an invalid response from the upstream server.

+ 503 Service Unavailable - The server is currently unable to handle the request due to a temporary condition which will be alleviated after some delay. You can choose to resend the request again.

### Authorization:
Spotify implements the OAuth 2.0 authorization framework

**Request Authorization:** To request an access token, make a POST call to the
https://accounts.spotify.com/api/token

receive an HTTP 200 response with a payload containing access_token, token_type, and expires_in values:

If everything goes well, receive a response similar to this containing the Access Token:
```
{
"access_token": "NgCXRKc...MzYjw",
"token_type": "bearer",
"expires_in": 3600
}
```
### Application requests authorization
Redirect url: https://accounts.spotify.com/authorize?
It will check the authorization by client_id

### Register new user
Method: post
Url: \register-user \
Status code: 200 (account create successful) & If the Partner User ID has already been linked to another Spotify user the request will fail with HTTP status code 409

### GET USER:
Url: https://api.spotify.com/v1/me
Check the client_id and client_secret

#####  Method: GET
##### Status code:
###### 200 with successful massage
###### 401 Bad or expire token
###### 403 Bad OAuth request (wrong consumer key, bad nonce, expired timestamp...).
###### 429 The app has exceeded its rate limits.

### GET USER PROFILE:
##### Url: https://api.spotify.com/v1/me/users/{user_id}
##### Method: GET
##### Status code:
+ 200 with successful massage
+ 401 Bad or expire token and send A short description of the cause of the error.
+ 403 Bad OAuth request (wrong consumer key, bad nonce, expired timestamp...) and send A short description of the cause of the error.
+ 429 The app has exceeded its rate limits and send A short description of the cause of the error.

### FOLLOW PLAYLIST:
##### Url: /playlists/{playlist_id}/followers
##### Method: PUT
##### Status code:
+ 200 Playlist followed
+ 401 Bad or expire token and send A short description of the cause of the error.
+ 403 Bad OAuth request (wrong consumer key, bad nonce, expired timestamp...) and send A short description of the cause of the error.
+ 429 The app has exceeded its rate limits and send A short description of the cause of the error.

### UNFOLLOW PLAYLIST:
##### Url: /playlists/{playlist_id}/followers
##### Method: DELETE
##### Status code:
+ 200 Playlist unfollowed
+ 401 Bad or expire token and send A short description of the cause of the error.
+ 403 Bad OAuth request (wrong consumer key, bad nonce, expired timestamp...) and send A short description of the cause of the error.
+ 429 The app has exceeded its rate limits and send A short description of the cause of the error.



