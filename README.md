# Ex.05 Design a Website for Server Side Processing
## Date:15/12/2024

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
```
 power.html
<html>
<head>
<meta charset='utf-8'>
<meta http-equiv="X-UA-Compatible" content='IE=edge'>
<title>POWER</title>
<meta name='viewport' content='width=device-width,initial-scale=1'>
<style type="text/css">
<body> {
background-color: blue;
}
.edge {
width: 1440px;
margin-left: auto;
margin-right: auto;
padding-top: 250px;
padding-left: 300px;
}
.box {
display: block;
border: thick dashed lime;
width: 500px;
min-height: 300px;
font-size: 20px;
background-color: blue;
}
.formelt {
color: orange;
text-align: center;
margin-top: 7px;
margin-bottom: 6px;
}
h1 {
color: rgb(255, 0, 179);
text-align: center;
padding-top: 20px;
}
</style>
</head>
</body>
<div class="edge">
<div class="box">
<h1>POWER</h1>
<form id="powerForm">
<div class="formelt">
INTENSITY: <input type="number" id="intensity" name="INTENSITY" required>(in W/m²)<br/>
</div>
<div class="formelt">
RESISTANCE: <input type="number" id="resistance" name="RESISTANCE" required>(in ohms)<br/>
</div>
<div class="formelt">
<input type="button" value="Calculate" onclick="calculatePower()"><br/>
</div>
<div class="formelt">
POWER: <input type="text" id="power" name="POWER" readonly>(in WATTS)<br/>
</div>
</form>
</div>
</div>
</body>
</html>

urls.py
from django.contrib import admin
from django.urls import path
from powerapp import views
urlpatterns=[
    path('admin/',admin.site.urls),
    path('POWER/',views.power, name="POWER"),
    path('',views.power,name="POWERROOT")
]
views.py
from django.shortcuts import render
def power(request):
    context=()
    context['POWER'] = "0"
    context['I'] = "0"
    context['R'] = "e"
    if request.method == 'POST':
        print("POST method is used")
        I=request.POST.get('instensity', '0')
        R=request.POST.get('resistance', 'e')
        print('request', request)
        print('INTENSITY=', I)
        print('RESISTANCE=',R)
        POWER= int(I)**2*int(R)
        context['[POWER]'] = POWER
        context['I']=I
        context['R']=R
        print('POWER', POWER)
    return render (request, 'powerapp/power.html',context)
```


## SERVER SIDE PROCESSING:
![Screenshot 2024-12-13 222510](https://github.com/user-attachments/assets/b37e906e-c4de-4fd6-a83c-3e2004373101)



## HOMEPAGE:
![Screenshot 2024-12-15 205256](https://github.com/user-attachments/assets/961ebe70-28ce-41e9-8cc9-a7349e4120cb)

## RESULT:
The program for performing server side processing is completed successfully.
