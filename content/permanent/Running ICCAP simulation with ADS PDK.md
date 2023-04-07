---
title: "Running ICCAP simulation with ADS PDK"
created: 2023-04-05 08:17
status: #permanent
tags: #cad/iccap
---

If you want to use a foundry provided ADS PDK in the ICCAP circuit tab to setup model validations for devices in ICCAP, which is often the case with GaAs foundries which almost exclusively deal with ADS PDKs, the procedure to do so is described below.

1. Locate the ADS models for the devices in the foundry PDK. They will usually have the extension of `*.library`
2. Create a file called `ADSlibconfig` in the `<ICCAP User Home>/hpeesof/circuit/config` directory. On linux `<ICCAP User Home>` is usually linux home directory (check it with `echo $HOME`). On windows it can be some other directory such as `C:\iccap`.
3. In the `ADSlibconfig` file, create model library definitions
 
```
<model1>    /path/to/ads/model1.library
<model2>    /path/to/ads/model2.library
```

Restart ICCAP to pull in these model libraries.

In the Circuit tab of ICCAP, create a netlist that looks like the example below:

```
define myfet (D G S B)

#uselib "model1" , "device_model_name"
device_model_name:M1 D G S B W=1u N=2

end myfet
```

Now you should be able to simulate the ADS PDK in ICCAP.