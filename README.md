# EX01 Developing a Simple Webserver
## Date:

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
'''
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<html>
<head>
    <title>Top 5 software companies</title>
</head>
<body>
    <table border="2" cellspacing="10" cellpadding="6">
        <caption>Top 5 Revenue Generating Software Companies</caption>
        <tr>
            <th>s.no</th>
            <th>companies</th>
            <th>revenue</th>
        </tr>
        <tr>
            <th>1</th>
            <th>Microsoft</th>
            <th>65 billion</th>
        </tr>
        <tr>
            <th>2</th>
            <th>Oracle</th>
            <th>29.5 billion</th>
        </tr>
        <tr>
            <th>3</th>
            <th>IBM</th>
            <th>29.1 billion</th>
        </tr>
        <tr>
            <th>4</th>
            <th>SAP</th>
            <th>6.4 billion</th>
        </tr>
        <tr>
            <th>5</th>
            <th>Symantec</th>
            <th>5.6 billion</th>
        </tr>
    </table>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
'''








## OUTPUT:
![WEB PIC1](https://github.com/dhinesh00406/simplewebserver/assets/147149471/860164cb-109b-467b-9086-5d2108e49585)

![WEBPIC2](https://github.com/dhinesh00406/simplewebserver/assets/147149471/886248fe-14af-4e3c-bc04-bb9f64313b63)



## RESULT:

The program for implementing simple webserver is executed successfully.
