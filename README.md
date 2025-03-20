

# README.md
## Problem Statement

Analyzing and visualizing complex network data, such as entities, events, relationships, and identity resolutions, can be challenging due to the volume and interconnected nature of the data. Traditional methods often lack the ability to process natural language queries, provide interactive visualizations, or highlight critical conditions (e.g., high-severity events or low-confidence identity resolutions). Additionally, there is a need for a user-friendly web interface that allows users to explore network data through multiple views, such as full network trees, detailed drill-downs, and dynamic tables, while also supporting preventive maintenance scheduling for proactive analysis.

## Solution Proposed 

The Intelligence_Identity System is a Flask-based web application designed to address these challenges by providing a comprehensive platform for visualizing and analyzing network data stored in an ArangoDB database. The solution integrates LangChain and GROQ for natural language query processing, translating user queries into ArangoDB Query Language (AQL) for seamless data retrieval. It leverages NetworkX and Pyvis for interactive graph visualizations, offering multiple views like full network trees, drill-down analysis, and red flag detection for critical conditions. The application also supports preventive maintenance scheduling and dynamic table views, making it a versatile tool for exploring and managing network data.

## Implementation Approach

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/network-visualization.git
   cd network-visualization
   ```

2. **Set Up a Virtual Environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install Dependencies**:
   Create a `requirements.txt` file with the following content:
   ```
   flask
   arango
   pyvis
   networkx
   langchain-community
   langchain-groq
   groq
   textwrap
   ```
   Then run:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Environment Variables**:
   Create a `.env` file in the root directory and add your GROQ API key:
   ```
   GROQ_API_KEY=your_groq_api_key_here
   ```

5. **Configure ArangoDB**:
   Ensure ArangoDB is running and accessible. Update the connection details in `app.py` if necessary:
   ```python
   client = ArangoClient(hosts="http://localhost:8529")
   db = client.db("_system", username="root", password="")
   ```

## Data Integration

   1.Connect to ArangoDB to fetch data from collections (Entities, Events, Relationships, Identity-Resolution).
   2.Use LangChain and GROQ to translate natural language queries into AQL for querying the database.

## Core Functionality Development

   1.Implement Flask routes for different views:
      1./full_tree: Displays the entire network graph of entities, events, and relationships.
      2./drilldown: Provides a detailed view of nodes with a search bar for navigation.
      3./red_flags: Highlights critical conditions using customizable thresholds.
      4./maintenance: Processes natural language queries for maintenance scheduling visualizations.
      5./table: Dynamically displays database table data based on user selection.
   2.Use NetworkX to construct graphs and Pyvis to render interactive visualizations, saving them as HTML files in the static/ directory.

## User Interface

   1.Develop HTML templates (details.html, full_tree.html, drilldown.html, etc.) in the templates/ directory to provide a user-friendly web interface.
   2.Add features like search bars, toggle buttons for red flags, and form submissions for natural language queries.

## Running the Application

   1. **Start the Flask Application**:
      ```bash
      python app.py
      ```
   
   2. **Access the Web Interface**:
      Open your web browser and navigate to `http://127.0.0.1:5000/`.

## Testing and Deployment

   **Access the web interface at http://127.0.0.1:5000/.**
   **Push the code to a GitHub repository for version control and collaboration:**
   ```bash
   git add .
   git commit -m "Initial commit of Intelligence_Identity System"
   git push origin main
   ```


## Technical Architecture and Flow

The architecture of the Intelligence_Identity System is designed to separate frontend and backend concerns, ensuring a modular and scalable application. Below is the architecture diagram and a description of the flow:

![Architecture](https://github.com/user-attachments/assets/8a123cd6-34ef-4945-8a9a-2d02706ce8c6)



## Video Reference for Intelligence Identity:

The following video provides a demonstration of the Intelligence_Identity System, showcasing its key features such as interactive graph visualization, red flag detection, and natural language query processing:



https://github.com/user-attachments/assets/e5158ede-9919-49a0-80a9-915213eb6718






## Technology Used

| Sl. No. | Technology          | Description |
|---------|---------------------|-------------|
| 1       | **ArangoDB**        | A multi-model database used to store and query network data (entities, relationships, events). |
| 2       | **LangChain**       | A framework for translating natural language queries into AQL and processing results. |
| 3       | **GROQ**            | A language model API for generating visualization code and enhancing query processing. |
| 4       | **NetworkX**        | A Python library for creating and manipulating graph structures. |
| 5       | **Pyvis**           | A library for generating interactive network visualizations rendered in HTML. |
| 6       | **Flask**           | A lightweight web framework for building the application’s web interface and routes. |
| 7       | **GIt**             | Version control system for managing the project’s codebase. |
| 8       | **Python 3.8+**     | The programming language used for developing the application. |






## Features

| Sl. No. | Feature Name                            | Description |
|---------|-----------------------------------------|-------------|
| 1       | **Natural Language Query Processing**   | Translates natural language queries into AQL using LangChain and GROQ, executing them on ArangoDB. |
| 2       | **Interactive Graph Visualization**     | Displays network data (entities, events, relationships) as interactive graphs using Pyvis and NetworkX. |
| 3       | **Red Flag Detection**                  | Identifies critical conditions (e.g., high-severity events, low-confidence identity resolutions) with customizable thresholds. |
| 4       | **Drill-Down View**                     | Provides a detailed view of nodes and their attributes, with a search bar for navigation. |
| 5       | **Full Network Tree**                   | Visualizes the entire network of entities, events, and identity resolutions in a single graph. |
| 6       | **Preventive Maintenance Scheduling**   | Generates visualizations for maintenance schedules based on user queries. |
| 7       | **Dynamic Table View**                  | Displays database table data dynamically based on user selection. |



## Prerequisites

Before running the application, ensure you have the following installed:

- Python 3.8 or higher
- ArangoDB (running locally or accessible via a network)
- GROQ API key
- Git (for version control)

## Contributing

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments

- **ArangoDB** for its robust multi-model database capabilities.
- **LangChain** and **GROQ** for enabling natural language query processing.
- **NetworkX** for graph construction and analysis.
- **Pyvis** for interactive and visually appealing network visualizations.
- **Flask** for a simple and effective web framework.

## Contact

We welcome your feedback and are happy to assist with any questions or issues!  
