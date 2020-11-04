# APOCO
## Adjusting Predictions On Coronavirus Outbreak  

This collection of Python's notebooks has the purpose of following the developement of the _SARS-COV-2_ outbreak of 2020.
The general approach is to write a set of differential equations that describe the processes ongoing into the population of a country during the diffusion of an infective disease.
The right choice of parameters describing the situation is crucial for both a qualitative and quantitative description of the phenomena.

### Models
The modelw we employ are based on a traditional SEIR, taken from the most used ones in the epidemiological modelling field. In particular: 
SEIRTD: susceptible-exposed-infected-hospitalized-intensivecare. (Currently overestimates largely the number of infected and hospitalized people).
SEAIRTD: susceptible-exposed-asymptomatic-infected-hospitalized-intensivecare.

### Choice of parameters
While some parameters can "easily" be guessed from the literature and the web, some others can not.
For example, the transmissivity, aka the rate of contacts with infected people resulting in a contagion depends on a lot of other factors and it is very difficult to guess. Also, the percentage of infected people needing hospitalization is stricly dependant on the policies deciding who is tested for Coronavirus and who don't, thus it is likely to change over time. 
Though this parameters are not easy to access, they have a strong influence on the disease spreading, so we fit them directly from the data avalaible until now. In particular, we splitted the data into several time-windows corresponding to different behaviours (epidemic control measures in Italy) and fitted the model separately onto them. The initial condition of a time-window is the last point of the model estimates on the previous time-window.
We believe that an appropriate choice of the model, joint to a good fit of the epidemiological curves taken from daily collected data, can describe what has happened since the start of outbreak and offer some hints on the future of the epidemic.

### Limitations
The main limitation of these models is their being built on "mean field equations". This means that all the individuals are identical and it's all deterministic: there is no source of variability neither on the parameters or in the behaviour of the model.  
This is a strong assumption, describing a population quite far from the real one of a country.
Also, the model do not take into account asymptomatic transmission, since no data is available about the daily number of asymptomatic infected people.
