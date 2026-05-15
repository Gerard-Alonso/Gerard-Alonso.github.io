The vapor-liquid-liquid equilibria (VLLE) for water + butanol + alkane mixtures was evaluated using the group contribution-based molecular SAFT-γ Mie equation of state [^1]. To that end, we used the SGTpy python module [^2], which is an open-source code distributed through the following Git-hub: 

[![SGTpy Repository](https://img.shields.io/badge/GitHub-SGTpy_Code-blue?logo=github&style=for-the-badge)](https://github.com/gustavochm/sgtpy)

We modeled the binary water + butanol / water + alkane / alkane + butanol binary mixtures, using as alkanes = hexane, heptane, octane and nonane. We saw good accuracy in reproducing all binary phase equilibria and then proceed to model the three-phase equilibria. We obtained the following ternary heteroazeotropic lines for each system: 

<p align="center">
  <img src="Assets/VLLLEs.png" alt="VLLLEs" width="100%">
  <figcaption>Figure 1: Ternary VLLE lines modeled with SAFT-γ Mie. The black lines are the binary VLLE for the alkane + water and water + butanol mixtures. The red and blue lines show the vapor and the liquid phases at equilibrium for the ternary VLLE. Liquid phases meet at a blue triangle representing the point where the vapor is at equilibrium with three different liquid phases simultaneously.</figcaption>
</p>

A three-phase line with a low temperature heteroazeotropic point was located for all systems, all containing a 4-phase point (VLLL) equilibrium alongside the VLLE line. In long-chain alkanes the heteroazeotrope coincides with the 4-phase point, whereas in short-chain alkanes they are located at different thermodynamic coordinates. The predicted results allowed to evaluate how molecular shape and interactions affect phase equilibria for alkane based entrainers. That is:
  - The less non-polar alkanes displace significantly the butanol-rich end of the VLLLE and keep the vapor end close to the water + alkane binary.
  - Large chain alkanes keep the butanol-rich end of the VLLLE similar to the binary water + butanol and displace significantly the vapor end.
This is correlated with the temperature of the binary azeotropes. When binary mixtures have similar heteroazeotropic temperatures the vapor phase is placed in the center of the line, whereas when they have different temperatures the vapor phase is found closer to the lower boiling point binary mixture. 

We then aimed to evaluate the suitability of those thermodynamic scenarios in a standard heteroazeotropic distillation process. We have built the residue curve maps and carried out material balances to determine which alkanes perform better for the dehydration. After observing the compositions of the $1^st$ column product, we concluded that the distillation frontiers prevent those mixtures to be directly separated with this setup. However, the existence of the 4-phase point opens up new separation scenarios that can be exploited for separation, since the decanter will not generate 2 phases, but 3 at equilibrium. Those 3 phases can be treated separately or mixed at different ratios depending on the process needs. Exploring different distillation processes lays out of scope for this project but should be kept in mind when treating with such mixtures in the future.

<p align="center">
  <img src="Assets/RCMs.png" alt="RMCs" width="100%">
  <figcaption>Figure 2: Residue curve maps for the water + butanol + alkane ternary mixtures. .</figcaption>
</p>

Process simulations can be carried out to design new separation setups, but distillation of such ternary mixtures ended in a 4-phase VLLLE configuration, which exhibitted large convergence issues. For this reason, we have produced a free code based on activity coefficient models to incorporate them in process simulations. __ complete tomorrow .--

The complete works are compiled in the Undergraduate Theses of Octavio Barría [^3] and Nicolás Díaz [^4]. Please check them out for more information. Hyperlinks are included to each paper and thesis.

[^1]: saft-g
[^2]: sgtpy
[^3]: octavio
[^4]: nico





---------------------------------------------------------------------------
<style>
  .banner-link {
    display: block;
    width: 100%;
    height: 80px;
    margin-bottom: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none !important;
    color: white !important;
    font-weight: bold;
    font-size: 1.2em;
    border-radius: 8px;
    transition: transform 0.2s, filter 0.2s;
  }
  .banner-link:hover {
    transform: scale(1.02);
    filter: brightness(1.1);
  }
  .etapa-1 { background: linear-gradient(90deg, #2c3e50, #4ca1af); } /* Azul grisáceo - Serio/Metodológico */
  .etapa-2 { background: linear-gradient(90deg, #5a3f37, #2c3e50); } /* Tonos tierra - Apolares/Hidrofóbicos */
  .etapa-3 { background: linear-gradient(90deg, #1e3c72, #2a5298); } /* Azul intenso - Polares/H2O */
</style>

<a href="./Methodology" class="banner-link etapa-1">
  STAGE 1: Methodology & Molecular Simulation
</a>

<a href="./Non-polar-entrainers" class="banner-link etapa-2">
  STAGE 2: Non-polar Entrainers (Hydrocarbons)
</a>

<a href="./Polar-entrainers" class="banner-link etapa-3">
  STAGE 3: Polar Entrainers (Ethers & Mixed)
</a>
