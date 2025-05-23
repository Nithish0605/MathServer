# Ex.05 Design a Website for Server Side Processing
## Date:2/05/2025

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
math.html
```
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Lamp Filament Power Calculator</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body {
    background-color: #1500fff2;
}
.edge {
    width: 100%;
    padding-top: 180px;
    text-align: center;
}
.box {
    display: inline-block;
    border: thick dashed #05d093;
    width: 500px;
    min-height: 300px;
    font-size: 20px;
    background-color: rgb(124, 160, 214);
}
.formelt {
    color: rgb(255, 0, 191);
    text-align: center;
    margin-top: 8px;
    margin-bottom: 6px;
}
h1 {
    color: black;
    padding-top: 20px;
}
</style>
</head>
<body>
<div class="edge">
    <div class="box">
        <h1>Lamp Filament Power Calculator</h1>
        <h3>NITHISH S (212224240105)</h3>
        <form method="POST">
            
            <div class="formelt">
                Intensity (I): <input type="text" name="intensity" value="{{I}}"></input> A<br/>
            </div>
            <div class="formelt">
                Resistance (R): <input type="text" name="resistance" value="{{R}}"></input> Ω<br/>
            </div>
            <div class="formelt">
                <input type="submit" value="Calculate"></input><br/>
            </div>
            <div class="formelt">
                Power (P): <input type="text" name="power" value="{{P}}"> W<br/>
            </div>
        </form>
        <div class="formelt">
            <b>Formula:</b> P = I<sup>2</sup>R
        </div>
    </div>
</div>
</body>
</html>
```
view.py 
```
from django.shortcuts import render
def surfacearea(request):
    context = {}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        print('request.POST:', request.POST)
        r = request.POST.get('radius', '0') 
        h = request.POST.get('height', '0') 
        print('radius =', r)
        print('height =', h)
        area = 2 * 3.14 * int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area =', area)
    
    return render(request, 'mathapp/math.html',context)
```
urls.py
```
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfacearea/',views.surfacearea,name="surfacearea"),
    path('',views.surfacearea,name="surfcaearea")
]
```

## SERVER SIDE PROCESSING:
![alt text](SERVER.png)

## HOMEPAGE:
![Screenshot 2025-05-19 102052](https://github.com/user-attachments/assets/e0a33c00-082e-4cb3-bc77-3b25d2b5c26d)

## RESULT:
The program for performing server side processing is completed successfully.
