Code snippet in Python of the Nebula API for chat completions.
```python
import requests
def chat_with_model():
    url = 'https://nebula.cs.vu.nl/api/chat/completions'
    headers = {
        'Authorization': f'Bearer <YOUR_TOKEN_HERE>',
        'Content-Type': 'application/json'
    }
    data = {
        "model": 'deepseek-r1:8b',
        "messages": [
            {
                "role": "system",
                "content": "You are a helpful assistant."
            },
            {
                "role": "user",
                "content": "Hello, how are you?"
            }
        ]
    }
    response = requests.post(url, headers=headers, json=data)
    return response.json()['choices'][0]['message']['content']
    ```