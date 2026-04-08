# Art of The Day

Art For Your Day randomly picks an artwork from the Metropolitan Museum of Art's collection ([API](https://metmuseum.github.io/) here) to display on the home page, refreshing with each visit. The search page allows users to find artworks by specific criteria.

The Met's collection is vast, which made working with its API an interesting challenge — raw queries rarely return the most relevant results. The core problem to solve was tuning the search experience: using user input intelligently to get relevant results, and filtering out objects with missing image data to keep the display clean.

The project also implements common security measures including rate limiting and input sanitisation, and maintains a server-side cache to avoid redundant API calls.

<b>[Live app](https://art-of-the-day.onrender.com/)</b>

## Reflection

This project gave me hands-on experience navigating the realities of third-party API integration.

It evolved from a simple get-and-display approach, to data pre-fetching due to the API rate limit. At the same time, I noticed that many results were missing image data. To tackle with it, I first added fallback images, but the missing data was too widespread for that to be a satisfying solution, so I filtered out those results instead. As I was learning more about networking and web security at the time, I added a cache for recent query results, along with input sanitisation and my own rate limiting to protect the server.

One problem persisted for long though - search results took too long to render, and easily hit the API limit, causing errors. My solution was to a) reduce the images per page from 8 to 6, b) handle API errors more granularly by waiting for seconds on a 403, and by using a fallback image on a 404, c) add an overall timer to return a "Request failed" error to the client when time is out.
