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
- `image_size` (optional): Choose your preferred image dimensions:
  - `square_hd` (default): High-definition square format
  - `square`: Standard square format
  - `portrait_4_3`: Portrait orientation with 4:3 aspect ratio
  - `portrait_16_9`: Portrait orientation with 16:9 aspect ratio
  - `landscape_4_3`: Landscape orientation with 4:3 aspect ratio
  - `landscape_16_9`: Landscape orientation with 16:9 aspect ratio

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
     -d '{
       "prompt": "[Your Character] chilling in the sun",
       "lora_id": "your-lora-id",
       "response_format": "url",
       "image_size": "square_hd"
     }'
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
        "response_format": "url",  # or "base64"
        "image_size": "square_hd"
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
    image_size: 'square_hd',
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
  "status": "success", // Request status
  "url": "https://api.craftengine.app/image/12345-image-id", // Public URL to access the image
  "image_id": "12345-image-id", // Unique identifier for the generated image
  "processing_time": "6.2" // Time taken to generate the image in seconds
}
```

### Base64 Response Format

```json
{
  "status": "success", // Request status
  "base64": "iVBORw0KGgoAAAANSUhEUgAA...", // Base64 encoded image data
  "image_id": "12345-image-id", // Unique identifier for the generated image
  "processing_time": "6.2" // Time taken to generate the image in seconds
}
```

## 💡 Tips

- Use detailed prompts for better results
- Choose between URL or base64 response format
- Images are publicly accessible via the returned URL
- Response time is typically 5-10 seconds

Need help? Just ping us on Telegram! 🎮
