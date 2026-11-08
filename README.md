# claude-diagrammer-skill

A Claude Code skill for turning structured diagram specifications into clean, blueprint-style SVG technical diagrams.

## Overview

This skill is designed for precise technical visuals that can be embedded in documentation, project READMEs, presentations, and technical communication. It uses a small JSON specification as the input to a local renderer, keeping the diagram definition separate from its visual output.

## Supported Diagram Scenarios

Use the skill for diagrams such as:

- Request and response flows.
- Software and cloud system architectures.
- Data pipelines and processing stages.
- Neural network and transformer blocks.
- State machines and lifecycle diagrams.
- Node-and-edge relationships.
- Component interactions and dependency maps.

## How It Works

The workflow has four main stages:

1. Translate the user's description into a structured JSON diagram specification.
2. Save the specification in a project file.
3. Render the specification into an SVG using the local command-line tool.
4. Inspect the SVG and provide the generated file as the final diagram.

## Installation

Install the renderer with pipx:

```bash
pipx install diagrammer
```

Install the skill in the Claude Code skills directory:

```bash
git clone https://github.com/Brajesh31/claude-diagrammer-skill.git ~/.claude/skills/diagrammer
```

## Usage

Describe the diagram and its intended audience. Include the main nodes, relationships, direction of flow, labels, and any visual constraints.

A typical command-line workflow is:

```bash
diagrammer path/to/spec.json > path/to/diagram.svg
```

The JSON schema should follow the renderer's accepted specification. Do not assume unsupported properties or invent configuration fields.

## Good Diagram Design

- Keep the number of nodes appropriate to the diagram's purpose.
- Use clear labels and consistent naming.
- Make direction and relationship types unambiguous.
- Group related components logically.
- Avoid crossing edges where a simpler layout is possible.
- Keep text readable at the final display size.
- Prefer one diagram per concern instead of combining unrelated systems.

## Validation Checklist

- Confirm that every referenced node exists.
- Check that edge endpoints point to valid nodes.
- Verify labels, grouping, and direction.
- Render the SVG and inspect it before sharing.
- Confirm that the SVG opens in a browser or documentation renderer.
- Ensure the diagram communicates the intended flow without requiring hidden context.

## Repository Contents

- `SKILL.md`: Main skill instructions and rendering workflow.
- `README.md`: Installation, usage, and diagram design guidance.

## Output

The expected output is an SVG file. Keep the JSON specification alongside project documentation when the diagram needs to be regenerated or maintained.
