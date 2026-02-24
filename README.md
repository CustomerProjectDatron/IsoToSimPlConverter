# ISO to SimPL Converter

A web-based application for converting ISO G-Code files to SimPL (Simple Programming Language) format for CNC machines.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Browser Support](https://img.shields.io/badge/browsers-Chrome%20%7C%20Firefox%20%7C%20Edge%20%7C%20Safari-brightgreen.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)

## 📋 Overview

The ISO to SimPL Converter is designed for CNC programmers and machine operators who need to convert between different G-Code formats. It provides a user-friendly interface for transforming ISO G-Code files into the simplified SimPL programming language used by DATRON machines.

## ✨ Features

### 🎯 Core Functionality

- **Drag & Drop Interface**: Simply drag ISO files (.iso, .g, .gcode, .txt) onto the application
- **Traditional File Browser**: Click to browse and select files
- **Real-time Conversion**: Automatic conversion from ISO G-Code to SimPL
- **Side-by-side View**: Compare original and converted code simultaneously
- **Syntax Highlighting**: Color-coded syntax for both G-Code and SimPL formats

### 📥 File Support

- Supports multiple file extensions: `.iso`, `.g`, `.gcode`, `.txt`
- Handles text files containing ISO G-Code content
- Preserves original comments and structure

### 💾 Export Options

- **Download**: Export converted files with `.simpl` extension
- **Copy to Clipboard**: Quick copying of converted code
- **Filename Preservation**: Maintains original filename with new extension

## 🛠️ Supported G-Code Commands

### Movement Commands

| ISO G-Code | SimPL Equivalent | Description                           |
| ---------- | ---------------- | ------------------------------------- |
| G0/G1      | MoveLin          | Rapid/Linear movement with parameters |
| G2/G3      | MoveCirc         | Circular interpolation (CW/CCW)       |

## 🚀 Getting Started

### Prerequisites

- Modern web browser (Chrome, Firefox, Edge, Safari)
- No installation required - runs entirely in the browser
- No internet connection needed after initial load

### Usage

1. **Open the Application**: Open `IsoToSimPlConverter.html` in your web browser
2. **Load ISO File**:
   - Drag and drop your ISO G-Code file onto the designated area, or
   - Click the upload area to browse and select a file
3. **View Results**: The converted SimPL code appears in the right panel
4. **Export**:
   - Use the download button to save the converted file
   - Use the copy button to copy code to clipboard

## 🔒 Security & Privacy

- **Client-side Processing**: All conversion happens in your browser
- **No Data Transmission**: Files never leave your computer
- **No Data Storage**: No user data is stored or logged

## 📝 License

This project is licensed under the MIT License - see the project documentation for details.

## 📞 Support

For technical support or questions about SimPL programming, please refer to the DATRON documentation or contact your local DATRON representative.

---

_Created: February 24, 2026_  
_Version: 1.0_  
_Compatible with DATRON SimPL format_
