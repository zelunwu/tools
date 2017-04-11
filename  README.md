XML configuration files for compiling MATLAB MEX-files using VS2017.
Tested on Windows 10 64-bit with MATLAB R2016b, Visual Studio 2017 (Enterprise Edition).

First copy the files to `MATLABROOT\bin\win64\mexopts` (this might trigger a UAC prompt).
Next run `mex -setup` and `mex -setup C++` in MATLAB, and select VS2017 compilers.
Finally test the new settings with a sample MEX-file:

```matlab
>>> mex -v -largeArrayDims test.cpp
>>> test()
```
```cpp
#include "mex.h"
void mexFunction(int nlhs, mxArray *plhs[], int nrhs, const mxArray*prhs[])
{
    plhs[0] = mxCreateDoubleScalar(42);
}
```
