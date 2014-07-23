# lifx-kinect
Drive all your lifx bulbs in your house with your voice.

## Requirements
* a Kinect plugged on Windows 8+
* Ruby 2.0+ with [official LIFX gem](https://github.com/LIFX/lifx-gem)
* No particulary skills in development

## Recommended
* one (for each room) fanless NUC ( like [Intel DE3815TYKHE](http://www.intel.com/content/www/us/en/nuc/nuc-kit-de3815tykhe.html), low power consumption ) with Windows 8 and a Kinect v2
* one Raspberry as LIFX daemon server
* Small experiences in procedural programmation if you want to customize the Grammar, Voices, or Language you want (i will create a small configuration file later)

## How does it work ?

LIFX team provide a lot of work ex-nihilo in only two years, but there is only 3 official languages API : [Obj-C](https://github.com/LIFX/LIFXKit) for iOS and [Java](https://github.com/LIFX/lifx-sdk-android) for Android and [Ruby](https://github.com/LIFX/lifx-gem) for everything else.

Microsoft created the Kinect for XBox experience, and after trying every voice recognition tools found ([independant opensource projects](http://en.wikipedia.org/wiki/List_of_speech_recognition_software), android, ios hacks...) but the problem is not really the software. Microphone has to be very good to catch words without paying too attention to the noise around in rooms of life in a common house. And if you look at the price on those hardware, it's a real pain.

I finally tried a Kinect bought 15 EUR on ebay.
And my conclusion if that the Kinect is truly at this time the best association of good hardware and good software development kit provided.
Yes it's C#, but it's easy enough to make small orders to drive LIFX bulbs.

Now i have two working kinects, one for each floor, and the source code is only 140 lines in Ruby, and 100 lines in C#.

## Installation

### Kinect

### Ruby LIFX daemon

LIFX bulbs have to be discovered to get addresses, status and to be able to send an order to them. This is a problem if you need a light to power on AS SOON AS you want to, and not 30 seconds after you are in the room (we'll talk later about Z-Wave or 433Mhz interface).

Plus, LIFX bulbs could have be driven directly through, but in real life bulbs and sometimes OFF (by the wall switch), and back ON later etc...

The aim of this daemon is to checkup every minutes and keep updated the list of bulbs awaiting for orders and ready to accept orders immediately.

If you already have downloaded the [official LIFX gem](https://github.com/LIFX/lifx-gem) you can install this two viki files into the examples already provided : 

```
/lifx-gem/examples/
├── auto-off
│   ├── auto-off.rb
│   └── Gemfile
├── identify
│   ├── Gemfile
│   └── identify.rb
├── travis-build-light
│   ├── build-light.rb
│   └── Gemfile
└── viki
    ├── Gemfile
    └── viki.rb
```

And you just have to run the command `bundle`


## Customization

### Robot name : how can i change the name 'viki' to something else ?

### Grammar : how can i make the words  ?

### Trigger events : how can i make 'viki' to call other webervices and talk back the answer ?

#What is LIFX ?

LIFX are Wi-Fi RGB bulbs with an awesome API to make everything you want to do.
You can see those official presentation videos on kickstarter :

[![ScreenShot](http://img.youtube.com/vi/cRaPQDzkJcQ/0.jpg)](http://youtu.be/cRaPQDzkJcQ)

And the official website : http://www.lifx.co/
