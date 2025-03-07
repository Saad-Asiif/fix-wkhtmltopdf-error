# Fixing the "Invalid wkhtmltopdf version" Error

This guide provides step-by-step instructions to resolve the **"Invalid wkhtmltopdf version"** error, commonly encountered in Frappe/ERPNext applications. Follow the steps below to install the correct version of `wkhtmltopdf` and ensure proper functionality.

---

## Steps to Fix the Error

### 1. Download the Correct Version of wkhtmltopdf
Download the required version (`0.12.6` with patched QT) using the following command:

```bash
wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox_0.12.6-1.focal_amd64.deb
```

### 2. Install the Downloaded Package
Install the downloaded .deb package using the following command:

```bash
sudo apt install ./wkhtmltox_0.12.6-1.focal_amd64.deb
```

### 3. Fix Dependency Issues (If Any)
If you encounter dependency issues during installation, run the following command to fix them:

```bash
sudo apt --fix-broken install
```

Then, reinstall the package:

```bash
sudo apt install ./wkhtmltox_0.12.6-1.focal_amd64.deb
```

### 4. Verify the Installation
Check the installed version of wkhtmltopdf to ensure it is correct:

```bash
wkhtmltopdf --version
```

The output should be:

```bash
wkhtmltopdf 0.12.6 (with patched qt)
```

### 5. Restart Frappe/ERPNext Services
Restart all services to apply the changes:

```bash
sudo supervisorctl restart all
```

### 6. Test PDF Generation
Go to your Print Format in Frappe/ERPNext and try generating a PDF. The "Invalid wkhtmltopdf version" error should no longer appear.
