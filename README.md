# ws2812b_py3.9 (NeoPixel LED SPI controller)
The rpi5-ws2812 Python library requires Python 3.11 or higher. Therefore, this code is for controlling NeoPixel LEDs via SPI on Python 3.9.

```bash
pip install spidev
```

## this is sample code how to use

```python
import sys
#sys.path.insert(0, 'PATH_TO_LEDCONTROLLER_CODE')
import led_controller

def main():
    SPI_BUS = 0
    SPI_DEVICE = 0
    LED_COUNT = 24

    # led_controller SPI Driver
    driver = led_controller.WS2812SpiDriver(SPI_BUS, SPI_DEVICE, LED_COUNT)
    strip = driver.get_strip()

    # led_controller LED EFFECT FUNCTION EXAMPLE
    led_controller.all_white_on(strip)
    time.sleep(2)
    led_controller.white_rotate(strip, delay=0.1)
    time.sleep(2)
    led_controller.all_off(strip)

if __name__ == '__main__':
    main()

```
