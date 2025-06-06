
# 🧠 Neural Network from Scratch in C

A modular and minimalistic C project implementing a fully functional artificial neural network — from file I/O to matrix algebra to forward/backward propagation — using only the C standard library.

## 📐 Project Principles

- No third-party libraries (standard C only)
- Fully modular architecture
- Implement your own matrix, training, data, and serialization layers
- Maintainability and extensibility
- Built with CMake
- Version-controlled with Git

---

## 🛠️ Project Setup

### 1. Project Initialization ✅
**Goal:** Create a clean Git + CMake-based repository.

**Tasks:**
- Initialize a Git repo
- Set up `.gitignore`
- Write `CMakeLists.txt` for modular build
- Create directory structure:

```bash
.
├── src/
│   ├── core/         # matrix ops, math utils
│   ├── model/        # neural net logic
│   ├── data/         # file I/O, dataset parsing
│   ├── train/        # training, evaluation
│   └── utils/        # common helpers
├── include/          # public headers
├── tests/            # unit tests (optional)
└── CMakeLists.txt
```

**Definition of Done (DoD):**
- Git initialized
- CMake builds basic "Hello World" in `main.c`
- Source and header folders structured

---

## 🧮 Core Layer: Math and Matrix Engine

### 2. Matrix Module ✅
**Goal:** Implement a dynamic matrix engine.

**Tasks:**
- Create a `Matrix` struct
- Implement allocation (`create_matrix`, `free_matrix`)
- Element access (`get`, `set`)
- Core operations:
  - addition, subtraction
  - scalar multiply/divide
  - dot product
  - transpose

**DoD:**
- All operations tested on basic matrices
- No memory leaks (use Valgrind if needed)

---

### 3. Activation Functions ✅
**Goal:** Implement differentiable activation functions.

**Tasks:**
- Implement:
  - Sigmoid
  - Tanh
  - ReLU
- Implement their derivatives

**DoD:**
- Functions return expected values on test inputs
- Can be applied element-wise to matrices

---

## 🧠 Model Layer: Neural Network Architecture

### 4. Neural Network Structures ✅
**Goal:** Define a neural network data structure.

**Tasks:**
- Define `Layer` struct (weights, biases, activations)
- Define `Network` struct (array of layers)
- Implement creation and deletion functions

**DoD:**
- Can create a network with arbitrary layer sizes
- All memory is managed correctly

---

### 5. Forward Propagation ✅
**Goal:** Implement the forward pass.

**Tasks:**
- Implement layer-by-layer computation
- Use activations on each layer
- Store intermediate values for backprop

**DoD:**
- Forward pass returns correct outputs on known inputs

---

### 6. Backpropagation ✅
**Goal:** Implement gradient computation and weight update.

**Tasks:**
- Implement loss function (e.g., MSE, cross-entropy)
- Compute gradients with chain rule
- Update weights and biases using learning rate

**DoD:**
- Weights update when training on small examples
- Loss decreases over time

---

## 📂 Data Layer: File Loading and I/O

### 7. Data Representation ✅
**Goal:** Create a generic dataset loader.

**Tasks:**
- Define `Dataset` struct (features, labels)
- Load CSV or TSV files into matrices
- Normalize features (min-max or standard)

**DoD:**
- Loads CSV dataset into memory
- Supports both regression and classification

---

### 8. Batching and Shuffling ✅
**Goal:** Implement batching for training.

**Tasks:**
- Slice dataset into mini-batches
- Implement dataset shuffling

**DoD:**
- Can iterate through data in batches
- Batches are randomized each epoch

---

## 🎯 Training & Evaluation

### 9. Training Loop ✅
**Goal:** Train the network over epochs.

**Tasks:**
- Loop through batches and epochs
- Perform forward + backward propagation
- Track loss and accuracy

**DoD:**
- Prints loss and accuracy per epoch
- Loss trends downward

---

### 10. Evaluation ✅
**Goal:** Evaluate model performance.

**Tasks:**
- Evaluate accuracy (for classification)
- Evaluate loss (for regression)

**DoD:**
- Evaluation prints metrics on test data

---

## 💾 Model Saving & Loading

### 11. Serialization ✅
**Goal:** Save and load model to/from file.

**Tasks:**
- Implement `save_model()` to custom binary format
- Implement `load_model()` to restore network

**DoD:**
- Saved model file loads without error
- Predictions before/after match

---

## 📦 Extras (Optional)

### 12. CLI Interface
**Goal:** Add simple CLI for training/evaluation

**Tasks:**
- Parse arguments (e.g., dataset path, epochs)
- Show usage help

---

### 13. Testing & Debugging Tools
**Goal:** Create basic test suite

**Tasks:**
- Add `tests/` for matrix, activation, etc.
- Create debugging macros/loggers

---

## 🧪 Example Use

```bash
# Build
cmake -S . -B build
cmake --build build

# Run
./build/neural_net --dataset data/iris.csv --epochs 1000
```

---

## 📚 Future Extensions

- Convolutional layers
- Optimizers: Adam, RMSprop
- Dropout, batch norm
- GPU acceleration (OpenCL)
- JSON config/model format
- GUI visualizer (SDL or ncurses)

---

## ✅ Final Checklist Before Release

- [ ] Memory-safe (no leaks)
- [ ] Passes all unit tests
- [ ] Well-structured commit history
- [ ] Modular, readable code
- [ ] Can be extended easily
