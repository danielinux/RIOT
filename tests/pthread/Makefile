include ../Makefile.tests_common

BOARD_BLACKLIST := arduino-duemilanove arduino-leonardo arduino-mega2560 \
                   arduino-nano arduino-uno jiminy-mega256rfr2 mega-xplained \
                   waspmote-pro
# arduino mega2560 uno duemilanove : unknown type name: clockid_t
# jiminy-mega256rfr2: unknown type name: clockid_t
# mega-xplained: unknown type name: clockid_t

USEMODULE += posix_headers
USEMODULE += pthread

include $(RIOTBASE)/Makefile.include
