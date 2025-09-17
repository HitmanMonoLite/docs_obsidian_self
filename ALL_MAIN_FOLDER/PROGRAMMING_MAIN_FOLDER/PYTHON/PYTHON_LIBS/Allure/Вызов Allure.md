Для запуска теста с использованием Allure в связке с pytest можно использовать команду:
```
pytest testPyMain.py --alluredir allure-results
```

`testPyMain.py` - это название тестируемого файла.
`allure-results` - это директория, куда будет сохранён отчёт.

---
Для вызова интерфейса отчёта необходимо перейти в директорию с папкой итогов тестирования `allure-results`. После использовать команду :
```
allure serve allure-results
```

Например директория с проектом это `C:\MyPrograms\Python\TestProject`.
Следовательно терминал должен выглядеть так:
![[Pasted image 20250624180918.png]]
