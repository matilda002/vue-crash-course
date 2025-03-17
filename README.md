# A counter with Vue3 props and Sass styling<br> 

I made this project to learn more about how Vue3 props worked and then ended up learning Sass as well. This may be an overworked counter, but it's been very fun to make! I did try to make it more web-accessible with example aria-hidden for the popup-image (it doesn't give any critical information), and colour contrast-ratio with AAA standards ᕙ(`▽´)ᕗ

How it works is the Parent (App.vue) holds the state of the counter and stores/updates to the local storage. Whenever you refresh the page or reload the project, the counter should keep its latest count. The sound each button makes is also stored here. In the Child (Btn.vue) is where the logic for emit and the popup picture. Props are defined in the Child to fill in the button's data, and to hold an action prop. This action prop is used as a parameter in the counter state function (updateCount in App.vue). It's just checking if the count is adding or subtracting to the counter. All data is pre-defined in a JS database located in the Parent's script.

The styling is made with just Sass/SCSS to make use of the amazing nesting features. I added a self-hosting woff2 font to match the Super Mario theme!

![Super Mario counter preview. Adding and subtracting to the counter.](src\assets\counter-preview.gif)

<br>

## Project Setup

### Installing dependices
```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Compile Sass to CSS

```sh
sass --watch src/scss:dist/css
```