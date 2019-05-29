# waterOnTheFire
First-in-Engine Timed Exercise Training Prop

This is my first Node-Red project, hopefully the first of many.

Node-red version 0.20.5

Node.JS version 10.15.3

Thanks to Patrick Murray for his ControlPi rasbian image that was used with some tweaking and updating as the base for this project. https://gitlab.com/patrickmurray/controlpi

Thanks also to my Brother-in-Law who gave me helpful examples and guidance as I ended up diving into learning basic Javascript, which was not even on my radar when I started down this rabbit hole!


I am a volunteer firefighter who has been experimenting with Node-Red and a Raspberry Pi to make training more interesting/fun and introduce a basic level of competitiveness that will hopefully encourage new members to join and get involved.

This project is my first attempt and grew from a Pi Zero W stuck in a hollow vinyl post cover with some LEDs drilled into it and a 5 gallon bucket with a float switch into what it is at this point.

Basic setup is a Pi 3 A+ and two 8xrelays installed in a waterproof box with waterproof connectors drilled into the side that have 50' cables extended to the two props and a power cable extending back to the Engine.

The Hardware is powered vie a PoE+ injector and splitter that is fed from the Engine AC generator. With all relays high and all LEDs lit the total power draw is about 1.7 Amps. Six relays and seven 12 Volt 6-LED clearance lights are used for each prop.

Each prop is two metal 55 gallon drums welded together to create a chute/reservoir target for the hose team.

Goal is for two teams to race each other and the clock to get the best time through a course/series of actions that culminates in filling a prop to a depth of ~20". The props are continuously drained via a 2" nipple at the base. With a 1.75" attack line/fog nozzle combo flowing 150 GPM at a distance of 30 feet, a properly controlled straight stream in calm conditions can fill the prop in under 40 seconds. Wind, distance and other complicating factors can extend this time even with excellent nozzle control.

Water depth is obtained via an HC-SR04 ultrasonic sensor mounted in the cap of a 2" PVC pipe mounted vertically in the reservoir.

In the place of visual extinguishment cues a row of LEDs are mounted across the base of each prop that show the water level in the prop. When the timer is started the first LED flashes until the water level reaches 5%. LEDs will follow the water level back down if poor nozzle control or other factors allow the water to drain faster than it is being filled.

Once the level reaches 100% the last LED lights, the clock stops, and the time is shown on the UI and also logged internally along with the Date, Time, Event Name and Firefighter Name. All LEDs stay lit until the unit is reset, which can only be done once the prop has drained fully.

Control is via the Dashboard which can be accessed by connecting to the Pi hosted Wifi and browsing to the UI page. After first boot setting the Date and Time is required before accessing the controls to insure accurate logging, although the accuracy is still subject to careless or negligent entries at this point.

There is a tech page that requires a passcode where the empty and full levels can be calibrated, although the defaults set on start-up are proving to be accurate and consistent so far. This tech page also shows the CPU temp, as well as the temp and humidity inside the box, which can get quite hot exposed in the sun. I have a failsafe shutdown built into it which has not been triggered yet but we have tried to keep it in shade as much as possible and of course water everywhere helps with the cooling too. The unit can also be rebooted or shutdown from here.

