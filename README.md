AgentGuard 🛡️
A governance layer for coding agents to evaluate when to continue, replan, or stop.

AgentGuard explores how autonomous coding agents can be monitored for unproductive execution and how governance decisions can balance task completion with computational cost.

Project status: Early development. The initial focus is on Shadow Mode, where governance recommendations are recorded without interrupting agent execution.

Problem Statement
Autonomous coding agents may repeatedly attempt fixes without making meaningful progress. Continuing can waste computational resources, while stopping too early can prevent a task from being completed successfully.

AgentGuard investigates a central question:

When should a coding agent continue working, reconsider its approach, or stop execution?

Proposed Approach
AgentGuard introduces a monitoring and governance layer around a coding agent. It evaluates execution history and recommends one of three actions:

CONTINUE — Allow the agent to continue its current approach.
REPLAN — Recommend reconsidering the current approach.
STOP — Recommend ending execution when further attempts appear unproductive.
These recommendations are intended to be evaluated against actual task outcomes.

Shadow Mode
The initial approach uses Shadow Mode, in which the governance layer records its recommendations while the coding agent continues executing normally.

This makes it possible to compare recommendations with eventual outcomes without allowing the monitoring layer to interrupt task execution.

Evaluation
AgentGuard focuses on evaluating the quality and consequences of governance decisions, including:

False stops: Cases where execution is stopped in principle, but the agent would have succeeded by continuing.
Unproductive continuation: Cases where additional execution consumes resources without achieving task success.
Replanning effectiveness: Whether changing approach can improve task outcomes.
Compute efficiency: The relationship between computational cost and successful task completion.
Evaluation results and performance claims will be reported only after experiments have been conducted.

Architecture
The project is organized into modules with distinct responsibilities:

Module	Responsibility
llm/	Language-model integration
agent/	Coding-agent execution
tools/	Tools available to the agent
trajectory/	Execution history and recorded steps
governor/	Governance decision logic
eval/	Evaluation and experiment analysis
tasks/	Coding tasks used in experiments
tests/	Automated tests
notes/	Development notes
The architecture will evolve as the implementation develops.

Technology Stack
Python — Core implementation
Ollama — Local language-model integration
pytest — Automated testing
Git and GitHub — Version control
Development Status
AgentGuard is under active development. Its monitoring mechanisms, governance logic, and evaluation methodology are being developed and tested.

No performance improvements or compute savings are claimed until they are supported by experimental evidence.

License
No license has been selected yet. Until a license is added, reuse and redistribution permissions have not been explicitly granted.

