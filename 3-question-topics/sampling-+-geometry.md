# Sampling + Geometry



## Sampling

* **478: Generate Random Point in a Circle**
* **497. Random Point in Non-overlapping Rectangles**
  * Pick a uniformly random integer point from rectangles.
  * Uses weighted random selection by area.
* **528. Random Pick with Weight**
  * Core weighted probability idea used in many geometry-random problems.
* **710. Random Pick with Blacklist**
  * Advanced random mapping / remapping technique.
* **470. Implement Rand10() Using Rand7()**
  * Rejection sampling fundamentals.
* **519. Random Flip Matrix**
  * Random selection without repetition.



## Geometry

* **223. Rectangle Area**
  * Geometry calculations.
* **812. Largest Triangle Area**
  * Coordinate geometry.
* **149. Max Points on a Line**
  * Geometric reasoning with coordinates.
* **1453. Maximum Number of Darts Inside of a Circular Dartboard**
  * Circle geometry.
* **1828. Queries on Number of Points Inside a Circle**
  * Circle inclusion checks.





## Random Point in Polygon

1. Split polygon into triangles.
2. Pick triangle weighted by area.
3. Generate random point inside triangle.

Point in triangle:

$$P=(1-\sqrt{u})A+\sqrt{u}(1-v)B+\sqrt{u}vC$$









