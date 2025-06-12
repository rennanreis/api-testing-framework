# API Testing Framework

![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)
![Status: Portfolio](https://img.shields.io/badge/status-portfolio-blue)
![Last Update](https://img.shields.io/badge/last_update-June_2025-brightgreen)

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

| Resource    | Type        | Scenario Description                                  | Status |
|-------------|-------------|--------------------------------------------------------|--------|
| People      | Positive    | GET by valid ID (`/people/1`)                         | ✅     |
|             | Negative    | GET by invalid ID (`/people/9999`)                    | ✅     |
|             | Negative    | GET with invalid format (`/people/abc`)               | ✅     |
|             | Chaining    | GET homeworld by URL from person                      | ✅     |
|             | Chaining    | GET starship by URL from person                       | ✅     |
|             | Chaining    | GET species by URL from person                        | ✅     |
|             | Chaining    | GET person by character URL from film                 | ✅     |
| Planets     | Positive    | GET by valid ID (`/planets/1`)                        | ✅     |
|             | Negative    | GET by invalid ID (`/planets/9999`)                   | ✅     |
|             | Negative    | GET with invalid format (`/planets/null`)             | ✅     |
| Films       | Positive    | GET by valid ID (`/films/1`)                          | ✅     |
|             | Negative    | GET by invalid ID (`/films/9999`)                     | ✅     |
|             | Negative    | GET with invalid format (`/films/!@#`)                | ✅     |
| Starships   | Positive    | GET by valid ID (`/starships/9`)                      | ✅     |
|             | Negative    | GET by invalid ID (`/starships/9999`)                 | ✅     |
|             | Chaining    | GET starship by URL from person                       | ✅     |
| Vehicles    | Positive    | GET by valid ID (`/vehicles/4`)                       | ✅     |
|             | Negative    | GET by invalid ID (`/vehicles/9999`)                  | ✅     |
| Species     | Positive    | GET by valid ID (`/species/1`)                        | ✅     |
|             | Negative    | GET by invalid ID (`/species/9999`)                   | ✅     |
| Mock        | Positive    | POST new person (mock)                                | ✅     |
|             | Positive    | PUT update person (mock)                              | ✅     |
|             | Positive    | DELETE person (mock)                                  | ✅     |
|             | Educational | POST with invalid payload (mock)                      | ✅     |

---

## 🧠 Project Highlights

- Clean and modular Postman collection organized by resource
- Use of environments with dynamic variables for flexible configuration
- Coverage for happy path, invalid IDs, and malformed parameters
- Chaining of related resources using data from previous responses (people → starships, species, etc.)
- Simulation of POST, PUT, DELETE using mock services (JSONPlaceholder)
- Educational test covering acceptance of invalid input by public APIs
- Newman integration for CLI-based test execution
- HTML report generation with `newman-reporter-html`
- Test naming and commit history follow Conventional Commits

---

## 📌 Roadmap & Status

- ✅ Postman collection created and organized
- ✅ Test coverage for all primary SWAPI resources (`GET`)
- ✅ Negative tests for invalid IDs and malformed inputs
- ✅ Chaining between people, homeworlds, starships, species and film characters
- ✅ Simulated POST, PUT, DELETE requests (mock)
- ✅ Educational test for invalid payload
- ✅ Newman execution and HTML reporting in place
- ✅ README fully documented with project context
- 🔄 Final step: GitHub Actions CI/CD integration

---

## 🎯 About

This project was created as part of a self-study portfolio in API testing.  
It focuses on delivering **reliable**, **maintainable**, and **automatable** test coverage for RESTful APIs, mimicking real-world test automation practices in microservices architecture.

---

## 📝 License

MIT — feel free to explore and learn, but external contributions (PRs or issues) are not being accepted.
