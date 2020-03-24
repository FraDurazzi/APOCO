# APOCO
## Adjusting Predictions On Coronavirus Outbreak  

These collection of Python's notebook have the purpose of following the developement of the _SARS-COV-2_ outbreak of 2020.
The general approach is to write a set of differential equations that describe the processes ongoing into the population of a country during the diffusion of an infective disease.
The right choice of parameters describing the situation is crucial for both a qualitative and quantitative description of the phenomena.

### Models
The models we employ are taken from the most used ones in the epidemiological modelling field. In particular, we are currently updating only the *SIR* and *SIQR* notebooks.  
SIR: susceptible-infected-recovered.
SIQR: susceptible-infected-quarantined-recovered. In this model, we also included birth and death rate to have an estimate of the number of victims.

### Choice of parameters
While some parameters can "easily" be guessed from literature and the web (average mortality and birth rate), some others can not. For example, the number of infected people will always be a number quite higher than the count of reported cases from the health system.
In the same way, the transmissivity, aka the rate of contacts with infected people resulting in a contagion depends on a lot of other factors and it is very difficult to guess.
On the other hand, though this parameters are not easy to access, they have a strong influence on the disease spreading, so we decided to fit them directly from the data avalaible until now.
We believe that an appropriate choice of the model, joint to a good fit of the epidemiological curves taken from daily collected data, can offer some hints on the future of the epidemic.

### Limitations
The main limitation of these models is their being built on "mean field equations". This means that all the individuals are identical and it's all deterministic: there is no source of variability neither on the parameters (birth/death rate) or in the behaviour of the model.  
This is a strong assumption, describing a population quite far from the real one of a country.
