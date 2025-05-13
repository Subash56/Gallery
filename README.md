# Ex.08 Design of Interactive Image Gallery
# Date:
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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Image Gallery</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #f06, #4a90e2);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
        }

        h1 {
            font-size: 3em;
            color: white;
            font-weight: bold;
            margin-bottom: 20px;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            0% {
                opacity: 0;
                transform: translateY(-20px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 15px;
            width: 80%;
            max-width: 1000px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            border-radius: 10px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover {
            transform: scale(1.05);
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease, filter 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
            filter: brightness(0.8);
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .overlay {
            opacity: 1;
        }

        .full-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .full-screen img {
            max-width: 90%;
            max-height: 90%;
            border-radius: 10px;
        }

        .full-screen.active {
            opacity: 1;
            visibility: visible;
        }

        .close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2em;
            color: white;
            cursor: pointer;
            background: none;
            border: none;
        }
    </style>
</head>
<body>
    <h1>Image Gallery</h1>
    <h1>CAR</h1>
    <div class="gallery" id="gallery">
       
    </div>

    <div class="full-screen" id="fullScreen">
        <button class="close-btn" id="closeBtn">&times;</button>
        <img id="fullScreenImg" src="" alt="Full View">
    </div>

    <script>
        const gallery = document.getElementById('gallery');
        const fullScreen = document.getElementById('fullScreen');
        const fullScreenImg = document.getElementById('fullScreenImg');
        const closeBtn = document.getElementById('closeBtn');

    
        const images = [
            
            
            
            'l.jpg',
            'maserati.jpg',
            'RR.webp',
            'bmw.jpg',
            'rr pink.jpg',
            'merc.jpg',
            'porsche.jpg',
            'electric-luxury-cars-doha.jpg'
            
        ];

        
        images.forEach((src, index) => {
            const item = document.createElement('div');
            item.classList.add('gallery-item');

            const img = document.createElement('img');
            img.src = src;
            img.alt = `Image ${index + 1}`;

            const overlay = document.createElement('div');
            overlay.classList.add('overlay');
            overlay.innerText = `Image ${index + 1}`;

            item.appendChild(img);
            item.appendChild(overlay);
            gallery.appendChild(item);

            item.addEventListener('click', () => {
                fullScreenImg.src = src;
                fullScreen.classList.add('active');
            });
        });

        
        closeBtn.addEventListener('click', () => {
            fullScreen.classList.remove('active');
        });

        
        fullScreen.addEventListener('click', (e) => {
            if (e.target === fullScreen || e.target === closeBtn) {
                fullScreen.classList.remove('active');
            }
        });
    </script>
</body>
</html>
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/61c6ba5a-9b4b-4fd5-b466-a2175c4648e6)
![image](https://github.com/user-attachments/assets/7f874afa-ea18-4bb4-a7eb-2529da4ecb00)
![image](https://github.com/user-attachments/assets/e43851f8-0750-444c-9628-d824a8d82a65)
![image](https://github.com/user-attachments/assets/743428f5-9b2f-4423-ab25-c3d9a7ebe08f)
![image](https://github.com/user-attachments/assets/6ce8c5e4-01da-4f20-bd65-a13e79387cbb)
![image](https://github.com/user-attachments/assets/622f58e3-23c0-4767-ae11-3e0ad1662109)




# RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
