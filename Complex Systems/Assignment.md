# Introduction
Today we will look at a complex system that many of you will be very familiar with: the Dutch rail schedule. Optimal scheduling in large complex networks (such as our rail system) is notoriously hard. Networks like this have to be balanced between efficiency and robustness. We want our system to be as fast as possible, while also functioning when things go wrong.

This folder contains two csv files: one with the stations and their coordinates, the other with all connections and their respective durations. First, construct a visualization of the rail network with the stations as nodes and the right connections between them.

# Assignment
In this assignment we are interested in two things: efficiency and robustness of our schedules. First you will attempt to find the most optimal schedule you can find. A schedule consists of up to 10 different trajectories, with a maximum duration of 3h per trajectory. Each station can only be visited once in each trajectory. The efficiency of the schedule is determined by a score function:

- S = ρ * 10000 - (N<sub>t</sub> + min / 10)
