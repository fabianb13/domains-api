# ipChecker
To facilitate running a home web server behind a router, this program checks to see if external IP has changed, alerts user via email, and automates editing forwarding rules on domains.google.com.

### Installation:
(Currently set up for Windows/Firefox, with my own Gmail address - change `GMAIL_USER` constant in `ipchecker.pyw` and allow less secure apps on your Google account to use.)

Install requirements:
`pip install -r requirements.txt`

Download `geckodriver.exe` (Webdriver for Firefox) from https://github.com/mozilla/geckodriver/releases and add location to PATH.

Use the `start.bat` file to start the program. A script is then automatically added to startup folder and the program will run on user login.

On first run, you will be asked to input your password which will then be encoded with base64 before being saved. If the IP needs to be changed a geckodriver console window will open and close automatically a few moments later when the process is finished. The initial console window that ran the program can be closed and the program will continue to run in the background (as a pythonw.exe process). It checks the IP every 6 hours while running and logs to `ipchecker.log`. Check this file if the program does not run as expected, or to see when the IP was last checked.

### Coming:
I will probably make a simpler version of this, which updates via the domains.google api, but it was fun to do it the Selenium way first!
