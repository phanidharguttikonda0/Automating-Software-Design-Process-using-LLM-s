# Automating Software Design Process using LLMs

This project aims to automate the software design process using Large Language Models (LLMs). It leverages the power of AI to assist in various stages of software development, from requirements gathering to code generation.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.8 or higher
- pip (Python package manager)
- Bash shell (for running the setup and project scripts)
- Java (for running PlantUML)

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/phanidharguttikonda0/Automating-Software-Design-Process-using-LLM-s.git
   cd Automating-Software-Design-Process-using-LLM-s
   ```

2. Run the setup script:
   ```
   chmod +x setup.sh
   ./setup.sh
   ```
   This script will create a virtual environment, activate it, and install all the required dependencies from the `requirements.txt` file.

## Usage

1. To run the project, use the provided `run_project.sh` script:
   ```
   chmod +x run_project.sh
   ./run_project.sh
   ```

2. Follow the prompts to input your project requirements and preferences.

3. The system will generate various artifacts, including:
   - System architecture diagrams
   - Class diagrams
   - Sequence diagrams
   - API specifications
   - Code snippets

4. Review the generated output in the `Data/processed` directory.

## Project Structure
```
├── run_project.sh
├── setup.sh
├── requirements.txt
├── plantuml.jar
├── src/
│ ├── data_processing/
│ │ └── pdf_extractor.py
│ ├── nlp/
│ │ └── nlp_pipeline.py
│ ├── uml_generation/
│ │ └── uml_generator.py
│ ├── diagram_renderer.py
│ └── main.py
├── Data/
│ ├── input/
│ └── processed/
├── .gitignore
└── README.md

```

## Some Common Errors in Setup Phase

The error ModuleNotFoundError: No module named 'torch._C' typically indicates that PyTorch was not installed properly or is incompatible with your system.
```
pip uninstall -y torch torchvision torchaudio
pip cache purge
pip install torch torchvision torchaudio
```
If you're still having issues, you might want to recreate your virtual environment:
```
deactivate  # Exit the current virtual environment
rm -rf venv  # Remove the old virtual environment
python -m venv venv  # Create a new virtual environment
source venv/Scripts/activate  # Activate the new environment
pip install -r requirements.txt  # Reinstall all your dependencies
```
Here's an updated run_project.sh script that incorporates these steps:
```
#!/bin/bash

# Activate virtual environment (for Windows Git Bash / MinGW)
source venv/Scripts/activate

# Uninstall existing PyTorch
pip uninstall -y torch torchvision torchaudio
pip cache purge

# Install PyTorch (adjust the command based on your system requirements)
pip install torch torchvision torchaudio

# Verify PyTorch installation
python -c "import torch; print(torch.__version__)"

# Run the main script
python src/main.py

echo "Project execution complete. Check the 'data/processed' folder for the output UML diagram."

```


Contributions to this project are welcome. Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin feature/your-feature`)
6. Create a new Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Additional Information

For more detailed documentation on this project, please visit our [Notion page](https://www.notion.so/Project-11c59cd34c37806ab046daee81d03d76).(Currently not available to public)
