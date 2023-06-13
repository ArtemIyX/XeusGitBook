# Armor system

## Clothes

Clothing has the ability to provide protection against adverse life-threatening conditions. Each armor component has a unique level of resistance to a certain type of damage, which is expressed as a numerical value by which it is divided.

## BLV

BLV - Base limb vulnerability

$$
BLV ∈ [0;2]
$$

_BLV_ On the example of a jacket

<table><thead><tr><th width="238">Damage Type</th><th>Value</th></tr></thead><tbody><tr><td>Stabbed</td><td>1.1</td></tr><tr><td>Cutting</td><td>2</td></tr><tr><td>Рубящий</td><td>1.1</td></tr><tr><td>Chopping</td><td>1</td></tr><tr><td>Bullet</td><td>1</td></tr><tr><td>Torn</td><td>1.5</td></tr></tbody></table>

### Calculating damage

$$
y = \frac{a}{r - BLV + 1}
$$

<table><thead><tr><th width="184">Variable</th><th>Description</th></tr></thead><tbody><tr><td>a</td><td>The amount of damage dealt</td></tr><tr><td>r</td><td>Resistance of this type of clothing</td></tr><tr><td>BLV</td><td>Basic limb vulnerability</td></tr></tbody></table>

#### Examples of damage calculations

_Example of calculating formulas for a heavy axe strike:_

`damage = 40 / (1.1 - бук + 1) // 36.36 Chopping Damage`

`damage = 10 / (1.0 - бук + 1) // 10.00 ImpactDamage`

## Clothes slots

Any clothing, body armor, for example, must be placed only in a designated slot for body armor and cannot be placed in a slot designated for another type of clothing, such as pants.

In addition, armor can provide additional inventory slots, allowing the wearer to store and carry more items. These extra inventory slots can be used to house a variety of items, including medical supplies, extra ammo, or other necessary tools.

## Overlap

Armor extends not only to its corresponding body parts, but also to neighboring body parts. For example, a jacket can also protect your abdomen and arms. The protection depends on the coating modifier. The greater it is, the greater the protection;

_Covering by example of a jacket_

<table><thead><tr><th width="235">Limb</th><th>Overlap value</th></tr></thead><tbody><tr><td>Head</td><td>0.0</td></tr><tr><td>Chest</td><td>1.0</td></tr><tr><td>Belly</td><td>1.0</td></tr><tr><td>Right hand</td><td>0.5</td></tr><tr><td>Left hand</td><td>0.5</td></tr><tr><td>Right leg</td><td>0.0</td></tr><tr><td>Left leg</td><td>0.0</td></tr></tbody></table>

### Calculation of overlapping

$$
y = (a-1 )* p)+1
$$

<table><thead><tr><th width="159">Variable</th><th></th></tr></thead><tbody><tr><td>a</td><td>Protection</td></tr><tr><td>p</td><td>Overlap</td></tr></tbody></table>

That is, for the chest and abdomen, the percentage of protection corresponds to the above.\
For the arms, the formula is as follows:

`overlap = ((1.1 - 1) * 0.5) + 1 // 1.05`\
`damage = 40 / (1.1 - BLV + 1 ) // 38.09`\\

## Cumulative effects

The effects of different armor work in combination, for example on the arm there is protection from hacker damage from the shoulder pad, elbow pad and jacket 1.1, 1.1 and 1.05 respectively. The result is calculated as follows:

`r = (1.1 + 1.1 + 1.05) // 1.25`\
`damage = 40 \ (r - 1.0 + 1) // 32.0`

## The final formula

$$
P_{i} =(((m_{i} - 1) * h_{i}) + 1) - b + 1
$$

{% hint style="info" %}
i - element index on a limb
{% endhint %}

$$
C=(\sum_{i=0}^{n-1}P_{i}) - n
$$

{% hint style="info" %}
С - the sum of the results of all armor elements on a given limb
{% endhint %}

$$
y =\frac{V}{C}
$$

<table><thead><tr><th width="88">Variable</th><th>Description</th></tr></thead><tbody><tr><td>V</td><td>Incoming damage</td></tr><tr><td>C</td><td>The coefficient of protection for this limb</td></tr><tr><td>P</td><td>Protection of each armor element on a given limb</td></tr><tr><td>n</td><td>The number of armor elements on a given limb</td></tr><tr><td>m</td><td>Protection Modifier</td></tr><tr><td>h</td><td>Overlap Modifier</td></tr><tr><td>b</td><td>Base limb vulnerability </td></tr></tbody></table>

```cpp
double UArmor::CalculateBlockElement(double blv) const{
    return (((m - 1) * h) + 1) - blv + 1;
}
double UManager::CalculateBlockCoeficient(EHitbox hitbox, double blv) const{
    auto armor = GetArmor(hitbox);
    double sum = 0.0f;
    for(const auto& var : armor){
        sum += var->CalculateBlockElement(blv);
    }
    return sum - armor.Num();
}
double UManager::CalculateDamage(float initialDamage, 
    EDamageType damageType, EHitbox hitbox) const{
    double blv = GetBlv(damageType, hitbox);
    double c = CalculateBlockCoeficient(hitbox, blv);
    return initialDamage / c;
}
```
