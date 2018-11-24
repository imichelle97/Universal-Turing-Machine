# Universal Turing Machine

#### Building blocks:
* setUp
* checkState
* checkInput
* pop
* updateState
* push
* reset (optional)
* checkFinal
* accept
* reject
* end

#### Progress
Sample input
```
1011D1010m011011D11010m011011D1101101101110mD11101101101110mD1110m010111101F101111
```

After setUp - ends at first D
```
1C1011D1010m011011D11010m011011D1101101101110mD11101101101110mD1110m010111101F101111S01
```

After checkState - ends at 1 after C
```
XC1011Dx010m011011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S01
```

After checkInput (will refactor code later) - ends at 0 after Y
```
XCY011Dx0y0m011011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S01
```

After pop (z) - ends at 0 in the state that satisfied both initial state, checkInput and Pop
```
XCY011Dx0y0z011011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S01
```

After updateState (c) - End: 0 after last c
```
11CY011Dx0y0z0cc011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S01
```

After push (p) - End: After the last input (Y) ( Note: pp = 111 )
```
11CY011Dx0y0z0cc0ppNx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S010111
```

After reset (reset everything to 0 and 1 except Y) - End: second input
```
11CY011D10101011011D11010m011011D1101101101110mD11101101101110mD1110m010111101F101111S010111
```

After checkState (2) - ends at 1 after C
```
XXCY011Nx0101011011Dxx010m011011Dxx01101101110mNxx101101101110mNxx10m010111101F101111S010111
```

After checkInput (2) - ends at 1 after C
```
XXCY0YYNx0101011011Nxx010m011011Dxx0yy01101110mNxx101101101110mNxx10m010111101F101111S010111
```

After pop (2) - ends at 1 after C ( Note: 111 = pp -> removed)
```
XXCY0YYNx0101011011Nxx010m011011Dxx0yy0pp01110mNxx101101101110mNxx10m010111101F101111S010
```

After updateState (2) - End: 0 after last c
```
111CY0YYNx0101011011Nxx010m011011Dxx0yy0pp0ccc0mNxx101101101110mNxx10m010111101F101111S010
```

After push (2) - End: After the last input (YY)
```
111CY0YYNx0101011011Nxx010m011011Dxx0yy0pp0ccc0mNxx101101101110mNxx10m010111101F101111S010
```

No more input -> checkFinal

After checkFinal -> reject 
```
tttCY0YYNx0101011011Nxx010m011011Dxx0yy0pp0ccc0mNxx101101101110mNxx10m010111101Ft0ttt1S010
```
