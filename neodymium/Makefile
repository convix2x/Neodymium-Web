# DO NOT TOUCH UNLESS ABSOLUTELY NESSECARY. this is the most delicate fucking makefile ever.

TARGET := iphone:clang:6.0:6.0
INSTALL_TARGET_PROCESSES = neodymium

include $(THEOS)/makefiles/common.mk

APPLICATION_NAME = neodymium

neodymium_FILES = \
    main.m \
    NWAppDelegate.m \
    NWRootViewController.m \
    Libs/utf8proc/utf8proc.c \
    Libs/quickjs/quickjs.c \
    Libs/quickjs/libregexp.c \
    Libs/quickjs/libunicode.c \
    Libs/quickjs/cutils.c \
    Libs/quickjs/dtoa.c \
    $(wildcard Libs/litehtml/src/*.cpp) \
    $(wildcard Libs/litehtml/src/gumbo/*.c)

neodymium_FRAMEWORKS = UIKit CoreGraphics

LITEHTML_INCLUDES = \
    -ILibs \
    -ILibs/quickjs \
    -ILibs/utf8proc \
    -ILibs/litehtml/include \
    -ILibs/litehtml/include/litehtml \
    -ILibs/litehtml/src \
    -ILibs/litehtml/src/gumbo \
    -ILibs/litehtml/src/gumbo/include/ \
    -ILibs/litehtml/src/gumbo/include/gumbo

neodymium_CCFLAGS = \
    -std=c++17 \
    -stdlib=libc++ \
    -frtti \
    -fexceptions \
    -faligned-allocation \
    -Wno-unguarded-availability \
    -D_LIBCPP_DISABLE_AVAILABILITY \
    -DCONFIG_VERSION=\"2024-01-01\" \
    $(LITEHTML_INCLUDES)

neodymium_CFLAGS = \
    -DCONFIG_VERSION=\"2024-01-01\" \
    $(LITEHTML_INCLUDES)

neodymium_LDFLAGS = \
    -stdlib=libc++ \
    -Wl,-lc++abi \
    -Wl,-undefined,dynamic_lookup

include $(THEOS_MAKE_PATH)/application.mk