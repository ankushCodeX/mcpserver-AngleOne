# Angel One MCP (Model Context Protocol)

This repository contains the Model Context Protocol implementation for Angel One trading platform, allowing you to interact with Angel One's trading APIs to get history data and get portfolio data.

## Prerequisites

- Python 3.10
- Angel One trading account
- API credentials from Angel One

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/angelone-mcp.git
cd angelone-mcp
git submodule update --init --recursive
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

3. Install the required dependencies:
**Linux/Mac**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
**Windows**:
```powershell
irm https://astral.sh/uv/install.ps1 | iex
```
```bash
uv pip install -r requirements.txt
```

## Configuration

1. Inside api.py file hardcode following parameters with your Angel One credentials:
```python
# test_credentials.py
API_KEY = "your_api_key"
CLIENT_CODE = "your_client_code"
PASSWORD = "PIN"
TOKEN = "your_token"  # Visit https://smartapi.angelbroking.com/enable-totp (copy the code/token below QR)
```

## Usage

1. You can start `api.py` as an mcp server to your mcp client:
2. If using Anthropic Desktop configuration update cloud_desktop_config.json. Local configuration file path can be found under settings > Developer > Edit Settings
3. If using Cline update MCP servers>Installed>configure MCP Servers and update cline_mcp_settings.json
```json
{
    "mcpServers": {
      "angleone": {
        "command": "C:/Users/<user>/.local/bin/uv",
        "args": [
          "--directory",
          "<local-project-path>/mcpserver-AngelOne/",
          "run",
          "api.py"
        ]
      }
    }
  }
```
