# SBMLNetworkWeb

A web-based implementation of [SBMLNetwork](https://github.com/sys-bio/SBMLNetwork) that visualizes Systems Biology Markup Language (SBML) models as interactive network diagrams in the browser.

## 🎯 Project Overview

SBMLNetworkWeb bridges computational biology and web visualization by rendering SBML models as interactive network diagrams. It uses WebAssembly for efficient SBML processing and D3.js for rich, interactive visualizations.

### Key Features
- **Interactive Network Diagrams**: Visualize species, reactions, and compartments
- **Auto-layout**: Automatic positioning of network elements
- **Layout Persistence**: Save and restore layout configurations
- **Real-time Rendering**: Dynamic updates and interactions
- **Cross-platform**: Runs in any modern web browser

## 🏗️ Project Structure

```
SBMLNetworkWeb/
├── libsbmlnetwork /          # Main application
│   ├── generic.html          # Primary SBML viewer application
│   ├── libsbmlnetwork.js     # JavaScript wrapper for WebAssembly
│   ├── libsbmlnetwork.wasm   # Compiled WebAssembly binary
│   └── layoutScript.html     # Additional layout functionality
├── sbml-examples/            # Sample SBML models
│   ├── simple_sbml_model.xml # Basic 3-species, 2-reaction model
│   └── figure_2_sbgn_compliant.xml # Complex SBGN-compliant model
├── d3-playground/            # D3.js learning environment
│   ├── index.html            # Basic D3.js canvas examples
│   └── README.md             # D3.js playground documentation
├── tests/                    # Test suite
│   ├── test.html             # Basic SBML autolayout tests
│   ├── test1.html            # Additional test cases
│   ├── test1Skia.html        # Skia graphics testing
│   ├── skiaTest.html         # More Skia graphics tests
│   └── testViewer.html       # Viewer-specific functionality tests
├── layout_stable.xml         # Stable SBML layout configuration
└── README.md                 # This file
```

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6 modules)
- **Visualization**: D3.js v7
- **SBML Processing**: WebAssembly (compiled from C++)
- **Data Format**: SBML (Systems Biology Markup Language)
- **Storage**: Browser localStorage for layout persistence
- **Development**: Local HTTP server for testing

## 🚀 How to Run and Test

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Python 3.x, Node.js, or PHP (for local server)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd SBMLNetworkWeb
   ```

2. **Start a local web server**

   **Option A: Python (Recommended)**
   ```bash
   python3 -m http.server 8000
   ```

   **Option B: Node.js**
   ```bash
   npx http-server -p 8000
   ```

   **Option C: PHP**
   ```bash
   php -S localhost:8000
   ```

3. **Open the main application**
   - Navigate to: `http://localhost:8000/libsbmlnetwork%20/generic.html`
   - You should see an interactive SBML network diagram

### Testing Different Components

#### 1. Main SBML Viewer
- **URL**: `http://localhost:8000/libsbmlnetwork%20/generic.html`
- **Features**: 
  - Interactive network diagram
  - Auto-layout functionality
  - Layout persistence
  - Reset layout button
  - Species and reaction visualization

#### 2. D3.js Playground
- **URL**: `http://localhost:8000/d3-playground/index.html`
- **Purpose**: Basic D3.js examples and learning environment

#### 3. Test Suite
- **Basic Tests**: `http://localhost:8000/tests/test.html`
- **Viewer Tests**: `http://localhost:8000/tests/testViewer.html`
- **Graphics Tests**: `http://localhost:8000/tests/skiaTest.html`

### Testing Different SBML Models

To test with different SBML models, modify line 42 in `libsbmlnetwork /generic.html`:

```javascript
// Change this line to test different models
const SBML_FILE = '../sbml-examples/simple_sbml_model.xml';
// or
const SBML_FILE = '../sbml-examples/figure_2_sbgn_compliant.xml';
```

## 🔍 What You Should See

### Main Application Features
1. **Network Diagram**: Species as nodes, reactions as connections
2. **Interactive Elements**: Hover effects and click interactions
3. **Auto-layout**: Automatic positioning of network elements
4. **Visual Components**:
   - Species nodes (circles)
   - Reaction nodes (small circles)
   - Directional arrows
   - Compartment backgrounds
   - Labels and annotations

### Browser Console Output
Look for these success messages:
- `✅ libSBMLNetwork WASM loaded.`
- `✅ Rendering complete.`
- Layout coordinates and information

## 🐛 Troubleshooting

### Common Issues

1. **CORS Errors**
   - **Problem**: Opening HTML files directly in browser
   - **Solution**: Always use a web server (see Quick Start above)

2. **WebAssembly Loading Failures**
   - **Problem**: WASM file not loading
   - **Solution**: Check browser console, ensure modern browser

3. **File Path Issues**
   - **Problem**: Space in `libsbmlnetwork /` folder name
   - **Solution**: Use URL encoding: `libsbmlnetwork%20/`

4. **Layout Not Appearing**
   - **Problem**: No visual elements shown
   - **Solution**: Check browser console for errors, verify SBML file path

### Browser Compatibility
- **Chrome**: 67+ (recommended)
- **Firefox**: 60+
- **Safari**: 11.1+
- **Edge**: 79+

## 📊 Sample SBML Models

### Simple Model (`simple_sbml_model.xml`)
- 3 species (S1, S2, S3)
- 2 reactions (R1, R2)
- Basic linear pathway

### Complex Model (`figure_2_sbgn_compliant.xml`)
- SBGN-compliant layout
- Multiple compartments
- Complex reaction networks

## 🔧 Development

### File Structure Details

- **`generic.html`**: Main application with D3.js visualization
- **`libsbmlnetwork.js`**: JavaScript interface to WebAssembly
- **`libsbmlnetwork.wasm`**: Compiled C++ code for SBML processing
- **Test files**: Various test scenarios for functionality validation

### Key Functions
- **Auto-layout**: Automatic positioning of network elements
- **Layout persistence**: Save/restore layouts in localStorage
- **Real-time rendering**: Dynamic updates and interactions
- **SBML parsing**: WebAssembly-based SBML processing

## 📚 Additional Resources

- [SBMLNetwork](https://github.com/sys-bio/SBMLNetwork) - Original C++ implementation
- [D3.js Documentation](https://d3js.org/) - Visualization library
- [SBML Specification](http://sbml.org/) - Systems Biology Markup Language

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is based on SBMLNetwork. Please refer to the original project for licensing information.
