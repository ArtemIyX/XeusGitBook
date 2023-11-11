---
description: Определение сущностей
---

# Definitions

* Отдавай предпочтение выносу классов в отдельные файлы. \
  _Исключение: классы-контейнеры данных_
* Отделяй типы данных (`struct`, `enum`), связанные с модулем, в отдельных файлах `.h`
* Применяй `namespace` для констант
* Предпочитают использовать `enum class : uint8`
* Добавляют `_None` и `_Max` `UMETA(Hidden)` в `enum`
* Используй `enum` только как вложенный в `class` или `namespace`
* Оъявляй все сущности в С++ файлах, не используй для этого Blueprints

```cpp
UCLASS(Abstract)
class XEUS_API UXeusTypes : public UObject
{
	GENERATED_BODY()
};
```

```cpp
USTRUCT(BlueprintType)
struct FWeaponConnection
{
	GENERATED_BODY()
};
```

```cpp
namespace EXeusCollisionChannel
{
	constexpr ECollisionChannel ECC_Interact = ECC_GameTraceChannel1;
	constexpr ECollisionChannel ECC_BiomeDefinition = ECC_GameTraceChannel2;
}
```

```cpp
namespace WidgetAction
{
	enum WidgetActionType
	{
		TYPE_WeaponWorkbench=1
		// ...
	};

	namespace WeaponWorkbench
	{
		enum WeaponWorkbenchAction
		{
			TYPE_SelectCorePart=1,
			// ...
		};
	}
}
```

```cpp
UENUM(BlueprintType)
enum class EWeaponPartGrade : uint8
{
	GRADE_None UMETA(Hidden),
	GRADE_Core UMETA(DisplayName="Core"),
	GRADE_Main UMETA(DisplayName="Main"),
	GRADE_Additional UMETA(DisplayName="Additional"),
	GRADE_Max UMETA(Hidden),
};
```

```cpp
UCLASS()
class XEUSWEAPONS_API AWeaponWorkBench : public AInteractableActor
{
	GENERATED_BODY()

public:
	enum EWeaponSound
	{
		SOUND_AddPart=1,
		SOUND_RemovePart=2,
		SOUND_AddWeapon=3,
		SOUND_RemoveWeapon=4
	};
};
```
