# pet_scheduler
Source code for mvp project - smart scheduler
Для создания исполняемого файла (.exe)  используем PyInstaller, а для уведомлений - библиотеку win10toast.

#  Инструкция по созданию исполняемого файла (.exe):
1. Установи необходимые библиотеки:

bash
pip install pyinstaller win10toast
2. Создай файл icon.ico (иконка для уведомлений) и поместите его в ту же папку, что и скрипт.

3. Создайте файл build_exe.py для сборки:
python

import PyInstaller.__main__

PyInstaller.__main__.run([
    'smart_scheduler.py',
    '--onefile',
    '--windowed',
    '--icon=icon.ico',
    '--name=SmartScheduler'
])

4. Запусти build_exe.py для создания исполняемого файла:

bash
python build_exe.py
5. После сборки исполняемый файл будет находиться в папке dist с именем SmartScheduler.exe.

# Как использовать:
1. Дважды щелкните по SmartScheduler.exe на рабочем столе.
2. В появившемся окне введите текст задачи.
3. Введите время напоминания в формате ДД-ММ-ГГГГ ЧЧ:ММ:СС или оставьте пустым для напоминания через 1 минуту.
4. Когда наступит время напоминания, появится уведомление с звуковым сигналом.

# Примечания:
Для работы уведомлений нужна Windows 10 или новее.
Иконка icon.ico должна быть в той же папке, что и исполняемый файл.
Все задачи сохраняются в файл tasks.json в той же папке.
Для более сложного планирования можно расширить функционал (например, добавить повторяющиеся задачи).
