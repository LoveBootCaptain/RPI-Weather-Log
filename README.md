# RPI-Weather-Log
A complete weather station for the RaspberryPi, using forecast.io and adafruit sensors to log all weather data to a file which can be used for SPLUNK data analysis.

## Install

`cd`

`git clone https://github.com/LoveBootCaptain/RPI-Weather-Log.git`

`cd RPI-Weather-Log`

`cp config.example.json config.json`

`sudo nano config.json`

Replace the "xxxx..." with your forecast.io-API-KEY in `"FORECAST_IO_KEY"`.
Replace the "xxxx..." with your Adafruit.io-API-KEY in `"ADAFRUIT_IO_KEY"`.

Change the size of the log file in `"LOG_SIZE"` (in Bytes). 10MB is default.
Change the number of log file backups in `"BACKUP_COUNT"`. 100 is default.
Change the refresh rate of weather data in `"REFRESH_RATE"`. 5min is default.

`CTRL + S` for save
`CTRL + X` for quit

`sudo chmod +x rpi_weather_log.sh` make the .sh script executable, this will run as service

`sudo mv rpi_weather_log.sh /etc/init.d` move the script to /etc/init.d so it can be used in CLI

`sudo shutdown -r now` reboot

## Test

To test if everything is set up correctly just try:

`sudo service rpi_weather_log start`

If everything is working correctly you can run the service on boot with:

`sudo update-rc.d rpi_weather_log defaults`