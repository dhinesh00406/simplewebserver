# EX01 Developing a Simple Webserver


## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```C
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<html>
	<title>web page </title>
<body>
	<table border="3" cellspacing="10">
	<caption> Top five Revenue Generating Software Companies </caption>
	<tr>
		<th> S.NO </th>
		<th>Company </th>
		<th> Revenue </th>
	</tr>
	<tr>
	<td> 1 </td>
	<td> MICROSOFT </td>
	<td> 65 Billion </td>
	</tr>
	<tr>
	<td> 2 </td>
	<td> Oracle </td>
	<td> 29.6 billion </td>
	</tr>
	<tr>
	<td> 3 </td>
	<td> IBM </td>
	<td> 29.1 billion </td>
	</tr>
	<tr>
	<td> 4 </td>
	<td> SAP </td>
	<td> 6.4 billion </td>
	</tr>
	<tr>
	<td> 5 </td>
	<td> Symantec </td>
	<td> 5.6 billion </td>
	</tr>
	</table>
</body>
</html>
 


"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![1](https://github.com/Rajkiran0604/simplewebserver/assets/164345543/024230aa-8144-4d94-b3b3-89bcf4308f3d)
![2](https://github.com/Rajkiran0604/simplewebserver/assets/164345543/d6e976e5-4982-4c09-b0a3-565f5fe3bf7d)
## RESULT:
The program for implementing simple webserver is executed successfully.
