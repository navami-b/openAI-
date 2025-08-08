from openai import OpenAI
import os

# Initialize client with API key from environment
client = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Send the prompt to GPT-3.5 Turbo
response = client.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain how rainbows are formed"}
    ],
    max_tokens=200
)

# Print the AI's reply
print("GPT-3.5 Turbo Response:\n")
print(response.choices[0].message.content)
