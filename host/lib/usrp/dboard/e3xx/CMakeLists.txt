#
# Copyright 2018 Ettus Research, a National Instruments Company
#
# SPDX-License-Identifier: GPL-3.0-or-later
#

IF(ENABLE_E300 OR ENABLE_E320)
        LIST(APPEND E3XX_SOURCES
        ${CMAKE_CURRENT_SOURCE_DIR}/e3xx_radio_ctrl_impl.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/e3xx_radio_ctrl_init.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/e3xx_ad9361_iface.cpp
        ${CMAKE_CURRENT_SOURCE_DIR}/e3xx_bands.cpp
    )
    LIBUHD_APPEND_SOURCES(${E3XX_SOURCES})
ENDIF(ENABLE_E300 OR ENABLE_E320)

IF(ENABLE_E300)
        MESSAGE(STATUS "E300 Enabled")
        LIST(APPEND E300_SOURCES
        ${CMAKE_CURRENT_SOURCE_DIR}/e31x_radio_ctrl_impl.cpp
    )
    LIBUHD_APPEND_SOURCES(${E300_SOURCES})
ENDIF(ENABLE_E300)

IF(ENABLE_E320)
        MESSAGE(STATUS "E320 Enabled")
        LIST(APPEND E320_SOURCES
        ${CMAKE_CURRENT_SOURCE_DIR}/e320_radio_ctrl_impl.cpp
    )
    LIBUHD_APPEND_SOURCES(${E320_SOURCES})
ENDIF(ENABLE_E320)
