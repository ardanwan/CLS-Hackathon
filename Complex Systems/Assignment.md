# Introduction
Today we will look at a complex system that many of you will be very familiar with: the Dutch rail schedule. Optimal scheduling in large complex networks (such as our rail system) is notoriously hard. Networks like this have to be balanced between efficiency and robustness. We want our system to be as fast as possible, while also functioning when things go wrong.

This folder contains two csv files: one with the stations and their coordinates, the other with all connections and their respective durations. First, construct a visualization of the rail network with the stations as nodes and the right connections between them.

# Assignment
In this assignment we are interested in two things: efficiency and robustness of our schedules. First you will attempt to find the most optimal schedule you can find. A schedule consists of up to 5 different trajectories, with a maximum duration of 3h per trajectory. Each station can only be visited once in each trajectory. The efficiency of the schedule is determined by a score function:

- S = ρ * 10000 - (20N<sub>t</sub> + t / 10)

In the file containing all stations, some are marked as 'critical'. These are important traffic hubs, which are vital for distributing the flow of passengers. The variable ρ in the score function is the fraction of critical stations that is serviced by at least 1 trajectory. N<sub>t</sub> is the total number of trajectories and t is the total service duration of all trajectories in minutes. We demonstrate the scroring system with an example schedule:

The example schedule consists of 3 trajectories:
- Den Haag Centraal - Leiden Centraal - Schiphol - Amsterdam Sloterdijk - Amsterdam Centraal - Almere - Lelystad | total 89 minutes
- Groningen - Assen - Zwolle - Amersfoort - Utrecht Centraal - s'Hertogenbosch - Eindhoven - Weert | total 168 minutes
- Den Helder - Alkmaar - Hoorn - Zaandam - Beverwijk - Haarlem - Sloterdijk - Amsterdam Centraal - Amsterdam Amstel - Hilversum | total 180 minutes

This schedule services 11 out of 23 critical stations, so ρ = 0.4783. This schedule would receive a score of S = 4783 - (60 + 44) = 4679. Of course you will find much better scoring schedules. Be warned however, finding the optimal solution (or even a good solution) is not trivial at all!

