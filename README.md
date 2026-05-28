# Ex.07 Design of Interactive Image Gallery
# Date:28/05/2026
# AIM:
To design a web application for an inteactive image gallery with minimum five images.

# DESIGN STEPS:
## Step 1:
Clone the github repository and create Django admin interface.

## Step 2:
Change settings.py file to allow request from all hosts.

## Step 3:
Use CSS for positioning and styling.

## Step 4:
Write JavaScript program for implementing interactivity.

## Step 5:
Validate the HTML and CSS code.

## Step 6:
Publish the website in the given URL.

# PROGRAM :
```
picture.html

{% load static %}
<html>
    <head>
        <title> Image Gallery </title>
        <style>
            .photo{
                display:flex;
                flex-direction:row;
                justify-content: space-evenly;
                justify-content:center;
                gap:50px;
                padding:10px;
            }
            .container{
                display:flex;
                flex-direction:column;
                gap:30px;
            }
            .photo img{
                display:flex;
                height:320px;
                width:auto;
                border: 2px solid black;
                border-radius: 15px;
                box-shadow: 0px 0px 13px black;
                cursor:pointer;
              
            }
            .photo img:hover{
                transform: scale(1.23);
                transition:transform 0.3s;
            }
            h1{
                text-align:center;
            }
            .gallery{
                display:none;
                position:fixed;
                z-index:100;
                top:0;
                left:0;
                width:100%;
                height:100%;
                overflow:scroll;
                background-color: rgba(0, 0, 0, 0.851);
            }
            .gallery img{
                position:relative;
                margin:auto;
                height:90%;
                width:auto;
            }
            .close{
                position:absolute;
                right:400px;
                top:24px;
                color:cornsilk;
                font-weight: bold;
                font-size:40px;
                transition: 0.3s;
                cursor:pointer;
            }
        </style>
    </head>
    <body>
        <h1>IMAGE GALLERY</h1>
        <div class="container">
        <div class="photo"> 
            <img src = " {% static 'gallery1.jpg' %} " onclick = "opengallery (this)">
            <img src = " {% static 'gallery2.jpg' %} " onclick = "opengallery (this)">
            <img src = " {% static 'gallery3.jpg' %} " onclick = "opengallery (this)">
        </div>
            <div class="photo">
            <img src = " {% static 'gallery4.jpg' %} " onclick = "opengallery (this)">
            <img src = " {% static 'gallery5.jpg' %} " onclick = "opengallery (this)">
        </div>
        </div>

        <div id="mygallery" class="gallery">
            <span class="close" onclick="closegallery( )">&times; </span>
            <img id="modalimg" src=" ">
        </div>
        <script>
            function opengallery (img) {
                const modal = document.getElementById("mygallery");
                const modalimg = document.getElementById("modalimg");
                modal.style.display = "flex";
                modalimg.src = img.src;
            }
            function closegallery( ){
                const modal = document.getElementById("mygallery").style.display="none";
            }
        </script>
    </body>
</html>
```
```
urls.py

from django.contrib import admin
from django.urls import path
from photosapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.photo),
]
```
```
views.py

from django.shortcuts import render
def photo(request):
    return render (request,'picture.html')
```
# OUTPUT:
<img width="1497" height="789" alt="image" src="https://github.com/user-attachments/assets/e8d3902b-b429-41bb-8c54-81d1dd1aa8c7" />

<img width="1493" height="755" alt="image" src="https://github.com/user-attachments/assets/65bea35f-36a4-40e3-9981-16f59123f14b" />

<img width="1498" height="755" alt="image" src="https://github.com/user-attachments/assets/5c70aed5-6939-4e3c-a5ee-82a560691c53" />

# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
