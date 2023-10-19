# New Features in Mystic Lugormod

## New command: `/grab`
The `/grab` command allows admins to "grab" an entity, and to drag it around by moving their character.
- `/grab` (without arguments) grabs the entity you're aiming at
- `/grab [entity]` grabs the specified entity (e.g. `/grab 42`)

You can adjust the distance between the grabbed entity and your character by using the `/GrabOffsetIncrease` and
`/GrabOffsetDecrease` commands.

You could bind them to e.g. `NUMPAD +` and `NUMPAD -` with:
- `bind kp_plus GrabOffsetIncrease`
- `bind kp_minus GrabOffsetDecrease`

**Tip:** Move your character with `noclip` for easier positioning.

Use `/grab` again to drop the entity.

**Tip:** If you ever have trouble releasing an entity using just `/grab`, you can always specify the entity number
(e.g. `/grab 42`) to drop it.

## New commands: `/GrabX`, `/GrabY`, `/GrabZ`
These commands allow admins to rotate entities along the corresponding axis, by rotating their character in a
right / left direction.

For instance, since `Z` is the vertical axis, using `/GrabZ` rotates the entity along the vertical axis.  
That is to say, its coordinates are rotated in the horizontal plane (`XY`).

As with `/grab`, they can be used:
- Either without arguments (e.g. `/GrabX`) to rotate the entity you're aiming at,
- Or by specifying the entity number (e.g. `/GrabX 42`)

**Note:** These 3 commands implement a "snapping" behavior:  
When the angles are close to 0, 90, 180 or 270 degrees, they get rounded to those values.  
It makes it easier to align entities horizontally, vertically, or against (most) walls.

`/GrabOffsetIncrease` and `/GrabOffsetDecrease` have no effect on these 3 commands, as the entity only rotates along its
center, and stays in the same location.

To drop the entity, use `/GrabX [entity]`, `/GrabY [entity]`, or `/GrabZ [entity]`.

## New command: `/clone`
The `/clone` command allows admins to clone entities.

It can be used:
- Either without arguments, to clone the entity you're aiming at,
- Or by specifying the entity number (e.g. `/clone 42`)

The cloned entity is automatically grabbed (as if you used the `/grab` command on it).

## New command: `/measure`
`/measure` allows admins to measure distances between 2 points.

Start by using `/measure` to mark the location you're aiming at.  
The command will display the coordinates of that point in the console.  

For instance:

    Marked location: (347 -727 -103)

Then, use `/measure` again to select the second location.  

The command will then give you:
- The coordinates of the second point,
- The total distance between the 2 points (purple),
- The difference between the X coordinates of the 2 points (red)
- The difference between the Y coordinates of the 2 points (green)
- The difference between the Z coordinates of the 2 points (blue)

For example:

    (347 -727 -103)->(485 -320 52) 456: 138 406 155

It will also display 4 lines in the 3D environment for 5 seconds, to help you visualize the distances.
- Purple: total distance
- Red: distance along the X axis
- Green: distance along the Y axis
- Blue: distance along the Z axis
