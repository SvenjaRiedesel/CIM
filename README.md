# CIM
Java script code for Risø Sequence Editor Custom Command to run Cooling-irradiation Modulation (CIM) experiments

To enable cooling-irradiation modulation on a Risø reader, a custom command needs to be used in Sequence Editor. The custom command can be created using Java script. The Java script written by Karsten Bracht Nielsen, DTU, to facilitate CIM, is made available on Github, via Zenodo (add Zenodo Doi) or by following this link: https://github.com/SvenjaRiedesel/CIM

If one would like to use CIM, the first part of the code needs to be adjusted for the respective measurement. There are six variables needed to be optimised:

const RampDuration = [s] // The ramp duration gives the time needed to cool a sample from temperature Tmax (e.g. 300 °C) to temperature Tmin (e.g. 25 °C)

const StartTemperature =	[°C]	// Temperature from which the sample should be cooled (e.g. 300 °C)

const EndTemperature =	[°C]	// Temperature to which the sample should be cooled (e.g. 25 °C)

const BetaDutyCycle =	[%]	// If the sample is supposed to be under constant beta irradiation during CIM, then set this to 100 %, adjust accordingly for pulsed irradiations

const BetaPeriod =	[s]	// This requires an input of time, if BetaDutyCycle = 100, then this equals RampDuration

const Heating Period	[s] // This defines the time/cooling step. Cooling during CIM is done in steps, with the duration of each step being calculated by dividing the RampDuration by the number of steps. The number of steps is calculated by dividing the temperature difference between Tmax and Tmin by the step size (e.g. 1 °C change in temperature when cooling from one step to the next). 
