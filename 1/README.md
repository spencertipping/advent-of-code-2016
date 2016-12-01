Part 1:

```sh
$ ni input FWpF_ p'r /^(.)(\d+)/' ,zAp'r 2*a-1, b' ,sA \
           p'^{$x = $y = $t = 0} $x += b * sin(a * 3.141592/2);
                                 $y += b * cos(a * 3.141592/2);
                                 ();
             END {r abs($x) + abs($y)}'
```

Part 2:

```sh
$ ni input FWpF_ p'r /^(.)(\d+)/' ,zAp'r 2*a-1, b' ,sA \
           p'^{$x = $y = 10000}
             for (1..b) {
               $x += sin(a * 3.141592/2);
               $y += cos(a * 3.141592/2);
               $x = int .5 + $x; $y = int .5 + $y;
               r $x, $y, abs($x - 10000) + abs($y - 10000) if ++$h{"$x,$y"} > 1;
             }'

```
