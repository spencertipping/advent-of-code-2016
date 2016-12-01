```sh
$ ni input FWpF_ p'r /^(.)(\d+)/' ,zAp'r 2*a-1, b' ,sA \
           p'^{$x = $y = $t = 0} $x += b * sin(a * 3.141592/2);
                                 $y += b * cos(a * 3.141592/2);
                                 ();
             END {r abs($x) + abs($y)}'
```
