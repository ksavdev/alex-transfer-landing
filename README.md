# Alex-Transfer Landing (Production Build)

This repository contains the **production build** (final bundle) of the landing page for the Alex-Transfer transportation service.  
View the live site here: [https://ksavdev.github.io/alex-transfer-landing/](https://ksavdev.github.io/alex-transfer-landing/)

## About the Project

**Goal**: Provide users with an easy way to learn about the Alex-Transfer service and immediately calculate trip costs.

**Technologies (already minified/bundled)**:
- HTML5
- CSS (minified)
- JavaScript (ES6+, bundled and minified)
- [Swiper.js](https://swiperjs.com/) – for the slider
- Asynchronous requests to external APIs (Nominatim, OpenRouteService)

> **Source Code** (Webpack/Gulp, JS modules) is located in a private repository and is not included here.

## Features

1. **Responsive Slider**
   - Implemented with [Swiper.js](https://swiperjs.com/).
   - Allows users to browse through informational blocks (e.g., services, testimonials) by swiping or clicking arrows.

2. **Trip Cost Calculator**
   - The user enters a departure and an arrival address (defaulted to Belarus).
   - The `requestLatitude` module uses [Nominatim OpenStreetMap](https://nominatim.org/) to convert the addresses into coordinates (lat, lon).
   - The `getRouteDistance` module sends a request to [OpenRouteService](https://openrouteservice.org/) (using the `foot-walking` profile by default — can be changed to `driving-car` if needed) to obtain the distance in kilometers.
   - The trip cost is calculated by multiplying the distance by a specific rate (`distance * 2` in the code).
   - Uses `async/await` for step-by-step data fetching and error handling.

3. **Loading Animation**
   - While calculations are in progress, the result element (`resultSpan`) displays a “Please wait, calculating…” message, and then shows the final cost after receiving the data.

4. **Form Validation**
   - The calculation form (`calculation-form`) uses built-in HTML5 validation.
   - If fields are empty or invalid, the user sees helpful prompts.

## How It Works (User Perspective)

1. Open the landing page and enter the departure and arrival addresses in the respective fields.
2. Click the “Calculate” button.
3. After a few seconds (during which the system fetches coordinates and the route distance), the final trip cost is displayed.

## Contact

- **Author**: [Kostia Savchenko](https://github.com/ksavdev)
- **E-mail**: [k.savchenko.dev@gmail.com](mailto:k.savchenko.dev@gmail.com)

---

> **Note**: This repository is intended for demonstrating the completed website only. All original files, including build scripts (Webpack/Gulp) and JS modules, reside in a private repository. If you have any questions, feel free to reach out via email or open an issue!
