---
description: Рекомендации к комментариями
---

# Comments

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
