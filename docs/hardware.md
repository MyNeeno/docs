---
hide:
  - footer
---

<p style="text-align: right;">Go to <a href="https://myneeno.com">myneeno.com</a></p>

---

# Hardware

## Description

The Neeno Armband is fitted with a powerful Nordic nRF52840 SoC and a set of
sensors measuring muscle activity and motion.

It can be easily connected to a computer or smartphone via BLE, and is equipped
with a USB-C connector for charging and data transfer, if required. Its
built-in battery can provide several hours of continuous operation on a single
charge.

## Specs

<div class="center-table" markdown>

| Features              |                                       |
|-----------------------|---------------------------------------|
| Processor             | Nordic nRF52840                       |
| Architecture          | ARM Cortex-M4                         |
| Clock Speed           | 64 MHz                                |
| Flash Memory          | 1 MB                                  |
| Connector             | USB-C                                 |
| Sensors               | Accelerometer, Gyroscope, surface EMG |
| Output Data Rate (Hz) | 40, 50, 100, 200, 400                 |
| Mean latency (ms)     | 28                                    |
| Battery               | 250 mAh                               |
| Board dimensions      | 45 x 22 x 18 mm                       |
| Weight                | 25 g                                  |

</div>

## Improvements

So far, there are two versions of the Neeno armband in the wild:

- **Neeno 1**, the very first released version back in 2023, but its
  development has been discontinued.

- **Neeno 2**, released in 2024, is the one we are currently focusing on, and
  it is the subject of most of the documentation you will find here.

Neeno 2, the successor of the very first Neeno Armband, comes with siginificant
improvements and new features:

- **USB-C Connector**: In contrast to the initial Micro USB, this connector is
  more durable and easier to use.

- **Improved Battery Life**: The Neeno 2 has a smaller battery, but it is more
  efficiently handled, which results in a longer battery life.

- **Smaller and Lighter**: a reduced print size and weight making it more
  comfortable to wear, going from 44 to 25 g (without straps.)

- **Improved Sensors**: Now with an upgraded 6-axis IMU sensor, which is more
  reliable than the 9-axis sensor previously used.

- **Improved Data Rate**: The Neeno 2 has an improved data rate, which allows
  for faster and more accurate data collection.

- **Reduced Latency**: A dramatically reduced latency makes it very responsive,
  going from 100 ms to 28 ms. And we still aim to further reduce it.

A wide range of software tools and libraries is constantly developed to make it
easy to integrate into existing workflows, allowing users to customize and
extend its functionality as desired.

Head to the [Software](software.md) section
to learn more about the software side of the Neeno Armband.
