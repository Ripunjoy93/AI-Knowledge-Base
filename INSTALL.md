## 🛠️ Installation Instructions  

### Using `requirements.txt` (pip + venv)  

#### 1️⃣ Create and activate a virtual environment  

```bash
# Create a virtual environment named 'venv'
python -m venv venv

# Activate the virtual environment
# On Windows:
venv\Scripts\activate

# On macOS/Linux:
source venv/bin/activate
```

#### 2️⃣ Install dependencies  

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### Using `environment.yml` (Conda)  

#### 1️⃣ Create and activate the Conda environment  

```bash
conda env create -f environment.yml
conda activate ai-base
```

### Updating the Environment  

```bash
# For pip-based installation
pip install --upgrade -r requirements.txt

# For Conda-based installation
conda env update --file environment.yml --prune
```

### Removing the Environment  

```bash
# Remove virtual environment (for venv)
rm -rf venv  # On macOS/Linux
rd /s /q venv  # On Windows (Command Prompt)

# Remove Conda environment
conda remove --name ai-base --all
```
