Note: This description may change over time. I've put a lot of work into developing this script (with some AI Programming assistance).
This script is designed to run an unstable D-T fuel Better Fusion Reactor for Mekanism.

Connection & Setup Requirements
•    Advanced Computer: Requires an attached modem (if using a wired modem, don't forget the networking cables).
•    Fusion Reactor Logic Adapter: Must also be connected via a modem.
•    Optional 3x3 Monitor: Used for displaying logs and status; connected via a modem.
•    Optional Redstone Relay: Connected via a modem; used to output a redstone signal when the reactor is turned off, or has crashed and the Error Level (ER) has dropped to 0.

Performance Scaling on Laggy Servers
I personally have 4 of these reactors running on the ValhallaMC server, and they run very well there.
(Information for players on laggy online servers): Since the server does not have a stable 20 TPS and the chunk tick rate is dynamically controlled by a server mod, machines (including the reactor) may suddenly tick at 1/2, 1/4, or 1/8 of their original speed depending on server load. Curiously, this does not affect the Computer itself.
Because of this, I had to make the script cycles modular. If you want to use this feature, you need a redstone timer that slows down matching the server's tick rate and sends a pulse once every 20ms under normal conditions. I use the RFTools Timer for this On the bottom of the computer—just a side note that is completely irrelevant to most players. 



tweaked advanced computer commands:

wget https://raw.githubusercontent.com/Mr-X88/Better_Fusion_Reactor_Controller/refs/heads/main/Better_Fusion_Reactor_Controller.lua Better_Fusion_Reactor_Controller

edit startup

shell.run("Better_Fusion_Reactor_Controller")

Ctrl  Save
Ctrl  Run 

How the Better Fusion Reactor for Mekanism Calculates Its Efficiency.
<img width="536" height="109" alt="grafik" style="display: block; margin-bottom: 25px;" src="https://github.com/user-attachments/assets/79803fbd-4b55-4cc7-bac7-872f2ce09b48" />

<p>And this is what the rearranged formula looks like.</p>
<img width="597" height="192" alt="grafik" style="display: block; margin-bottom: 25px;" src="https://github.com/user-attachments/assets/a63c645d-d41a-4f93-a902-01876899c659" />

<p>And that is what the Advanced Computer calculates.</p>
<p></p>
<p>EF = min(100, max(0, 22 / ((|TR - CR| / 100) + 0.2) - 10))</p>
<p>Here, |TR - CR| represents the absolute value of the difference between the reactivity values.</p>

