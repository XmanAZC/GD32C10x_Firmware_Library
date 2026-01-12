import rtconfig
from building import *

# get current directory
cwd = GetCurrentDir()

path = [
    cwd + '/CMSIS/GD/GD32C10x/Include',
    cwd + '/CMSIS',
    cwd + '/GD32C10x_standard_peripheral/Include',]

CPPDEFINES = ['USE_STDPERIPH_DRIVER']

# The set of source files associated with this SConscript file.

src = Split('''
CMSIS/GD/GD32C10x/Source/GCC/startup_gd32c10x.s
CMSIS/GD/GD32C10x/Source/system_gd32c10x.c
GD32C10x_standard_peripheral/Source/gd32c10x_gpio.c
GD32C10x_standard_peripheral/Source/gd32c10x_rcu.c
GD32C10x_standard_peripheral/Source/gd32c10x_dma.c
GD32C10x_standard_peripheral/Source/gd32c10x_exti.c
GD32C10x_standard_peripheral/Source/gd32c10x_misc.c
GD32C10x_standard_peripheral/Source/gd32c10x_fmc.c
''')

if GetDepend(['RT_USING_SERIAL']) or GetDepend(['BSP_USING_UART']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_usart.c']

if GetDepend(['RT_USING_I2C']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_i2c.c']

if GetDepend(['RT_USING_SPI']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_spi.c']
    
if GetDepend(['BSP_USING_SPI_SLAVE']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_spi.c']

if GetDepend(['RT_USING_CAN']) or GetDepend(['BSP_USING_CAN']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_can.c']

if GetDepend(['RT_USING_ADC']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_adc.c']

if GetDepend(['RT_USING_DAC']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_dac.c']

if GetDepend(['RT_USING_RTC']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_rtc.c']
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_pmu.c']

if GetDepend(['RT_USING_WDT']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_wwdgt.c']
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_fwdgt.c']

if GetDepend(['BSP_USING_SDRAM']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_exmc.c']

if GetDepend(['RT_USING_PWM']) or GetDepend(['BSP_USING_PWM']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_timer.c']

if GetDepend(['BSP_USING_USB_HID']):
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_pmu.c']
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_timer.c']
    src += ['GD32C10x_standard_peripheral/Source/gd32c10x_ctc.c']
    src += ['GD32C10x_usbfs_library/driver/Source/drv_usb_core.c']
    src += ['GD32C10x_usbfs_library/driver/Source/drv_usb_dev.c']
    src += ['GD32C10x_usbfs_library/driver/Source/drv_usbd_int.c']
    src += ['GD32C10x_usbfs_library/driver/Source/drv_usbd_int.c']
    src += ['GD32C10x_usbfs_library/device/core/Source/usbd_core.c']
    src += ['GD32C10x_usbfs_library/device/core/Source/usbd_enum.c']
    src += ['GD32C10x_usbfs_library/device/core/Source/usbd_transc.c']
    src += ['GD32C10x_usbfs_library/device/class/hid/Source/standard_hid_core.c']
    CPPDEFINES += ['USE_USB_FS']
    path += [cwd + '/GD32C10x_usbfs_library/driver/Include']
    path += [cwd + '/GD32C10x_usbfs_library/device/core/Include']
    path += [cwd + '/GD32C10x_usbfs_library/device/class/hid/Include']
    path += [cwd + '/GD32C10x_usbfs_library/ustd/common']
    path += [cwd + '/GD32C10x_usbfs_library/ustd/class/hid']

group = DefineGroup('Libraries', src, depend = [''], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')
