---
layout: default
title: Tutoriales
---


# Simulation Tutorials

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 

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
