---
share: true
aliases: 
type: "record"
sub-type: "fish"
created: NaN 
modified: NaN
---
#fishies 
 ![]() 
# Data
## General
family:: 
genus:: 
species:: 
region::  
origin:: 
sizeInch:: 
sizeCm:: `$= Math.round(dv.current()["sizeInch"] * 2.54).toFixed(2)`
color:: 
disposition:: 
## Care
minTankSizeInGallons:: 
minTankSizeInLiters:: `$= Math.round(dv.current()["minTankSizeInGallons"]  * 3.785412)`
flow:: 
minpH:: 
idealpH:: 
maxpH:: 
minHardnessPPM:: 
maxHardnessPPM:: 
substrateColor:: 
diet:: 
minTempF:: 
maxTempF:: 