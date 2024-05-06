# EX01 Developing a Simple Webserver
## Date:13/03/2024

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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Webserver</title>
</head>
<body>
    <h1>Top 5 Revenue Companies</h1>
    <ol>
        <li>Apple</li>
        <li>Google</li>
        <li>Amazon</li>
        <li>Samsung</li>
        <li>TATA</li>
    </ol>
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
![fundamentals pic1](https://github.com/dhinesh00406/simplewebserver/assets/147149471/1eda9530-887a-4145-aeb0-13da781b0af5)
![fundamentals pic2](https://github.com/dhinesh00406/simplewebserver/assets/147149471/c165866e-29a3-4f4d-9637-0fa2c7c1e55b)

## RESULT:
The program for implementing simple webserver is executed successfully.
