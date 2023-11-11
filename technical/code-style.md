---
description: Стиль кода для программистов Xeus
---

# Code style

## Syntax

### Basic constructions

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
