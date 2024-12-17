---
layout: post
title: "Setting Up Python Virtual Environments on macOS"
date: 2024-12-16
categories: [python, development]
tags: [python, virtualenv, pyenv, conda, macos]
---

When working with Python projects on macOS, it's essential to use virtual environments to manage dependencies. Here are three common approaches to setting up virtual environments.

## Using venv (Python's Built-in Tool)

Python's built-in `venv` module is the simplest option:

```bash
# Create a new virtual environment
python3 -m venv myenv

# Activate the environment
source myenv/bin/activate

# Deactivate when done
deactivate
```

## Using pyenv

`pyenv` offers more flexibility in managing multiple Python versions:

```bash
# Install pyenv via Homebrew if not installed
brew install pyenv

# Add to your shell configuration (~/.zshrc or ~/.bash_profile)
echo 'eval "$(pyenv init --path)"' >> ~/.zshrc

# Install a specific Python version
pyenv install 3.11.0

# Set global Python version
pyenv global 3.11.0

# Set local Python version for current directory
pyenv local 3.11.0

# Create virtual environment with pyenv-virtualenv
pyenv virtualenv 3.11.0 myenv

# Activate the environment
pyenv activate myenv

# Deactivate
pyenv deactivate
```

## Using conda

Conda is particularly useful for data science projects:

```bash
# Install Miniconda if not installed
brew install --cask miniconda

# Initialize conda for your shell
conda init zsh  # or bash if using bash

# Create new environment
conda create --name myenv python=3.11

# Activate the environment
conda activate myenv

# Deactivate
conda deactivate
```

After activating any of these environments, you can install packages using pip:

```bash
pip install package_name
```

Each approach has its merits: `venv` is built into Python and perfect for simple projects, `pyenv` excels at managing multiple Python versions, and `conda` is ideal for data science work with complex dependencies.