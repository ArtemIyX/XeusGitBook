---
description: Сравнение деталей кода в Unreal Engine 4.27.2
---

# UE Difference

## Data types

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

### using, typedef

* Для создания синонима длинного типа данных применяй ключевые слова \
  `using` или `typedef`
* Используйте `using` или `typedef` для повышения локальной читаемости кода
* В стандарте C++ 11 `using` и `typedef` считаются синонимами
* При выборе между using и typedef, отдайте предпочтение using, так как typedef не всегда поддерживает шаблоны

> The alias declaration is compatible with templates, whereas the C style typedef is not.

```cpp
typedef void (UWeaponWorkbenchAction::*FunctionPtrType)(int32 a);     // ok
using FunctionPtrType = void (UWeaponWorkbenchAction::*)(int32 a;     // better
```

### define

* Избегайте использования #define для определения констант; \
  вместо этого рекомендуется применять constexpr
* Использование макросов и подстановка бесконечного числа параметров данных удобны в контексте Unreal Engine 4 с использованием директивы #define

```cpp
#define NETMODE_WORLD (((GEngine == nullptr) || (GetWorld() == nullptr)) ? TEXT("") \
    : (GEngine->GetNetMode(GetWorld()) == NM_Client) ? TEXT("[Client] ") \
    : (GEngine->GetNetMode(GetWorld()) == NM_ListenServer) ? TEXT("[ListenServer] ") \
    : (GEngine->GetNetMode(GetWorld()) == NM_DedicatedServer) ? TEXT("[DedicatedServer] ") \
    : TEXT("[Standalone] "))
```

```cpp
#define TRACE(Category, Format, ...) \
{ \
    SET_WARN_COLOR(COLOR_CYAN);\
    const FString Msg = FString::Printf(TEXT(Format), ##__VA_ARGS__); \
    if (Msg == "") \
    { \
        UE_LOG(Category, Log, TEXT("%s%s() : %s"), NETMODE_WORLD, FUNC_NAME, *GetNameSafe(this));\
    } \
    else \
    { \
        UE_LOG(Category, Log, TEXT("%s%s() : %s"), NETMODE_WORLD, FUNC_NAME, *Msg);\
    } \
    CLEAR_WARN_COLOR();\
}
```
