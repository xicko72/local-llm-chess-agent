# Local LLM chess agent

A chess-playing agent that asks a local Llama model to choose from legal moves. `python-chess` checks its answer; if the model returns no legal move or Ollama is unavailable, a material-and-tactics heuristic chooses instead. The notebook compares the hybrid agent with a random baseline, alternating White and Black, and can render a game as a GIF.

## Run

1. Install Python dependencies: `pip install -r requirements.txt`.
2. Install [Ollama](https://ollama.com/) and run `ollama pull llama3.2:3b`, then start its local service.
3. Open `chess_agent.ipynb` with Jupyter and run the cells in order.

The notebook defaults to 50 games and `USE_OLLAMA = True`. LLM inference can make this slow. For a quick check, set `N_GAMES = 2`; set `USE_OLLAMA = False` to exercise the heuristic without Ollama. The demo creates `chess_demo_frames/` and `chess_agent_demo.gif` locally.

The evaluation counts wins, draws and losses from the test agent’s perspective. The notebook outputs are cleared so displayed results come from your own run. This is a small experiment, not a competitive chess engine.
