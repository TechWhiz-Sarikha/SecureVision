# SecureVision

**SecureVision** is an advanced web application vulnerability scanning and reporting tool. It identifies and reports security flaws in real-time using AI-powered Scrape Scan.

## Features

- **Real-Time Vulnerability Scanning**: Quickly scans web applications for security flaws.
- **Scrape Scan with AI**: Uses web scraping and generative AI to fetch the latest vulnerabilities.
- **Downloadable Reports**: Export scan results in JSON format.
- **Historical Scan Tracking**: Keeps track of past scans.
- **Dashboard Overview**: Provides a centralized view of scanning activities.

## Technology Stack

- **Frontend**: HTML, CSS, Bootstrap, JavaScript
- **Backend**: Java (JSP, Servlets, GlassFish Server)
- **Database**: Apache Derby
- **AI Integration**: OpenAI API, LangChain, FAISS
- **API Integrations**: Google Search API (via SerpAPI)

## Installation & Setup

### Prerequisites
- Java 8+
- Apache Derby Database
- GlassFish Server
- Python (for web scraping)
- Maven (for dependencies)

### Steps to Run
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/SecureVision.git
   cd SecureVision

2. Set up the database:
  cd database
  java -jar derby.jar start
3. Deploy on GlassFish:
  mvn clean install
  mvn package
4. Start the application:
  mvn jetty:run
5. Open your browser and visit:
  http://localhost:8080/SecureVision

## Usage
1.Register/Login to SecureVision.
2.Initiate a Vulnerability Scan by entering a target URL.
3.View Reports and track security over time.
4.Download JSON Reports for further analysis.

## Contributing
We welcome contributions! Follow these steps:
1.Fork the repository.
2.Create a new branch: git checkout -b feature-branch
3.Commit your changes: git commit -m "Added feature"
4.Push to your fork: git push origin feature-branch
5.Create a Pull Request.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

### **3. `.gitignore`**
Excludes unnecessary files.

/target/ /.derby_db/ /*.log *.class *.jar *.war *.zip *.iml *.DS_Store *.vscode/ *.idea/ node_modules/

### **4. `LICENSE` (MIT License)**

```markdown
MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy of this software...

**5. GitHub Actions (ci.yml)**

Automate builds and tests on push.

name: Java CI/CD Pipeline

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v3

      - name: Setup Java
        uses: actions/setup-java@v3
        with:
          distribution: 'temurin'
          java-version: '17'

      - name: Build with Maven
        run: mvn clean install

      - name: Run Tests
        run: mvn test
