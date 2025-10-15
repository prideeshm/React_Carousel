# Ex05 Image Carousel
## Date:15.10.2025
## Name:Prideesh M

## AIM
To create a Image Carousel using React 

## ALGORITHM
### STEP 1 Initial Setup:
Input: A list of images to display in the carousel.

Output: A component displaying the images with navigation controls (e.g., next/previous buttons).

### Step 2 State Management:
Use a state variable (currentIndex) to track the index of the current image displayed.

The carousel starts with the first image, so initialize currentIndex to 0.

### Step 3 Navigation Controls:
Next Image: When the "Next" button is clicked, increment currentIndex.

If currentIndex is at the end of the image list (last image), loop back to the first image using modulo:
currentIndex = (currentIndex + 1) % images.length;

Previous Image: When the "Previous" button is clicked, decrement currentIndex.

If currentIndex is at the beginning (first image), loop back to the last image:
currentIndex = (currentIndex - 1 + images.length) % images.length;

### Step 4 Displaying the Image:
The currentIndex determines which image is displayed.

Using the currentIndex, display the corresponding image from the images list.

### Step 5 Auto-Rotation:
Set an interval to automatically change the image after a set amount of time (e.g., 3 seconds).

Use setInterval to call the nextImage() function at regular intervals.

Clean up the interval when the component unmounts using clearInterval to prevent memory leaks.

## PROGRAM
# App.jsx
```
import React, { useState } from 'react';
import './App.css';
import car1 from './assets/car.jpg';
import car2 from './assets/cr.jpg';

const images = [car1, car2];

function App() {
  const [index, setIndex] = useState(0);

  const showPrevious = () => {
    setIndex((prevIndex) =>
      prevIndex === 0 ? images.length - 1 : prevIndex - 1
    );
  };

  const showNext = () => {
    setIndex((prevIndex) =>
      prevIndex === images.length - 1 ? 0 : prevIndex + 1
    );
  };

  return (
    <div className="app">
      <h1 className="title">Cars Carousel</h1>
      <div className="carousel">
        <img
          src={images[index]}
          alt={`Car ${index + 1}`}  
          className="carousel-image"
        />
      </div>
      <div className="buttons">
        <button onClick={showPrevious}>Previous</button>
        <button onClick={showNext}>Next</button>
      </div>
      <footer className="footer">  M PRIDEESH 212223040154</footer>
    </div>
  );
}

export default App;

```
# App.css
```

.app {
  text-align: center;
  margin-top: 40px;
  background-color: #f0f4f8;  /* light background color */
  width: 800px;               /* set fixed width */
  height: 800px;              /* set fixed height */
  margin-left: auto;          /* center horizontally */
  margin-right: auto;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 0 15px rgba(0,0,0,0.2);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.title {
  font-size: 2rem;
  margin-bottom: 20px;
}

.carousel {
  width: 450px;
  height: auto;
  margin: 0 auto; /* centers the carousel horizontally */
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px #aaa;
}

.carousel-image {
  width: 100%;
  height: auto;
  display: block;
  margin: 0 auto; /* centers the image if needed */
}

.buttons {
  margin-top: 20px;
}

button {
  margin: 0 10px;
  padding: 10px 20px;
  font-size: 1rem;
  cursor: pointer;
}

/* New footer style */
.footer {
  margin-top: 30px;
  font-size: 1rem;
  color: #555;
  font-style: italic;
}
```
## OUTPUT

<img width="1919" height="1079" alt="Screenshot 2025-10-15 083844" src="https://github.com/user-attachments/assets/90de2ade-b5f1-4f26-a67f-e952b1597319" />

<img width="1915" height="1077" alt="Screenshot 2025-10-15 083851" src="https://github.com/user-attachments/assets/c78d2363-b949-4049-8bb6-f67c1e55763e" />


## RESULT
The program for creating Image Carousel using React is executed successfully.
