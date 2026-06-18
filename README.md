# SIP Calculator with Long-Term Tax Adjustment

## Overview
This is a simple web application built using Python Flask to calculate the returns on a Systematic Investment Plan (SIP) in mutual funds, adjusted for long-term capital gains (LTCG) tax.

## Features
*   Calculates future value of SIP investments based on monthly contribution, expected annual return, and investment period.
*   Estimates gross returns and applies a simplified long-term capital gains tax calculation (currently set at 10%, representing Indian equity fund taxation beyond the annual exemption limit).
*   Displays key metrics including total invested, gross return, tax amount, net return after tax, and the final investment value post-tax.
*   Provides a basic, responsive web interface styled using Tailwind CSS via CDN.

## Technology Stack
*   **Backend:** Python Flask
*   **Frontend:** HTML, Tailwind CSS (via CDN)
*   **Calculation Logic:** Pure Python (using basic math and the standard SIP future value formula)

## Setup Instructions

### Prerequisites
*   Python 3.x installed on your system.

### Installation & Running Locally
1.  Clone this repository: `git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git`
2.  Navigate into the project directory: `cd YOUR_REPOSITORY_NAME`
3.  Install Flask: `pip install Flask`
4.  Run the application: `python app.py`
5.  Open your web browser and go to `http://127.0.0.1:5000`

## Calculation Details
*   The future value is calculated using the standard SIP formula:  
    `FV = P * [ ((1 + i)^n - 1) / i ] * (1 + i)`
    *   `P`: Monthly Investment
    *   `i`: Monthly Interest Rate (`Annual Return Rate / 12 / 100`)
    *   `n`: Number of Months (`Years * 12`)
*   Gross Return = Future Value (Gross) - Total Amount Invested
*   Taxable Gain = Gross Return (Assumes gain is taxable, simplified model ignoring annual exemption limits like Rs 1 Lakh in India)
*   Tax Amount = Taxable Gain * (LTCG Tax Rate / 100) (Currently hardcoded as 10%)
*   Net Return = Gross Return - Tax Amount
*   Final Value After Tax = Total Amount Invested + Net Return

## Notes
*   This is a simplified calculator for illustrative purposes. Real-world taxation and fund performance can be more complex (e.g., debt fund taxation varies with holding period, indexation benefits).
*   The tax rate is currently hardcoded within the Python function. It can be made dynamic or configurable as a user input in future enhancements.
*   The UI is basic and styled with Tailwind CSS for immediate visual improvement without extensive custom CSS.

## Files
*   `app.py`: Contains the Flask application logic, calculation function, and route definitions.
*   `templates/index.html`: Contains the HTML structure and Tailwind CSS classes for the web interface.