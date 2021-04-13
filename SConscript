import os
import shutil

Import('rtconfig')
from building import *

cwd = GetCurrentDir()
src	= Glob('pdfgen.c')

CPPPATH = [cwd]

#delate non-used files
try:
    shutil.rmtree(os.path.join(cwd,'.github'))
    shutil.rmtree(os.path.join(cwd,'data'))
    shutil.rmtree(os.path.join(cwd,'tests'))
    os.remove(os.path.join(cwd,'.clang-format'))
    os.remove(os.path.join(cwd,'appveyor.yml'))
    os.remove(os.path.join(cwd,'Dockerfile'))
    os.remove(os.path.join(cwd,'docker-launch.sh'))
    os.remove(os.path.join(cwd,'Makefile'))
    os.remove(os.path.join(cwd,'pdfgen.dox'))
    os.remove(os.path.join(cwd,'tests.sh'))
    os.remove(os.path.join(cwd,'TODO'))
except:
    pass

group = DefineGroup('PDFGen', src, depend = ['PKG_USING_PDFGEN'], CPPPATH = CPPPATH)

Return('group')
