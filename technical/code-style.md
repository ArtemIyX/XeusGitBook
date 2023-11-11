---
description: Стиль кода для программистов Xeus
---

# Code style

## Syntax

### Comments

* Аннотируйте кратким описанием назначение каждой функции
* Предоставьте подробные пояснения в файле .cpp
* Для документации применяйте Doxygen
* Используйте разграничивающие комментарии
* Не забывайте вставлять #pragma region.&#x20;
* Отмечайте незавершенные участки кода с помощью комментария // TODO:&#x20;
* Объясняйте условия проверок и запланированные части кода.

```cpp
// Called when the game starts or when spawned
virtual void BeginPlay() override;
```

```cpp
// Called when the game starts or when spawned
void ADebugChunk::BeginPlay() 
{

}
```

```cpp
/**
* @brief Accepts notifications from client chunk generation
* @param InChunk Chunk target
*/
void NotifyClientChunkCreated(AWorldChunk* InChunk);
```

```cpp
// ================================= MOVEMENT ALLOWS ========================================
bool ABaseXeusCharacter::MovementAllowed_Implementation() const
{
	return true;
}

bool ABaseXeusCharacter::LayAllowed_Implementation() const
{
	return false;
}
```

```cpp
#pragma region BlueprintFunctions

UFUNCTION(BlueprintImplementableEvent, DisplayName="PrepareClientMesh")
bool BP_PrepareClientMesh();

UFUNCTION(BlueprintImplementableEvent, DisplayName="Start Walking Camera Shake")
void BP_StartWalkingShake();

#pragma endregion
```

```cpp
// TODO: Async load
UWeaponPartDataAsset* weaponPartData =
		UXeusAssetManager::Get()
		->LoadAsset<UWeaponPartDataAsset>(setPartData->PartId);
```

```cpp
// Make sure it's valid
if (!IsValid(InCorePart))
	return false;

// Make sure we dont have weapon
if (HasWeapon())
	return false;
```

### Basic constructions

* Фигурные скобки с новой строчки
* Пробелы между ключевыми словами и скобками
* Разделение блоками кода

```cpp
{
    // some code
}
{
    // another code
}
```

```cpp
if (condition)
{
    // code here
}
else if (another_condition)
{
    // code here
}
else 
{
    // code here
}
```

```cpp
for (int32 i = 0; i < n; ++i)
{
    // code here
}
```

```cpp
for (FVector& var : Vertices)
{
    // code here
}
```

```cpp
while (condition)
{
    // code here
}
```

```cpp
switch (GenerationType)
{
	case EMeshGenerationType::Delay:
		StartDelaySpawn(server);
		break;
	case EMeshGenerationType::Instant_Both:
		StartInstantSpawn(server);
		break;
	case EMeshGenerationType::Instant_ServerOnly:
	{
		// code here
		break;
	}
	default:
		StartDelaySpawn(server);
		break;
}
```
