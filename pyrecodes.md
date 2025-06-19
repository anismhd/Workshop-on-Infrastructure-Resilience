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

where  $D_{i,RS} (t)$ and $S_{i,RS}^C (t)$ are the demand and supply capacity of component i for R/S at time t, respectively.

System R/S distribution model, $\phi_{RS}$ , simulates the transfer of the considered R/Ss among components, and accounts for the topology and the state of the R/S distribution network, dispatch/allocation strategies of the system operator and the physical laws that govern the distribution of the considered R/S. Finally, the amount of supply made available to a component $i$ at time $t$ for a R/S is estimated using distribution model is termed as $S_{i,RS}^{av} (t)$.

The amount of R/S component $i$ consumes at time $t$ , $C_{i,RS} (t)$, is the smaller of component’s demand $D_{i,RS} (t)$ and the supply available to the component, $S_{i,RS}^C (t)$

$$ C_{i,RS}(t) = min(S_{i,RS}^{av} (t), D_{i,RS} (t)) $$

The aggregate sum of the consumptions of all components for a R/S at time $t$ is the system’s consumption for R/S at time $t$, 

$$ C_{sys,RS}(t) = \sum C_{i,RS}(t) $$

The damage state of a component evolves during the system resilience assessment interval. All components are assumed to be undamaged and fully functional at time $t_0$ before a disaster happens. Damage states of each component immediately after the disaster are determined using component vulnerability functions that link the intensity of a disaster at the location of the component to its damage state. The recovery process is represented by a decrease of component damage state and a corresponding increase in component functionality, reflected in the evolution of component demand $D_{i,RS} (t)$, supply capacity $S_{i,RS}^C (t)$ and consumption $C_{i,RS}(t)$ over time during system resilience assessment.

A systems Lack of Resilience is defined as the inability of current demand of the system, as defined in Eq. (1), cannot be fully met by system supply. Quantitatively, this can be defined as;

$$ LoR_{sys, R/S} = \int_{t_0}^{t_f} (D_{sys,RS}(t) - C_{sys,RS}(t)) dt $$

## Implementation in pyrecodes
![object-oriented architecture of pyrecodes](Presentation/Figures/pyrecodes_oop.PNG)
