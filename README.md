Elasticfeed Plugins
===================

Client
------
Create directory for your plugin definition by category e.g. `sensor/weather-on-mars`. Plugin definition is responsible for core logic of your plugin.

Server
------
Create directory for your plugin server definition e.g. `plugins/sensor-weather-on-mars`
```go

package main

import (
  "github.com/feedlabs/elasticfeed/plugin"
  sensor "github.com/feedlabs/elasticfeed-plugin/sensor/weather-on-mars"
)
  
func main() {
	server, err := plugin.Server()
	if err != nil {
		panic(err)
	}
	server.RegisterSensor(new(sensor.Sensor))
	server.Serve()
}

```

Build
-----
You need to get the latest version of `elasticfeed` to build plugin.
```
  go get github.com/feedlabs/elasticfeed
```

Future goals
------------
![image](https://cloud.githubusercontent.com/assets/1843523/7337493/07542bca-ec2c-11e4-8750-383940f06034.png)
