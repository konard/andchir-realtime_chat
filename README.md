# realtime_chat
Live chat on Python

## Installation

Install dependencies:
~~~
pip install -r requirements.txt
~~~

## Run server

~~~
python main.py
~~~

## Send message via console client

~~~
python main.py --client aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb
python main.py --client bbbbbbbb-bbbb-bbbb-bbbb-bbbbbbbbbbbb aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa
~~~

## Send message via HTTP API

You can send messages via HTTP POST request to `/api/send-message`:

~~~bash
curl -X POST http://localhost:8000/api/send-message \
  -H "Content-Type: application/json" \
  -d '{
    "recipientUuid": "aaaaaaaa-aaaa-aaaa-aaaa-aaaaaaaaaaaa",
    "messageText": "Привет! Это сообщение отправлено через curl!",
    "senderName": "System"
  }'
~~~

**Note:** The recipient must be connected and registered with their UUID for the message to be delivered.

