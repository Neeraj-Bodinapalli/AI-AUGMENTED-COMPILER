# 🚀 AI-Augmented Compiler

An intelligent compiler optimization system that leverages Machine Learning to automatically predict and apply the best code optimization techniques for C programs.

## 📋 Project Description / Overview

This project implements an AI-powered compiler that combines traditional compiler design principles with modern machine learning techniques. The system analyzes C source code, generates intermediate representation (IR), extracts comprehensive features, and uses a trained Random Forest model to intelligently select and apply the most effective optimization technique.

## ✨ Key Features

- 🤖 **ML-Driven Optimization Selection** - Intelligent prediction of optimal optimization techniques
- 🔄 **Automatic Optimization Application** - Seamless integration of ML predictions with optimization engine
- 🎨 **Interactive GUI** - Visual comparison of original vs optimized code with detailed statistics
- 📊 **Performance Analysis** - Runtime comparison and cost estimation for optimized code
- 🧩 **Multiple Optimization Techniques** - Support for 5 major optimization strategies
- 🔍 **Advanced Feature Extraction** - 15+ features extracted from IR code for ML analysis

## 🛠️ Technologies Used

### Programming Languages
- **Python 3.6+** - Core ML and optimization logic
- **C** - Compiler implementation
- **Flex/Bison** - Lexical analysis and parsing

### Machine Learning & Data Science
- **scikit-learn** - Random Forest classifier for optimization prediction
- **pandas** - Data processing and feature management
- **numpy** - Numerical computations
- **joblib** - Model serialization and loading

### GUI Framework
- **tkinter** - Graphical user interface

## 📁 Project Structure

```
c-compiler/
│
├── compiler.exe                    # Compiled C compiler executable
├── compiler_model.joblib          # Trained ML model (Random Forest)
├── requirements.txt               # Python dependencies
│
├── Core Application Files
│   ├── optimization_gui.py        # Main GUI application
│   ├── optimization_predictor.py  # ML prediction system
│   ├── optimizer.py              # Optimization engine (5 techniques)
│   ├── ir_feature_extractor.py   # Feature extraction from IR
│   ├── ir_to_c.py                # IR to C code translator
│   ├── build_executables.py      # Build executables for testing
│   └── compare_runtime.py        # Runtime performance comparison
│
├── Compiler Source
│   ├── lexer.l                   # Flex lexer source (tokenization)
│   └── parser.y                  # Bison parser source (grammar and IR)
│
├── Machine Learning
│   ├── train_model.py            # Model training script
│   └── features.csv              # Training dataset
│
└── Test Files
    ├── input1.c                  # Example test file
    └── C-codes/                  # Test suite (50+ test cases)
```

## 🔧 Installation Instructions

### Prerequisites
- Python 3.6 or higher
- pip (Python package manager)

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd c-compiler
```

### Step 2: Install Dependencies
```bash
pip install -r requirements.txt
```

## 🚀 Usage Guide

### Launch GUI
```bash
python optimization_gui.py
```

### Steps to Use:
1. Click **"Browse"** button
2. Select a C source file (e.g., `input1.c` or any file from `C-codes/`)
3. Click **"Analyze"**
4. View results:
   - **Original vs Optimized IR** - Side-by-side code comparison
   - **Statistics Panel** - Instruction count, cost analysis, improvement metrics
   - **Runtime Panel** - Performance comparison (if C compiler available)
   - **Info Panel** - Description of applied optimization

## 🏗️ Architecture / How It Works

### System Pipeline

```
┌─────────────┐
│  C Source   │
│    Code     │
└──────┬──────┘
       │
       ▼
┌─────────────────┐
│  Lexer (lexer.l)│  Tokenization
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Parser (parser.y)│  Parsing & IR Generation
└────────┬────────┘
         │
         ▼
┌──────────────────────┐
│ Intermediate Code    │  Three-address code
│    (IR)              │
└────────┬─────────────┘
         │
         ▼
┌──────────────────────────┐
│ Feature Extraction       │  Extract 15 features:
│ (ir_feature_extractor.py)│  - Instruction count
└────────┬─────────────────┘  - Complexity metrics
         │                     - Loop analysis
         ▼                     - Expression patterns
┌──────────────────────────┐
│ ML Model Prediction      │  Random Forest predicts
│ (compiler_model.joblib)  │  optimal optimization
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│ Optimization Engine      │  Apply predicted
│ (optimizer.py)           │  optimization
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│ Optimized IR             │
└────────┬─────────────────┘
         │
         ▼
┌──────────────────────────┐
│ GUI Visualization        │  Side-by-side comparison
│ (optimization_gui.py)    │  Statistics & Performance
└──────────────────────────┘
```

### Supported Optimizations

The system implements 5 major optimization techniques:

1. **Constant Folding** - Evaluates constant expressions at compile-time and propagates constant values
2. **Dead Code Elimination** - Removes unreachable code and unused variables using liveness analysis
3. **Common Subexpression Elimination** - Eliminates redundant calculations within basic blocks
4. **Strength Reduction** - Replaces expensive operations (multiplication/division) with cheaper ones (addition/subtraction) in loops
5. **Loop-Invariant Code Motion** - Moves loop-invariant calculations outside loops to reduce computation overhead



