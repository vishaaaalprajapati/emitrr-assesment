<h1 align="left">🐱 EMITRR-Exploding Kittens 🐱</h1>
<p align="left">A Web-Based Card Game</p>


## Live Link
[live demo](https://exploding-kittens.netlify.app/) to experience the game

## Instructions for Running the Game Locally

1. **Clone the Repository**
   - Open your terminal and navigate to the directory where you want to clone the repository.
   - Run the following command to clone the repository:
     ```bash
     git clone https://github.com/sachindolase/EMITRR-Exploding-Kittens.git
     ```

2. **Set Up Server**
   - Navigate to the `EMITRR-Exploding-Kittens` directory:
     
   - Start the backend:
     1. **Setting up your environment:**
        ```bash
        cd backend
        touch .env
        echo "PORT=(Specify the port)" >> .env
        echo "REDIS_URL=(Your Redis URI)" >> .env
        ```
     2. **To start in development mode:**
        ```bash
        npm install
        npm run start:dev
        ```
        <p align="center">OR</p>
     3. **To build the backend:**
        ```bash
        npm run build
        npm start
        ```

3. **Start the frontend**
   - Navigate back to the root directory:
     ```bash
     cd ..
     cd frontend
     touch .env
     echo "VITE_API_URL=http://localhost:(PORT)" >> .env
     npm install
     ```
   - To run in development mode:
     ```bash
     npm run dev
     ```
     <p align="center">OR</p>
   - To build the app:
     ```bash
     npm run build
     npm run preview
     ```
4. **Access the Game**
   - Open your web browser and go to [http://localhost:(PORT)](http://localhost:5173) to access the game.

## Game Instructions

The game deck consists of 4 different types of cards:

- Cat card 🐱
- Defuse card 🚫
- Shuffle card 🔀
- Exploding kitten card 💣

When the game starts, there will be a deck of 5 cards ordered randomly. Each time a user clicks on the deck, a card is revealed and removed from the deck. A player wins the game once all 5 cards are drawn, and there are no cards left in the deck.

## Rules

- If the drawn card is a cat card, it is removed from the deck.
- If the card is an exploding kitten (bomb), the player loses the game.
- A defusing card can be used to defuse one bomb from subsequent cards drawn.
- If the card is a shuffle card, the game restarts, and the deck is refilled with 5 cards.

## Assumptions

- The game currently lacks user authentication.
- On startup, the game assigns a random username. If not changed/confirmed, scores won't be saved.
- If you choose a username that doesn't exist, a new user will be created.
- The game polls the database every 8 seconds for real-time updates in the leaderboard table.
