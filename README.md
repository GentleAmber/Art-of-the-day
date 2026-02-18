# Art of The Day

<b>[Live app](https://art-of-the-day.onrender.com/)</b>

This is a small entertaining project in which I practiced integrating public API with my own application and parsing request queries. A lot of effort was devoted to tuning up the API, such as filtering out artworks without image data. The Metropolitan Museum's public API is used here: [The Metropolitan Museum of Art Collection API](https://metmuseum.github.io/)

This project implements basic security measures, including rate limiting and input processing, and a cache map which stores queried results to improve performance.


To run the project locally, download the repo, run `npm i` in the terminal under the root. After all packages are installed, run `node index.js`, and enter `localhost:3000` in your browser.
