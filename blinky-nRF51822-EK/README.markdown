## Preparation

You need to make slight modifications to make the SDK work under Linux / Mac OS X. First, edit `Makefile.common` in `nrf51822/Source/templates/gcc/`, uncomment the following statements

    ifeq ($(OS),Windows_NT)
    include $(TEMPLATE_PATH)Makefile.windows
    else
    include $(TEMPLATE_PATH)Makefile.posix
    endif

Then you need to clone `Makefile.windows` as `Makefile.posix`. Make sure `GNU_INSTALL_ROOT` in this file points to the correct path.

