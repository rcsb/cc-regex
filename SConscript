#
# SConscript for regex-v2.2
# Created: Aug 16, 2006 - Jdw
# Updated: Aug 23, 2006 - Jdw
#             Add object install
#          Mar 30, 2011 - jdw clone environment -
##
Import('env')
env=env.Clone()
#
#if (len(env.subst('$MYDEBUG')) > 0):
#	dict = env.Dictionary()
#	for k,v in dict.items():
#		print  k, " = ", str(v)
#
libName = 'regex'
libSrcList =['src/regcomp.c',
            'src/regexec.c',
            'src/regerror.c',
            'src/regfree.c']

libObjList = [s.replace('.c','.o') for s in libSrcList] 
libIncList =['include/regex.h']

myLib=env.Library(libName,libSrcList)
#
#
env.Install(env.subst('$MY_LIB_INSTALL_PATH'),myLib)
env.Alias('install-lib',env.subst('$MY_LIB_INSTALL_PATH'))
#
env.Install(env.subst('$MY_INCLUDE_INSTALL_PATH'),libIncList)
env.Alias('install-include',env.subst('$MY_INCLUDE_INSTALL_PATH'))
#
env.Install(env.subst('$MY_OBJ_INSTALL_PATH'),libObjList)
env.Alias('install-obj',env.subst('$MY_OBJ_INSTALL_PATH'))
#
env.Default('install-lib','install-include','install-obj')

#
