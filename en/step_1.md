Each of the starter animations in the `animation.css` file has an `animation` property group that states how the animation should run:

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 1
line_highlights: 2
---
.spinme {
  animation: rotate-center linear 8s 2; /* Time taken for animation and number of repetitions */
  display: inline-block;
}
 
--- /code ---

The `animation` line in the `spinme` example is broken up into:
+ `rotate-center` - the name of the animation
+ `linear` - the animation timing (linear is the same playing speed throughout, other examples are `ease`, `ease-in` and `ease-out`)
+ `8s` - the duration of the animation in seconds
+ `2` - the number of times the animation should run (can be `infinite` for continuous running

Changing any of these values will alter the animation. Another way to customise the animaton is by adjusting the `@keyframes` rule.  `@keyframes` control how the element should look when a percentage of the running animation is complete.  

In the `rotate-center` animation used by `spinme` the animation rotates the object from 0 degrees at the start of the animation (0%), round to 360 degrees at the end of the animation (100%). 

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 6
---
@keyframes rotate-center {
/* The spin me animation code */
  0% { /* Rotate from 0 to 360 degrees */
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}
 
--- /code ---

Animations can have specific styles applied at other percentage points during the animation run. For example the `scale` animation has specified points at 0%, 20%, 40%, 60% and 80%:

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 6
---

@keyframes scale {
  /* The scale animation code */
  0% {
    transform: scale(1, 1);
  }
  20% {
    transform: scale(1.1, 1.1);
  }
  40% {
    transform: scale(1.2, 1.2);
  }
  60% {
    transform: scale(1.1, 1.1);
  }
  80% {
    transform: scale(1, 1);
  }
}
 
--- /code ---

The animation can have more than one style changed at each point. For example the `bounce` animation changes the size and Y-coordinate to create a realistic bounce effect:

--- code ---
---
language: html
filename: animation.css
line_numbers: true
line_number_start: 22
---

@keyframes bounce {
  /* The bounce animation code */
  0% {
    transform: scale(1, 1) translateY(0); /* Starting position and actual size */
  }
  10% {
    transform: scale(1.1, 0.9) translateY(0); /* Grow width and shrink height for pre bounce squash effect */
  }
  30% {
    transform: scale(1, 1) translateY(-6rem); /* Return to actual size and move emoji up 100px from current position */
  }
  50% {
    transform: scale(1, 1) translateY(0); /* Move emoji back to starting position */
  }
}
 
--- /code ---

You can change colour, position, size, rotation and many more properties by changing the `@keyframes` code.
