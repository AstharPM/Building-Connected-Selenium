BuildingConnected Automation with OTP Handling

This project automates the login and data extraction process from [BuildingConnected](https://app.buildingconnected.com) using **Selenium WebDriver**, **IMAP (Gmail)** for OTP retrieval, and **Requests** for authenticated API calls.

---

Features

- Automates login to BuildingConnected (supports Autodesk SSO).
- Dynamically retrieves and inputs OTP sent to Gmail.
- Navigates to a selected project and extracts data.
- Transfers authenticated session cookies to `requests` for backend API access.

---

How It Works

### 1. **Selenium Login Automation**

- Opens the login page using ChromeDriver.
- Submits email and password.
- Detects redirect to Autodesk login (if applicable).
- Waits for and inputs OTP code automatically.

### 2. **OTP Retrieval via Gmail IMAP**

- Connects securely to Gmail's IMAP server.
- Searches for the latest OTP email from `noreply@signin.autodesk.com`.
- Extracts the 6-digit OTP code using regex.

### 3. **Session Cookie Extraction**

- After login, Selenium captures cookies from the browser session.
- These cookies are passed into a `requests.Session()` object.

### 4. **Authenticated Data Access**

- Uses the `requests` library with cookies to make authenticated HTTP requests.
- Extracted data (like HTML content) is printed or saved.

---

## 🛠 Technologies Used

- `Selenium` – browser automation
- `imapclient` + `pyzmail` – email and OTP processing
- `requests` – HTTP requests with session persistence
- `re` – regex for OTP extraction
- `python-docx` or Markdown for documentation (optional)

---

## 📂 File Structure
