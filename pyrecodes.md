# Brief Description of pyrecodes
## General
iRe-CoDeS (Resilience-Compositional Demand/Supply) is bottom-up quantitative resilience assessment methodology proposed by \cite{pyrecodes} is described in detail.
The approach in applicable to systems for __finite a time period__ following a __single disaster__, and assesses resilience while considering the inter dependencies among its subsystems. __pyrecodes__ an open-source python implementation of the iRe-CoDeS framework.

In iRe-CoDeS framework resilience is quantifies the resilience of a system concerning a specific resource or service by contrasting the supply, demand, and consumption of the considered resource or service within the system during the resilience assessment interval. When the system's demand cannot be met by the available supply, a __Lack of Resilience (LoR)__ occurs.

## Bried Description of iRe-CoDeS framework
An interconnected system in iRe-CoDeS framework is modelled as omponents that exchanges resources and services (R/Ss) (ex: building material, labour or inspection services). For residential community, these component can be residential building which provides service of shelter, power plants which provides electricity, road networks which provides service of enabling exchange of R/Ss. 

The systems demand and supply capacity for a R/S at time $t$, $D_{sys,RS} (t)$ and $S_{sys,RS}^C(t)$, are defined as the aggregate of the demands and supply capacities of all components for that R/S at time $t$

$$ D_{sys,RS} (t) = \sum_{i \in (1,2,\dots,I)} D_{i,RS} (t) $$


$$ S_{sys,RS}^C(t) = \sum_{i \in (1,2,\dots,I)} S_{i,RS}^C (t) $$
