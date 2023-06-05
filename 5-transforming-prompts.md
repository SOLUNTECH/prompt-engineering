# Transforming

In this notebook, we will explore how to use Large Language Models for text transformation tasks such as language translation, spelling and grammar checking, tone adjustment, and format conversion.

## **Content Table**

- [**Translation**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/5-transforming-prompts.md#translation)

- [**Tone Transformation**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/5-transforming-prompts.md#tone-transformation)

- [**Format Conversion**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/5-transforming-prompts.md#format-conversion)

- [**Spellcheck/Grammar check**](https://github.com/SOLUNTECH/prompt-engineering/blob/main/5-transforming-prompts.md#spellcheck-grammar-check)

---

## Translation

ChatGPT is trained with sources in many languages. This gives the model the ability to do translation. Here are some examples of how to use this capability.

`Example prompt 1:`

```text
Translate the following English text to Spanish:
```Hi, I would like to order a blender```
```

`Example prompt 2:`

```text
Tell me which language this is: 
```Combien coûte le lampadaire?```
```

`Example prompt 3:`

```text
Translate the following  text to French and Spanish
and English pirate:
```I want to order a basketball```
```

`Example prompt 3:`

```text
Translate the following text to Spanish in both the \
formal and informal forms: 
'Would you like to order a pillow?'
```

### Universal Translator

Imagine you are in charge of IT at a large multinational e-commerce company. Users are messaging you with IT issues in all their native languages. Your staff is from all over the world and speaks only their native languages. You need a universal translator!

`Example prompt:`

```text
  Translate the following text to English and Korean: ```La performance du système est plus lente que d'habitude.```
  Translate the following text to English and Korean: ```Mi monitor tiene píxeles que no se iluminan.```
  Translate the following text to English and Korean: ```Il mio mouse non funziona```
  Translate the following text to English and Korean: ```Mój klawisz Ctrl jest zepsuty```
  Translate the following text to English and Korean: ```我的屏幕在闪烁```
```

## Tone Transformation

Writing can vary based on the intended audience. ChatGPT can produce different tones.

`Example prompt:`

```text
Translate the following from slang to a business letter: 
'Dude, This is Joe, check out this spec on this standing lamp.'
```

## Format Conversion

ChatGPT can translate between formats. The prompt should describe the input and output formats.

`Example prompt:`

```text
Translate the following python dictionary from JSON to an HTML table with column headers and title:
data_json = { "resturant employees" :[ 
    {"name":"Shyam", "email":"shyamjaiswal@gmail.com"},
    {"name":"Bob", "email":"bob32@gmail.com"},
    {"name":"Jai", "email":"jai87@gmail.com"}
]}
```

## Spellcheck/Grammar check.

Here are some examples of common grammar and spelling problems and the LLM's response. 

To signal to the LLM that you want it to proofread your text, you instruct the model to 'proofread' or 'proofread and correct'.

`Example prompt 1:`

```text
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```The girl with the black and white puppies have a ball.```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```Yolanda has her notebook.```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```Its going to be a long day. Does the car need it’s oil changed?```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```Their goes my freedom. There going to bring they’re suitcases.```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```Your going to need you’re notebook.```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```That medicine effects my ability to sleep. Have you heard of the butterfly affect?```
Proofread and correct the following text and rewrite the corrected version. If you don't find and errors, just say "No errors found". Don't use any punctuation around the text: ```This phrase is to cherck chatGPT for speling abilitty```
```

`Example prompt 2:`

```text
proofread and correct this review: ```Got this for my daughter for her birthday cuz she keeps taking mine from my room.  Yes, adults also like pandas too.  She takes it everywhere with her, and it's super soft and cute.  One of the ears is a bit lower than the other, and I don't think that was designed to be asymmetrical. It's a bit small for what I paid for it though. I think there might be other options that are bigger for the same price.  It arrived a day earlier than expected, so I got to play with it myself before I gave it to my daughter.```
```

`Example prompt 3:`

```text
proofread and correct this review. Make it more compelling. 
Ensure it follows APA style guide and targets an advanced reader. 
Output in markdown format.
Text: ```Got this for my daughter for her birthday cuz she keeps taking mine from my room.  Yes, adults also like pandas too.  She takes it everywhere with her, and it's super soft and cute.  One of the ears is a bit lower than the other, and I don't think that was designed to be asymmetrical. It's a bit small for what I paid for it though. I think there might be other options that are bigger for the same price.  It arrived a day earlier than expected, so I got to play with it myself before I gave it to my daughter.```
```
