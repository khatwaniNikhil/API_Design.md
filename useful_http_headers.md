top http headers
https://pentest-tools.com/blog/essential-http-security-headers
https://stackoverflow.com/questions/30062024/why-is-the-http-header-for-authentication-called-authorization

1. WWW-Authenticate header
	server replying to client - go first authenticate yourself(may be with thirdparty) via one of the provided schemes
	and then make hit(alongwith authorization header) to get your access checked and then data will  be returned

2. Authorization header
	post authentication done, client will send authorization token to server for access control verfication based data access.

Note: http basic creates confusion among authentication and authorization as authentication is same as authorization(username and password only)

3. Access-Control-Allow-Origin

Site1.com responding with below header to browser to confirm that site2 is allowed to acces site 1's content
Access-Control-Allow-Origin: Site2.com

4. cookies 

cookie sent by server to client
"Set-Cookie" header
for security can set 
	1. "Secure" attribute - A cookie set with this attribute will only be sent over HTTPS and not over the clear-text HTTP protocol
	2. "HTTPOnly" attribute - The browser will not permit JavaScript code to access the contents of the cookies set with this attribute. 
				This helps in mitigating session hijacking through XSS attacks.

client sending cookie in subsequent requests
"Cookie" header

5. X-FrameOptions 
This header is used to protect the user against ClickJacking attacks by forbidding the browser to load the page in an iframe element.
"DENY" - This will not allow the page to be loaded in a frame on any website.
"same-origin" -  This will allow the page to be loaded in a frame only if the origin frame is the same
		 i.e. A page on www.site.com will load in a frame only if the parent page on which the frame is being loaded has the same origin (www.site.com)
"allow-from uri" - The frame can only be displayed in a frame on the specified domain/origin.
