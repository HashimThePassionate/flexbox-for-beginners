## 🖼️🎡 Responsive Image Gallery

**[Image Carousel Live Preview](https://hashimthepassionate.github.io/image-carousel/)**

### Table of Contents 📚
- [🖼️🎡 Responsive Image Gallery](#️-responsive-image-gallery)
  - [Table of Contents 📚](#table-of-contents-)
- [1. Introduction 📸✨](#1-introduction-)
- [2. Responsive Image Gallery 🖼️🧩](#2-responsive-image-gallery-️)
  - [**HTML Structure** ](#html-structure-)
  - [**CSS Styling** ](#css-styling-)
  - [**Explanation** ](#explanation-)
- [3. Image Carousel 🎡📸](#3-image-carousel-)
  - [**HTML Structure** ](#html-structure--1)
  - [**CSS Styling** ](#css-styling--1)
  - [**JavaScript** ](#javascript-)
  - [**Explanation** ](#explanation--1)
- [4. Customization Tips 🧑‍🎨✨](#4-customization-tips-)

## 1. Introduction 📸✨
In this guide, we’ll create two types of image displays using **Flexbox** and **JavaScript**:
- A **Responsive Image Gallery** that adjusts images into rows and resizes them to fit the screen.
- An **Image Carousel** that lets users navigate through images using a slideshow effect.

Both examples are clean, stylish, and can be easily customized to fit any project. 🎨🖼️

## 2. Responsive Image Gallery 🖼️🧩

### **HTML Structure** <a name="gallery-html"></a>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Image Gallery</title>
    <link rel="stylesheet" href="gallery.css">
</head>
<body>
    <div class="gallery">
        <img src="https://via.placeholder.com/300" alt="Image 1">
        <img src="https://via.placeholder.com/300" alt="Image 2">
        <img src="https://via.placeholder.com/300" alt="Image 3">
        <img src="https://via.placeholder.com/300" alt="Image 4">
        <img src="https://via.placeholder.com/300" alt="Image 5">
        <img src="https://via.placeholder.com/300" alt="Image 6">
    </div>
</body>
</html>
```

### **CSS Styling** <a name="gallery-css"></a>

```css
body {
    background-color: #f5f5f5;
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

.gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    max-width: 900px;
    justify-content: center;
}

.gallery img {
    width: 200px;
    height: 150px;
    object-fit: cover;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
}

.gallery img:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}
```

### **Explanation** <a name="gallery-explanation"></a>
1. **Flexbox** is used to ensure images **wrap** onto new rows when there’s not enough space.
2. **Hover effects** make the gallery interactive, with smooth scaling and shadow effects.
3. **`object-fit: cover;`** maintains the aspect ratio, ensuring images fill their container neatly. 🧩📸

## 3. Image Carousel 🎡📸

### **HTML Structure** <a name="carousel-html"></a>

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Carousel</title>
    <link rel="stylesheet" href="carousel.css">
</head>
<body>
    <div class="carousel">
        <button class="carousel-btn prev">&#10094;</button>
        <div class="carousel-track">
            <img src="./images/mashroom.jpg" alt="Slide 1">
            <img src="./images/flower.jpg" alt="Slide 2">
            <img src="./images/mountain.jpg" alt="Slide 3">
            <img src="./images/sunset.jpg" alt="Slide 4">
        </div>
        <button class="carousel-btn next">&#10095;</button>
    </div>
    <script src="carousel.js"></script>
</body>
</html>
```

### **CSS Styling** <a name="carousel-css"></a>

```css
body {
    background-color: #f5f5f5;
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
}

.carousel {
    position: relative;
    width: 600px;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.carousel-track {
    display: flex;
    transition: transform 0.4s ease-in-out;
}

.carousel img {
    width: 600px;
    height: 400px;
    object-fit: cover;
}

.carousel-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    font-size: 2em;
    border-radius: 50%;
    transition: background-color 0.3s ease;
}

.carousel-btn:hover {
    background-color: rgba(0, 0, 0, 0.8);
}

.prev {
    left: 10px;
}

.next {
    right: 10px;
}
```

### **JavaScript** <a name="carousel-js"></a>

```js
let currentIndex = 0;
const track = document.querySelector('.carousel-track');
const slides = Array.from(track.children);
const nextButton = document.querySelector('.next');
const prevButton = document.querySelector('.prev');

function updateSlidePosition() {
    track.style.transform = `translateX(-${currentIndex * 600}px)`;
}

nextButton.addEventListener('click', () => {
    currentIndex = (currentIndex + 1) % slides.length;
    updateSlidePosition();
});

prevButton.addEventListener('click', () => {
    currentIndex = (currentIndex - 1 + slides.length) % slides.length;
    updateSlidePosition();
});
```

### **Explanation** <a name="carousel-explanation"></a>
1. **HTML**: The `.carousel` contains **navigation buttons** and a `.carousel-track` that holds the images.
2. **CSS**:
   - Uses **`overflow: hidden;`** to ensure only one image is visible at a time.
   - Buttons are styled and positioned for easy **navigation**.
3. **JavaScript**:
   - Handles the **slide navigation** by adjusting `translateX` on the `.carousel-track`.
   - Clicking the buttons shifts the track, displaying the **next** or **previous** image. 🎯🚀

## 4. Customization Tips 🧑‍🎨✨

- **Image Sizes**: Adjust the image width and height to fit different layouts.
- **Animations**: Experiment with different **transition effects** to enhance interactivity.
- **Add More Images**: Expand the gallery or carousel by adding more `<img>` elements.
- **Button Styling**: Change the **carousel buttons** to icons or custom graphics for a unique touch.