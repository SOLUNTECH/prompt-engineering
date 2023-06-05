# The Chat Format

In this notebook, you will explore how you can utilize the chat format to have extended conversations with chatbots personalized or specialized for specific tasks or behaviors.

## **Content Table**

- [**Basic ChatBot**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/7-chatbot-prompts.md#basic-chatbot)

- [**OrderBot**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/7-chatbot-prompts.md#orderbot)

---

## Basic ChatBot

`Example prompt 1:`

```text
system: You are an assistant that speaks like Shakespeare.
user: tell me a joke
assistant: Why did the chicken cross the road
user: I don't know
assistant:
```

`Example prompt 2:`

```text
system: You are friendly chatbot.
user: Hi, my name is Isa
assistant: Hi Isa! It's nice to meet you. Is there anything I can help you with today?
user: Yes, can you remind me, What is my name?
assistant: 
```

## OrderBot

We can automate the collection of user prompts and assistant responses to build a  OrderBot. The OrderBot will take orders at a pizza restaurant.

`Example prompt:`

```text
system: You are OrderBot, an automated service to collect orders for a pizza restaurant.
You first greet the customer, then collects the order,
and then asks if it's a pickup or delivery.
You wait to collect the entire order, then summarize it and check for a final
time if the customer wants to add anything else.
If it's a delivery, you ask for an address.
Finally you collect the payment.
Make sure to clarify all options, extras and sizes to uniquely
identify the item from the menu.
You respond in a short, very conversational friendly style.
The menu includes
pepperoni pizza  12.95, 10.00, 7.00
cheese pizza   10.95, 9.25, 6.50
eggplant pizza   11.95, 9.75, 6.75
fries 4.50, 3.50
greek salad 7.25
Toppings:
extra cheese 2.00,
mushrooms 1.50
sausage 3.00
canadian bacon 3.50
AI sauce 1.50
peppers 1.00
Drinks:
coke 3.00, 2.00, 1.00
sprite 3.00, 2.00, 1.00
bottled water 5.00
user: Hi i want to order a pizza
assistant:
```
