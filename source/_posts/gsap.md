---
title: GSAP
date: 2023-11-17 15:23:31
background: bg-[#8dcf06]
tags:
  - Animation
  - Library
categories:
  - Animation
intro: |
  A quick reference cheatsheet for GSAP, a flexible and Animation Library
plugins:
    - copyCode
---
## Code to Getting Started {.cols-1}
```html 
<!DOCTYPE html>
<html lang="en">
<head>
    <title>GSAP: Getting Started</title>
</head>
<body>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js" integrity="sha512-Ic9xkERjyZ1xgJ5svx3y0u3xrvfT/uPkV99LBwe68xjy/mGtO+4eURHZBW2xW4SZbFrF1Tf090XqB+EVgXnVjw==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <script src="script.js"></script>
</body>
</html>
``` 
## Getting Started
### All {.row-span-2}
```js  {.wrap}
gsap.to("<Target_Element>",{
    duration: <NumberInSecond>
    delay: <NumberInSecond>
    repeat: <NumberInSecond> //-1 = infinite repeat
    yoyo: <TrueOrFalse>
    scale: <Number>
    rotate: <Number>
  })
```
### To
```js
gsap.to("<Target_Element>",{
  // Code
})
```
### From
```js
gsap.from("<Target_Element>",{
  // Code
})
```
### Duration
```js
gsap.to("<Target_Element>",{
  duration: <NumberInSecond>
})
```
### Delay
```js
gsap.to("<Target_Element>",{
  delay: <NumberInSecond>
})
```
### Repeat
```js {.wrap}
gsap.to("<Target_Element>",{
  repeat: <NumberInSecond> //-1 = infinite repeat
})
```
### Yoyo
```js {.wrap}
gsap.to("<Target_Element>",{
  yoyo: <TrueOrFalse>
})
```
### Scale
```js {.wrap}
gsap.to("<Target_Element>",{
  scale: <Number>
})
```
### Rotate
```js {.wrap}
gsap.to("<Target_Element>",{
  rotate: <Number>
})
```

### Stagger
```js
gsap.to("<Target_Element>",{
  stagger: <NumberInSecond>
})
```

## ScrollTigger
### ScrollTigger
```js
gsap.from("<Target_Element>",{
  scrollTigger: {
    trigger: "<Target_Element>",
    scroller: "body",
    markers: true, // Optional 
    start: " top/bottom <Number>%", 
    end: " top/bottom <Number>%", 
    scrub: true / 1 To 5
  }
})
```

## locomotive {.cols-1}

### locomotive + ScrollTrigger 
```js
gsap.registerPlugin(ScrollTrigger);

// Using Locomotive Scroll from Locomotive https://github.com/locomotivemtl/locomotive-scroll

const locoScroll = new LocomotiveScroll({
  el: document.querySelector("#main"),
  smooth: true
});
// each time Locomotive Scroll updates, tell ScrollTrigger to update too (sync positioning)
locoScroll.on("scroll", ScrollTrigger.update);

// tell ScrollTrigger to use these proxy methods for the "#main" element since Locomotive Scroll is hijacking things
ScrollTrigger.scrollerProxy("#main", {
  scrollTop(value) {
    return arguments.length ? locoScroll.scrollTo(value, 0, 0) : locoScroll.scroll.instance.scroll.y;
  }, // we don't have to define a scrollLeft because we're only scrolling vertically.
  getBoundingClientRect() {
    return {top: 0, left: 0, width: window.innerWidth, height: window.innerHeight};
  },
  // LocomotiveScroll handles things completely differently on mobile devices - it doesn't even transform the container at all! So to get the correct behavior and avoid jitters, we should pin things with position: fixed on mobile. We sense it by checking to see if there's a transform applied to the container (the LocomotiveScroll-controlled element).
  pinType: document.querySelector("#main").style.transform ? "transform" : "fixed"
});

// each time the window updates, we should refresh ScrollTrigger and then update LocomotiveScroll. 
ScrollTrigger.addEventListener("refresh", () => locoScroll.update());

// after everything is set up, refresh() ScrollTrigger and update LocomotiveScroll because padding may have been added for pinning, etc.
ScrollTrigger.refresh();

gsap.from("<Target_Element>",{
  duration: <NumberInSecond>
  delay: <NumberInSecond>
  repeat: <NumberInSecond> //-1 = infinite repeat
  yoyo: <TrueOrFalse>
  scale: <Number>
  rotate: <Number>
  scrollTigger: {
    trigger: "<Target_Element>",
    scroller: "#main",
    markers: true, // Optional 
    start: " top/bottom <Number>%", 
    end: " top/bottom <Number>%", 
    scrub: true / 1 To 5
  }
})

```

Reference
- [GSAP] (https://www.youtube.com/watch?v=8_JcQq_mlOg) _Sheryians Coding School_