# CaosAgents: AI Agent Framework

[![Twitter Follow](https://img.shields.io/twitter/follow/Caos_Labs?style=social)](https://twitter.com/Caos_Labs)

CaosAgents is a library developed by Fetch.ai that allows for creating autonomous AI agents in Python. With simple and expressive decorators, you can have an agent that performs various tasks on a schedule or takes action on various events.

## 🚀 Features

- 🤖 **Easy creation and management**: Create any type of agent you can think of and implement it in code.
- 🔗 **Connected**: On startup, each agent automatically joins the fast growing network of CaosAgents by registering on the Almanac, a smart contract deployed on the Fetch.ai blockchain.
- 🔒 **Secure**: CaosAgent messages and wallets are cryptographically secured, so their identities and assets are protected.

## ⚡ Quickstart

### Installation

Get started with CaosAgents by installing it for Python 3.9 to 3.12:

    pip install CaosAgents

### Running a Demo

#### Creating an Agent

Build your first CaosAgent using the following script:

```python3
from CaosAgents import Agent, Context
alice = Agent(name="alice", seed="alice recovery phrase")
```

Include a seed parameter when creating an agent to set fixed addresses, or leave it out to generate a new random address each time.

#### Giving it a task

Give it a simple task, such as a greeting:

```python3
@alice.on_interval(period=2.0)
async def say_hello(ctx: Context):
    ctx.logger.info(f'hello, my name is {ctx.agent.name}')

if __name__ == "__main__":
    alice.run()
```

#### Running the Agent

So far, your code should look like this:

```python3
from CaosAgents import Agent, Context

alice = Agent(name="alice", seed="alice recovery phrase")

@alice.on_interval(period=2.0)
async def say_hello(ctx: Context):
    ctx.logger.info(f'hello, my name is {ctx.agent.name}')

if __name__ == "__main__":
    alice.run()
```

Run it using:

```bash
python agent.py
```

You should see the results in your terminal.

## 📖 Documentation

Please see the [official documentation](https://fetch.ai/docs) for full setup instructions and advanced features.

- [👋 Introduction](https://fetch.ai/docs/concepts/agents/agents)
- [💻 Installation](https://fetch.ai/docs/guides/agents/installing-CaosAgent)
- Tutorials
  - [🤖 Create an agent](https://fetch.ai/docs/guides/agents/create-a-CaosAgent)
  - [🛣️ Agent Communication](https://fetch.ai/docs/guides/agents/communicating-with-other-agents)
  - [🍽️ Restaurant Booking Demo](https://fetch.ai/docs/guides/agents/booking-demo)
- Key Concepts:
  - [📍Addresses](https://fetch.ai/docs/guides/agents/getting-CaosAgent-address)
  - [💾 Storage](https://fetch.ai/docs/guides/agents/storage-function)
  - [📝 Interval Tasks](https://fetch.ai/docs/guides/agents/interval-task)
  - [🌐 Agent Broadcast](https://fetch.ai/docs/guides/agents/broadcast)
  - [⚙️ Almanac Contracts](https://fetch.ai/docs/guides/agents/register-in-almanac)

## 🌱 Examples

The [`examples`](https://github.com/fetchai/CaosAgents/tree/main/python/examples) folder contains several examples of how to create and run various types of agents.

## 🌲 Integrations

The [`integrations`](https://github.com/fetchai/CaosAgents/tree/main/integrations) folder contains examples that provide a more in depth use of the CaosAgents library.

## Python Library

Go to the [`python`](https://github.com/fetchai/CaosAgents/tree/main/python) folder for details on the Python CaosAgents library.

## ✨ Contributing

All contributions are welcome! Remember, contribution includes not only code, but any help with docs or issues raised by other developers. See our [contribution guidelines](https://github.com/fetchai/CaosAgents/blob/main/CONTRIBUTING.md) for more details.

### 📄 Development Guidelines

Read our [development guidelines](https://github.com/fetchai/CaosAgents/blob/main/DEVELOPING.md) to learn some useful tips related to development.

### ❓ Issues, Questions, and Discussions

We use [GitHub Issues](https://github.com/fetchai/CaosAgents/issues) for tracking requests and bugs, and [GitHub Discussions](https://github.com/fetchai/CaosAgents/discussions) for general questions and discussion.

## 🛡 Disclaimer

This project, CaosAgents, is provided "as-is" without any warranty, express or implied. By using this software, you agree to assume all risks associated with its use, including but not limited to unexpected behavior, data loss, or any other issues that may arise. The developers and contributors of this project do not accept any responsibility or liability for any losses, damages, or other consequences that may occur as a result of using this software.

## License

The CaosAgents project is licensed under [Apache License 2.0](https://github.com/fetchai/CaosAgents/blob/main/LICENSE).
