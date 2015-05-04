## installation notes using PerlDD v0.09

```
tar -xvzf PerlDD-0.09.tgz
cd PerlDD-0.09
patch -p1 < PerlDD-0.07.patch
```

Then change line 1132 of `Cudd.xs` to:

```
RETVAL = Cudd_DumpBlif(dd, len, dds, inames, onames, NULL, file_ptr, 0);
```

and continue:
```
perl Makefile.pl
make
make install
```

run with something like:
```
time perl anzu.pl --dyn -i path/to/spec7.cfg -o out.txt
```
