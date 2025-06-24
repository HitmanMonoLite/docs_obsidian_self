**! ВСЕ ОБЪЕКТЫ ДОЛЖНЫ НАЧИТАТЬСЯ С `test` ЧТОБЫ МОДУЛЬ ИХ УВИДЕЛ !**
Пример:
```python
from selenium import webdriver  
from selenium.webdriver.common.by import By  
from time import sleep  
  
driver = webdriver.Firefox()  
wait_time = 0.5  
  
def test_selenium_py():  
    driver.get("https://www.selenium.dev/selenium/web/web-form.html")  
  
    title = driver.title  
  
    driver.implicitly_wait(0.5)  
  
    text_box = driver.find_element(by=By.NAME, value="my-text")  
    submit_button = driver.find_element(by=By.CSS_SELECTOR, value="button")  
  
    sleep(wait_time)  
  
    text_box.send_keys("Selenium")  
  
    sleep(wait_time)  
  
    submit_button.click()  
  
    sleep(wait_time)  
  
    message = driver.find_element(by=By.CLASS_NAME, value="lead")  
    print("message is:", message)  
    text = message.text  
    print("text is:", text)  
  
    driver.quit()  
  
    # driver.get("https://roomplan.ru/app/")  
    # title = driver.title    # print(title)  
  
if __name__ == "__main__":  
    pass
```

Библиотека, для тестирования.
![[Pasted image 20250623140858.png]]

выполняет проверку какого либо объекта в файле или файла целиком.

--------------------------
Также, варианты запусков:
![[Pasted image 20250623141503.png]]

---------------------------------------------
**Запуск тестов по аргументам коллекции**

Передайте имя файла модуля относительно рабочего каталога, за которым следуют спецификаторы, такие как имя класса и имя функции. разделенные `::`символы и параметры из параметризации, заключенные в `[]`.

Чтобы запустить определенный тест в модуле:
`pytest tests/test_mod.py::test_func`

Чтобы запустить все тесты в классе:
`pytest tests/test_mod.py::TestClass`

Указание конкретного метода испытаний:
`pytest tests/test_mod.py::TestClass::test_method`

Указание конкретной параметризации теста:
`pytest tests/test_mod.py::test_func[x1,y2]`

----------------

**Запуск тестов по выражениям маркеров**

Для запуска всех тестов, которые украшены `@pytest.mark.slow`декоратор:
`pytest -m slow`

Для запуска всех тестов, которые оформлены аннотированными `@pytest.mark.slow(phase=1)`декоратор, с `phase`аргумент ключевого слова установлен на `1`:
`pytest -m "slow(phase=1)"`

-----------------

**Запуск тестов из пакетов**

`pytest --pyargs pkg.testing`

Это импортирует `pkg.testing`и использовать его расположение в файловой системе для поиска и запуска тестов.

---------------

**Прочитать аргументы из файла**

Все вышеперечисленное можно прочитать из файла с помощью `@`префикс:
`pytest @tests_to_run.txt`

где `tests_to_run.txt`содержит по одной записи в каждой строке, например:
```
tests/test_file.py
tests/test_mod.py::test_func[x1,y2]
tests/test_mod.py::TestClass
-m slow
```

Этот файл также можно создать с помощью `pytest --collect-only -q`и изменены по мере необходимости.
