# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
from django.shortcuts import render,HttpResponse

# Create your views here.
def trial(request):
    return HttpResponse('<p>Hello</p>')
def htm(request):
    return render(request,"home.html")

content = '''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Lenovo ThinkPad Gen 16 i5 Specifications</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <header>
            <h1>Lenovo ThinkPad Gen 16 i5 Specifications</h1>
        </header>
        
        <section class="specs">
            <h2>Key Specifications</h2>
            <table>
                <tr>
                    <th>Processor</th>
                    <td>Intel Core i5 (12th Gen)</td>
                </tr>
                <tr>
                    <th>Display</th>
                    <td>16-inch WQXGA (2560 x 1600)</td>
                </tr>
                <tr>
                    <th>Memory</th>
                    <td>8GB or 16GB DDR4 RAM</td>
                </tr>
                <tr>
                    <th>Storage</th>
                    <td>512GB SSD (configurable)</td>
                </tr>
                <tr>
                    <th>Graphics</th>
                    <td>Intel Iris Xe Graphics</td>
                </tr>
                <tr>
                    <th>Operating System</th>
                    <td>Windows 11 Pro</td>
                </tr>
                <tr>
                    <th>Battery</th>
                    <td>57Wh, up to 10 hours</td>
                </tr>
                <tr>
                    <th>Weight</th>
                    <td>1.50 kg (3.31 lbs)</td>
                </tr>
                <tr>
                    <th>Ports</th>
                    <td>2 x USB 3.2, 2 x USB-C, HDMI, Ethernet</td>
                </tr>
                <tr>
                    <th>Camera</th>
                    <td>1080p HD webcam</td>
                </tr>
            </table>
        </section>
        
        <footer>
            <p>&copy; 2024 Lenovo. All rights reserved.</p>
        </footer>
    </div>
    <style>
    /* Reset default margin and padding */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Body styling */
body {
    font-family: 'Arial', sans-serif;
    background-color: #f4f4f9;
    color: #333;
}

/* Container to hold all content */
.container {
    width: 80%;
    margin: 0 auto;
}

/* Header styling */
header {
    background-color: #003366;
    color: white;
    padding: 20px 0;
    text-align: center;
}

header h1 {
    font-size: 2.5rem;
    margin: 0;
}

/* Specs section styling */
.specs {
    background-color: white;
    padding: 20px;
    margin-top: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.specs h2 {
    font-size: 2rem;
    margin-bottom: 20px;
    color: #003366;
}

/* Table styling */
table {
    width: 100%;
    border-collapse: collapse;
}

th, td {
    padding: 12px;
    text-align: left;
    border-bottom: 1px solid #ddd;
}

th {
    background-color: #003366;
    color: white;
}

td {
    background-color: #f9f9f9;
}

tr:hover {
    background-color: #f1f1f1;
}

/* Footer styling */
footer {
    background-color: #003366;
    color: white;
    text-align: center;
    padding: 10px;
    margin-top: 40px;
    border-radius: 5px;
}
</style>
</body>
</html>




'''

from http.server import HTTPServer,BaseHTTPRequestHandler
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()
# OUTPUT:
![image](https://github.com/user-attachments/assets/f996ef93-6cbc-4f96-b9ef-d2afc0ec6052)

# RESULT:
![image](https://github.com/user-attachments/assets/c2739788-5cce-4ac8-baa3-4576b79af289)

The program for implementing simple webserver is executed successfully.
