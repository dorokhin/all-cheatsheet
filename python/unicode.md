# Python unicode

Посвящается любителям вставлять в исходники программ для Pyhon версии >= 3.x заголовок с указанием кодировки.

```python
#!/usr/bin/python
# -*- coding: <encoding name> -*-
```

**Этого не надо делать если вы используете python версии >= 3.x и ваша система нативно поддерживает unicode, 
ваши исходники по умолчанию в unicode (UTF-8).**


Надо указаывать только в случае если используемая кодировка отличается от unicode (UTF-8)


### Ссылки:
[PEP 3120 -- Using UTF-8 as the default source encoding](https://www.python.org/dev/peps/pep-3120/)
[PEP 263 -- Defining Python Source Code Encodings](https://www.python.org/dev/peps/pep-0263/)
[Should I use encoding declaration in Python 3?](https://stackoverflow.com/a/14083123)
