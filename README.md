# 🌡️ Rack Panel Fan Controller (ESPhome) 🌀

This is an ESPhome configuration for a rack panel fan controller with a thermostat and a small OLED SSD1306 64x48 display. The fan controller adjusts the fan speed based on temperature thresholds, and the display shows temperature, fan speed, and other information.

## 📋 Features

- Temperature monitoring using the SHT3xD sensor
- Automatic fan speed control based on temperature thresholds
- Manual fan speed control
- OLED display with multiple pages
- Display of temperature, fan speed, and other information
- Configurable temperature thresholds and minimum fan speed

## 🛠️ Requirements

- ESP8266-based board (e.g., Wemos D1 Mini)
- SSD1306 OLED display (64x48)
- SHT3xD temperature and humidity sensor
- Fan compatible with PWM control
- ESPhome

## 🔧 Installation

1. Copy the provided ESPhome configuration to your project's YAML file.
2. Replace the following placeholders with your own values:
    - `!secret wifi_ssid`: Your WiFi SSID
    - `!secret wifi_password`: Your WiFi password
    - `!secret ota_password`: A password for OTA updates
    - `!secret wifi_ap_password`: A password for the fallback hotspot
3. Compile and upload the firmware to your ESP8266 board using ESPhome.
4. After uploading, the device will automatically connect to your WiFi network and register itself in Home Assistant.

## 🎛️ Usage

The fan controller will automatically adjust the fan speed based on the temperature thresholds set in the configuration. You can also manually control the fan speed using the Home Assistant dashboard.

The OLED display will show multiple pages with the following information
- Temperature graph 📈
- IP address, temperature, and fan speed 🌡️💨
- Current date and time 📅⏰
- Cube animation 🎲

The display pages will switch automatically every 7.5 seconds.

## ⚙️ Configuration Options

You can customize the following configuration options to better suit your needs:

- `device_name`: The device's name used for the MQTT topic.
- `friendly_name`: A user-friendly name for the device.
- `device_description`: A description of the device.
- `temperature_threshold_low`: The temperature (in Celsius) at which the fan will start at its minimum speed.
- `temperature_threshold_high`: The temperature (in Celsius) at which the fan will run at its maximum speed.
- `minimum_fan_speed`: The minimum fan speed (in percentage) when the temperature reaches the lower threshold.

## ❓ Troubleshooting

If the device cannot connect to your WiFi network, it will create a fallback hotspot with the SSID "Noctua Fallback Hotspot" and the password you set in the `!secret wifi_ap_password` placeholder. Connect to this hotspot and navigate to `192.168.4.1` to access the captive portal. Here, you can configure the WiFi credentials for your network.

## 🎨 Customization

You can further customize the display pages or add more pages by modifying the `lambda` functions in the `display` section of the configuration. For example, you can add new elements, change the text formatting, or modify the layout.

## 📜 License

This ESPhome configuration is provided under the MIT License. You are free to use, modify, and distribute this configuration, provided that you give appropriate credit to the original author and include the license notice in any copies or modified versions.
