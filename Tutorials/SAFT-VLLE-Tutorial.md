---
layout: default
title: Tutorials
---


# Tutorials for a VLLE simulation with SGTpy

In this page we will share how to carry out proper VLLE calculations with the SGTpy code [^1] using a simple mixture of LJ fluids. The first thing one needs is a suitable hardware to run the code. This may be your own computer, an HPC cluster or some on-line tool such as Google Colab. In this tutorial I will assume you do not have no access to any computing resources, so you will use Google Colab. 

Google Colab allows users to work for a limited time for free. This tutorial will allow you to open a ready to run jupyter-notebook into google collab to run the VLLE calculation.

First enter into the Colab webpage, get an account (if you don't have it already) and log in. If your account is ready, just click the following link to open the LAMMPS-ready Colab notebook:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Gerard-Alonso/Gerard-Alonso.github.io/blob/main/Tutorials/SGTpy.ipynb)

The notebook guides you through 2 different case scenarios where you'll model the VLLE of:
- A binary LJ mixture, with single non-associative monomers
- A complex ternary mixture, with associative chains.

Every piece of code you need to run both simulations is already included in the notebook, so you should continue there. Additional tutorials on how to define species, extract properties and calculate different phase equilibria with sgtpy can be found in the GitHub of the original developers:

[![SGTpy Repository](https://img.shields.io/badge/GitHub-SGTpy_Code-blue?logo=github&style=for-the-badge)](https://github.com/gustavochm/sgtpy)

[^1]: Mejía, A. E.A. Müller, G. Chaparro, (2021) SGTPy: A Python Code for Calculating the Interfacial Properties of Fluids Based on the Square Gradient Theory Using the SAFT-VR Mie Equation of State. J. Chem. Inf. Model. 61: 1244-1250.

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
