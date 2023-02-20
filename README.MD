[Original THingiverse post](https://www.thingiverse.com/thing:4781812)

The Cube is an optical filament motion sensor designed to use your old direct drive hobb gear extruder, The body mimics a Nema 17 stepper so almost any extruder kit can be used to guild the filament. The encoder has 36 slots and should provide down to 2mm jam or runout detection. I have tested it running at 5mm.
It will work with whatever size filament your extruder kit can handle and since it's driving an encoder wheel material transparency isn't an issue.

It uses a standard red board optical end stop with the socket on the opposite side from the sensor.

The concept was to build an motion sensor using standard 3D printer parts you may have as spares and common fasteners you can get at your local hardware store

The body has cavities for 8 M3 nuts that will be embedded in the print using the pause and insert function ( see your slicer documentation)

The back cover has a 31mm bolt circle so it should fit most Nema17 motor mounts
It's a simple block so it can easily be remixed into a custom mount of your design

Hardware needed.

A single hobb extruder kit        
m5 x40 hex bolt - pan , hex or socket head will work.      
M5 nut      
8 x M3 x 14mm screws      
8 M3 nuts      
2 x m3 x 6 screws      
2 x 625 bearings ( I scavenged some from old carriage wheels )      
Whatever M3 lengths your extruder needs      
1 optical end stop      

You need to have M600 Filament change enabled in Marlin and M412 enabled for runout detection with a runout distance set. If Marlin does not see a pulse from the sensor in the set filament runout distance it will trigger an M600 to unload and let you re feed the filament.

I'll work on adding notes to configure Filament change in Marlin.

In Reprap (Duet) I have it set for 0.6 pulses pr mm. I got the following results after monitoring it's output on a print.

M591 D0
Pulse-type filament monitor on pin servo0, disabled, sensitivity 0.977mm/pulse, allowed movement 60% to 160%, check every 3.0mm, measured sensitivity 0.982mm/pulse, measured minimum 97%, maximum 102% over 81.5mm
