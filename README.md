This repository contains automation tests for Magento Application using Cypress and Cucumber. The tests are designed to ensure the proper functionality and stability of a Magento  e-commerce platform through behavior-driven development (BDD).
Prerequisites
Before we begin, make sure we have the following installed on your machine:

Node.js (>=12.x) and npm (Node Package Manager)
Cypress (for automation testing)
Cucumber (for BDD-style tests)
Git (for version control)
Installation
Follow these steps to set up the project locally:

Clone the repository:

bash
Copy code
git clone https://github.com/Josephjohn1994/Cypress-cucumber-magento-2.git
cd Cypress-cucumber-magento-2
Install dependencies: Once you're inside the project directory, install the required dependencies using npm:

bash
Copy code
npm install
Configuration
You may need to configure certain settings before running the tests.

Magento 2 Configuration: Make sure your Magento 2 instance is up and running. You’ll need access to the testing environment, which can be a local or remote instance.

Environment Variables: You may need to configure environment variables for credentials, URLs, or other settings. You can create a .env file and add relevant information such as:

makefile
Copy code
MAGENTO_URL=http://your-magento-site.com
USERNAME=yourUsername
PASSWORD=yourPassword
Cypress Configuration: Configure Cypress by editing cypress.json and set your base URL and other relevant options.

Example cypress.json:

json
Copy code
{
  "baseUrl": "http://your-magento-site.com",
  "viewportWidth": 1000,
  "viewportHeight": 660
}
Running Tests
1. Run tests with Cucumber:
To run the tests using Cypress with Cucumber, execute the following command:

bash
Copy code
npx cypress open
This will open the Cypress test runner. You can select and run the tests from the Cypress interface.

2. Run tests in Headless Mode:
If you want to run the tests in headless mode (without the GUI), use the following command:

bash
Copy code
npx cypress run
This will run all the tests in headless mode and output the results in the terminal.

Test Structure
The test cases are written using Cucumber syntax (Gherkin) and are located in the following structure:

kotlin
Copy code
cypress/
├── integration/
│   └── tests/
│       ├── login.feature
│       └── checkout.feature
├── support/
│   ├── commands.js
│   ├── index.js
└── fixtures/
    └── data.json
Feature Files
Feature files contain the BDD test scenarios in .feature format using the Gherkin syntax. Example:

gherkin
Copy code
Feature: User Login

  Scenario: Valid user login
    Given I open the login page
    When I enter valid credentials
    Then I should see the user dashboard
Step Definitions
Step definitions match the steps in the feature files and define the automation actions to take. The step definitions are located in cypress/support/step_definitions.

Cypress Commands
Custom Cypress commands can be added in cypress/support/commands.js. These are reusable actions that can be called in any test file.

Reporting
Once tests are executed, you can view the detailed reports and logs in the Cypress Dashboard or output files (depending on the configuration).

Troubleshooting
If you face any issues while running the tests:

Check your Magento environment: Ensure the Magento 2 site is accessible and all services are running.
Review the Cypress console: Errors or issues will be logged in the Cypress test runner console.
Check feature and step definitions: Ensure your .feature files and step definitions are correctly implemented.
