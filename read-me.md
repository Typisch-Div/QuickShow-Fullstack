# QuickShow

QuickShow is a movie ticket booking app. Browse movies and showtimes, choose seats, and keep track of bookings. There is also an admin area for managing shows and viewing bookings.

## What it uses

- React and Vite for the client
- Express and MongoDB for the server
- Clerk for sign-in
- Stripe for checkout
- TMDB for movie data

## Run it locally

You will need Node.js, a MongoDB connection, and credentials for Clerk, Stripe, and TMDB.

Open two terminals in the project folder.

### Server

```bash
cd server
npm install
```

Create `server/.env` and add the values your setup needs:

```env
MONGODB_URI=your_mongodb_connection_string
TMDB_API_KEY=your_tmdb_api_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
STRIPE_CURRENCY=usd
CLIENT_URL=http://localhost:5173
```

Start the API:

```bash
npm run dev
```

The server listens on port 3000.

### Client

In the other terminal:

```bash
cd client
npm install
```

Create `client/.env`:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BASE_URL=http://localhost:3000
VITE_TMDB_IMAGE_BASE_URL=https://image.tmdb.org/t/p/original
VITE_CURRENCY=$
```

Start the app:

```bash
npm run dev
```

Vite will print the local address to open in your browser.

## Deployment

The `client` and `server` folders include Vercel configuration files. To deploy, configure the required environment variables in your hosting provider and deploy each part with the appropriate settings. A Vercel config file by itself does not mean the app is currently online.
