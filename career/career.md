# Вопросы с собеседований

## Содержание
1. [Стажер LLM, NLP в Мегафон](#cтажер-llm,-nlp-в-мегафон)

---

## Стажер LLM, NLP в Мегафон

**Задача 1:**
Напишите функцию, которая принимает строку и возвращает 5 самых частых слов в тексте.  
Необходимо:  
- Игнорировать регистр.  
- Игнорировать знаки пунктуации.

**Ответ:**
```
from collections import  Counter

def top_words(text, n=5):
    for val in '!.,?:;':
      text = text.lower().replace(val, '')
    a = text.split()
    c = Counter(a)
    return c.most_common(n)
```

**Задача 2:**
Реализуйте функцию, которая принимает строку и возвращает словарь: биграмма → частота.  
Биграммы формируются из последовательности слов (игнорируя пунктуацию).


**Ответ:**
```
def bigrams(text):
  text = text.lower()
  for val in '!.,?:;':
    text = text.replace(val, '')
  a = text.split()
  arr = [(a[i], a[i+1]) for i in range(len(a)-1)]
  c = Counter(arr)
  return dict(c.most_common())


text = "I love NLP. I love coding in Python."
print(bigrams(text))
assert bigrams(text) == {('i', 'love'): 2, ('love', 'nlp'): 1, ('nlp', 'i'): 1, ('love', 'coding'): 1, ('coding', 'in'): 1, ('in', 'python'): 1}
```

---
