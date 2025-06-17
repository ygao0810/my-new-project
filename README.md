# Project Title

SmartRoute: Optimizing Shipping Routes for Low Carbon Emissions

## Summary

SmartRoute is a tool that helps logistics companies minimize carbon emissions by finding the most efficient shipping routes between ports. It uses distance data, emission rates, and AI-powered optimization to recommend the lowest-emission path.

## Background

Global shipping is a major contributor to CO₂ emissions. With rising concerns about climate change and sustainable supply chains, there's increasing demand for smarter logistics.

This project addresses:
* Inefficient routing of cargo ships
* High CO₂ emissions due to long or suboptimal paths
* Need for accessible tools to help companies reduce their carbon footprint

I'm personally interested in combining AI and sustainability, and this project bridges both.


## How is it used?

SmartRoute is intended for shipping companies or sustainability officers planning overseas routes. Users input:
* The departure port
* A list of intermediate ports
* The final destination

The system calculates all possible routes and returns the one with the least total CO₂ emissions, based on known distances and emissions per kilometer.

![image of a cat](/MV_Ocean_Luck_2005-01-24.jpg)

def calculate_emissions(route, distance_matrix, emission_rate):
    total = 0
    for i in range(len(route)-1):
        total += distance_matrix[route[i]][route[i+1]]
    return total * emission_rate


## Data sources and AI methods
Distances are based on data adapted from Sea-Distances.org between key ports. Emission rate is assumed to be 0.020 kg CO₂/km per ton shipped.

| Port Code      | 	City       |
| -------------- | ----------- |
| PAN            | Panama      |
| AMS            | Amsterdam   |
| CAS            | Casablanca  |
| NYC            | New York    |
| HEL            | Helsinki    |

The AI technique used is combinatorial optimization, evaluating permutations of routes. In future versions, this could be improved using:
* Genetic algorithms
* Reinforcement learning for adaptive routing

## Challenges

This project:
* Does not account for real-time weather, port congestion, or political disruptions
* Assumes a constant emission rate for all routes
* Doesn't scale well to dozens of cities without optimization improvements

Ethically, it’s important to use such tools responsibly and ensure emissions estimates are accurate for policy or regulatory use.

## What next?

To move forward:
* Add real shipping constraints (e.g., refueling ports, fuel types)
* Use real-time data via APIs
* Implement an interactive UI for logistics teams

To scale the project, I’d need:
* Access to large-scale shipping datasets
* Expertise in supply chain management
* Support in deploying to cloud platforms


## Acknowledgments

* Inspired by the Building AI course
* Distance data inspired by Sea-Distances.org
* Container Ship by Alf van Beem / CC0 1.0
