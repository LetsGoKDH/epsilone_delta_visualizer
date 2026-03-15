# ε-δ Explorer

An interactive web-based visualization tool for exploring the ε-δ (epsilon-delta) definition of continuity and uniform continuity in calculus.

## 🌐 Live Demo

Visit: [https://letsgokdh.github.io/epsilone_delta_visualizer/](https://letsgokdh.github.io/epsilone_delta_visualizer/)

The application automatically detects your device and redirects to the optimized version:
- **Desktop/Laptop**: Wide layout with sidebar controls
- **Mobile/Tablet**: Vertical layout optimized for touch

Or access directly:
- Desktop version: [desktop.html](https://letsgokdh.github.io/epsilone_delta_visualizer/desktop.html)
- Mobile version: [mobile.html](https://letsgokdh.github.io/epsilone_delta_visualizer/mobile.html)

## 📖 Overview

This tool helps students and educators visualize the epsilon-delta (ε-δ) definition of limits, continuity, and uniform continuity. It provides:

- **Interactive visualization** of how δ depends on ε and x₀
- **Real-time computation** of δ values for given ε and x₀
- **Automatic detection** of discontinuities and their types
- **Uniform continuity testing** across the entire domain
- **12 preset functions** covering common cases

## ✨ Features

### 🎯 Core Functionality

1. **Function Input**
   - Custom function parser using [math.js](https://mathjs.org/)
   - Support for standard mathematical functions (sin, cos, tan, exp, log, sqrt, abs, floor, etc.)
   - Real-time syntax validation

2. **Interactive Visualization**
   - Dynamic graph rendering with adjustable ranges
   - Visual representation of ε and δ neighborhoods
   - Color-coded regions for easy understanding

3. **Sliders**
   - **x₀ slider**: Choose the point of interest
   - **ε slider**: Set the tolerance (logarithmic scale)

4. **Domain Modes**
   - **Bounded interval [a, b]**: Support for open/closed endpoints
   - **Real numbers ℝ**: Explore behavior across the entire real line

5. **Automated Analysis**
   - **Continuity Check**: Detects discontinuities, undefined points, and asymptotes
   - **Uniform Continuity Test**: Computes global δ_min and determines if the function is uniformly continuous
   - **Heine-Cantor Theorem**: Automatically applies for closed bounded intervals

### 📊 Mathematical Features

#### Preset Functions

| Function | Continuity | Uniform Continuity | Notes |
|----------|------------|-------------------|-------|
| 1/x | Discontinuous at 0 | N/A | Vertical asymptote |
| x² | Continuous on ℝ | Not uniformly continuous on ℝ | δ depends on x₀ |
| sin(x) | Continuous on ℝ | Uniformly continuous on ℝ | Bounded derivative |
| √x | Continuous on [0, ∞) | Uniformly continuous on [0, ∞) | - |
| x³ | Continuous on ℝ | Not uniformly continuous on ℝ | - |
| tan(x) | Discontinuous (asymptotes) | N/A | Asymptotes at π/2 + nπ |
| eˣ | Continuous on ℝ | Not uniformly continuous on ℝ | Grows exponentially |
| ln(x) | Continuous on (0, ∞) | Uniformly continuous on [a, ∞) | - |
| \|x\| | Continuous on ℝ | Uniformly continuous on ℝ | Lipschitz continuous |
| ⌊x⌋ | Discontinuous (jumps) | N/A | Jump discontinuities at integers |
| sin(1/x) | Discontinuous at 0 | N/A | Essential discontinuity |
| x·sin(1/x) | Continuous at 0 (removable) | Not uniformly continuous | Pathological example |

## 🚀 Usage

### Online

Simply visit the [live demo](https://letsgokdh.github.io/epsilone_delta_visualizer/) and start exploring!

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/LetsGoKDH/epsilone_delta_visualizer.git
   cd epsilone_delta_visualizer
   ```

2. **Open in browser**
   - Open `index.html` in your web browser
   - Or use a local server:
     ```bash
     python -m http.server 8000
     # Then visit http://localhost:8000
     ```

## 🎓 Educational Applications

### For Students

- **Visualize abstract concepts**: See how ε and δ relate geometrically
- **Experiment with functions**: Try different functions and see their behavior
- **Understand uniform continuity**: Compare how δ changes (or doesn't change) with x₀

### For Educators

- **Classroom demonstrations**: Use during lectures to illustrate concepts
- **Homework assignments**: Assign students to explore specific functions
- **Assessment tool**: Ask students to predict behavior before checking

## 🧮 Mathematical Background

### Continuity

A function f is **continuous at x₀** if:

∀ε > 0, ∃δ > 0 such that ∀x: |x - x₀| < δ ⇒ |f(x) - f(x₀)| < ε

This means:
- For any desired precision ε
- We can find a δ (which may depend on both ε and x₀)
- Such that f(x) stays within ε of f(x₀) whenever x is within δ of x₀

### Uniform Continuity

A function f is **uniformly continuous** on a domain D if:

∀ε > 0, ∃δ > 0 such that ∀x₁, x₂ ∈ D: |x₁ - x₂| < δ ⇒ |f(x₁) - f(x₂)| < ε

Key difference:
- δ depends **only on ε**, not on the specific points x₁, x₂
- A single δ works for the entire domain

### Heine-Cantor Theorem

Every continuous function on a **closed bounded interval** [a, b] is uniformly continuous.

The tool automatically applies this theorem when:
- Domain mode is set to "구간 [a, b]"
- Both endpoints are closed
- The function is continuous on the interval

## 🛠️ Technical Details

### Technologies

- **HTML5 Canvas**: For high-performance graph rendering
- **Vanilla JavaScript**: No framework dependencies
- **[math.js](https://mathjs.org/)**: Mathematical expression parser
- **CSS3**: Modern styling with custom properties

### Browser Compatibility

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- Mobile browsers: ✅ Optimized version available

### Performance

- Lightweight: ~50KB total (uncompressed)
- Fast rendering: 60 FPS on modern devices
- Efficient algorithms: δ computation capped at 500 iterations
- Deferred verdict calculation: Doesn't block rendering

## 📱 Device-Specific Features

### Desktop Version
- Wide sidebar with all controls visible
- Larger graph area (expandable)
- Hover effects on buttons
- Mouse-optimized sliders

### Mobile Version
- Vertical layout with graph at top
- Touch-optimized controls (larger tap targets)
- Collapsible sections to save space
- Gesture-friendly sliders
- Sticky header

## 🤝 Contributing

Contributions are welcome! Here are some ways you can help:

- 🐛 **Report bugs**: Open an issue describing the problem
- 💡 **Suggest features**: Share your ideas for improvements
- 📝 **Improve documentation**: Help make the README clearer
- 🌐 **Add translations**: Translate the interface to other languages
- 🧪 **Add test cases**: Suggest interesting functions to include as presets

### Development

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Developed for Calculus 1 (미적분학 1) course at POSTECH
- Inspired by classical epsilon-delta proofs and visualizations
- Built with modern web technologies for accessibility

## 📧 Contact

- GitHub: [@LetsGoKDH](https://github.com/LetsGoKDH)
- Repository: [epsilone_delta_visualizer](https://github.com/LetsGoKDH/epsilone_delta_visualizer)

---

**Note**: This tool is for educational purposes and provides numerical approximations. For rigorous proofs, consult your textbook or instructor.

## 🌟 Star History

If you find this tool helpful, please consider giving it a star ⭐ on GitHub!
