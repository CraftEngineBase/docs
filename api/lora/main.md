# 🎨 Lora API

Welcome to our Lora image generation API!
Let's get you started with creating amazing images and your own LoRAs.

## 🚀 Getting Started

To start generating images right away. You'll need:

- Your API key
- The Lora ID

Both will be handed to you by the CraftEngine team.

## 🎯 Request Format

Before generating images, understand the available options:

- `prompt` (required): Your text description for the image
- `lora_id` (required): The unique identifier for your LoRA model
- `response_format` (required): Choose between:
  - `url`: Returns a public URL to access your image
  - `base64`: Returns the image data directly, keeping it private within your system

### 🖥️ Generate an Image

Here's how to generate an image in different languages:

### API URL

```bash
https://api.craftengine.app/image/create/lora
```

#### Using cURL

```bash
curl -X POST "https://api.craftengine.app/image/create/lora" \
-H "X-API-Key: your-api-key" \
-H "Content-Type: application/json" \
-d '{"prompt": "[Your Character] chilling in the sun", "lora_id": "your-lora-id", "response_format": "url"}'
```

### 🐍 Python

```python
import requests

response = requests.post(
    "https://api.craftengine.app/image/create/lora",
    headers={
        "X-API-Key": "your-api-key",
        "Content-Type": "application/json"
    },
    json={
        "prompt": "[Your Character] chilling in the sun",
        "lora_id": "your-lora-id",
        "response_format": "url"  # or "base64"
    }
)

print(response.json())
```

### 🟨 JavaScript

```javascript
fetch('https://api.craftengine.app/image/create/lora', {
  method: 'POST',
  headers: {
    'X-API-Key': 'your-api-key',
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    prompt: '[Your Character] chilling in the sun',
    lora_id: 'your-lora-id',
    response_format: 'url', // or "base64"
  }),
})
  .then((res) => res.json())
  .then((data) => console.log(data));
```

## 📝 Response Format

Depending on your chosen `response_format`, you'll receive one of these responses:

### URL Response Format

```json
{
  "status": "success",
  "url": "https://api.craftengine.app/image/12345-image-id",
  "image_id": "12345-image-id",
  "processing_time": "6.2"
}
```

### Base64 Response Format

```json
{
  "status": "success",
  "base64": "iVBORw0KGgoAAAANSUhEUgAA...",
  "image_id": "12345-image-id",
  "processing_time": "6.2"
}
```

## 💡 Tips

- Use detailed prompts for better results
- Choose between URL or base64 response format
- Images are publicly accessible via the returned URL
- Response time is typically 5-10 seconds

Need help? Just ping us on Telegram! 🎮
