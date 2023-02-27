Lecture 8: Web & HTTP

WebPage
- Consists of a few objects
	- HTML
	- JPEG
	- Applet java
	- Audio
- Consists of base HTML-File 
	- Includes referenced-Objects
	- Each object is addressable by URL

HTTP
- By Default uses TCP (Port 80)
	- Websites are important
	- Intention is to display all contents of the page
- Is Stateless
	- Does not hold any past client requests
	- Uses info from current request to gather information, i.e, cookies
- Connections
	- Non-persistent HTTP
		- Handshake, transfer data and then close connection
		- Need multiple connections to download files
		- 1 object per handshake + base Page
		- Used in HTTP 1.0 only
		- Response Time
			- RTT, Time for small packet to travel from client to server and back
			- 2xRTT + File Transmission time
				- This is due to one RTT required for a Handshake + one more for the Object itself
		- OS Overhead required for each TCP Connection
		- Browsers often have to fetch referenced Objects using parallel TCP Connections
	- persistent HTTP
		- covered in [[CNET 22 Feb, 2023]]
- Requests
	- HTTP 1.0
		- GET, POST, HEAD
		- HEAD: Ask server to leave requested Object out of response
	- HTTP 1.1
		- GET, POST, HEAD + PUT, DELETE
		- PUT: Upload file in entity body to path specified in URL field
		- DELETE: Deletes file specified in the URL field
- Response Codes
	- Appears in the first line
		- 200 OK
		- 301 Moved to a new location specified in location
		- 400 Bad Request
		- 404 Not Found
		- 505 HTTP Version not supported
- Cookies
	- Used to give State to a client
	- For first connection
		- Server creates and saves a cookie ID and sends its in its response back to the client
	- For a already established connection
		- Client sends the cookie ID

