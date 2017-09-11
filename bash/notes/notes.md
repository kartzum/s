# Bash

## Code

### Dictionary
```
declare -A PAGE_SIZES
PAGE_SIZES[7]=10
PAGE_SIZES[8]=20
for K in ${!PAGE_SIZES[@]};
do
 V=${PAGE_SIZES[$K]}
 echo $K, $V
done
```

### Loop
```
declare -A PAGE_NUMBERS
PAGE_NUMBERS[7]=`seq 1 2`
PAGE_NUMBERS[8]=`seq 1 3`
for N_ in ${!PAGE_NUMBERS[@]};
do
 V_=${PAGE_NUMBERS[$N_]}
 echo $N_
 for I_ in $V_;
 do
  echo $I_
 done
done
```

### Loop + math operations
```
function loop() {
local -i c=0
while [ $c -lt 10 ];
do
 echo $c
 let c=c+1
done
}
```
### Background Jobs
[Bash Trick: Watching Multiple Background Jobs](http://jeremy.zawodny.com/blog/archives/010717.html)

```
#!/bin/bash

FAIL=0

echo "starting"

./sleeper 1 0 &
./sleeper 1 0 &
./sleeper 2 1 &
./sleeper 1 0 &

for job in `jobs -p`
do
    echo ${job}
    wait ${job} || let "FAIL+=1"
done

echo ${FAIL}

if [ "$FAIL" == "0" ];
then
    echo "YAY!"
else
    echo "FAIL! ($FAIL)"
fi
```

```
#!/usr/bin/perl -w

use strict;

my $time = $ARGV[0] || 1;
my $exit = $ARGV[1] || 0;

sleep $time;
exit  $exit;
```

### Codes

* eq - equal
* ne - not equal
* lt - less than
* le - less than or equal
* gt - greater than
* ge - greater than or equal

