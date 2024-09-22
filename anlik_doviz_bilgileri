#Anlık döviz bilgilerine Gemini uzerinde ulaşım

import requests
from vertexai.generative_models import (
    Content,
    FunctionDeclaration,
    GenerativeModel,
    Part,
    Tool,
)

model = GenerativeModel("gemini-1.5-flash-001")

get_exchange_rate_func = FunctionDeclaration(
    name="get_exchange_rate",
    description="Güncel döviz kur değerlerini öğrenmek",
    parameters={
    "type": "object",
    "properties": {
        "currency_date": {
            "type": "string",
            "description": "Tarih mutlaka şu formatta olmalı YYYY-AA-GG yoksa en güncel tarih belirlenir"
        },
        "currency_from": {
            "type": "string",
            "description": "ISO 4217 formatında döviz kuru çevrilecek "
        },
        "currency_to": {
            "type": "string",
            "description": "ISO 4217 formatında döviz kuru değeri istenen"
        }
    },
         "required": [
            "currency_from",
            "currency_date",
      ]
  },
)

exchange_rate_tool = Tool(
    function_declarations=[get_exchange_rate_func],
)

prompt = """2024-09-21 tarihli 1 USD tutarının Türk Lirası karşılığı ne kadardır acaba? 50 USD kaç Türk lirası yapar?"""

response = model.generate_content(
    prompt,
    tools=[exchange_rate_tool],
)

response.candidates[0].content

params = {}
for key, value in response.candidates[0].content.parts[0].function_call.args.items():
    params[key[9:]] = value
params

import requests
url = f"https://api.frankfurter.app/{params['date']}"
api_response = requests.get(url, params=params)
api_response.text

response = model.generate_content(
    [
    Content(role="user", parts=[
        Part.from_text(prompt + """ adım adım detaylı bir şekilde ve döviz kuru ve tarih bilgisi de dahil ederek cevap veriri misin"""),
    ]),
    Content(role="function", parts=[
        Part.from_dict({
            "function_call": {
                "name": "get_exchange_rate",
            }
        })
    ]),
    Content(role="function", parts=[
        Part.from_function_response(
            name="get_exchange_rate",
            response={
                "content": api_response.text,
            }
        )
    ]),
    ],
    tools=[exchange_rate_tool],
)


response.candidates[0].content.parts[0].text
