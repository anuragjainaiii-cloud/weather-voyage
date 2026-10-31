# Weather Voyage

Working React + Vite weather and travel planning web app.

## Run locally

1. Install Node.js 20+.
2. Run `npm install`.
3. Run `npm run dev` and open the displayed local URL.
4. Search a city (at least 3 characters), **select a suggestion**, then click **What's the Weather**.

The weather and city search work without any API keys. Events require the server-side Ticketmaster key and Vercel functions (local Vite alone does not host `/api/events`). To test events locally, install the Vercel CLI and run `vercel dev` after linking a Vercel project and configuring its environment variables.

## Deploy

1. Push this folder to GitHub and import the repository in Vercel.
2. Framework preset: Vite; build command: `npm run build`; output: `dist`.
3. Register at https://developer.ticketmaster.com/ and create a free Discovery API key.
4. Add `TICKETMASTER_API_KEY` in Vercel project environment variables, then redeploy.
5. Confirm events work for a supported city. Empty event results are expected in some markets.

## API sources and constraints

- City autocomplete: https://geocoding-api.open-meteo.com/v1/search
- Current/hourly/16-day forecasts: https://api.open-meteo.com/v1/forecast
- Events: https://developer.ticketmaster.com/products-and-docs/apis/discovery-api/v2/
- Booking: https://www.booking.com/ destination search link. **Not an affiliate link.** An approved affiliate ID and applicable partner terms are needed before affiliate tracking can be added. No booking API integration is needed for an outbound link.
- Open-Meteo free hosted API is for non-commercial use subject to limits and attribution; commercial monetization may require a paid license or a different provider. Ticketmaster free API requires a key and has rate limits and limited market coverage.
- Month, quarter, 6-month and annual predictions are intentionally not fabricated. The Month+ tab explains the limitation. Historical climate normals are a future enhancement.
- No automatic city selection, no simulated weather or events, no hardcoded event fixtures.

## Validation checklist

- Search `Del`, select Delhi, and compare temperature/time against the Open-Meteo forecast endpoint.
- Search `Lon` and select the intended London from the list (multiple Londons may exist).
- Search an invalid city and confirm no-match state.
- Select a city and check current conditions, 24 upcoming hours, time-of-day, 7-day and 16-day forecasts.
- Switch Celsius/Fahrenheit and verify conversion.
- Click Book my travel and confirm an external Booking.com destination search opens.
- Configure Ticketmaster key and confirm event date filtering and links; test an unsupported city and partner outage.
- Check responsive layout on mobile.

## Future work

Historical climate normals, approved affiliate deep links, licensed landmark images, maps/navigation, analytics and automated browser tests. No claim of universal event coverage or year-long predictive accuracy is made.
