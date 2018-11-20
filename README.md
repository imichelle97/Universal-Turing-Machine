# Universal Turing Machine

#### Building blocks:
* setUp
* checkState
* checkInput
* pop
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
1C1011D1010m011011D11010m011011D1101101101110mD11101101101110mD1110m010111101F101111S
```

After checkState (will refactor code later) - ends at 1 after C
```
XC1011Dx010m011011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S
```

After checkInput (will refactor code later) - ends at 0 after Y
```
XCY011Dx0y0m011011Nx1010m011011Nx101101101110mNx1101101101110mNx110m010111101F101111S
```
