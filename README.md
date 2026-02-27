# bot
yfinace
twilio
pandas
name: Daily Stock Monitor
on:
schedule:
- cron: '0 14 * * 1-5' # Runs at 2:00 PM UTC (9:00 AM EST) Mon-Fri
workflow_dispatch: # Allows you to run it manually for testing

jobs:
build:
runs-on: ubuntu-latest
steps:
- name: Checkout code
uses: actions/checkout@v2
- name: Set up Python
uses: actions/setup-python@v2
with:
python-version: '3.9'
- name: Install dependencies
run: pip install -r requirements.txt
- name: Run bot
run: python bot.py
