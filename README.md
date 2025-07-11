# 🔍 PhantomPHP - PHP Malware 

## 📌 Why Use PhantomPHP?
* Detects malicious code patterns in PHP files
* Identifies dangerous functions (`exec`, `system`, `passthru`)
* Finds file inclusion vulnerabilities (LFI/RFI)
* Scans entire directories recursively
* Provides clear JSON output for analysis
* Lightweight and easy to integrate

---
## 🛠 Usage
# Scan directory
node index.js -d /path/to/php/files

# Save results to file
node index.js -d /path/to/files -o results.json

# Show help
node index.js --help

---

## 📝 Sample Output
    {
      "file": "upload.php",
      "issues": [
    {
      "type": "command_injection",
      "match": "exec($_GET['cmd'])",
      "line": 15,
      "severity": "high"
    }
    ]
    }

---

## 🏷 Detection Patterns

        Type        	          Example Pattern
    Base64 Decode	      eval(base64_decode("PD9waHA..."));
    Command Injection	  system($_POST['command']);
    File Inclusion	    include($_GET['page'] . '.php');

---
### 📜 License
    MIT © Mangala-Manmatharaja


## 🧰 Installation
```bash
# Clone repository
git clone https://github.com/yourusername/PhantomPHP.git
cd PhantomPHP

# Install dependencies
npm install
