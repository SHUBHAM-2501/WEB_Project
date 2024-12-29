# Wanderlust

Wanderlust is a travel-related web application built using Node.js, Express, and MongoDB. It allows users to manage listings and reviews for various travel destinations.

## Project Structure

```
- app.js            : Main entry point of the application.
- cloudConfig.js    : Configures Cloudinary for image storage.
- controllers/      : Contains logic for handling requests and responses.
  - listings.js     : Handles CRUD operations for listings.
  - reviews.js      : Handles CRUD operations for reviews.
  - users.js        : Handles user authentication and registration.
- init/             : Scripts for initializing the database with sample data.
  - data.js         : Sample data for listings.
  - index.js        : Script to initialize the database with sample data.
- middleware.js     : Custom middleware for authentication, authorization, and validation.
- models/           : Defines Mongoose schemas and models.
  - listing.js      : Schema for listings.
  - reviews.js      : Schema for reviews.
  - user.js         : Schema for users.
- public/           : Contains static assets.
  - css/            : Stylesheets.
  - js/             : Client-side JavaScript files.
- routes/           : Defines application routes.
  - listing.js      : Routes for listing operations.
  - review.js       : Routes for review operations.
  - user.js         : Routes for user operations.
- schema.js         : Defines Joi schemas for request validation.
- utils/            : Utility functions and custom error classes.
  - ExpressError.js : Custom error class for handling errors.
  - wrapAsync.js    : Utility for wrapping async route handlers.
- views/            : EJS templates for rendering HTML pages.
  - layouts/        : Layout templates.
  - includes/       : Partial templates like navbar and footer.
  - listings/       : Templates for listing pages.
  - users/          : Templates for user pages.
```

## Key Features

### 1. User Authentication
- Users can sign up, log in, and log out.
- Authentication is handled using Passport.js with the `passport-local` strategy.

### 2. Listings Management
- Users can create, read, update, and delete listings.
- Listings include details like title, description, image, price, location, and country.
- Images are uploaded to Cloudinary.

### 3. Reviews Management
- Users can add and delete reviews for listings.
- Reviews include a rating and a comment.

### 4. Geocoding
- Listings include geographical coordinates obtained using the Mapbox Geocoding API.

### 5. Error Handling
- Custom error handling middleware to catch and display errors.

## Getting Started

### Prerequisites
- Node.js installed on your machine
- MongoDB Atlas account
- Cloudinary account
- Mapbox account

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd wanderlust
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the root directory with the following variables:
   ```env
   NODE_ENV=development
   ATLAS_URL=<your-mongodb-atlas-url>
   SECRET=<your-secret-key>
   CLOUD_NAME=<your-cloudinary-cloud-name>
   CLOUD_API_KEY=<your-cloudinary-api-key>
   CLOUD_API_SECRET=<your-cloudinary-api-secret>
   MAP_TOKEN=<your-mapbox-token>
   ```

4. Initialize the database with sample data:
   ```bash
   node init/index.js
   ```

5. Start the server:
   ```bash
   node app.js
   ```

6. Access the application at:
   ```
   http://localhost:8080
   ```
