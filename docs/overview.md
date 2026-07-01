# Project overview

This repository is for building an accurate Renault Clio Renaultsport 182 F4R 738 engine for Engine Simulator Community Edition v0.1.14A.

The project has two layers:

## 1. Reference layer

This contains values that are either confirmed by Renault, supported by Renault Sport competition documentation, or strongly supported by OE-fit catalogues.

Examples:

- 82.7 mm bore
- 93.0 mm stroke
- 1,998 cc displacement
- 11.0:1 compression ratio
- 182 hp DIN at 6,500 rpm
- 200 Nm at 5,250 rpm
- F4R 738 engine identity

## 2. Correlation layer

This contains values that are adjusted because Engine Simulator CE does not model the whole Renault ECU, transient fuelling, idle air control, dephaser strategy, catalyst behaviour, or full intake/exhaust thermal behaviour.

Examples:

- total rotating inertia
- idle throttle plate position
- idle flow rate
- intake velocity decay
- low-rpm ignition catch
- limiter duration
- approximated head flow curves

The aim is to avoid pretending that every simulator value is a factory value. Where we know a value, it goes in the reference layer. Where we have to tune around simulator limitations, it is marked as a correlation value.
