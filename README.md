# API Testing Framework

![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)
![Status: Portfolio](https://img.shields.io/badge/status-portfolio-blue)
![Last Update](https://img.shields.io/badge/last%20update-May%202025-brightgreen)

> ⚠️ This project is part of a personal portfolio and is not open to external contributions (pull requests or issues) at this time.

An API test automation project for the [Star Wars API (SWAPI)](https://swapi.py4e.com/), using **Postman** for test design and **Newman** for CLI execution and reporting.

This project simulates a professional API test strategy, including environment management, reusable request structure, and HTML reports for analysis and presentation.

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/rennanreis/api-testing-framework.git
cd api-testing-framework

# Install Newman and the HTML reporter
npm install -g newman newman-reporter-html

# Run the collection and generate an HTML report
newman run postman/swapi_collection.json \
  --environment postman/local_swapi_environment.json \
  --reporters cli,html \
  --reporter-html-export reports/api-test-report.html
```

---

## 📂 Project Structure

```
api-testing-framework/
├── postman/
│   ├── swapi_collection.json               # Postman collection
│   └── local_swapi_environment.json       # Postman environment (SWAPI mirror)
├── reports/
│   └── api-test-report.html               # Generated HTML test report
└── README.md                              # Documentation
```

---

## ✅ Test Scenarios

| Endpoint                     | Method | Description             | Status |
|-----------------------------|--------|-------------------------|--------|
| `/people/{{personId}}`      | GET    | Fetch person by ID      | ✅     |

> Additional endpoints (planets, films, vehicles) can be added as the project evolves.

---

## 🧠 Project Highlights

- Clean and structured Postman collection
- Use of environments to support flexible configuration
- Newman integration for automated CLI execution
- HTML report generation with `newman-reporter-html`
- Manual override of headers to bypass API restrictions
- Versioned and commit-organized using Conventional Commits
- Optimized for clarity in QA portfolios and technical articles

---

## 📌 Roadmap & Status

- ✅ Collection created and tested in Postman  
- ✅ Environment configuration standardized  
- ✅ CLI execution with Newman working  
- ✅ HTML reports exported and versioned  
- 🔄 Next: add coverage for additional endpoints (planets, films, etc)  
- 🔄 Optional: integrate with CI tools (e.g., GitHub Actions)

---

## 🎯 About

This project was created as part of a self-study portfolio in API testing.  
It focuses on delivering reliable, maintainable, and automatable test coverage for RESTful APIs, mimicking real-world test automation practices in microservices architecture.

---

## 📝 License

MIT — feel free to explore and learn, but external contributions (PRs or issues) are not being accepted.
