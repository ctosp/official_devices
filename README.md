Updater
=======
Simple application to download and apply OTA packages.

Uploading
----------

Get your devices.jason as format in shown server requirements and Pull Request at this link: https://github.com/ctosp/official_devices as below example 

Example:
ctosp/official_devices/master/whyred/devices.json

create a folder as shown in example and paste your generated changelog in changelog.txt then Pull Request at this link: https://github.com/ctosp/official_devices as below

Example:
ctosp/official_devices/master/changelogs/whyred/changelog.txt

Server requirements
-------------------
The app sends `GET` requests to the URL defined by the `ota_server_url`
resource (or the `ctosp.ota.uri` system property) and expects as response
a JSON with the following structure:
```json
{
  "response": [
    {
      "datetime": "1558539782",
      "filename": "CTOSP-v2.0-20190523-whyred-OFFICIAL.zip",
      "id": "6f8334dee9387bfaa23d12e33cf458f0",
      "romtype": "OFFICIAL",
      "size": 719282414,
      "url": "https://master.dl.sourceforge.net/project/ctosp/whyred/CTOSP-v2.0-20190523-whyred-OFFICIAL.zip",
      "version": "v2.0"
    }
  ]
}
```

The `datetime` attribute is the build date expressed as UNIX timestamp.  
The `filename` attribute is the name of the file to be downloaded.  
The `id` attribute is a string that uniquely identifies the update.  
The `romtype` attribute is the string to be compared with the `ro.ctosp.buildtype` property.  
The `size` attribute is the size of the update expressed in bytes.  
The `url` attribute is the URL of the file to be downloaded.  
The `version` attribute is the string to be compared with the `ro.ctosp.build.version` property.  

Additional attributes are ignored.