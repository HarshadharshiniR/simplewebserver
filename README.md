# EX01 Developing a Simple Webserver
## Date:12/10/2024

## AIM: 
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html lang="en">
<head>
    <title>configuration of my laptop</title>
</head>
<body bgcolor="cylon">
    <h1 align ="center">configuration of my laptop(Harshadharshinni,24900177)</h1>
    <pre>
        <ul >
        <li><b>Device name</b>       DESKTOP-P1C9LOB</li>
        <li><b>processor </b >       AMD Athlon Silver 3050U with Radeon Graphics 2.30 GHz</li>
        <li><b>Installed RAM </b>    8.00 GB (5.92 GB usable)</li>
        <li><b>Device ID</b>         EF372F6D-2E48-4B5A-B99F-E9BB97A4BF54</li>
        <li><b>product ID </b>       00356-24587-25956-AAOEM</li>
        <li><b>System type</b>       64-bit operating system, x64-based processor</li>
        <li><b>Pen and Touch</b>     No pen or touch input is available for this display</li>
        <li><u><b>this is the end bro</b></u></li></ul>
    </ul>
    </pre>
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
![alt text](<Screenshot 2024-11-22 150134.png>)
![alt text](<Screenshot 2024-11-22 150134.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
