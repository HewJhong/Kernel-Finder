# 🎯 Graph Kernel Finder

An interactive web application for finding and analyzing kernels in directed graphs. This tool provides a comprehensive solution for graph theory enthusiasts, students, and researchers to explore kernel structures in directed graphs.

![Graph Kernel Finder Screenshot](https://img.shields.io/badge/Status-Active-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)

## 🌟 Features

- **🔍 Interactive Analysis**: Real-time kernel detection and verification
- **📊 Comprehensive Results**: Detailed analysis with step-by-step verification
- **🎨 Modern UI**: Beautiful, responsive design with smooth animations
- **⚡ Fast Performance**: Optimized algorithms with performance metrics
- **📝 Flexible Input**: Support for custom graph formats
- **🔬 Educational**: Perfect for learning graph theory concepts

## 🧮 What is a Kernel?

In graph theory, a **kernel** in a directed graph G is a set X ⊆ V(G) of vertices such that:

1. **Domination Condition**: For every vertex v ∈ V(G), either v ∈ X or there exists another vertex u ∈ X such that (u,v) ∈ A(G)
2. **Independence Condition**: For every edge (v,w) ∈ A(G), either v ∉ X or w ∉ X

Think of a kernel as a set of "monitoring stations" where:
- Every location is either a monitoring station OR is watched by at least one station
- No two monitoring stations watch each other directly

## 🚀 Getting Started

### Prerequisites

- Any modern web browser (Chrome, Firefox, Safari, Edge)
- No additional installations required!

### Running the Application

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/graph-kernel-finder.git
   cd graph-kernel-finder
   ```

2. **Open the application**:
   ```bash
   # Simply open index.html in your browser
   open index.html
   # or
   python -m http.server 8000  # For local server
   ```

3. **Start analyzing graphs**!

## 📖 How to Use

### Input Format

The application accepts directed graphs in the following format:

```
n m
j1 j2 ... jd : i
```

Where:
- `n`: number of vertices
- `m`: number of edges
- `j1 j2 ... jd : i`: vertices j1, j2, ..., jd are in-neighbors of vertex i

### Example Input

```
4 4
2 : 1
1 3 : 2
: 3
2 : 4
```

This represents:
- 4 vertices, 4 edges
- Vertex 1 has in-neighbor 2
- Vertex 2 has in-neighbors 1 and 3
- Vertex 3 has no in-neighbors
- Vertex 4 has in-neighbor 2

### Step-by-Step Usage

1. **Enter your graph data** in the input textarea
2. **Click "Find All Kernels"** to start the analysis
3. **Review the results**:
   - Graph structure visualization
   - List of all found kernels
   - Detailed verification for each kernel
   - Performance statistics

## 🔧 Technical Details

### Algorithm

The application uses a brute-force approach that:

1. **Parses** the input graph format
2. **Generates** all possible subsets of vertices (2^n combinations)
3. **Tests** each subset against both kernel conditions
4. **Verifies** and displays results with detailed explanations

### Complexity

- **Time Complexity**: O(2^n × (n + m)) where n = vertices, m = edges
- **Space Complexity**: O(n + m) for graph storage
- **Practical Limit**: ~10 vertices (1024 subsets) for reasonable performance

### Performance Optimizations

- Early termination on condition failures
- Efficient set operations using JavaScript Set
- Minimal DOM manipulations for better rendering

## 📊 Example Graphs

### Complete Example
```
7 9
3 : 1
3 : 2
4 : 3
3 : 4
3 7 : 5
4 : 6
5 6 : 7
```
**Result**: This graph has 2 kernels: {3, 6} and {1, 2, 4, 7}

### Simple Cycle
```
3 3
2 : 1
3 : 2
1 : 3
```
**Result**: This graph has no kernels (odd cycle)

### Path Graph
```
3 2
: 1
1 : 2
2 : 3
```
**Result**: This graph has 1 kernel: {1, 3}

## 🎨 Features Overview

| Feature | Description |
|---------|-------------|
| **Real-time Analysis** | Instant kernel detection as you input graphs |
| **Visual Feedback** | Color-coded results with success/error indicators |
| **Detailed Verification** | Step-by-step explanation of why each set is/isn't a kernel |
| **Performance Metrics** | Execution time and subset count statistics |
| **Error Handling** | Helpful error messages for invalid inputs |
| **Responsive Design** | Works perfectly on desktop and mobile devices |

## 🛠️ Built With

- **HTML5** - Structure and semantics
- **CSS3** - Styling with modern features (Grid, Flexbox, Animations)
- **Vanilla JavaScript** - Core functionality and algorithms
- **No external dependencies** - Runs entirely in the browser

## 📚 Educational Resources

### Graph Theory Concepts
- [Kernel (Graph Theory) - Wikipedia](https://en.wikipedia.org/wiki/Kernel_(graph_theory))
- [Introduction to Graph Theory](https://www.example.com)
- [Directed Graphs and Their Properties](https://www.example.com)

### Related Algorithms
- Dominating Sets
- Independent Sets
- Vertex Covers
- Stable Sets

## 🙏 Acknowledgments

- Built with Claude Sonnet 4
- Originally inspired by Monash University Malaysia FIT2014
