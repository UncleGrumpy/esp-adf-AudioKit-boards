# Espressif Audio Development Framework

[![Documentation Status](https://readthedocs.com/projects/espressif-esp-adf/badge/?version=latest)](https://docs.espressif.com/projects/esp-adf/en/latest/?badge=latest)

Espressif Systems Audio Development Framework (ESP-ADF) is the official audio development framework for the [ESP32](https://espressif.com/en/products/hardware/esp32/overview), [ESP32-S2](https://www.espressif.com/en/products/socs/esp32-s2) and [ESP32-S3](https://www.espressif.com/en/products/socs/esp32-s3) SoCs.

> Note: The "main" branch of this fork is based off of ESP-ADF v2.4 with the addition of support for the ESP32 Audio Kit v2.2 boards (with es8388 codec) and the older AI Thinker Audio boards with the ac101 codec. The board are nearly impossible to tell apart, if you bought it after mid-to-late 2020 you can be almost certain it has the es8388, if it has an all black antenna it does for sure. The ac1010 codec were used for a limited number of the early AI Thinker Audio boards, these are also labeled v2.2 but have shiny copper traces on the antenna. The ac101 became unavailable and was replaced by the es8388 for the majority of these board. Unless you know for sure your board uses the ac101 you best bet is to try the ESP32-Audio-Kit v2.2 board in `menuconfig->Audio Hal->Audio board` first, if you get a codec failure error and have copper traces on you v2.2 board then you can select ESP32-AiThinker-Audio in menuconfig.
<div align="center"><img src="https://user-images.githubusercontent.com/69995513/167242904-18700bfb-b4dd-4a07-8f1b-d3e4b9b20722.png" alt ="menuconfig->Audio Hal->Audio board" align="center" /></div>

## Overview

ESP-ADF supports development of audio applications for the Espressif Systems SoCs in the most comprehensive way. With ESP-ADF, you can easily add features, develop audio applications from simple to complex:
- Music player or recorder supports audio formats such as MP3, AAC, FLAC, WAV, OGG, OPUS, AMR, TS, EQ, Downmixer, Sonic, ALC, G.711 and etc.
- Play music from sources: HTTP, HLS (HTTP Live Streaming), SPIFFS, SDCARD, A2DP-Source, A2DP-Sink, HFP and etc.
- Integrate Media services such as: DLNA, VoIP and etc.
- Internet Radio
- Voice recognition and integration with online services such as Alexa, DuerOS and etc.

As a general, the ESP-ADF features will be supported as shown below:

<div align="center"><img src="docs/_static/adf_block_diagram.png" alt ="ADF Block Diagram" align="center" /></div>

## Developing with the ESP-ADF

### IDF Version

The following table shows the ESP-IDF versions supported by ESP-ADF at the current time. The lable ![alt text](docs/_static/yes-checkm.png "supported") means supported, and the lable ![alt text](docs/_static/no-icon.png) means not supported.

The ESP-IDF master branch is marked as not supported because the major feature changes it has introduced may cause conflicts with ESP-ADF. Yet, the ADF examples not affected by those feature changes can still run correctly on the IDF master branch.

End of Life IDF branches are marked as not supported, such as ESP-IDF Release/v4.0. See [IDF Supported Periods](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/versions.html#support-periods) for details.


|                       | ESP-IDF <br> Release/v3.3 | ESP-IDF <br> Release/v4.0| ESP-IDF <br> Release/v4.1| ESP-IDF <br> Release/v4.2| ESP-IDF <br> Release/v4.3| ESP-IDF <br> Release/v4.4 | ESP-IDF <br> Master |
|:----------- |:---------------------: | :---------------------:| :---------------------:|:---------------------: | :---------------------:| :---------------------:| :---------------------:|
| ESP-ADF <br> Master  |  ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/no-icon.png "not supported") |  ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") |![alt text](docs/_static/no-icon.png "not supported") |
| ESP-ADF <br> Release/v2.4  | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/no-icon.png "not supported")  | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") <sup> **1** </sup> | ![alt text](docs/_static/no-icon.png "not supported")  |
| ESP-ADF <br> Release/v2.3  | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/no-icon.png "not supported")  | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/yes-checkm.png "supported") | ![alt text](docs/_static/no-icon.png "not supported") | ![alt text](docs/_static/no-icon.png "not supported") |![alt text](docs/_static/no-icon.png "not supported") |


**Note 1:** The built-in IDF branch of ESP-ADF v2.4 is IDF Release/v4.4 at the current time.


### Quick Start

You need one of ESP-IDF versions described in [ESP-ADF Releases](https://github.com/espressif/esp-adf/releases), one of audio boards below and headphones.

**Note:**  If this is your first exposure to ESP-IDF, proceed to **Getting Started** documentation specific for [ESP32](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html), [ESP32-S2](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/get-started/index.html), or [ESP32-S3](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/index.html) SoCs.

Click on one of audio boards shown below to set up and start using ESP-ADF.

### Hardware

Espressif Systems has released a number of boards for ESP-ADF to develop audio applications. Click the links below to learn more information on each board.

It is recommended to use the ESP-ADF master branch, as it has the latest bugfixes and the new features.

|                       | [ESP32-LyraT](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyrat.html) | [ESP32-LyraTD-MSC](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyratd-msc.html) | [ESP32-LyraT-Mini](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyrat-mini.html) | [ESP32-Korvo-DU1906](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-korvo-du1906.html) | [ESP32-S2-Kaluga-1 Kit](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/hw-reference/esp32s2/user-guide-esp32-s2-kaluga-1-kit.html)|[ESP32-S3-Korvo-2](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/user-guide-esp32-s3-korvo-2.html)|
|:----------- |:---------------------: | :---------------------:| :---------------------:|:---------------------: | :---------------------:| :---------------------:|
|  |  [<img src="docs/_static/esp32-lyrat-v4.2-side.jpg" width="120" alt ="ESP32-LyraT Development Board" align="center" />](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyrat.html)  |  [<img src="docs/_static/esp32-lyratd-msc-v2.2.jpg" width="120" alt ="ESP32-LyraTD-MSC Development Board" align="center" />](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyratd-msc.html)  |  [<img src="docs/_static/esp32-lyrat-mini-v1.2.png" width="110" alt ="ESP32-LyraT-Mini Development Board" align="center" />](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-lyrat-mini.html)  |  [<img src="docs/_static/esp32-korvo-du1906-v1.1.png" width="110" alt ="ESP32-Korvo-DU1906 Development Board" align="center" />](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/get-started-esp32-korvo-du1906.html)  |  [<img src="docs/_static/esp32-s2-kaluga-1-kit.png" width="100" alt ="ESP32-LyraT-Mini Development Board" align="center" />](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s2/hw-reference/esp32s2/user-guide-esp32-s2-kaluga-1-kit.html) |  [<img src="docs/_static/esp32-s3-korvo-2-v3.0-overview.png" width="120" alt ="ESP32-S3-Korvo-2 Development Board" align="center" />](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/user-guide-esp32-s3-korvo-2.html) |
| ESP-ADF Master        | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png)   | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) |
| ESP-ADF Release/v2.4  | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png)   | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) |
| ESP-ADF Release/v2.3  | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png)   | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/yes-checkm.png) | ![alt text](docs/_static/no-icon.png "not supported") |

[supported]: https://img.shields.io/badge/-supported-green "supported"
[not supported]: https://img.shields.io/badge/-not%20supported-orange "not supported"



#### Examples

Check folder [examples](examples) that contains sample applications to demonstrate API features of the ESP-ADF.

# Resources

* [Documentation](https://docs.espressif.com/projects/esp-adf/en/latest/index.html) for the latest version of https://docs.espressif.com/projects/esp-adf/. This documentation is built from the [docs directory](docs) of this repository.
* The [esp32.com forum](https://esp32.com/) is a place to ask questions and find community resources. On the forum there is a [section dedicated to ESP-ADF](https://esp32.com/viewforum.php?f=20) users.
* [Check the Issues section on github](https://github.com/espressif/esp-adf/issues) if you find a bug or have a feature request. Please check existing Issues before opening a new one.
* If you're interested in contributing to ESP-ADF, please check the [Contributions Guide](https://esp-idf.readthedocs.io/en/latest/contribute/index.html).
