include ../Makefile.tests_common

BOARD_INSUFFICIENT_MEMORY := arduino-duemilanove arduino-leonardo \
                             arduino-mega2560 arduino-nano arduino-uno chronos \
                             i-nucleo-lrwan1 msb-430 msb-430h nucleo-f030r8 \
                             nucleo-f031k6 nucleo-f042k6 nucleo-l031k6 \
                             nucleo-l053r8 stm32f0discovery stm32l0538-disco \
                             telosb waspmote-pro wsn430-v1_3b wsn430-v1_4

USEMODULE += gnrc_ipv6_nib_router
USEMODULE += gnrc_ndp
USEMODULE += gnrc_netif
USEMODULE += embunit
USEMODULE += netdev_ieee802154
USEMODULE += netdev_test

CFLAGS += -DGNRC_NETTYPE_NDP=GNRC_NETTYPE_TEST
CFLAGS += -DGNRC_PKTBUF_SIZE=512
CFLAGS += -DTEST_SUITES

include $(RIOTBASE)/Makefile.include
