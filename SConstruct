#!/bin/python

env0 = Environment();
env1 = Environment();
env2 = Environment();

# Product of this for loop wont be available in glob in Program(...) below
for a in range(1,41):
    env = env0
    SConscript('lib'+str(a)+'/SConscript', duplicates=0, variant_dir = 'bin0/lib'+str(a), exports=['env'])
    env = env1
    SConscript('lib'+str(a)+'/SConscript', duplicates=0, variant_dir = 'bin1/lib'+str(a), exports=['env'])
    env = env2
    SConscript('lib'+str(a)+'/SConscript', duplicates=0, variant_dir = 'bin2/lib'+str(a), exports=['env'])

prog0 = env.Program('prog0',['main.cpp'] + Glob('bin0/*/*.a') )
prog1 = env.Program('prog1',['main.cpp'] + Glob('bin1/*/*.a') )
prog2 = env.Program('prog2',['main.cpp'] + Glob('bin2/*/*.a') )

Alias('program0',prog0)
Alias('program1',prog1)
Alias('program2',prog2)
