
# GAIA: Decentralized, Trustless, and Resilient AI

Welcome to the GAIA project!

GAIA is an open-source, decentralized platform for collaborative training and inference of AI models. Our mission is to democratize AI, ensuring open access to powerful tools while preserving privacy and security.

## Table of Contents
- [Overview](#overview)
- [MVP Components](#mvp-components)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

## Overview
GAIA aims to create a distributed network where users contribute their hardware (CPUs, GPUs, and storage) to train and run AI models. The project is designed with **privacy** and **decentralization** at its core, empowering contributors to control their resources and data.

Key features of GAIA include:
- **Zero Trust Architecture**: Nodes run in isolated environments (Docker, WASM) to ensure trustless execution.
- **Privacy-Preserving**: No private data is stored; only aggregated, anonymized statistics are retained.
- **Fair Reward System**: Contributors are rewarded based on their compute power, memory usage, uptime, and energy efficiency.
- **Decentralized Governance**: A DAO governs the decision-making process, with proposals for models, training goals, and rewards.

## MVP Components

### Phase 1: MVP Node Local

In this first phase of the GAIA project, we focus on the foundational components necessary for a local node to participate in the network. Below is an overview of the minimum viable components (MVP) for this initial phase.

| **Module**              | **Language** | **Brief Description**                                                              |
|-------------------------|--------------|------------------------------------------------------------------------------------|
| **node-core**            | Rust         | The main node service. It handles the controller, communications, and logging for the node. |
| **wasm-task-runner**     | Rust         | A lightweight engine that runs tasks for inference and training in WASM (WebAssembly) for efficiency and portability. |
| **benchmarking-agent**   | Rust         | A hardware performance measurement tool that tracks local CPU, RAM, VRAM, and estimated energy usage to assess node performance. |
| **cli-node-manager**     | Rust         | Command-line interface for registering the node, launching and monitoring its state, and executing tasks. |
| **zk-simulator (mock)**  | Rust         | A simulated component for testing zk-proof (Zero-Knowledge Proofs) in validation tasks without actual zk-proofs implementation. |
| **proto-comm**           | Rust         | Basic peer-to-peer communication framework (using Tokio, libp2p, or QUIC) for node communication within the decentralized network. |
| **task-queue-local**     | Rust         | A minimal task queue that manages task execution order and validates tasks prior to execution. It simulates task handling without full functionality. |

### Descriptions of MVP Components

1. **node-core**  
   This is the heart of the local node service. It manages all essential node operations, including coordinating communications with other nodes, logging, and overall control of the node's tasks. It's written in Rust for performance and reliability.

2. **wasm-task-runner**  
   The WASM task runner is designed to execute lightweight tasks related to inference and model training. By using WebAssembly (WASM), the tasks can be executed in a secure and efficient manner across multiple platforms without dependency on specific hardware architectures.

3. **benchmarking-agent**  
   This component measures the performance of the local hardware, including CPU, RAM, VRAM, and estimated energy consumption. It provides real-time feedback on the node's capabilities, ensuring that resource allocation is optimized based on actual hardware performance.

4. **cli-node-manager**  
   The CLI (Command Line Interface) is a utility for users to manage their local nodes. This component allows users to register their node, launch and monitor the node's state, and execute tasks. It ensures easy interaction with the system from the terminal or command prompt.

5. **zk-simulator (mock)**  
   While Zero-Knowledge Proofs (ZK-proofs) are part of the GAIA project's long-term goal, the ZK-simulator in this phase is a mock component. It allows for testing the general structure and functionality of ZK-proofs without actually implementing them, laying the groundwork for future ZK-based validation.

6. **proto-comm**  
   The P2P (Peer-to-Peer) communication module is built using Rust, leveraging Tokio and libp2p or QUIC protocols to enable nodes to communicate efficiently and securely in the decentralized network. This ensures a fast and reliable messaging system for GAIA nodes.

7. **task-queue-local**  
   A minimal implementation of a task queue for node management, which handles the execution order of tasks. It ensures that tasks are validated before execution, though it is currently a simplified version of what will eventually be a fully distributed task queue system.

## Architecture

GAIA's architecture is made up of several key components:

- **Node Service**: The software running on user machines that contributes resources to the network.
- **Smart Contracts**: The blockchain infrastructure governing the tokenomics, staking, and DAO governance.
- **Reward Model**: Logic for calculating node rewards based on different performance metrics (time, compute power, energy efficiency, etc.).
- **Benchmarking Service**: Automatically evaluates node performance, assigning them tasks accordingly.
- **Governance**: A decentralized autonomous organization (DAO) that governs the direction of the network and model selection.

For a more detailed breakdown of each component, see the respective directories:
- `/src/node`: Node service implementation.
- `/src/smart-contracts`: Blockchain and smart contract code.
- `/src/reward-model`: Logic for calculating node rewards.
- `/src/utils`: Utility functions used across components.

## Getting Started

Follow the instructions below to get started with GAIA on your local machine:

### Prerequisites
- [Rust](https://www.rust-lang.org/learn/get-started) installed (for building the node service).
- [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/install/) installed (for containerized setup).

### Local Setup
1. Clone this repository:

   ```bash
   git clone https://github.com/your-org/gaia-project.git
   cd gaia-project
   ```

2. Build and run the necessary containers:

   ```bash
   docker-compose up --build
   ```

3. For more detailed usage, refer to the documentation in `/docs`:
   - [Whitepaper](docs/whitepaper.md)
   - [Manifesto](docs/manifesto.md)

## Contributing

We welcome contributions! Here's how you can help:
- **Report issues**: Found a bug or something unclear? Let us know by opening an issue.
- **Submit pull requests**: If you have a fix or feature, fork this repo and submit a PR.

Please refer to the contributing guidelines in the `/docs` directory for more details.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
