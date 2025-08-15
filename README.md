Codebase Linker
An intelligent, client-side dependency visualizer for Android projects.

[Live Demo](https://aboayman-oss.github.io/codebase-linker/)

<img width="1902" height="896" alt="image" src="https://github.com/user-attachments/assets/179eb117-cdf5-4c41-99ee-221f074cd540" />

Why?
- Modern Android projects are complex. As a codebase grows, understanding the relationships between different files—activities, layouts, view models, and resources—becomes increasingly difficult. It's hard to answer critical questions like:

"If I change this file, what else might break?"

"What are the most architecturally significant parts of this feature?"

"How tightly coupled is this module?"

Codebase Linker was built to answer these questions. It's a static analysis tool that runs entirely in your browser, providing a deep, contextual understanding of your project without requiring any setup, server-side processing, or code uploads.

✨ Features
Advanced Dependency Analysis: 
- Goes beyond simple text search to find deep connections, including:

- Inheritance and interface implementations.

- Custom Views used in XML layouts.

- tools:context links between layouts and code.

- Preference key usage.

- Reflection and ProGuard rule dependencies.

- Importance Ranking: 
Uses a PageRank-style algorithm on a weighted graph to dynamically score and rank every file. This highlights the most critical parts of your architecture, separating core logic from peripheral assets.

- Semantic Connection Types: Understand why files are connected (e.g., Logic, Layout Inflate, Resource Usage) for a richer, more intuitive understanding of the dependency graph.

- Interactive Filtering: Instantly filter the dependency graph by importance tier (Must, Recommended, Optional) or by connection type to focus on what matters.

- 100% Client-Side & Offline: Your code is never uploaded. All parsing and analysis happens securely in your browser. After the initial page load, the tool works completely offline.

How It Works
- The tool performs a multi-pass analysis on your source files directly in the browser:

- File Parsing: It reads your Kotlin/Java, XML, Gradle, and ProGuard files.

- Graph Construction: It builds a comprehensive, weighted dependency graph. Each connection ("edge") is assigned a weight and a semantic type based on its architectural significance (e.g., an inheritance link is weighted more heavily than a resource link).

- Importance Calculation: A PageRank algorithm is run on the graph. This recursively calculates an "importance score" for each file based on the number and weight of its connections.

- Interactive Visualization: The results are presented in a clean, filterable UI, allowing you to explore your project's architecture from any entry point.

How to Use:
- Open the Live Demo.

- Click the Import button.

- Select "Import Folder" to choose your local Android project directory, or "Import ZIP" to use a zipped version of your project.

- Wait for the analysis to complete (this may take a moment for large projects).

- Click on any file in the left-hand tree to see its connections and explore your codebase!

🔒 Privacy
- Your privacy and security are paramount. This tool is built on the principle of "no data leaves your machine." All file processing and analysis happens locally in your browser via JavaScript. Your code is never sent to a server.

Technologies Used
HTML5 / CSS3 / JavaScript (ESM)

Web Workers: For performing the heavy analysis without freezing the UI.

JSZip: For handling .zip file imports.

Made with ❤️ for the Android community.
