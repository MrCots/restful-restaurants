# RESTful Restaurants

A full-stack restaurant list app with a React front-end and an Express back-end. Browse restaurants, star your favorites, and add comments to the ones you've starred. I built the four starred-restaurant REST endpoints on top of the provided starter code.

## Tech Stack

- **Front-end:** React (Create React App)
- **Back-end:** Node.js, Express, nodemon
- **Data:** in-memory arrays that simulate a database (no persistence between server restarts)

## API Endpoints

All starred-restaurant routes are mounted at `/restaurants/starred`.

| Feature | Method | Route | Description |
|---------|--------|-------|-------------|
| 6 | GET | `/` | List all starred restaurants (joined with restaurant names) |
| 7 | GET | `/:id` | Get one starred restaurant by its starred id |
| 8 | POST | `/` | Star a restaurant (body: `{ id }` of the restaurant) |
| 9 | DELETE | `/:id` | Remove a restaurant from the starred list |
| 10 | PUT | `/:id` | Update the comment (body: `{ newComment }`) |

Each route returns `404` when the requested record does not exist.

## Getting Started

Start the back-end first, because it uses port 3000.

```bash
# Back-end
cd backend
npm install
npm start

# Front-end (in a second terminal)
cd frontend
npm install
npm start
```

When prompted that port 3000 is in use, answer `Y` so the front-end runs on another port (usually 3001).

## Project Structure

```
backend/
  routes/
    restaurants.js          # all restaurants (provided)
    starredRestaurants.js   # starred restaurants (my endpoints, Features 7-10)
frontend/
  src/
    api/                    # fetch calls to the back-end
    components/             # React UI
```

## What I Learned

- How route parameters (`req.params`) differ from the request body (`req.body`)
- Matching HTTP methods to intent: GET reads, POST creates, PUT updates, DELETE removes
- Joining data from two collections by a shared key (`restaurantId`)
- Mutating an array item in place with `.find()` versus rebuilding an array with `.filter()`
- Choosing status codes the front-end expects, and returning response shapes that match the other routes
