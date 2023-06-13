---
description: Combat system for melee
---

# Fighting system

## Basic information

### Specifications

The weapon contains the following data:

* Attack directions: it stores information about different attack directions, their speed, damage modifier and overall efficiency.
* Directional damage type: the weapon also determines the type of damage that will be dealt depending on the chosen direction of attack.
* Length: weapons have a certain length, which indicates their range.
* Weight: each weapon has its own weight, which can affect the character's speed and maneuverability when using the weapon.
* Sharpening: a weapon can have a certain level of sharpening, which affects its effectiveness and impact force.
* Status: information about the weapon's state, such as integrity, wear or damage.
* Potion applied: it can also indicate if any potion has been applied to the weapon that affects its characteristics or attack effects.

### Direction of attack

The process of choosing the direction of the attack includes the following steps:

* Character movement: While the character is actively moving in one direction (forward, backward, left, right), an attack direction selection action is performed.
* Clicking the attack button: The user clicks the attack button using the left mouse button (LMB). This initiates the attack direction selection process.
* Weapon positioning: The character automatically positions the weapon according to the chosen attack direction. For example, to attack from above, to lunge, to attack from the left or to attack from the right, the weapon will be positioned in the appropriate position.
* Making an attack: In order for the character to make an attack, the user must release the attack button. This action signals the start of the attack in the selected direction.

### Block direction

The process of choosing the block direction is similar to the process of choosing the attack direction, except using the right mouse button (RMB) instead of the left mouse button (LMB). It is important to note that heavier weapons have an advantage in block piercing and more efficient attack absorption compared to weapons of lesser mass.

### Attack charge

When the attack key is held for a long time, the Force accumulates, which is a damage modifier (from 0.5 to 2 ×) and depends on the characteristics of a particular weapon. The rate of accumulation of Power also depends on the parameters of the weapon.

When the maximum Power level is reached, the attack is able to break through the opponent's block. However, the accumulation and maintenance of Strength requires the expenditure of endurance of the character. Heavier weapons require a longer time to accumulate Strength and at the same time reduce the endurance of the character to a greater extent.

If the character holds down the attack key for too long, the Power level begins to decrease. When the Power level drops to zero, the character lowers the weapon and loses the ability to use it effectively for a while (a fine is imposed).

Thus, holding the attack key allows you to accumulate Power, which affects damage modification, but requires stamina. It is important to control the level of Force in order to avoid reducing it to zero and the associated time limit on the use of weapons.

### Block charge

The charge of the unit is a numeric value that decreases from 1 to 0 after pressing the right mouse button (PCM). The charge level of the block affects the ability to absorb an attack from the enemy. The maximum charge of the block allows you to completely absorb the attack (except when the enemy uses significantly heavier weapons), while the minimum charge of the block allows you to skip the attack completely. Maintaining a block requires a certain level of endurance.

## Techniques in battle

### Kick

A kick involves the use of a separate button to perform it. During the execution of the blow, you cannot move, however, if the blow is performed during the jerk, it will not be interrupted, and the damage will be increased.

A kick causes significant physical damage and pushes the opponent away if he is not in a squat position or is not protected by a shield.

The impact on the shield leads to the forced knocking down of the [shield] (fighting-system.md#shit) without imposing penalties, the opponent simply lowers the shield and can then raise it again.

### Chamber

The chamber is a complex technique that combines blocking and attack. When executing an opponent's strike a few milliseconds after it in the same direction, you can perform a chamber. As a result, the enemy's attack will be repulsed, and then, after a short time, the enemy will be automatically struck with minimal possibility of blocking it.

For example, if you are attacked from above and you have just released the left mouse click button (i.e., the attack is launched), and at that moment you quickly press the left mouse button from the same side, you will be able to block the enemy's attack and cause damage to him.

### Clinch

With the simultaneous maximum impact of the players, a clinch state occurs, in which a special animation demonstrates how the characters use the force of weapons against each other. At this point, players are invited to participate in a mini-game in which you need to press certain buttons sequentially. The player who gets ahead of the opponent in performing the N-number of taps will cause damage.

If none of the players managed to get ahead of the opponent in performing the N-number of clicks, the clinch ends, and both players automatically make a dash back at the usual price of endurance. However, during the clinch, the player can make a jerk back to stop the clinch state, but this will require twice the expenditure of stamina compared to a normal jerk.

#### The mechanics of the mini-game during the clinch

In the case of a clinch, players interact with a mini-game where certain buttons must be pressed sequentially. Each player has their own unique set of buttons, and both players press the buttons independently of each other. Due to the lack of visibility of the opponent's clicks, players cannot observe which buttons he presses. The main goal is to be the first to reach the end point of the mini-game, for example, by making 10 consecutive taps.

It is important to note that the buttons to be pressed appear randomly in a certain radius from the center of the screen. Thus, players need to quickly navigate and react to the appearance of buttons in real time.

{% hint style="info" %}
In order to show the players their current position relative to the opponent, it is necessary to display information about how each of the players is ahead or behind the opponent in performing button presses. This can be represented visually, for example, in the form of a progress bar or a numeric value showing the progress of each player to reach 10 taps.
{% endhint %}

### Riposte

When you hold down the attack button (left mouse button) and then press the block button (right mouse button), the attack charge is converted into a block charge, but will not continue to accumulate. If the character is in motion at this time, the direction of attack automatically changes according to the current direction of movement.

If while holding the block button (the right mouse button) and releasing this button (but while holding the attack button - the left mouse button), the charge of the block is converted into a charge of force, but will not continue to accumulate. If the character is in motion at this time, the direction of attack will also correspond to the current direction of movement.

## Conducting a battle

### Block/Attack direction

The weapon has primary and secondary attack directions. When performing an attack from the main direction, the main type of damage corresponding to this weapon is applied (for example, for a spear, this is a lunge and stabbing damage). In the case of an attack from a secondary direction, a secondary type of damage is used (for example, for a spear, this is all other attacks and shock damage).

When moving the mouse in the direction of the attack, the damage inflicted increases, and when moving in the opposite direction, the damage decreases. This allows the player to control the impact force based on the mouse movement.

The length of the weapon affects the radius of destruction. Weapons with a longer length have a larger radius, which allows you to reach targets at a greater distance.

### Dashes

By pressing certain buttons, the player can make a dash in a certain direction, which allows him to use it to evade attacks. If the player makes a dash in the direction of the enemy or simply approaches him and attacks, then the damage inflicted on the enemy increases. However, if the player makes a dash back or retreats, the damage will be less.

Some types of damage can stop a player's movement and attack if they penetrate the defense and exceed a certain damage threshold. If a blow hits the head area and causes damage above a certain limit, then a stun effect occurs, as a result of which the player cannot attack and perform jerks.

### Attack charge indicators

During the accumulation of the attack charge, the character will produce auditory effects in the form of the sound of inspiration. When the charge reaches the maximum value, there will be a pause. If the player makes an attack at this moment, the character will make a sharp exhalation sound with a growl. If the charge starts to decrease, the sound of exhalation will be heard. If the attack is not made at the maximum charge, the player will hear just a sharp exhalation. Both the player and his opponent will perceive these sounds.

While charging the attack, you can see a flicker on the weapon, starting from the handle to the end. When this flicker reaches the end, the attack will be fully charged. If the player misses this moment, the flicker will disappear. This effect is visible to both the player and the opponent.

Hit indicators will be used. If the player hits an enemy, a special sound will be played. If a hit occurs in the head, the sound will be more "juicy". If critical damage is dealt (damage exceeding the base value by two times), the character will make a "hyhy" sound.

### Dodge indicator

In the case when the opponent missed the character due to his jerk, the character will make a sound of "hyhy".

### Endurance

If a character's stamina is depleted during a fight or escape, his movement and ability to fight are not prohibited, however, a penalty is imposed that affects most of the character's parameters, and damage is also inflicted proportional to the level of endurance. Gradually, this leads to a decrease in the overall tone of the character and, eventually, can lead to loss of consciousness.

### Reaction to the full block

When blocking an attack by a character, the opponent's camera will be slightly shifted in the direction of the block, and the player's character will make a "heehy" sound.

### Sharpness&#x20;

Sharpness is a parameter that reflects the player's attentiveness to his weapon and affects the damage caused by cutting and slashing attacks. In the manufacture of weapons has 100% sharpening. However, it can be improved by pumping up to 125%. If the sharpening level drops to zero, all cutting and slashing damage will be lost. The value of sharpening decreases during strikes on the enemy.

### Backstab

In the case when the character strikes the opponent in the back when he is in a standing position, the damage will be doubled.

## Intermediate formula

```cpp
TArray<float> arr = { 
    PowerCharge, Sharp, AttackSideMult, 
    MovementSpeedMult, MouseSpeedMult, JumpStrengthMult 
};
float Damage = BaseDamage;
for (float element : arr) {
    Damage *= element;
}
```

<table><thead><tr><th width="223"></th><th></th></tr></thead><tbody><tr><td>BaseDamage</td><td>Базовый урон этого оружия некого типа</td></tr><tr><td>PowerCharge</td><td>Модификатор от уровня заряда силы</td></tr><tr><td>Sharp</td><td>Модификатор от заточки</td></tr><tr><td>AttackSideMult</td><td>Модификатор угла(стороны) атаки</td></tr><tr><td>MovementSpeedMult</td><td>Модификатор от скорости (рывок).</td></tr><tr><td>MouseSpeedMult</td><td>Модификатор от скорости движения мышки</td></tr><tr><td>JumpStrengthMult</td><td>Модификатор от прыжка</td></tr><tr><td>Damage</td><td>Проходящий урон (что дальше взаимодействует с броней)<br></td></tr></tbody></table>

## Shield

### Shield description

The shield has a permanent hitbox that protects against arrows. The shield also has durability, which is spent when absorbing damage. Depending on the type of shield, it can either break and disappear, or lose all its effectiveness (while remaining in the inventory for possible repairs)

### Shield usage

To raise the shield, you need to press the right mouse button. When the shield is raised, a scale appears, which is filled when blocking attacks. The more this scale is filled, the faster the character's stamina is consumed (even if the scale is filled to zero, the stamina still slowly decreases). When the scale reaches the maximum value, the character's hand is forcibly lowered, and the shield becomes unavailable for a while. In addition, the scale begins to fill up slowly three seconds after raising the shield.

When blocking an attack with a shield, when the scale is empty, the attacking opponent cannot attack for several seconds. At this point, the player has the opportunity to go into a counterattack.

Primitive shields are designed only to protect against arrows, they are not able to stop bullets. However, advanced shields provide full protection from shelling.

### Shield attack

When you hold down the right mouse button and simultaneously press the attack button, the character will strike with a shield. The radius of this attack is small, and immediately after the strike, the character cannot continue to hold the shield. If this attack hits the enemy, he will be stunned.

### Shield bash (stun)

There is a kind of shield attack. If during a raised shield and an empty scale to make a dash forward, the character will make a sharp jump, overcoming a greater distance than usual, then this action will stun the enemy and cause damage.

\