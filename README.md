# ♟️ Real-Time Multiplayer Chess — Phoenix LiveView

A two-player online chess game where both boards update live over a single shared link — no page reloads, no polling. Built in a 24-hour individual hackathon at the **Doofinder Code Challenge 2022**, where it won the **Knight Award (most original project)**.

> 🏆 **Knight Award — Most Original Project**, Doofinder Code Challenge (Oct 2022)

<!-- Replace with a short gameplay GIF: two browser windows, a move on one board appearing instantly on the other -->
![Gameplay demo](https://user-images.githubusercontent.com/482075/194532319-b5dc8969-2737-4546-9f39-d6dc2b3a92b7.png)

## What it does

- Real-time multiplayer chess for two players over the web.
- Create a game at a shareable URL — send the link, your opponent joins, you're playing.
- Moves render on both boards instantly via Phoenix LiveView (server-pushed, no client polling).
- Legal-move validation, turn handling, and win detection.
- Live game feedback in the UI.

## How it works

Game state lives server-side and is pushed to both connected clients over LiveView's websocket, so a move made by one player appears on the opponent's board with no refresh.

- The player who creates the game gets the **white** pieces.
- Joining a game is just opening the shared `/game/:game_name` URL in another browser.

## Tech

- **Elixir** (1.12+) / **Phoenix** / **Phoenix LiveView**
- Server-rendered, real-time UI — no separate JS frontend framework.

Hackathon constraint: **no dependencies beyond those in `mix.exs`** were allowed. That meant no off-the-shelf chess library — move generation and validation are implemented from scratch in Elixir.

## Running locally

```bash
# Requires Elixir 1.12+ (asdf recommended)
mix deps.get
mix phx.server
```

Open two browser windows at `http://localhost:4000`, create a game in one, share the URL to the other, and play.

---

<sub>Originally built from Doofinder's provided Phoenix chess template during the Oct 2022 code challenge.</sub>
