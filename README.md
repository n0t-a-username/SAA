## Skin Animation Manipulation (SAA) Method

**Getting Started:**
- SAA is a simplistic system for creating "4D" skins without any game/client modifications or need for 3rd party apps. 

- Its like math, where each animation is a variable, and adding or removing variables will drastically change the outcome.

- Nothings set in stone. A custom skin you make can completely change in one or two updates if mojang so chooses to do an animation reveamp

- SAA's do not work properly when using a custom animations pack like "Actions N Stuff"


**The Basics:**

This whole system relys on one file: ``Skins.json``
```
{
    "format_version": "1.10.0",
    "serialize_name": "name",
    "localization_name": "name",
    "skins": [
        {
            "localization_name": "name",
            "geometry": "geometry.humanoid.custom",
            "texture": "skin.png",
            "cape": "cape.png",
            "animations": {
                "humanoid_base_pose": "animation.humanoid.base_pose",
                "look_at_target": "controller.animation.humanoid.look_at_target",
                "cape": "animation.player.cape",
                "move.arms": "animation.player.move.arms",
                "move.legs": "animation.player.move.legs",
                "holding": "animation.player.holding",
                "attack.positions": "animation.player.attack.positions",
                "attack.rotations": "animation.player.attack.rotations",
                "bob": "animation.player.bob"
            },
            "type": "free",
            "enable_attachables": true
        }
    ]
}
```
- This is a basic setup with all the animation targets that run continuously and are not action specific. Although, there are some animations that are both for example attack positions and rotations can target the torso and above continuously but also have special animation play on the player swinging/punching.

**Animations 101:**

- Animations can do the following: move, delete and reshape parts of the humanoid skin, as well as stop existing animations and stop them from happening no matter if they're continuous or conditional animations (like sneaking)
-  You can use `animation.witch.general` to stop an animation from happening OR you could use `animation.evoker.general` to remove limbs/body parts
- Some animations can change how they look depending on what target you set them to.

**Theoretical:**

Previously I mentioned in the documentation that texture packs like "Actions N Stuff" Can cause the skin packs to not work properly, with that said it is theoretically possible one could make a custom animation, apply it in both a texture pack and have it registered to a target in a skin pack, to have a custom animation only you and your friends could see as long as they have the texture pack enabled with the skin selected.

**Patching?**

The chance of this getting patched is slim. As majority of servers have a built in skin anti-cheat and players can just disable non trusted skins, in their settings. But this doesnt mean mojang cant or wont revoke this feature from us if abused in a way they see unfit.
