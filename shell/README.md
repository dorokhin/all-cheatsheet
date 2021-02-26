# Linux shell

[bash-hackers](https://wiki.bash-hackers.org/)

[Xargs](https://ru.wikipedia.org/wiki/Xargs) - утилита для формирования списка аргументов и выполнения команды в UNIX-подобных операционных системах. Команда xargs объединяет зафиксированный набор заданных в командной строке начальных аргументов с аргументами, прочитанными со стандартного ввода, и выполняет указанную команду один или несколько раз.

[ripgrep](https://github.com/BurntSushi/ripgrep) - быстрый поиск с возможностью замены по содержимому в файлах, аналог GREP, ASK, написан на RUST, понимает регулярные выражения, игнорирует ресурсы указанные в .gitignore, автоматически пропускает бинарные, скрытые файлы, много фич.


## list process by memory usage
```bash
ps axo rss,comm,pid | awk '{ proc_list[$2] += $1; } END { for (proc in proc_list) { printf("%d\t%s\n", proc_list[proc],proc); }}' | sort -n | tail -n 10 | sort -rn | awk '{$1/=1024;printf "%.0fMB\t",$1}{print $2}'
```
```
5304MB	chrome
734MB	jetbrains-toolbox
130MB	Xorg
79MB	nemo
69MB	nemo-desktop
66MB	systemd-journal
...
```
