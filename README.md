# FabLang

[![Join our Discord](https://img.shields.io/badge/Discord-Join%20our%20server-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/agora-999382051935506503) [![Subscribe on YouTube](https://img.shields.io/badge/YouTube-Subscribe-red?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/@kyegomez3242) [![Connect on LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/kye-g-38759a207/) [![Follow on X.com](https://img.shields.io/badge/X.com-Follow-1DA1F2?style=for-the-badge&logo=x&logoColor=white)](https://x.com/kyegomezb)

*The Domain-Specific Language for Industrial Design and Manufacturing*


**FabLang** is a domain-specific programming language crafted to streamline industrial design and make parts easier to manufacture. It bridges the gap between conceptual design and production-ready models by providing an intuitive syntax tailored for engineers and designers. With FabLang, you can create precise, parametric models that seamlessly integrate with existing CAD/CAM tools.

---

## Features

- **Intuitive Syntax**
  - Designed for readability and ease of use.
  - Syntax resembles engineering notation for quick adoption.

- **Parametric Modeling**
  - Define dimensions and properties as variables.
  - Support for equations and relationships between parameters.

- **Geometric Primitives and Operations**
  - Built-in shapes: boxes, cylinders, spheres, cones.
  - Boolean operations: union, difference, intersection.

- **Units and Measurements**
  - Explicit unit support (mm, cm, inches).
  - Automatic unit conversion and consistency checks.

- **Constraints and Relations**
  - Set geometric constraints (parallelism, concentricity).
  - Maintain relationships automatically during modifications.

- **Material Properties**
  - Assign materials with properties like density and strength.
  - Integrate material considerations into design calculations.

- **Error Checking and Optimization**
  - Automatic detection of manufacturability issues.
  - Suggestions for design modifications to improve production.

- **Integration with CAD/CAM**
  - Export to standard formats: STEP, IGES, STL.
  - Import existing models for modification or analysis.

- **Extensibility**
  - Support for modules and user-defined functions.
  - API for extending language capabilities.

- **Visualization**
  - Real-time 3D rendering within the development environment.
  - Cross-sectional views and detailed inspection tools.

---

## Getting Started

### Installation

FabLang is currently in development. Installation instructions will be provided upon official release. Stay tuned for updates!

### Basic Syntax Overview

```plaintext
// Define parameters with units
length = 100 mm;
width = 50 mm;
height = 25 mm;

// Create a box using the parameters
box(length: length, width: width, height: height);
```

---

## Examples

### Example 1: Parametric Part with Hole

```plaintext
// Parameters
length = 150 mm;
width = 100 mm;
height = 50 mm;
hole_diameter = 20 mm;

// Material Assignment
material("Aluminum 6061");

// Base Geometry
base = box(length: length, width: width, height: height);

// Create a Hole
hole = cylinder(diameter: hole_diameter, height: height + 10 mm);

// Position the Hole at the Center of the Base
hole = translate(x: length / 2, y: width / 2, z: -5 mm) {
    hole;
};

// Subtract Hole from Base to Create the Final Part
part = difference {
    base;
    hole;
};

// Export the Part to a STEP File
export(part, format: "STEP", filename: "parametric_part.step");
```

### Example 2: Gear Generator Module

```plaintext
module gear(teeth_count: int, module_size: float) {
    pitch_diameter = module_size * teeth_count;
    addendum = module_size;
    dedendum = 1.25 * module_size;
    // Gear profile calculations
    // ...
    gear_profile = // Generate gear profile geometry
    return gear_profile;
}

// Generate a Gear with Specific Parameters
my_gear = gear(teeth_count: 24, module_size: 2 mm);
export(my_gear, format: "STEP", filename: "gear.step");
```

---

## Documentation

Comprehensive documentation is available to help you get the most out of FabLang:

- **[Language Guide](docs/language_guide.md)**: Detailed explanation of syntax and language features.
- **[Standard Library Reference](docs/standard_library.md)**: Documentation of built-in functions and modules.
- **[Tutorials](docs/tutorials/)**: Step-by-step guides for creating various designs.
- **[API Documentation](docs/api.md)**: Information on extending FabLang through the API.

---

## Contributing

We welcome contributions from the community! To contribute:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes with clear messages.
4. Submit a pull request detailing your changes.

Please read our [Contributing Guidelines](CONTRIBUTING.md) for more information.

---

## License

FabLang is released under the [MIT License](LICENSE). You are free to use, modify, and distribute this software as per the terms of the license.

---
<!-- 
## Support

For questions, issues, or suggestions:

- **Issue Tracker**: [GitHub Issues](https://github.com/yourusername/fablang/issues)
- **Email**: support@fablang.org
- **Community Forum**: [FabLang Discussions](https://github.com/yourusername/fablang/discussions) -->

---

## Roadmap

- **Version 0.1**
  - Basic syntax implementation.
  - Core geometric primitives and operations.
  - Simple exporter for common CAD formats.

- **Version 0.2**
  - Enhanced error checking and optimization features.
  - Integration with additional CAD/CAM tools.
  - Expanded standard library.

- **Future Releases**
  - Advanced simulation and analysis capabilities.
  - Improved IDE features with real-time collaboration.
  - AI-assisted design suggestions and optimizations.

---

## Acknowledgments

- **Community Contributors**: Thank you to everyone who has contributed to FabLang's development.
- **Open-Source Libraries**: FabLang utilizes several open-source projects. See [ACKNOWLEDGMENTS.md](ACKNOWLEDGMENTS.md) for details.

---

*Empower your industrial design process with FabLang—where precision meets efficiency.*
