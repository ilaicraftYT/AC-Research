Between all the research, you will find a Math/MathUtils static class, here you can see all the functions included on it

### Function `getVectorOnEyeHeight`
This function takes a `Player` object and returns the player's location in the game by adding the player's eye height to their current location.

The mathematical formula is as follows:

Let $P$ be the player's current position, $h$ be the player's eye height, and $P'$ be the resulting position after adding the player's eye height to their current position.

$$
P' = P + \begin{pmatrix} 0 \\ h \\ 0 \end{pmatrix}
$$
Programtically:
```php
$player->getLocation()->add(0, $playerAPI->getPlayer()->getEyeHeight(), 0);
```


### Function `getDeltaDirectionVector`
This function takes a `Player` object and a distance $d$ and returns the player's direction vector multiplied by the given distance.

The mathematical formula is as follows:

Let $d$ be the given distance, $v$ be the player's direction vector, and $v'$ be the resulting vector after multiplying $v$ by $d$.

$$
v' = v \cdot d
$$

Programtically:
```php
$player->getDirectionVector()->multiply($distance);
```

### Function `distance`
This function takes two `Vector3` objects and returns the distance between them.

The mathematical formula is as follows:

Let $v_1$ and $v_2$ be the two given vectors and $d$ be the resulting distance.

$$
d = \sqrt{(v_{1x} - v_{2x})^2 + (v_{1y} - v_{2y})^2 + (v_{1z} - v_{2z})^2}
$$
Programtically:
```php
sqrt(pow($from->getX() - $to->getX(), 2) + pow($from->getY() - $to->getY(), 2) + pow($from->getZ() - $to->getZ(), 2));
```

### Function `pingFormula`
This function takes a ping number and returns an integer value representing the ping divided by 50 and rounded up to the next integer.

The mathematical formula is as follows:

Let $p$ be the given ping number and $n$ be the resulting integer value.

$$
n = \left\lceil\frac{p}{50}\right\rceil
$$
Programtically:
```php
return (int)ceil($ping / 50);
```