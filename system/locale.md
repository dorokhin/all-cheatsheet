# perl: warning: Setting locale failed.

### Обычно на свежеустановленной Ubuntu появляется ошибка, при установке пакетов:

```bash
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
	LANGUAGE = (unset),
	LC_ALL = (unset),
	LC_TIME = "ru_RU.UTF-8",
	LC_MONETARY = "ru_RU.UTF-8",
	LC_ADDRESS = "ru_RU.UTF-8",
	LC_TELEPHONE = "ru_RU.UTF-8",
	LC_NAME = "ru_RU.UTF-8",
	LC_MEASUREMENT = "ru_RU.UTF-8",
	LC_IDENTIFICATION = "ru_RU.UTF-8",
	LC_NUMERIC = "ru_RU.UTF-8",
	LC_PAPER = "ru_RU.UTF-8",
	LANG = "en_US.UTF-8"

```

Это можно исправить следующим способом:

```bash
dpkg-reconfigure locales
```
далее выбрать необходимые локали и нажать ОК.
Нам нужны:
```bash
en_US.UTF-8
ru_RU.UTF-8
```
