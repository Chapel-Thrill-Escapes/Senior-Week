# Senior Week Project

## Overview
This project is designed to automate the process of gathering email addresses, phone numbers, and majors of UNC Chapel Hill's Spring 24 Graduating Seniors for Chapel Thrill Escapes, a student-run escape room experience. The script performs web scraping to collect the required information and then sends personalized emails to the gathered contacts, inviting them to participate in a Senior Week event hosted by Chapel Thrill Escapes.

## Prerequisites
To run this script, you will need R installed on your computer along with RStudio or another R IDE of your choice. Ensure you have internet access for web scraping and email sending functionalities.

## Dependencies
The script requires the installation of several R packages:
- `dplyr`
- `tidyverse`
- `rvest`
- `RSelenium`
- `wdman`
- `netstat`
- `xml2`
- `webdriver`
- `purrr`
- `readr`
- `usethis`
- `dotenv`
- `here`
- `gmailr`
- `gptstudio`

The script automatically checks for and installs any missing packages.

## Setup Instructions
1. **Clone or Download the Script**: Clone this repository or download the R script to your local machine.

2. **Selenium & WebDriver Setup**: Ensure you have Docker installed or download the Selenium Standalone Server and WebDriver (e.g., ChromeDriver or geckodriver) compatible with your browser version.

3. **Environment Setup**:
   - Place the `GmailCredentials.json` file in the project root directory.
   - Ensure the `.secret` folder exists in the project root for storing OAuth cache.

4. **Data Preparation**:
   - Prepare a CSV file named `Spring 24 Grad Senior.csv` with at least the columns `PID`, `Name.First`, and `Emails` populated. Place this file in a `data` directory within the project root.

5. **Run the Script**: Open the R script in RStudio or your preferred IDE and execute it.

## Script Execution
The script is divided into several sections:
- **Setup**: Loads required libraries and sets the working directory.
- **Emails Collection**: If set to TRUE, the script scrapes the UNC directory for emails, phone numbers, and majors of the graduating seniors. This part uses RSelenium for web navigation and rvest for HTML content parsing.
- **Email Sending**: Authenticates with Gmail using `gmailr` and sends personalized emails to the collected addresses. It includes a check to ensure the Gmail sending limit is not exceeded.

## Important Notes
- **Selenium Server**: Ensure the Selenium Server is running before executing the script.
- **Email Limits**: Gmail has strict limits on the number of emails that can be sent in a day. The script includes a function to check for these limits to prevent account suspension.
- **Personalization**: Customize the email content, subject, and attachments as needed.

## Troubleshooting
- **Selenium Connection Issues**: Ensure the correct version of WebDriver is installed and compatible with your browser version.
- **Gmail Authentication**: Follow the `gmailr` setup instructions carefully to ensure successful authentication.
- **Data File Format**: Verify the CSV file format and column names match the script's expectations.

## Contact
For any issues or questions, please contact Chapel Thrill Escapes at `admin@chapelthrillescapes.com`.
