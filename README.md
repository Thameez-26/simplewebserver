# EX01 Developing a Simple Webserver
## Date:05.03.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
````
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="cyan">
<table border="4" cellspacing="1" cellpadling="1" height="300" width="700" bgcolor="white">
<caption>TOP SOFTWARE COMPANIES WITH REVENUE</caption>
		<tr>
			<th>COMPANY</th>
			<th>REVENUE</th>
			<th>PERCENTAGE</th>
		</tr>
		<tr>
			<td>Google</td>
			<td>4541397</td>
			<td>1</td>
		</tr>

		<tr>
			<td>Meta</td>
			<td>3216464</td>
			<td>2</td>
		</tr>

		<tr>
			<td>SAMSUNG</td>
			<td>1649465</td>
			<td>3</td>
		</tr>
                 <tr>
			<td>TCS</td>
			<td>51918518</td>
			<td>4</td>
		</tr>

                 <tr>
			<td>Infosys</td>
			<td>5191587</td>
			<td>5</td>
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
````

## OUTPUT:
![image](https://github.com/user-attachments/assets/5368b050-f2e8-4aac-9355-256f55715fd5)
![image](https://github.com/user-attachments/assets/f28b5ecb-707f-4603-b853-0ed1d51bf3da)



## RESULT:
The program for implementing simple webserver is executed successfully.
