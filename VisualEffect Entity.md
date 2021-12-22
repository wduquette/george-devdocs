# VisualEffect Entity
#doc 

A visual effect entity represents a sprite animation on the map.  Visual effects are rendered last, after base terrain, features, and mobiles.  Every visual effect entity has:

- A `VisualEffect` component, definining an `Animation` to be animated by the [[Animator System]].
- The animation may animate the `VisualEffect` itself, or something else (e.g., a [[Mobile Entity]]).
	- In the former case, the animation will modify the visual effect entity's own `Loc` and `Sprite`
	- The latter case, it will modify the `Loc` and `Sprite` of the target mobile.


