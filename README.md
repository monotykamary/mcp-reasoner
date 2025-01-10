# MCP Reasoner
A reasoning implementation for Claude Desktop that lets you use both Beam Search and Monte Carlo Tree Search (MCTS). tbh this started as a way to see if we could make Claude even better at complex problem-solving... turns out we definitely can.

### Current Version:
**v2.0.0**

#### What's New:

> Added 2 Experimental Reasoning Algorithms:
>
>     - `mcts-002-alpha`
>
>         - Uses the A* Search Method along with an early *alpha* implementation of a Policy Simulation Layer
>
>         - Also includes an early *alpha* implementation of Adaptive Exploration Simulator & Outcome Based Reasoning Simulator
>
>     *NOTE* the implementation of these alpha simulators is not complete and is subject to change
>
>     - `mcts-002alt-alpha`
>
>         - Uses the Bidirectional Search Method along with an early *alpha* implementation of a Policy Simulation Layer
>
>         - Also includes an early *alpha* implementation of Adaptive Exploration Simulator & Outcome Based Reasoning Simulator
>
>     *NOTE* the implementation of these alpha simulators is not complete and is subject to change


What happened to `mcts-001-alpha` and `mcts-001alt-alpha`?
> Quite simply: It was useless and near similar to the base `mcts` method. After initial testing the results yielded in basic thought processes was near similar showing that simply adding policy simulation may not have an effect.

So why add Polciy Simulation Layer now?
> Well i think its important to incorporate Policy AND Search in tandem as that is how most of the algorithms implement them.

#### Previous Versions:
**v1.1.0**

> Added model control over search parameters:
>
> beamWidth - lets Claude adjust how many paths to track (1-10)
>
> numSimulations - fine-tune MCTS simulation count (1-150)

## Features
- Two search strategies that you can switch between:
   - Beam search (good for straightforward stuff)
   - MCTS (when stuff gets complex) with alpha variations (see above)
- Tracks how good different reasoning paths are
- Maps out all the different ways Claude thinks through problems
- Analyzes how the reasoning process went
- Follows the MCP protocol (obviously)

## Installation
```
git clone https://github.com/frgmt0/mcp-reasoner.git 

OR clone the original:

git clone https://github.com/Jacck/mcp-reasoner.git

cd mcp-reasoner
npm install
npm run build
```

## Configuration
Add to Claude Desktop config:
```
{
  "mcpServers": {
    "mcp-reasoner": {
      "command": "node",
      "args": ["path/to/mcp-reasoner/dist/index.js"],
    }
  }
}
```

## Testing

[More Testing Coming Soon]

## Benchmarks

[Benchmarking will be added soon]

Key Benchmarks to test against:

- MATH500

- GPQA-Diamond

- GMSK8

- Maybe Polyglot &/or SWE-Bench

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
