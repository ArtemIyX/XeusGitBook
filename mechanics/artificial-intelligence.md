---
description: Система поведения животных
---

# Artificial intelligence

## Характеристики

{% hint style="warning" %}
Система поведения будет заменена на полунейронную механику
{% endhint %}

Каждое животное обладает определенными параметрами, которые можно разделить на три категории: базовые, подвидовые и личные.

Базовые параметры являются общими для всех животных на всех серверах игры. Эти параметры одинаковы для всех экземпляров данного вида животных в игровом мире.

Подвидовые параметры представляют собой изменения, которые происходят у некоторых существ в зависимости от сервера. На каждом сервере определенные виды животных могут иметь отличия в поведении и характеристиках. Это позволяет создать уникальную игровую среду и разнообразие среди видов животных.

Личные параметры представляют собой небольшие изменения в параметрах для конкретного экземпляра животного определенного подвида. Эти изменения делают каждое животное индивидуальным и уникальным в пределах своего подвида.

Таким образом, базовые параметры общие для всех животных, подвидовые параметры изменяются в зависимости от сервера, а личные параметры вносят небольшие изменения в характеристики каждого конкретного существа определенного подвида.

### Информация о существах

В мире игры, все данные о животных хранятся в чанках мира в виде досье для каждого существа. Количество досье и разнообразие видов животных в чанке зависят от биома и предыдущих взаимодействий. Например, в чанке, относящейся к холодному биому, может быть меньше видов существ. Важно отметить, что количество животных, которые реально находятся на территории, всегда меньше, чем количество досье, которые хранятся в базе данных.

Когда одно существо погибает от рук инвазора, после некоторого времени оно заменяется другим существом, которое имеет немного лучшие параметры. В то же время, с течением времени, животное может умереть от старости, и затем, через некоторое время, его заменит существо с более низкими параметрами. Таким образом, в чанке всегда присутствует как минимум один вид травоядного животного и один вид всеядного/хищника. Количественное соотношение между ними всегда одинаковое, например, на каждых трех травоядных приходится один хищник.

## Поведение

Каждое существо хранит в себе параметры.

{% hint style="warning" %}
Из-за нейронной системы это будет иметь другой вид, но суть не поменяется
{% endhint %}

1. **Вид**\
   _Всегда одинаковое_
2. **Подвид** \
   _На разных серверах разное_
3. **Хищник**/**травоядный**/**всеядный**\
   _Всегда одинаковое_
4. **Бойкий**/**трусливый** \
   _На разных серверах разное_
   * Будет ли существо отвечать на агрессию или убегать?
   * Зависит от подвида и индивидуального характера (последнее приоритетнее)
   * Реакция при получении урона
5. **Пофигист**/**активный**\
   _На разных серверах разное_
   * Будет ли существо реагировать на инвазора или других животных иного вида?
   * Бойкий – нападет, трусливый убегает
   * Зависит от подвида и индивидуального характера.&#x20;
   * Реакция при обнаружении
6. **Стайный/одиночный** \
   _На разных серверах разное_
   * Зависит от подвида и индивидуального характера (последнее приоритетнее)
   * Будет ли существо прибиваться к животным такого же вида?
7. **Ночной**/**дневной**/**переходящий**\
   _На разных серверах разное_
   * Зависит от подвида и индивидуального характера
   * Будет ли существо активно днем, ночью, или утром и вечером?
8. **Аккуратный**/**берсерк**\
   _На разных серверах разное_
   * Зависит от подвида и индивидуального характера (последнее приоритетнее)
   * Будет ли убегать, если здоровье слишком низкое?

## Модификаторы

В игре присутствуют модификаторы, которые изменяют базовые параметры существ. Существуют два типа модификаторов, которые могут наслаиваться друг на друга:

1. Подвидовой модификатор: Этот тип модификатора специфичен для каждого подвида существ и изменяет базовые параметры их характеристик. Например, если базовый параметр равен 100, а подвидовой модификатор составляет 1.1, то применение модификатора к базовому параметру приведет к значению 110.
2. Личный модификатор: Этот тип модификатора вносит индивидуальные изменения в параметры конкретного существа определенного подвида. Например, если после применения подвидового модификатора базовый параметр становится равным 110, а личный модификатор также равен 1.1, то применение личного модификатора приведет к значению 121.

Примеры модификаторов в игре могут включать:

* Размер: Модификатор, который изменяет физические размеры существа.
* Цвет: Модификатор, который изменяет внешний цвет или расцветку существа.
* Скорость бега: Модификатор, который изменяет скорость передвижения существа во время бега.
* Скорость атаки: Модификатор, который изменяет скорость, с которой существо может атаковать.
* Урон: Модификатор, который изменяет уровень урона, наносимого существом во время атаки.

Таким образом, модификаторы могут изменять базовые параметры существ и классифицируются как подвидовые (специфичные для подвидов) и личные (индивидуальные для конкретных существ).