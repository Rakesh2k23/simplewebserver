# EX01 Developing a Simple Webserver
## Date:5/10/2023

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
```

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
        <li>Microsoft</li>
        <li>Oracle</li>
        <li>IBM</li>
        <li>Accenture</li>
        <li>SAP</li>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()


```






## OUTPUT:
![Screenshot 2023-11-01 000243](https://github.com/Rakesh2k23/simplewebserver/assets/141472158/8c7e5d38-dc9d-4e85-9784-42e26831beef)

![image](https://github.com/Rakesh2k23/simplewebserver/assets/141472158/a43278d1-7ab2-428b-81eb-3d7179ce418a)



## RESULT:
The program for implementing simple webserver is executed successfully.
