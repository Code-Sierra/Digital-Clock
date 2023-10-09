# JavaScript Clock Documentation

## Overview

This JavaScript script creates a digital clock that displays the current time, updating every second. The clock uses the 12-hour format with an AM/PM indicator.

## Code Description

1. **HTML Elements**: Get the clock components (hours, minutes, seconds, and AM/PM) from the HTML document.

```javascript
const hoursEl = document.getElementById("hours");
const minutesEl = document.getElementById("minutes");
const secondsEl = document.getElementById("seconds");
const ampmEl = document.getElementById("ampm");
```

2. **Update Clock Function**: A function that updates the clock components every second.

```javascript
function updateClock(){
    // Get current time
    let h = new Date().getHours();
    let m = new Date().getMinutes();
    let s = new Date().getSeconds();
    let ampm = "AM";
    
    // Convert to 12-hour format
    if(h > 12){
        h = h - 12;
        ampm = "PM";
    }

    // Add leading zero if less than 10
    h = h < 10 ? "0" + h : h;
    m = m < 10 ? "0" + m : m;
    s = s < 10 ? "0" + s : s;

    // Update HTML elements
    hoursEl.innerText = h;
    minutesEl.innerText = m;
    secondsEl.innerText = s;
    ampmEl.innerText = ampm; 
    
    // Call the function every second
    setTimeout(() => {
        updateClock();
    }, 1000)
}
```

3. **Initial Call**: Call the `updateClock` function to start the clock.

```javascript
updateClock();
```

## Example Usage

1. **Include HTML Elements**: In your HTML file, include the following elements where you want the clock to appear.

```html
<span id="hours"></span>:<span id="minutes"></span>:<span id="seconds"></span> <span id="ampm"></span>
```

2. **Include JavaScript**: Include the script either within a `<script>` tag or link to an external JavaScript file.

```html
<script>
    // Include the JavaScript code here
</script>
```

3. **Load the Page**: Load the HTML page in a web browser. The digital clock will be displayed and updated every second.

## Applications

This script can be used in a variety of applications, including:

1. **Websites and Web Apps**: Display the current time on websites and web applications.
2. **Dashboards**: Include a clock in user dashboards or control panels.
3. **Clock Widgets**: Use as a standalone clock widget on websites.
4. **Event Timers**: Use as a base for event countdown timers or stopwatches.
