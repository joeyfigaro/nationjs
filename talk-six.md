# Making music with the web audio API (@stevekinney, steve@turing.io)
**github.com/stevekinney/making-music**
**github.com/stevekinney/octavian**

## Web Audio API
- starts with context
` window.AudioContext || window.webkitAudioContext;`
`new AudioContext();`

## Contexts
- sound sources
- destination
`let oscillator = context.createOscillator();`
`oscillator.connect(audioDestination);`
`oscillator.start(0);`
`oscillator.stop(0);`
`oscillator.disconnect(0);`

## Sound sources
- oscillator (make soundwaves: wavelength, amplitude)
- getusermedia api for microphone
- load a file


## Research and Tools
*facetrackingEvent*
Orientation APIs
WebRTC
Gamepad API
