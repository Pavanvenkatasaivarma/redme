

# README.md

## Architecture 

![Architecture](https://github.com/user-attachments/assets/1b9a7f30-8fd3-4280-82c9-a4d319c492a8)


## Project Overview

This project is a Flask-based web application designed to visualize and analyze network data stored in an ArangoDB database. It integrates LangChain and GROQ for natural language query processing, translating queries into ArangoDB Query Language (AQL), and uses NetworkX and Pyvis for interactive graph visualizations. The application supports multiple views, including a full network tree, drill-down analysis, red flag detection, and preventive maintenance scheduling, making it a versatile tool for exploring entity relationships, events, and identity resolutions.

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

## Running the Application

1. **Start the Flask Application**:
   ```bash
   python app.py
   ```

2. **Access the Web Interface**:
   Open your web browser and navigate to `http://127.0.0.1:5000/`.

## Usage

### Home Page
- Navigate to `/` to access the main interface (`details.html`).

### Full Network Tree
- Go to `/full_tree` to view the complete network of entities, events, and identity resolutions.

### Drill-Down Analysis
- Visit `/drilldown` for a detailed view of nodes and their attributes, with a search bar for easy navigation.

### Red Flag Detection
- Access `/red_flags` to see a graph highlighting critical conditions (e.g., high-severity events).

### Preventive Maintenance Scheduling
- Navigate to `/maintenance`:
  - Submit a natural language query (e.g., "Visualize maintenance schedule for entities") via POST request.
  - View the resulting graph at `static/visualize.html`.

### Dynamic Table View
- Go to `/table`:
  - Use GET (`?table=entities`) or POST (`table=entities`) to display data from a specific table.

### Example Interactions
- **Full Tree**: `http://127.0.0.1:5000/full_tree`
- **Drill-Down**: `http://127.0.0.1:5000/drilldown`
- **Red Flags**: `http://127.0.0.1:5000/red_flags`
- **Maintenance Query**: Submit "Show network of events" via `/maintenance` form.
- **Table View**: `http://127.0.0.1:5000/table?table=relationships`

## Code Structure

- **app.py**: The main Flask application file containing routes, query processing, and visualization logic.
- **templates/**: Directory for HTML templates (`details.html`, `full_tree.html`, `drilldown.html`, `red_flags.html`, `maintenance.html`, `table.html`, etc.).
- **static/**: Directory for storing static files like `full.html`, `drill.html`, `red.html`, and `visualize.html`.

## Technology Stack

| Sl. No. | Technology          | Description |
|---------|---------------------|-------------|
| 1       | **ArangoDB**        | A multi-model database used to store and query network data (entities, relationships, events). |
| 2       | **LangChain**       | A framework for translating natural language queries into AQL and processing results. |
| 3       | **GROQ**            | A language model API for generating visualization code and enhancing query processing. |
| 4       | **NetworkX**        | A Python library for creating and manipulating graph structures. |
| 5       | **Pyvis**           | A library for generating interactive network visualizations rendered in HTML. |
| 6       | **Flask**           | A lightweight web framework for building the application’s web interface and routes. |

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
