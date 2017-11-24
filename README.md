clone from https://gist.github.com/ea4541d5621f3d62e67029e393e523a0.git
Non-original 

XML configuration files for compiling MATLAB MEX-files using VS2017.
Tested on Windows 10 64-bit with MATLAB R2016b and Visual Studio 2017 (Enterprise Edition),
but it should also work with the Community Edition.

1. First copy the files to `MATLABROOT\bin\win64\mexopts` (this might trigger a UAC prompt).
2. Next run `mex -setup` and `mex -setup C++` in MATLAB, and select VS2017 compilers.
3. Finally test the new settings with a sample MEX-file:

```matlab
>> mex -v -largeArrayDims test.cpp
>> test()
```
```cpp
#include "mex.h"
void mexFunction(int nlhs, mxArray *plhs[], int nrhs, const mxArray*prhs[])
{
    plhs[0] = mxCreateDoubleScalar(42);
}
```
