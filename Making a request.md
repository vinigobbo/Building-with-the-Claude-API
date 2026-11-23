```python
from dotenv import load_dotenv
load_dotenv()

from anthropic import Anthropic

client = Anthropic()
model = "claude-opus-5-5"
```
```bash
%pip install "anthropic<1" python-dotenv
```

```bash
ANTHROPIC_API_KEY="your_api_key"
```