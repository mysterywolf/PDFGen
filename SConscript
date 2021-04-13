Import('rtconfig')
from building import *

cwd = GetCurrentDir()
src	= Glob('pdfgen.c')

CPPPATH = [cwd]

group = DefineGroup('PDFGen', src, depend = ['PKG_USING_PDFGEN'], CPPPATH = CPPPATH)

Return('group')
