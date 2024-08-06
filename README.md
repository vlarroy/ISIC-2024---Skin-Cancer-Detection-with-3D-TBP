# ISIC 2024 Challenge Data Setup

This document outlines the steps to set up the directory structure and download the necessary data files for the ISIC 2024 Challenge using the Kaggle API.

## Prerequisites

- Ensure you have the [Kaggle API](https://www.kaggle.com/docs/api) set up and configured on your system. This includes placing your API token in the appropriate location (`~/.kaggle/kaggle.json`).
- Ensure `tar` is installed on your system to extract the contents of the ZIP file.

## Steps

### Step 1: Create Directories for Data Storage

Create the necessary directories where the challenge data will be stored.

```bash
mkdir -p ~/data/isic-2024-challenge
```

### Step 2: Download the ISIC 2024 Challenge Dataset

Download the dataset using the Kaggle API. Ensure you have the credentials configured before running this command. The `-w` flag ensures that only the files necessary for the competition are downloaded.

```bash
kaggle competitions download isic-2024-challenge -p ~/data/isic-2024-challenge/
```

### Step 3: Extract the Downloaded ZIP File

Extract the contents of the `isic-2024-challenge.zip` file.

```bash
tar -xf ~/data/isic-2024-challenge/isic-2024-challenge.zip -C ~/data/isic-2024-challenge/
```

### Step 4: Remove the ZIP File After Extraction

Delete the ZIP file to free up disk space since its contents are now extracted.

```bash
rm ~/data/isic-2024-challenge/isic-2024-challenge.zip
```

### Step 5: Create a virtual environment

Set up a Python virtual environment to manage dependencies separately from your system Python installation. This helps maintain clean and reproducible setups.

```bash
python -m venv .venv
```

### Step 6: Activate environment

Activate the virtual environment to start using the isolated Python environment. This ensures that the dependencies you install are only available in this environment.

```bash
source .venv/bin/activate
```

For Windows, use:

```bash
.venv\Scripts\activate
```

### Step 7: Install the requirements

Install the necessary Python packages listed in the `requirements.txt` file. This file should contain all the dependencies required for your project.

```bash
pip install -r requirements.txt
```

## Troubleshooting

- If you encounter issues with the Kaggle download, verify that your API credentials are correctly set up and that you have agreed to the competition rules on the Kaggle website.

- If the `tar` command fails, ensure the ZIP file downloaded correctly and is not corrupted.