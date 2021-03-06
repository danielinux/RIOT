include ../Makefile.tests_common

BOARD_INSUFFICIENT_MEMORY := arduino-duemilanove arduino-leonardo arduino-nano \
                             arduino-uno chronos msb-430 msb-430h \
                             nucleo-f031k6 telosb wsn430-v1_3b wsn430-v1_4 z1

USEMODULE += xtimer

USEPKG += u8g2

# set default device parameters in case they are undefined
TEST_OUTPUT ?= 1

TEST_I2C ?= 0
TEST_SPI ?= 0

TEST_ADDR ?= 0x3c

TEST_PIN_CS ?= GPIO_PIN\(0,0\)
TEST_PIN_DC ?= GPIO_PIN\(0,0\)
TEST_PIN_RESET ?= GPIO_PIN\(0,0\)

ifeq ($(TEST_OUTPUT),3)
TEST_DISPLAY ?= u8g2_Setup_ssd1306_128x64_noname_1
endif

ifeq ($(TEST_OUTPUT),4)
TEST_DISPLAY ?= u8g2_Setup_ssd1306_i2c_128x64_noname_1
endif

# features depend on output type
ifeq ($(TEST_OUTPUT),1)
USEMODULE += u8g2_utf8
endif

ifeq ($(TEST_OUTPUT),2)
USEMODULE += u8g2_sdl
endif

ifeq ($(TEST_OUTPUT),3)
FEATURES_REQUIRED += periph_gpio periph_spi
endif

ifeq ($(TEST_OUTPUT),4)
FEATURES_REQUIRED += periph_gpio periph_i2c
endif

# export parameters
CFLAGS += -DTEST_OUTPUT=$(TEST_OUTPUT)

CFLAGS += -DTEST_SPI=$(TEST_SPI)
CFLAGS += -DTEST_I2C=$(TEST_I2C)

CFLAGS += -DTEST_ADDR=$(TEST_ADDR)

CFLAGS += -DTEST_PIN_CS=$(TEST_PIN_CS)
CFLAGS += -DTEST_PIN_DC=$(TEST_PIN_DC)
CFLAGS += -DTEST_PIN_RESET=$(TEST_PIN_RESET)

CFLAGS += -DTEST_DISPLAY=$(TEST_DISPLAY)

# HACK Blacklist native as `murdock` fails on utf-8 characters for native tests
TEST_ON_CI_BLACKLIST += native

include $(RIOTBASE)/Makefile.include
