# Generative AI in Geotechnical Engineering

## 🎯 Purpose
This repository demonstrates how to leverage Large Language Models (LLMs) and AI-powered coding assistants to process, analyze, and visualize large geotechnical datasets. It serves as a teaching tool for geotechnical engineers and data scientists to learn practical applications of generative AI in their field.

## 📊 Dataset
The repository includes an example GeoJSON file from Geosetta containing **85,994 geotechnical data points** across the United States. This real-world dataset provides an excellent foundation for demonstrating various AI-assisted data processing tasks.

## 🚀 Example Tasks for AI Assistants

### Basic Data Analysis
1. **Count Total Points**
   - Ask: "Count the total number of points in the GeoJSON file"
   - Expected: 85,994 points

2. **Regional Distribution Analysis**
   - Ask: "Count points in Eastern US (longitude > -95) vs Western US"
   - Result: Eastern US: 69,055 points | Western US: 16,939 points

### Data Visualization
3. **Interactive Plotly Map**
   - Ask: "Create an interactive Plotly scatter map showing all geotechnical points with zoom capabilities"
   - AI generates complete Python code for interactive visualization

4. **Density Heatmap**
   - Ask: "Generate a heatmap showing the density of geotechnical investigations by state"
   - AI creates choropleth maps with state boundaries

### Advanced AI Applications

5. **SVG Network Diagram Generation**
   - Ask: "Generate an SVG diagram showing the data processing pipeline for geotechnical site investigation data"
   - AI creates visual workflows without traditional drawing tools

6. **Mermaid Flowcharts**
   - Ask: "Create a Mermaid diagram showing the decision tree for soil classification based on coordinates"
   - Example output:
   ```mermaid
   graph TD
     A[Load GeoJSON Data] --> B{Check Longitude}
     B -->|< -100| C[Western Region]
     B -->|-100 to -85| D[Central Region]
     B -->|> -85| E[Eastern Region]
     C --> F[Seismic Zone Analysis]
     D --> G[Tornado Alley Considerations]
     E --> H[Hurricane Zone Analysis]
   ```

7. **Automated Report Generation**
   - Ask: "Generate a markdown report summarizing the geographical distribution, create statistical plots, and identify data clusters"
   - AI produces comprehensive analysis with embedded visualizations

8. **SQL Query Generation**
   - Ask: "Convert this GeoJSON to SQL CREATE and INSERT statements for a PostGIS database"
   - AI generates database-ready SQL with spatial data types

9. **Python Class Generation**
   - Ask: "Create a Python class to manage geotechnical boring logs with methods for filtering by region, depth, and soil type"
   - AI generates object-oriented code structure

10. **Data Quality Analysis**
    - Ask: "Identify potential data quality issues like duplicate points, outliers, or impossible coordinates"
    - AI performs automated QA/QC checks

### Multi-Agent Workflows

11. **Complex Analysis Pipeline**
    - Ask: "Use multiple agents to: 1) Clean the data, 2) Perform clustering analysis, 3) Generate visualizations, 4) Create a summary report"
    - Demonstrates agent orchestration for complex tasks

12. **Cross-Reference with External Data**
    - Ask: "Correlate these points with USGS earthquake data and identify high-risk zones"
    - Shows integration of multiple data sources

## 🛠️ Getting Started

### Prerequisites
- Python 3.8+
- AI coding assistant (OpenCode, OpenAI API, Claude, GitHub Copilot, or similar)
- Basic familiarity with JSON/GeoJSON format

### Installing OpenCode (Recommended AI Assistant)

OpenCode is a powerful AI coding assistant that works directly in your terminal. Here's how to set it up:

1. **Install OpenCode**
   ```bash
   curl -fsSL https://opencode.ai/install | bash
   ```

2. **Restart your terminal or reload your shell configuration**
   ```bash
   source ~/.bashrc
   # or for zsh users:
   # source ~/.zshrc
   ```

3. **Set up your OpenRouter API key**
   ```bash
   opencode auth login
   ```
   Follow the prompts to enter your OpenRouter API key. You can get one at [OpenRouter](https://openrouter.ai/).

4. **Start using OpenCode with this repository**
   ```bash
   # Navigate to the repository
   cd Generative_AI_In_Geotechnical
   
   # Start OpenCode
   opencode
   
   # Try an example prompt:
   # "Count the total number of points in Example_data_from_Geosetta.geojson"
   ```

### Using OpenCode's Plan Mode as a Learning Partner

OpenCode offers a unique **Plan Mode** feature that makes it an excellent learning companion for understanding geotechnical data processing:

#### What is Plan Mode?
Plan Mode (`opencode --plan`) allows you to explore and understand solutions before executing them. The AI will:
- Explain what it would do step-by-step
- Show you the code it would write
- Discuss different approaches
- Help you understand the logic without making actual changes

#### How to Use Plan Mode for Learning

1. **Start OpenCode in Plan Mode**
   ```bash
   opencode --plan
   ```

2. **Ask exploratory questions**
   ```
   # Example prompts in plan mode:
   "Show me how you would analyze the clustering patterns in this GeoJSON data"
   "Explain different ways to visualize this geotechnical data"
   "Walk me through creating a data pipeline for soil classification"
   ```

3. **Understand before executing**
   - Review the AI's planned approach
   - Ask follow-up questions about specific steps
   - Learn the reasoning behind each decision
   - Once comfortable, run without `--plan` to execute

#### Learning Partner Strategies

**For Beginners:**
- Start in plan mode to understand each step
- Ask "why" questions about the approach
- Request alternative solutions to compare methods

**For Intermediate Users:**
- Use plan mode to explore advanced techniques
- Compare different libraries and frameworks
- Understand performance implications

**For Advanced Users:**
- Explore architectural decisions
- Discuss optimization strategies
- Plan complex multi-step workflows

#### Example Learning Session
```bash
# Start in plan mode
opencode --plan

# Ask a learning-focused question
"I want to understand how to process this GeoJSON file. Can you walk me through:
1. How to parse the structure
2. What libraries would be best for analysis
3. Common pitfalls to avoid
Show me the code you would write and explain each part."

# Review the plan, ask clarifying questions
"Why did you choose pandas over geopandas for this task?"

# When ready, exit and run without --plan to execute
opencode
"Now implement the solution we discussed"
```

#### Benefits of Plan Mode for Learning
- **Risk-free exploration** - Understand without breaking anything
- **Deeper understanding** - See the reasoning behind solutions
- **Multiple perspectives** - Explore different approaches
- **Interactive learning** - Ask questions and get explanations
- **Build confidence** - Review before executing

### Quick Start
1. Clone this repository
2. Install OpenCode (see above) or use your preferred AI assistant
3. Load the example GeoJSON file
4. Try the example prompts with your AI assistant
5. Experiment with your own queries

### Example Python Setup
```python
import json
import pandas as pd
import plotly.express as px

# Load the geotechnical data
with open('Example_data_from_Geosetta.geojson', 'r') as f:
    data = json.load(f)

# Extract coordinates
points = []
for feature in data['features']:
    lon, lat = feature['geometry']['coordinates']
    points.append({'longitude': lon, 'latitude': lat})

df = pd.DataFrame(points)
print(f"Loaded {len(df)} geotechnical data points")
```

## 📚 Learning Objectives
- Understand how to formulate effective prompts for geotechnical data analysis
- Learn to leverage AI for rapid prototyping of data processing scripts
- Explore creative applications of LLMs beyond traditional coding
- Practice iterative refinement of AI-generated solutions
- Develop workflows combining multiple AI capabilities

## 🎓 Educational Use Cases

### For Students
- Learn GIS data processing without extensive programming background
- Quickly prototype analysis methods
- Generate boilerplate code for assignments

### For Professionals
- Rapid data exploration and quality checks
- Automated report generation
- Quick visualization for client presentations
- Code documentation and refactoring

### For Researchers
- Literature review automation
- Statistical analysis code generation
- Hypothesis testing workflows
- Publication-ready figure generation

## 🔬 Advanced Challenges

1. **Machine Learning Pipeline**: Ask AI to create a complete ML pipeline for predicting soil bearing capacity based on location
2. **3D Visualization**: Generate three.js code for 3D visualization of boring logs
3. **API Development**: Create a FastAPI server to serve this geotechnical data
4. **Data Augmentation**: Generate synthetic geotechnical data points using AI
5. **Natural Language Queries**: Build a system that converts plain English questions about the data into executable code

## 📝 Tips for Effective AI Prompting

1. **Be Specific**: Include data format, expected output, and any constraints
2. **Iterative Refinement**: Start simple, then add complexity
3. **Context Matters**: Provide sample data structure when asking for processing code
4. **Verify Output**: Always validate AI-generated analysis results
5. **Learn from Examples**: Study how AI structures solutions for similar problems

## 🤝 Contributing
We welcome contributions! Please share your creative AI prompts and use cases for geotechnical data analysis.

## 📄 License
This project is open source and available for educational purposes.

## 🔗 Resources
- [Geosetta](https://www.geosetta.org/) - Source of geotechnical data
- [GeoJSON Specification](https://geojson.org/)
- [Plotly Documentation](https://plotly.com/python/)
- [OpenAI API Documentation](https://platform.openai.com/docs)

## 💡 Next Steps
Try these progressively challenging tasks:
1. Start with basic counting and filtering
2. Move to visualization tasks
3. Attempt multi-step analysis workflows
4. Create custom tools and functions
5. Build complete applications with AI assistance

---
*This repository is maintained as an educational resource for the geotechnical engineering community to explore the intersection of AI and geospatial data analysis.*