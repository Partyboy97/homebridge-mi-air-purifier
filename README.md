Features

    Switch on / off.

    Control modes:

      Idle / Off: Lift fan speed to 0% from Home app.

      Auto: Lift fan speed between 1 - 60%.

      Silent: Lift fan speed between 61 - 80%.

      Favorite / High: Lift fan speed great than 80%.

    Switch child lock on / off.

    Switch LED light on / off.

    Switch buzzer sound on / off.

    Display temperature.

    Display humidity.

    Display air quality.

Installation

    Install required packages.

    npm install -g homebridge-mi-air-purifier miio

    ​

    Make sure your Homebridge server is same network with your air purifier, then run following command to discover the token.

    miio discover --sync

    You may need to wait few minutes until you get the response similar to below:

    Device ID: 49466088
    Model info: Unknown
    Address: 192.168.1.8
    Token: 6f7a65786550386c700a6b526666744d via auto-token
    Support: Unknown

    ​

    Record down the Address and Token values as we need it in our configuration file later.

    If you are getting ?????????????? for your token value, please reset your device and connect your Homebridge server directly to the access point advertised by the device.

    Then run the command again.

    miio discover --sync

    ​

    Add following accessory to the config.json.

      "accessories": [
        {
          "accessory": "MiAirPurifier",
          "name": "Bed Room Air Purifier",
          "ip": "ADDRESS_OF_THE_AIR_PURIFIER",
          "token": "TOKEN_FROM_STEP_3",
          "showTemperature": true,
          "showHumidity": true,
          "showAirQuality": true,
          "showLED": true,
          "showBuzzer": true
        },
        {
          "accessory": "MiAirPurifier",
          "name": "Living Room Air Purifier",
          "ip": "ADDRESS_OF_THE_AIR_PURIFIER",
          "token": "TOKEN_FROM_STEP_3",
          "showTemperature": true,
          "showHumidity": true,
          "showAirQuality": true,
          "showLED": true,
          "showBuzzer": true
        }
      ]

    Notes: Set value for showTemperature, showHumidity, showAirQuality, showLED, showBuzzer to true or false to show or hide these sensors in Home app.

    ​

    Restart Homebridge, and your Mi air purifier will be added to Home app.

License

See the LICENSE file for license rights and limitations (MIT).
