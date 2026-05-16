---
layout: default
title: Tutorials
---


# Tutorials for a VLLE simulation with LAMMPS

In this page we will share how to carry out proper VLLE simulations with the LAMMPS code. The first thing one needs is a suitable hardware to run the code. This may be your own computer, an HPC cluster or some on-line tool such as Google Colab. In this tutorial I will assume you do not have no access to any computing resources, so you will use Google Colab. 

First enter into the webpage, get an account (if you don't have it already) and log in. A new window will open to select a *ipynb* file to start working. Select "Upload" and open the following notebook shared here:

[![Download Colab Notebook](https://img.shields.io/badge/Download-Notebook%20ZIP-blue?style=for-the-badge&logo=github)](LAMMPS_GPU.ipynb)

This notebook has 2 blocks:
- An installation block for GPU-based LAMMPS with an NVIDIA T4 architecture (the standard Google Colab uses for free users)
- An execution block with 1 CPU + 1 GPU


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
