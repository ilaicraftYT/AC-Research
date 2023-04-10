>Means unusual range/reach while fighting or placing/breaking blocks.

## Normal values:
**PLAYER FIGHT REACH: 3**. *Can be affected by player's lag.*
**PLAYER BLOCK RANGE: *[UNKNOWN BY RESEARCH]**


## Possible implementations

### API's Check
PocketMine itself doesn't cancels this specific invalid movement, but there's a built-in method for checking locations (but not comparing).

**EntityDamageByEntityEvent** (Entity attacks another entity)

~~~php
$cause = $event->getCause();
$entity = $event->getEntity();
$damager = $event->getDamager();
$locationVictim = $entity->getLocation();
$locationDamager = $damager->getLocation();  
if($cause === EntityDamageEvent::CAUSE_ENTITY_ATTACK && $damager instanceof Player){
    $isPlayerTop = $locationVictim->getY() > $locationDamager->getY() ? ($locationVictim->getY() - $locationDamager->getY()) : 0; # I don't know what does this, but it seems to do false positives without it and some ACs include it
    $distance = Math::distance($locEntity, $locDamager) - $isPlayerTop; # Calcs distance between player and player, see Math file.
        if($distance > 3.2){ # Give some margin
            // Oops! Failed!
        }
    }
~~~

But there's a problem: Some clients seem to bypass this check, i don't know how for now. Probably i did some mistake writing the check.
