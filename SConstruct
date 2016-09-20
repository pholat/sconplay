#!/bin/python

env = Environment();

# Product of this for loop wont be available in glob in Program(...) below
for a in range(1,41):
    SConscript('lib'+str(a)+'/SConscript', exports=['env'])

prog = env.Program('prog',['main.cpp'] + Glob('bin/*/*.a') )
Alias('program',prog)
