# FRED Economic Dashboard with OpenAI Real‑Time Analysis

This notebook fetches key U.S. economic indicators from the **St. Louis Fed FRED** database and asks **OpenAI GPT‑4o** to generate concise, real‑time commentary for each chart.

## 1  Installation
Run this once in a terminal (not in the notebook) if the libraries are missing:
```bash
pip install fredapi pandas matplotlib openai python-dotenv
```
NOTE: If you have uv installed (recommended), the you'll need to use:
```bash
uv pip install fredapi pandas matplotlib openai python-dotenv
```

## 2  Obtain API Keys
### 2.1  FRED API Key
1. Create or sign in to your account at <https://fred.stlouisfed.org>.
2. Go to **My Account → API Keys**.
3. Click **Generate** (or copy your existing key).

### 2.2  OpenAI API Key
1. Sign in to your OpenAI account and open <https://platform.openai.com/account/api-keys>.
2. Click **Create new secret key** and copy it immediately — you won't see it again.

## 3  Set Environment Variables
### 3.1  Temporary (per terminal session)
**Command Prompt**
```cmd
set FRED_API_KEY=your-fred-key
set OPENAI_API_KEY=your-openai-key
```
**PowerShell**
```powershell
$env:FRED_API_KEY="your-fred-key"
$env:OPENAI_API_KEY="your-openai-key"
```

### 3.2  Permanent (System Settings)
1. Search *Environment Variables* → **Edit the system environment variables**.
2. Click **Environment Variables…** → under *User variables* click **New…** and add
   `FRED_API_KEY` and `OPENAI_API_KEY`.

### 3.3  Project‑Local `.env` File *(recommended for notebooks)*
Create a file named `.env` in the same folder as this notebook:
```text
FRED_API_KEY=your-fred-key
OPENAI_API_KEY=your-openai-key
```
The next cell loads these automatically via **python‑dotenv**.
