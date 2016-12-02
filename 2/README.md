Part 1:

```sh
$ ni input F//p'r FR 1' p'^{$x=$y=1} /U/?--$y:/L/?--$x:/R/?++$x:++$y, $x=min(2,max(0,$x)), $y=min(2,max(0,$y)) for F_; $x+$y*3+1'
```

Part 2:

```sh
$ ni input F//p'r FR 1'    p'^{$x=0, $y=2, @letters = split //, "  1   234 56789 ABC   D  "}
     $lx=$x, $ly=$y,
     (/U/?--$y:/L/?--$x:/R/?++$x:++$y),
     $y=max(0, min 4, $y), $x=max(0, min 4, $x),
       ($letters[$x+$y*5] eq " " and ($x, $y) = ($lx, $ly))
     for F_;
     r $x, $y, $letters[$x+$y*5]'
```
