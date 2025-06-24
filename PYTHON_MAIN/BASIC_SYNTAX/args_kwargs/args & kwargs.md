Опциональные параметры, пример:
```python
def print_these(a=None,b=None,c=None):
	print(a, "is stored in a")   
	print(b, "is stored in b")   
	print(c, "is stored in c")
	
	print_these(c=3, a=1)
	
	# 1 is stored in a
	# None is stored in b
	# 3 is stored in c
	
```


**==Оператор «звёздочка»==**

Оператор ```*``` в python позволяет "распаковывать" объекты, внутри которых хранятся некие элементы:
```python
a = [1,2,3]
b = [*a,4,5,6]

print(b) 

# [1,2,3,4,5,6]
```

`*args` — это сокращение от «arguments» (аргументы), а ```**kwargs``` — сокращение от «keyword arguments» (именованные аргументы). (Имена args и kwargs использованы для понимания, наименования *аргументов* и *параметров* могут быть любыми)