# Thermal Monitor V1

I built this Excel model to see how a temperature controller reacts as the temperature changes and when readings stop coming in.

The most interesting result was at 44°C. On the way up, the controller showed **Warning**. After it reached **Alarm** at 45°C, it stayed in **Alarm** at 44°C and switched back to **Warning** at 43°C. That helped me understand how hysteresis keeps an alarm from switching back and forth near its threshold.

I also tested what happens when the sensor stops reporting. The controller held its last state until three seconds had passed since the last valid reading, then showed **Sensor Fault**. In a separate startup test, it waited for the first reading, reported a fault after three seconds, and returned to **Normal** when a 30°C reading arrived.

All 10 steps in the combined Excel test matched my expected states. Open the [workbook](Thermal%20Monitor%20V1.xlsx) and start with the **Full Controller Test** tab to follow the sequence.
