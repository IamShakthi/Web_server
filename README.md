# Developing a Simple Webserver

# AIM:

To develop a simple webserver to display about top five programming language.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:

```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Welcome</h1>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address=('',8080)      
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.server_forever()
```
 
## OUTPUT:
### server side output
![server side output](./images/server%20output.png)
### client side output
![client side output](./images/clientoutput.png)
## RESULT:
The program is executed successfully.Thus the web server is developed to display about top five programming languages.
