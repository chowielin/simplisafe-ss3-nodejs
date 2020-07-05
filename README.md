# NOTE
This project is archived and no longer maintained. Please instead refer to: https://github.com/nzapponi/homebridge-simplisafe3

# simplisafe-ss3
SimpliSafe ss3 versioned REST API NodeJS client
# Install
`npm install -g simplisafe-ss3`
# Usage
```
var SS3Client = require('simplisafe-ss3')
var ss3Client = new SS3Client('username', 'password')
```
## Login
```
ss3Client.login()
		.then(function() {
			console.log('User ID: ' + ss3Client.userId)
			console.log('Sub ID: ' + ss3Client.subId)
			console.log('Token: ' + ss3Client.token)
		}, function(err) {
			console.log('Login failed due to: ' + err.message)
			throw err
		})
```
## Logout
```
ss3Client.logout()
		.then(function() {
			console.log('Logged out')
		})
```
## Get Alarm State
```
ss3Client.getAlarmState()
		.then(function(alarmState) {
			console.log('Alarm state: ' + alarmState)
		})
```
## Set Alarm State
```
// One of 'off', 'home', 'away'
ss3Client.setState('away')
		.then(function() {
			console.log('Alarm state was set')
		})
```
## Get Sensors
```
// Useful for getting the states of the sensors like entry sensors, water sensors, smoke sensors, etc.
ss3Client.getSensors()
		.then(function(sensors) {
			// do something with sensor data
		})

/*
{
  "account": "xxx",
  "success": true,
  "sensors": [
    {
      "status": {

      },
      "setting": {
        "alarm": 1
      },
      "name": "Master BR",
      "serial": "xxx",
      "type": 3,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {

      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 0,
        "home": 0,
        "off": 0
      },
      "name": "Family Room",
      "serial": "xxx",
      "type": 4,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {

      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 0,
        "home": 0,
        "off": 0
      },
      "name": "Dining Room",
      "serial": "xxx",
      "type": 4,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {

      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 0,
        "home": 0,
        "off": 0
      },
      "name": "Upstairs",
      "serial": "xxx",
      "type": 4,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "alarm": 1
      },
      "name": "Powder Room",
      "serial": "xxx",
      "type": 9,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "alarm": 1
      },
      "name": "Bathroom",
      "serial": "xxx",
      "type": 9,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "alarm": 1
      },
      "name": "Master Bath",
      "serial": "xxx",
      "type": 9,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "alarm": 1
      },
      "name": "Waterheater",
      "serial": "xxx",
      "type": 9,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "test": false,
        "tamper": false,
        "malfunction": false,
        "triggered": false
      },
      "setting": {

      },
      "name": "Bedroom",
      "serial": "xxx",
      "type": 8,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "test": false,
        "tamper": false,
        "malfunction": false,
        "triggered": false
      },
      "setting": {

      },
      "name": "Office",
      "serial": "xxx",
      "type": 8,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {

      },
      "setting": {
        "alarmVolume": 3,
        "doorChime": 0,
        "exitBeeps": 2,
        "entryBeeps": 2
      },
      "name": "Front Door",
      "serial": "xxx",
      "type": 13,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 1,
        "home": 1,
        "off": 0
      },
      "name": "Patio Door",
      "serial": "xxx",
      "type": 5,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 1,
        "home": 1,
        "off": 0
      },
      "name": "Back Door",
      "serial": "xxx",
      "type": 5,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 1,
        "home": 1,
        "off": 0
      },
      "name": "Front Door",
      "serial": "xxx",
      "type": 5,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {
        "triggered": false
      },
      "setting": {
        "instantTrigger": false,
        "away2": 1,
        "away": 1,
        "home2": 1,
        "home": 1,
        "off": 0
      },
      "name": "Garage",
      "serial": "xxx",
      "type": 5,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    },
    {
      "status": {

      },
      "setting": {
        "lowPowerMode": false,
        "alarm": 1
      },
      "name": "Front Door",
      "serial": "xxx",
      "type": 1,
      "flags": {
        "swingerShutdown": false,
        "lowBattery": false,
        "offline": false
      }
    }
  ],
  "lastUpdated": 1523220141,
  "lastSynced": 1523220141,
  "lastStatusUpdate": 1523220138
}
*/
```
