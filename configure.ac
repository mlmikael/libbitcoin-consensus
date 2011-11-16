AC_INIT([libbitcoin], [0.1], [genjix@riseup.net])
AC_LANG(C++)
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([-Wall -Werror])
LT_INIT
AC_PROG_CXX
CHECK_GXX_CPP0X
CFLAGS="-ggdb"
CXXFLAGS="-ggdb"
my_CXXFLAGS="$ac_cv_cxx_cpp0x_flag -Wall -pedantic -pthread -Wextra -fstack-protector-all"
AC_SUBST([my_CXXFLAGS])
AX_BOOST_BASE
AX_BOOST_SYSTEM
AX_BOOST_THREAD
AX_BERKELEY_DB_CXX([5.1], [], [AC_MSG_ERROR(Could not find a version of the library)])
PKG_CHECK_MODULES([protobuf], [protobuf >= 2.4])
PKG_CHECK_MODULES([SSL], [libssl >= 0.9])

AC_ARG_WITH([pkgconfigdir], AS_HELP_STRING([--with-pkgconfigdir=PATH],
    [Path to the pkgconfig directory [[LIBDIR/pkgconfig]]]),
    [pkgconfigdir="$withval"], [pkgconfigdir='${libdir}/pkgconfig'])
AC_SUBST([pkgconfigdir])

AC_CONFIG_FILES([Makefile include/bitcoin/Makefile src/Makefile libbitcoin.pc])
AC_OUTPUT
