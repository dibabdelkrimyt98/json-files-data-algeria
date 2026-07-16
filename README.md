# json-files-data-algeria
Algerian Open Data Hub: JSON datasets on wilayas, communes, universities, academic programs, &amp; residences. Perfect for devs building location, education, or admin apps in Algeria. | Algérie : données JSON sur wilayas, communes, universités, filières, résidences. Idéal pour applications géolocalisées, éducatives ou administratives.
___________________

# 🇩🇿 Algerian Open Data Hub
### Comprehensive JSON Datasets for Algeria's Administrative & Educational Systems

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![JSON](https://img.shields.io/badge/Data-JSON-blue.svg)](https://www.json.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Made in Algeria](https://img.shields.io/badge/Made_in-Algeria-green.svg)](https://github.com/)

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Datasets](#-datasets)
- [Installation & Usage](#-installation--usage)
- [Data Structure](#-data-structure)
- [Use Cases](#-use-cases)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🌟 Overview

This repository serves as a comprehensive, open‑source data hub for developers, researchers, and organizations working with Algerian administrative, educational, and geographic data. All datasets are curated from official sources and structured in JSON format for easy integration into modern applications.

### 🎯 Key Features
- ✅ **58 Wilayas** (Provinces) with coordinates and Arabic names
- ✅ **1,700+ Communes** with postal codes and geographic coordinates
- ✅ **50+ Universities** and Higher Education Institutions
- ✅ **100+ Academic Programs** organized by domain
- ✅ **University Residences** with locations and capacities
- ✅ **Bilingual** (Arabic/French/English) data support

---

## 📦 Datasets

### 1. **Wilayas** (`wilayas.json`)
Complete list of Algerian provinces with administrative codes, names, and geographic coordinates.

```json
{
  "id": "16",
  "code": "16",
  "name": "Alger",
  "ar_name": "الجزائر",
  "longitude": "36.7538259",
  "latitude": "3.057841"
}
```

### 2. **Communes** (`communes.json`)
Detailed municipality data including postal codes, Arabic names, and precise coordinates.

```json
{
  "id": "554",
  "post_code": "16001",
  "name": "Alger Centre",
  "wilaya_id": "16",
  "ar_name": "الجزائر الوسطى",
  "longitude": "36.7681618",
  "latitude": "3.0404258"
}
```

### 3. **Universities** (`universites.json`)
Comprehensive listing of higher education institutions including universities, university centers, and national schools.

```json

{
  "الجامعات": [
    {
      "الاسم": "جامعة العلوم والتكنولوجيا هواري بومدين (USTHB)",
      "الولاية": "الجزائر"
    }
  ],
  "المراكز_الجامعية": [...],
  "المدارس_الوطنية_العليا": [...]
}
```

### 4. **Academic Programs** (`filieres.json`)
Structured list of university programs organized by academic domains with codes.
```json

{
  "domains": [
    {
      "code": "A00",
      "nom": "علوم وتكنولوجيا",
      "filieres": ["علوم وتكنولوجيا", "تعدين", "محروقات", ...]
    }
  ]
}

```
### 5.  **University Residences** (`residences_univ.json`)
Detailed information about university housing managed by the National Office of University Works.

```json

{
  "directions_oeuvres_universitaires": [
    {
      "nom_direction": "البليدة",
      "wilaya": {
        "id": "09",
        "nom": "البليدة"
      },
      "residences_universitaires": [
        { "nom": "الإقامة الجامعية الصومعة 01" }
      ]
    }
  ]
}

```


## 🚀 Installation & Usage
### Installation


```
git clone https://github.com/username/algerian-open-data.git
cd algerian-open-data
```

### Basic Usage in Python
```
import json

# Load wilaya data
with open('wilayas.json', 'r', encoding='utf-8') as f:
    wilayas = json.load(f)

# Find a specific wilaya
alger = next(w for w in wilayas if w['name'] == 'Alger')
print(f"Alger coordinates: {alger['longitude']}, {alger['latitude']}")

# Load communes
with open('communes.json', 'r', encoding='utf-8') as f:
    communes = json.load(f)

# Get all communes in Algiers
algiers_communes = [c for c in communes if c['wilaya_id'] == '16']
```

### Usage in JavaScript

```
const fs = require('fs');

// Load data
const wilayas = JSON.parse(fs.readFileSync('wilayas.json', 'utf8'));
const communes = JSON.parse(fs.readFileSync('communes.json', 'utf8'));

// Find commune by postal code
const commune = communes.find(c => c.post_code === '16001');
console.log(`Commune: ${commune.name} (${commune.ar_name})`);

```

## 📊 Data Structure

### Geographic Data
  Coordinate System: WGS84 (EPSG:4326)

  Format: Decimal degrees (DD)

  Accuracy: 6 decimal places (~11.1 cm precision)

### Administrative Hierarchy 

```
Wilaya (Province)
    └── Commune (Municipality)
        └── Postal Codes
```

### Education System Structure

```
Higher Education
    ├── Universities
    ├── University Centers
    ├── National Schools
    └── Research Institutions
        └── Academic Domains (A00 - P00)
            └── Programs/Filieres
```

## 💡 Use Cases

### 1. Geolocation Services

    Build location‑based apps for Algerian cities

    Implement address autocomplete systems

    Create interactive maps of Algeria

### 2. Educational Platforms

    University search and comparison tools

    Program finder applications

    Student housing locator

### 3. Administrative Systems

    E‑government services

    Postal code validation

    Population and demographic studies

### 4. Research & Analysis

    Academic research on Algerian education

    Urban planning studies

    Statistical analysis of educational distribution

## 🤝 Contributing

We welcome contributions! Here's how you can help : 

    Fork the repository

    Create a feature branch (git checkout -b feature/amazing-feature)

    Commit your changes (git commit -m 'Add some amazing feature')

    Push to the branch (git push origin feature/amazing-feature)

    Open a Pull Request

### Contribution Guidelines
Ensure JSON validity using tools like jsonlint

Maintain consistent formatting (2 spaces indentation)

Update documentation for any data changes

Respect the bilingual structure (Arabic/French/English)

### 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

### 🙏 Acknowledgments

Ministry of Interior, Local Authorities and Territorial Planning

Ministry of Higher Education and Scientific Research

National Office of University Works (ONOU)

National Institute of Cartography and Remote Sensing


### 📞 Contact & Support

    WhatsApp: +213557013804

    Email: dibabdelkrimyt98@gmail.com


### 🔄 Roadmap

    Add more educational institutions
    
    Include historical and cultural sites
    
    Add population data per commune
    
    Create a REST API wrapper
    
    Add data visualization tools
    
    Include transportation network data
    
    Add economic and commercial data

### ⭐ Star the Repository

If you find this data useful, please consider starring the repository to help others discover it!

## GitHub Topics

algeria, data, json, open-data, api, wilayas, communes, universities, education, algerian-cities, postal-codes, geolocation, students, academic-programs, higher-education, algeria-data, algeria-json, algeria-api, arabe, français, english, geographic-data, administrative-divisions, university-residences, filieres, education-algeria
