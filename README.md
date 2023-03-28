# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

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
Developed by:Preethi.A.A
Reference number:212222110035

from http.server import HTTPServer,BaseHTTPRequestHandler

content="""
<!DOCTYPE html>
<html>
    <head>
        <title> Saveetha Engineering college</title>
    </head>
    <body text="000000" bgcolor="F5BDFFS">  
            <h1 align="center"> Saveetha Engineering college</h1>
            <h2 align="right"> Autonomous</h2>
                <ul type="square">
                    <li> CSE(cyber security)</li>
                    <li> CSE(Iot)</li>
                    <li> AIDS</li>
                    <li> AIML</li>
                    <a href="http://www.saveetha.ac.in">visit our website</a>
                    
                </ul>

            </body>
    </head>
</html> 
"""

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
       print("Get request received...")
       self.send_response(200)
       self.send_header('content-type','text/html; charset=utf-8')
       self.end_headers()
       self.wfile.write(content.encode())

print("This is my webserver")
server_address=('',8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```
## OUTPUT:

![Screenshot 2023-03-28 222757](https://user-images.githubusercontent.com/120115840/228318369-9aa0a697-276e-46fb-8ccd-9fb5a1444626.png)

## RESULT:
The program is executed succesfully.
