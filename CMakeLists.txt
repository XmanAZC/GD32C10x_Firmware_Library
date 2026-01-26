cmake_minimum_required(VERSION 3.15)

add_library(gd32c103 STATIC)

target_compile_definitions(gd32c103 PUBLIC
    USE_STDPERIPH_DRIVER
)

target_sources(gd32c103 PRIVATE
    GD32C10x_standard_peripheral/Source/gd32c10x_adc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_bkp.c
    GD32C10x_standard_peripheral/Source/gd32c10x_can.c
    GD32C10x_standard_peripheral/Source/gd32c10x_crc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_ctc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_dac.c
    GD32C10x_standard_peripheral/Source/gd32c10x_dbg.c
    GD32C10x_standard_peripheral/Source/gd32c10x_dma.c
    GD32C10x_standard_peripheral/Source/gd32c10x_exmc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_exti.c
    GD32C10x_standard_peripheral/Source/gd32c10x_fmc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_fwdgt.c
    GD32C10x_standard_peripheral/Source/gd32c10x_gpio.c
    GD32C10x_standard_peripheral/Source/gd32c10x_i2c.c
    GD32C10x_standard_peripheral/Source/gd32c10x_misc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_pmu.c
    GD32C10x_standard_peripheral/Source/gd32c10x_rcu.c
    GD32C10x_standard_peripheral/Source/gd32c10x_rtc.c
    GD32C10x_standard_peripheral/Source/gd32c10x_spi.c
    GD32C10x_standard_peripheral/Source/gd32c10x_timer.c
    GD32C10x_standard_peripheral/Source/gd32c10x_usart.c
    GD32C10x_standard_peripheral/Source/gd32c10x_wwdgt.c
    CMSIS/GD/GD32C10x/Source/GCC/startup_gd32c10x.s
    CMSIS/GD/GD32C10x/Source/system_gd32c10x.c
)

set(GD32C10x_Firmware_Library_INCLUDE_DIR
    CMSIS/GD/GD32C10x/Include
    CMSIS
    GD32C10x_standard_peripheral/Include
)

target_include_directories(gd32c103 PUBLIC
    ${GD32C10x_Firmware_Library_INCLUDE_DIR}
)

