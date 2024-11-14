# SoftwareProjectDocumentation
# Music Library
Music Library Albums API

This API lets users manage a music library by retrieving, adding, updating, and deleting albums. Each album includes details such as the artist, album title, record label, and sales figures. Below is a guide to the available endpoints.

Table of Contents

Endpoints
GET /data/albums/{id}
POST /data/albums
PUT /data/albums/{id}
DELETE /data/albums/{id}
Authentication
Error Handling
GET /data/albums/{id}
This endpoint retrieves information about a specific album using its ID.

Description: Returns details about an album.
Path Parameter:

id (string, required): The unique ID of the album.
Responses:
200 OK: The album details were retrieved successfully.
404 Not Found: No album was found with the provided ID.
Example Request:
GET /data/albums/12345

POST /data/albums
This endpoint allows you to add a new album to the music library.

Description: Creates a new album record.
Body Parameter:

album (object, required): Contains the album details.
singer (string): The artist’s name.
album (string): The album title.
label (string): The record label.
sales (string): The album’s sales information.
Responses:
200 OK: The album was successfully added.
400 Bad Request: The provided data is invalid.
Example Request:
POST /data/albums
Content-Type: application/json

{
"singer": "Artist Name",
"album": "Album Title",
"label": "Record Label",
"sales": "500000"
}

PUT /data/albums/{id}
This endpoint updates the details of an existing album by its ID.

Description: Modifies an album's information.
Path Parameter:

id (string, required): The unique ID of the album.
Body Parameter:
album (object, required): Updated album details.
singer (string): The updated artist’s name.
album (string): The updated album title.
label (string): The updated record label.
sales (string): The updated sales information.
Responses:
200 OK: The album was successfully updated.
404 Not Found: No album was found with the provided ID.
400 Bad Request: The provided data is invalid.
Example Request:
PUT /data/albums/12345
Content-Type: application/json

{
"singer": "Updated Artist Name",
"album": "Updated Album Title",
"label": "Updated Record Label",
"sales": "600000"
}

DELETE /data/albums/{id}
This endpoint deletes an album from the library using its ID.

Description: Removes an album from the library.
Path Parameter:

id (string, required): The unique ID of the album.
Responses:
200 OK: The album was successfully deleted.
404 Not Found: No album was found with the provided ID.
Example Request:
DELETE /data/albums/12345

Authentication
All API requests require authentication. Include a valid token in the Authorization header.

Example:
Authorization: Bearer <your-token-here>

Error Handling
Standard HTTP response codes are used to indicate the outcome of each request.

200 OK: The request was successful.
400 Bad Request: The request was invalid or incomplete.
404 Not Found: The requested resource was not found.
500 Internal Server Error: An unexpected error occurred on the server.
Each error response contains a descriptive message to help troubleshoot the issue.
