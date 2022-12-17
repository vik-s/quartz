20221017-0907
Status: #how-to
Tags: #cadence #simulation

## What is transient AC analysis?

Let's say that you have to run [[s-parameter]] simulation as a function of time, where conditions such as voltages are changing in the window of time, then you need to run the AC simulation at every time point that is of interest.

## What is an example where transient AC analysis is useful?

If an amplifier is being turned ON, or turned off, or the bias conditions in the amplifier are changing, and you want to find out how quickly an AC parameter such as gain takes to change from one value to another, then you need to run transient AC analysis

## How do you do this in Virtuoso ADE?

In the transient analysis setup, go to `Options`, and go to the `Output` tab. You will see a section called `ACTIMES SETTINGS` where there are the following settings:
1. `acnames`: Names of ac, noise, sp, stb, or xf analyses to be performed at each time point in the `actimes` array. The named small-signal analyses are not run separately but only as part of the transient analysis.
2. `actimes`: Times when AC analysis (such as ac, noise, sp, stb, xf) specified in `acname` array are performed
3. `actime_pair`: If set to yes, there is a 1:1 correspondence between the values in `acnames` and `actimes`. For example, `acnames[0]` will run at `actimes[0]`. If set to no, all analysis in acnames will be run at each `actimes` time.
	1. This option does not seem to be in the transient analysis settings form. This is likely used in command line simulation.


---
# References

Spectre Circuit Simulator Reference, Jan 2020, Pg. 423.