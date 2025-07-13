# Angular Animations

### Setup
Import **BrowserModule** and **BrowserAnimationsModule** in the `app.module.ts` file. 

**Note:** Do not import the two modules in other feature modules.

### Instructions For Creating Fade Animations

1. Create a utility file for the animations: `animation.ts`.
2. Create transitions for fadeIn effect
```js
const enterTransition = transition(':enter', [
  style({
    opacity: 0,
  }),
  animate('0.25s ease-in', style({ opacity: 1 })),
]);
```
3. Create transitions for fadeOut effect
```js
const exitTransition = transition(":exit", [
  style({
    opacity: 1,
  }),
  animate("0.25s ease-out", style({ opacity: 0 })),
]);
```

4. Create trigger for fadeIn effect
```js
export const fadeIn = trigger('fadeIn', [enterTransition]);
```

5. Create trigger for fadeOut effect
```js
export const fadeOut = trigger('fadeOut', [exitTransition]);
```
### Importing and Using Animations
1. Import the animations in the TS file (from the animations utility file)
```js
import { fadeIn, fadeOut } from '../../animations';
```
2. In the component decorator, add the animations to the animations array
```js
animations: [fadeIn, fadeOut]
```
3. In the HTML file, add the animations to the tags that have to be animated using the @ attribute
```html
<section @fadeOut @fadeIn></section>
```