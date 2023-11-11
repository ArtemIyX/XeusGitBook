---
description: Сравнение деталей кода в Unreal Engine 4.27.2
---

# UE Difference

## Типы данных

### int vs int32

> Both int32 and int are valid types, so that’s why it compiles, though the size of int is implementation-based. Because of this, int32 is usually used in UE4 code to keep things working cross-platform.

Для обеспечения кросс-платформенной совместимости использetv тип данных `int32`, поскольку размер `int` может различаться в зависимости от платформы компиляции.

```cpp
int a;                // bad
int32 a;              // ok

unsigned char b;      // bad
uint8 b;              // ok

signed long long int c;      // bad
int64 c;                     // ok
```

### nullptr vs NULL

> You should really try to avoid using NULL if possible and instead use nullptr. It’s a lot safer if only because you’re not checking against a number (zero) - and it’s part of the C++ language as of C++11 (which is required by Rocket in any case!)

`NULL` просто является альтернативным термином для 0. Однако, для обеспечения безопасности при работе с указателями, используем `nullptr`.

```cpp
int* ptr = NULL;        //bad
int* ptr = nullptr;     //ok
```
