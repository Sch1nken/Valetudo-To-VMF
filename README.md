# Valetudo to VMF
This little script can be used to convert [Valetudo](https://github.com/Hypfer/Valetudo) Mapdata (containing segments) to Source-Engine VMF Maps (for use with the Hammer Editor).

In its current state it is neither very flexible nor easily extendable. I don't know if I will ever do aynthing more than this proof of concept. If you're reading this, feel free to go wild with the idea :). 

## Libraries Used
 - [earcut](https://github.com/mapbox/earcut)
 - [simplify-js](https://github.com/mourner/simplify-js)
 - [imagetracerjs](https://github.com/jankovicsandras/imagetracerjs)

## Known Issues
 - Sometimes brushes get malformed(?) and can't be loaded into hammer. This is less likely to happen when simplifying the map first ([See Here](https://github.com/Sch1nken/Valetudo-To-VMF/blob/main/valetudo.html#L331))
 - The generated map is not optimized (lots of triangles). Someone more skilled than me could try to create combined convex shapes from groups if polygons). Hammer can work with any convex 3d shape as a brush.
 - The map does need at least one of the following added to compile (and make sense for CSGO in this case): Skybox (or at the very least cordon bounds), 1+ T-Spawns, 1+ CT-Spawns, Buyzones for each Team, Bombspot/Hostages, at least a light_environment so make it look nicer.

## Thoughts
 - Maybe use Valetudos polygon areas (i.e. No-Go-Zones) to create T/CT-Spawns/BombZones
 - Actually write a maintainable and non-janky script :)