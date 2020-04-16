## Overview

The Engine Simulation Toolkit custom device provides a configuration-based experience for validating engine control units (ECUs) in VeriStand. The custom device can be [combined with an engine physics model](https://www.ni.com/en-us/support/documentation/supplemental/11/using-simulation-models-with-ni-veristand.html) to create a complete ECU hardware-in-the-loop system.

## Usage

The Engine Simulation Toolkit custom device requires a bitfile that includes the [Engine Simulation Toolkit FPGA IP](https://github.com/ni/niveristand-engine-simulation-toolkit-fpga-ip). Measurement and generation options are conifgurable from the custom device once the bitfile has been loaded.

The Engine Simulation Toolkit FPGA IP library includes examples for creating bitfiles. These examples can be used as starting points for building custom bitfiles.

![FPGA System Diagram](Support/FPGA%20Diagram.jpg)

The FPGA bitfile is responsible for generating sensor simulations and responding to events provided by the ECU. These generations and event measurements are all based on the Angle Processing Unit (APU).

![APU Diagram](Support/APU%20Diagram.png)

### Custom Device Components

<table>
    <tbody>
        <tr>
            <th align="Left">Component</th>
            <th align="Left">Features</th>
        </tr>
        <tr>
            <td>Angle Processing Unit</td>
            <td>
                <ul>
                    <li>Simulates rotational position and speed</li>
                    <li>Optional simulated acceleration</li>
                    <li>Forward and reverse rotation</li>
                    <li>Configurable cycle length up to 1440 degrees</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Analog Replay</td>
            <td>
                <ul>
                    <li>Typical crank and cam variable reluctance sensor simulation</li>
                    <li>Replays any data file over a crank or cycle rotation</li>
                    <li>Scale voltage by engine speed or manually</li>
                    <li>Rotationally phase playback position at run time</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Digital Pattern Generation</td>
            <td>
                <ul>
                    <li>Typical crank and cam Hall effect sensor simulation</li>
                    <li>Generates arbitrary digital pulses based on engine position</li>
                    <li>Intuitive, powerful GUI for pattern design</li>
                    <li>Rotationally phase playback position at run time</li>
                    <li>Fault playback at run time by removing or adding teeth</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Directional Speed Sensor Simulation</td>
            <td>
                <ul>
                    <li>Enables ECUs to track engine position during start/stop</li>
                    <li>Timed pulses generated at tooth centers with configurable forward and reverse widths</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Knock Sensor Simulation</td>
            <td>
                <ul>
                    <li>Generates base- and high-frequency analog signals</li>
                    <li>Base frequency optionally scaled from engine speed</li>
                    <li>Pseudorandom probability</li>
                    <li>Arbitrary number of cylinders</li>
                    <li>Fully configurable frequencies and amplitudes</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>ECU Event Timing Capture</td>
            <td>
                <ul>
                    <li>Validate ECU injection and ignition events</li>
                    <li>Start and end position plus duration measurement</li>
                    <li>Position measurement correction by reference angle</li>
                    <li>Window expected events by engine position</li>
                    <li>Event error detection (stuck on, orphan edges, all active window)</li>
                    <li>Arbitrary number of events per cycle per window</li>
                    <li>Active high or low</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

### Detailed Specifications

<table>
    <tbody>
        <tr>
            <th align="Left">Component</th>
            <th align="Left">Specification</th>
        </tr>
        <tr>
            <td>Angle Processing Unit</td>
            <td>
                <ul>
                    <li>0.0055 degree crank resolution</li>
                    <li>0.011 degree cycle resolution</li>
                    <li>± 72,342 rpm</li>
                    <li>0.0175 rpm/sec maximum acceleration</li>
                    <li>5.33 rpm/sec acceleration resolution</li>
                    <li>25 ns update rate</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Analog Replay</td>
            <td>
                <ul>
                    <li>65,536 data points per cycle maximum</li>
                    <li>Resamples data file to memory size</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Digital Pattern Generation</td>
            <td>
                <ul>
                    <li>1,024 pulses per cycle maximum</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Directional Speed Sensor Simulation</td>
            <td>
                <ul>
                    <li>1,024 pulses per cycle maximum</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Knock Sensor Simulation</td>
            <td>
                <ul>
                    <li>0.0015% probability resolution</li>
                    <li>Output frequencies limited only by AO speed</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>ECU Event Timing Capture</td>
            <td>
                <ul>
                    <li>0.8 µs duration resolution</li>
                    <li>209.7 ms event duration maximum</li>
                    <li>Number of pulses per cycle per window limited only by FPGA space</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

## References

[Legacy Release Notes](https://forums.ni.com/t5/NI-VeriStand-Add-Ons-Documents/NI-Engine-Simulation-Toolkit-for-NI-VeriStand/ta-p/3520878)

[Legacy Support Forum](https://forums.ni.com/t5/NI-VeriStand-Add-Ons-Discussions/Engine-Simulation-Toolkit-Feedback/td-p/3373614?profile.language=en)
