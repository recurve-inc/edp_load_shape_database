# SEAT/EDP Year 3: Load Shape Database

### 3 June, 2021
### Recurve Inc.


Contact: Mariano Teehan, Senior Software Engineer, Recurve

mariano@recurve.com

-----

## Background


The following was proposed in the SEAT/EDP Year 3 plan:

**Phase 1: Development of Load Shape Database**

Recurve will work with LBNL and NREL to create a database of annual hourly energy data that corresponds to different conditions that might be experienced in commercial office buildings, such as extreme weather conditions, high and low energy usage, high and low temperature dependence, high and low baseload consumption, high and low discretionary consumption, and other features that will be useful for developing load shape queries.

This data will be loaded into a database and joined with a building characteristic table that allows segmentation based on particular characteristics of the simulated buildings. Recurve will create load shape profiles of each of the buildings using CalTRACK 2.0 Hourly methods and load the derivative outputs into a separate table.

## The Energy Data Observatory

The Energy Data Observatory (EDO), comprising phases 2 and 3 of the SEAT/EDP Year 3 plan, is a web application designed to allow users to query a load shape database and view a resulted aggregated load shape which has been obscured through differential privacy.  The initial scope of the EDO was to provide a mechanism for users to publish load shapes that would otherwise not be publshable -- for example, to communicate the potential impact of a program or policy change.  The initial deployment of the EDO was intended to be used with a synthetic dataset, though we envisioned a possibiliy of using genuine data and allowing users to upload datasets to use the EOD.


Following discussions with the EDP Technical Advisory Group, the scope of the EDO has shifted towards providing a tool that can ease the adoption and implementation of differential privacy by allowing stakeholders to gain an intuitive understanding of its mechanisms and their implications.  With this shift in scope, it is less important that the synthetic dataset used in the EDO is realistic, and more important that it illustrates a range of use cases that stakeholders may encounter, especially those that may be difficult to differentially privatize, e.g. small datasets and/or datasets with significant high outliers.

THe current design plan of the EDO includes a load shape database which presents a small library of load shapes, and interactive tooling to allow users to construct larger datasets on the fly, according to parameters selected by the user interactively, through the use of duplication of load shapes with the addition of random additive noise and linear scaling factors.  


## The Load Shape Databaase

The load shape database requires data be provided in the following form:

- A time series database, with columns for timestamp, meter_id, and usage, with one entry per hour, spanning at least one year per meter.
- A metadata table, with columns for meter_id and any available metadata columns.

This repository contains a Jupyter notebook which includes code to extract a set of loadshapes from the LBNL [AlphaBuilding Synthetic Dataset](https://lbnl-eta.github.io/AlphaBuilding-SyntheticDataset/).  This dataset contains nine high-resolution simulations of an office building, under three different efficiency regimes and in three different climate zones.  The notebook extracts a facility-level hourly electricity trace and reformated it into the required time series and metadata formats.

These nine traces form the 



During discussions with the EDP Technical Advisory Group, 

the scope of the Energy Data Observatory (EDO -- Phase 2 of the Year 3 plan) has expanded

