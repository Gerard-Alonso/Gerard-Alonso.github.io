---
layout: default
title: Tutorials
---


# Tutorials for a VLLE simulation with LAMMPS

In this page we will share how to carry out proper VLLE simulations with the LAMMPS code using a simple mixture of LJ fluids. The first thing one needs is a suitable hardware to run the code. This may be your own computer, an HPC cluster or some on-line tool such as Google Colab. In this tutorial I will assume you do not have no access to any computing resources, so you will use Google Colab. 

Google Colab allows users to work for a limited time using a combination of 2 CPUs + 1 GPU (Nvidia T4) for free. This tutorial will allow you to run a VLLE calculation for a short time frame and analyze the obtained results. Proper publication-level simualtions require significantly more time and statistics to properly run but free Google Colab will disconnect us before ending those simulations. For this reason, inputs will come with comments on how to modify them to improve them from "cheap examples" to "publication ready simulations".

First enter into the Colab webpage, get an account (if you don't have it already) and log in. A new window will open to select a *ipynb* file to start working. Select "Upload" and open the following notebook shared here:

[![Download Colab Notebook](https://img.shields.io/badge/Download-Notebook-blue?style=for-the-badge&logo=github)](LAMMPS_GPU.ipynb)

This notebook has 2 blocks:
- An installation block for GPU-based LAMMPS with an NVIDIA T4 architecture (the standard Google Colab uses for free users)
- An execution block with 1 CPU + 1 GPU

GPU installation is strongly recomended because VLLE simulations on LJ fluids is extremely efficient. Simulations in a single CPU will be 4 h long wereas 1 CPU + 1 GPU will last 4 minutes. the GPU is not available by default, one needs to manually select a session with it clicking at "Runtime" > "Change Runtime Type" and then select the T4 GPU accelerator in the pop-up window. After "Saving" the settings, the session will be GPU ready. 

<p align="center">
  <img src="../Assets/Colab Setting.png" alt="Colab setting" width="100%">
</p>

Execute the $1^{st}$ block and install GPU-LAMMPS. This is an "almost-minimal" installation of LAMMPS containig the basic packages and the optional RIGID, GPU and EXTRA-PAIR packages. The installation may last for around 35 minutes and a message will pop up at some point informing that the GPU is not being used. Ignore the message and wait for the installation to complete. I recommend starting this tutorial with time and setting the installation right now, even if you are not ready to simulate. You can set everything up in parallel to the installation process.



A continuación, se muestra un ejemplo de cómo procesar datos de una simulación usando Python y Pandas:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Cargar datos de una simulación de LAMMPS o VASP
data = pd.read_csv('log_file.csv')

# Calcular el promedio de la energía total
mean_energy = data['Energy'].mean()
print(f"La energía promedio es: {mean_energy}")
---
# Graficar la evolución de la temperatura
plt.plot(data['Step'], data['Temp'])
plt.xlabel('Timestep')
plt.ylabel('Temperature (K)')
plt.show()
```
Esto es un ejemplo de código para bash

```bash
for i in $(seq 1 10); do cat "hola $i" ; done
clear
pip install lammps
```

y este es un ejemplo de input de lammps

```lammps
fix  id  all  nvt  temp 200 200 1000
run 100000
```

Eso sería de momento
