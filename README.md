# PNG → SVG Converter (Potrace)
Bash-скрипт для пакетной конвертации PNG-изображений в оптимизированные SVG-файлы.  
Предназначен в первую очередь для иконок и простой UI-графики.

Скрипт автоматически конвертирует изображения через ImageMagick и Potrace, очищает SVG от лишних данных и минифицирует результат.

---

## Возможности

- Пакетная обработка всех `.png` файлов из папки `source/`
- Автоматическое создание папки `svg/`
- Конвертация PNG → PNM → SVG
- Удаление:
  - XML declaration и DOCTYPE
  - `<metadata>` от Potrace
  - атрибутов `width`, `height`, `preserveAspectRatio`
- Приведение SVG к использованию `currentColor`
- Замена `fill="white"` → `fill="none"`
- Минификация SVG:
  - удаление переносов строк
  - удаление лишних пробелов
- Автоматическое закрытие окна Terminal после выполнения (macOS)

---

## Структура проекта
```
project/
├── source/
│ ├── icon1.png
│ ├── icon2.png
│ └── ...
├── svg/
│ ├── icon1.svg
│ ├── icon2.svg
│ └── ...
└── png-to-svg.sh
```
---

## Зависимости

Скрипт рассчитан на macOS и требует следующие утилиты:

- ImageMagick (`convert`)
- Potrace
- Perl
- sed

### Установка через Homebrew
```bash
brew install imagemagick potrace
```

---

## Использование

- Помести PNG-файлы в папку source/
- Сделай скрипт исполняемым (один раз):
```bash
chmod +x png-to-svg.sh
```
- Запусти скрипт:
```bash
./png-to-svg.sh
```
- Готовые SVG-файлы появятся в папке svg/


## Лицензия

Свободное использование без ограничений.
В случае модификаций — pull requests приветствуются.





