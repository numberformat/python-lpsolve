# LPSolve

Currently the latest python fully supported is Python 2.6

Download and install Python 2.6 and use the official installer.

There must be a registry entry for python 2.6 which is inserted when official installer is used

```sh
# download from
# https://sourceforge.net/projects/lpsolve/files/lpsolve/5.5.2.11/

# lp_solve_5.5.2.11_dev_win64.zip - windows libs (put in path)
# lp_solve_5.5.2.11_Python2.6_exe_win64 - use the installer

## Alternative solution

# As an alternative install the zip into your c:\ drive and setup the path variable

# Expand in: C:\Python-2.6
# PATH=C:\Python-2.6\lpsolve\lib;%PATH%

# start python command line from the C:\Python-2.6\python.exe

# Test program:
```

```py
from lpsolve55 import *
lp = lpsolve('make_lp', 0, 4)
lpsolve('set_verbose', lp, IMPORTANT)
ret = lpsolve('set_obj_fn', lp, [1, 3, 6.24, 0.1])
ret = lpsolve('add_constraint', lp, [0, 78.26, 0, 2.9], GE, 92.3)
ret = lpsolve('add_constraint', lp, [0.24, 0, 11.31, 0], LE, 14.8)
ret = lpsolve('add_constraint', lp, [12.68, 0, 0.08, 0.9], GE, 4)
ret = lpsolve('set_lowbo', lp, 1, 28.6)
ret = lpsolve('set_lowbo', lp, 4, 18)
ret = lpsolve('set_upbo', lp, 4, 48.98)
ret = lpsolve('set_col_name', lp, 1, 'COLONE')
ret = lpsolve('set_col_name', lp, 2, 'COLTWO')
ret = lpsolve('set_col_name', lp, 3, 'COLTHREE')
ret = lpsolve('set_col_name', lp, 4, 'COLFOUR')
ret = lpsolve('set_row_name', lp, 1, 'THISROW')
ret = lpsolve('set_row_name', lp, 2, 'THATROW')
ret = lpsolve('set_row_name', lp, 3, 'LASTROW')
ret = lpsolve('write_lp', lp, 'a.lp')
print lpsolve('get_mat', lp, 1, 2)
78.26
```