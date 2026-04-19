---
up: "[[Generative AI MOC]]"
date: 2025-07-29
created: 2025-07-29 13:07
title: Model Context Protocol (MCP)
aliases:
  - MCP
  - Model Context Protocol
tags:
  - ai/mcp
  - ai/standards
  - ai/agents
  - type/protocol
link:
---
The field of [[artificial intelligence|Artificial Intelligence (AI)]] is rapidly evolving, with [[large language models|Large Language Models (LLMs)]] and AI agents becoming increasingly sophisticated. However, their potential is often limited by their access to external information and tools. The **Model Context Protocol (MCP)**, an open-source, open standard framework introduced by Anthropic in November 2024, addresses this limitation by providing a **standardized way for AI systems to interact with the "outside world", particularly large language models (LLMs) and AI agents, integrate and share data with external tools, systems, and data sources.** This article explores the key aspects of MCP and its potential to revolutionize AI applications.

### The Need for a Universal Connector
Imagine a world where AI models can seamlessly access and utilize a vast array of external tools, systems, and data sources. Before MCP, connecting AI models to these resources often required complex, custom integrations. MCP aims to simplify this process, acting as a **universal connector, similar to a USB-C port for hardware, but for AI applications.** It provides a consistent and standardized way for AI to interact with the world beyond its initial training data.

### Key Features and Benefits of MCP
MCP offers several key features and benefits that enhance the capabilities and interoperability of AI systems.  Here's a breakdown of key aspects of MCP:
* **Enables Context Awareness:** LLMs are powerful but often limited to the data they were trained on. MCP allows AI agents to access real-time, external information, making them more contextually aware and capable of performing tasks that require up-to-date or specific external data.
* **Client-Server Architecture:**  MCP utilizes a client-server architecture to facilitate communication between AI applications and external tools:
    * **MCP Host:** This is the AI application that the user interacts with (e.g., an AI chatbot, an IDE with AI features, or a custom AI agent).
    * **MCP Client:** Resides within the Host application and manages the connection to specific MCP servers. It handles communication, protocol negotiation, and relays requests and responses.
    * **MCP Server:** These are external programs that expose specific capabilities (tools, resources, and prompts) to the AI model via the client. A server acts as a bridge or adapter for a particular external service (e.g., a GitHub MCP server to interact with GitHub, a file MCP server to access local files, or a database MCP server).
* **Key Capabilities Exposed by Servers:** MCP utilizes a client-server architecture to facilitate communication between AI applications and external tools:
    * **Tools (Model-controlled):** These are functions or actions that the AI model can call to perform specific operations (e.g., a tool to send an email, a tool to fetch weather data, or a tool to run a calculation).
    * **Resources (Application-controlled):** These are data sources that the AI can access to retrieve information without performing a side effect (e.g., fetching the content of a document, a user's calendar data, or historical logs).
    * **Prompts (User-controlled):** These are reusable templates or workflows that can be triggered by user actions, guiding the AI in how to interact with tools or resources.
* **Standardization Benefits:** MCP offers several advantages due to its standardized approach:
    * **Reduced Integration Complexity:** Developers no longer need to build custom integrations for every new data source or tool.
    * **Increased Interoperability:** Different AI applications can easily connect to a wide range of MCP-compatible servers, fostering a more robust ecosystem.
    * **Enhanced AI Capabilities:** AI agents can move beyond simple text prediction to perform complex, multi-step tasks that leverage external information and actions.
* **Open Standard:** MCP is open-source, encouraging widespread adoption and collaboration across the AI industry. Major AI providers like [[openai|OpenAI]] and [[google deepmind|Google DeepMind]] have reportedly adopted or plan to support MCP.

### The Future of Agentic AI
In essence, MCP provides the missing layer that allows AI models to become truly "agentic" – intelligent programs that can autonomously pursue goals and take action by connecting to and utilizing the vast array of external tools and data sources available in the digital world.

### Further Exploration
For a deeper understanding of MCP and its implications, consider watching John Savill's video, which discusses MCP and Agent to Agent (A2A) for business leaders. The video helps to understand how MCP acts like a USB C for AI application and how A2A helps in complex Agent to Agent communication to enable multi-agent solutions. These two open standards are complimentary to one another that will help the future apps with Agentic capabilities.

<iframe width="560" height="315" src="https://www.youtube.com/embed/s8xJTAu5icM?si=kr-pVFb8nnbPlzCP" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
By providing a standardized and open framework for AI interaction, MCP is poised to play a crucial role in the future of AI, enabling more powerful, versatile, and interconnected AI applications.
