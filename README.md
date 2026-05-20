# Metode Rekayasa Perangkat Lunak KOMB - Ilmu Komputer UGM 2026

Kelompok 8:

- Rayhan Haldi Hermawan (24/545406/PA/23176)
- Pratama Nanindra Aji (24/533677/PA/22604)
- Muhammad Rayyan Buna Satria (24/543564/PA/23096)
- Kevin Febriano (24/541948/PA/23002)

# Agentic AI Framework Generator

## Description

This project is a tool/pipeline that automatically generates Agentic AI framework code from Knowledge Graphs (KGs) of Agentic AI patterns. The system reads KGs constructed using the [Agentic AI Ontology](https://w3id.org/agentic-ai/onto) and transforms them into executable code for target frameworks such as CrewAI and AutoGen.

### Project Overview

The generator bridges the gap between abstract agentic AI patterns defined in ontologies and concrete implementations in popular agentic AI frameworks. By parsing Knowledge Graphs that describe agentic AI patterns, the tool can automatically produce runnable code that implements these patterns in different target frameworks.

### Key Features

- **Ontology-based Generation**: Uses the standard Agentic AI Ontology (https://w3id.org/agentic-ai/onto) as the foundation
- **Multi-framework Support**: Generates code for multiple agentic AI frameworks:
  - CrewAI
  - AutoGen
- **Knowledge Graph Parsing**: Reads and interprets KGs in RDF/Turtle format (.ttl, .rdf)
- **Pattern Recognition**: Extracts agentic AI patterns including agents, tasks, tools, and workflows
- **Automated Code Generation**: Produces executable Python scripts for target frameworks

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/nauraranantya/agentic-generator.git
   cd agentic-generator
   ```
2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate       # macOS/Linux
venv\Scripts\activate          # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Usage

### Option 1: Generate Multi-Agent Code from Knowledge Graph

1. Place the Knowledge Graph (in .ttl or .rdf format) inside the data/ folder, or use the existing dummy data in `data/` or `kg_g3/`.
   Example: `data/dummy_kg.ttl`

2. Run the automated pipeline:

   ```bash
   python runner.py
   ```

   This will automatically:
   - Parse the knowledge graph ontology
   - Generate CrewAI framework code
   - Generate AutoGen framework code

3. Check the `output/` folder for generated scripts:
   - `crewai_generated.py`
   - `autogen_generated.py`

### Option 2: Test Workflow Simulation (Demo)

1. Place your gpt-4o-mini API key in a `.env` file in the root directory:

   ```
   OPENAI_API_KEY=your-api-key-here
   ```

2. Run the pre-configured workflow test:

   ```bash
   python test_email_workflow.py
   ```

   This demonstrates a complete email auto-responder workflow using CrewAI with:
   - Email classification
   - Automated response generation
   - Quality review process

   OR

   ```bash
   python test_cust_support_workflow.py
   ```

   This demonstrates a customer support ticket handling workflow using AutoGen with:
   - Ticket classification and prioritization
   - Multi-agent collaboration for resolution
   - Automated response generation

3. View the complete workflow execution and results in the console output.
