# EX01 Developing a Simple Webserver

# Date:14.10.2024
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
views.py
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lenovo ThinkPad Gen 16 i5 Specifications</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        .container {
            width: 80%;
            margin: 0 auto;
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            overflow: hidden;
        }

        header {
            background-color: #003366;
            color: white;
            padding: 20px;
            text-align: center;
        }

        header h1 {
            margin: 0;
            font-size: 24px;
        }

        .specifications {
            padding: 20px;
        }

        .specifications h2 {
            color: #003366;
            text-align: center;
            margin-bottom: 20px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 0 auto;
            font-size: 16px;
        }

        table th, table td {
            text-align: left;
            padding: 10px;
            border: 1px solid #ddd;
        }

        table th {
            background-color: #003366;
            color: white;
        }

        table tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        table tr:hover {
            background-color: #e6f7ff;
        }

        footer {
            background-color: #003366;
            color: white;
            text-align: center;
            padding: 10px 0;
            margin-top: 20px;
        }

        footer p {
            margin: 0;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Lenovo ThinkPad Gen 16 i5 Specifications</h1>
        </header>
        <section class="specifications">
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
urls.py
```
from django.contrib import admin
from django.urls import path
from app1 import views

urlpatterns = [
    path('admin/', admin.site.urls),
]
```
# OUTPUT:
![Screenshot 2024-11-18 144759](https://github.com/user-attachments/assets/c4bfd82d-0671-4a11-9ed6-af8c161e2a3b)
![Screenshot 2024-11-18 144904](https://github.com/user-attachments/assets/66732cc7-a085-4725-9c7b-fa2d212c5d12)


# RESULT:
The program for implementing simple webserver is executed successfully.
