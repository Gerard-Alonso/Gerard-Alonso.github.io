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

We then aimed to evaluate the suitability of those thermodynamic scenarios in a standard heteroazeotropic distillation process. We have built the residue curve maps and carried out material balances to determine which alkanes perform better for the dehydration. After observing the compositions of the $$1^{st}$$ column product, we concluded that the distillation frontiers prevent those mixtures to be directly separated with this setup. However, the existence of the 4-phase point opens up new separation scenarios that can be exploited for separation, since the decanter will not generate 2 phases, but 3 at equilibrium. Those 3 phases can be treated separately or mixed at different ratios depending on the process needs. Exploring different distillation processes lays out of scope for this project but should be kept in mind when treating with such mixtures in the future.

<p align="center">
  <img src="Assets/RCM.png" alt="RMCs" width="100%">
  <figcaption>Figure 2: Residue curve maps for the water + butanol + alkane ternary mixtures. The green dashed curve shows the composition of the liquid phase exiting the condenser after the $$1^{st}$$ column .</figcaption>
</p>

Process simulations can be carried out to design new separation setups, but distillation of such ternary mixtures ended in a 4-phase VLLLE configuration, which has convergence difficulties due to the 3 liquids at equilibrium. For this reason, we have produced a free code based on activity coefficient models to incorporate robust 3-liquid equilibrium calculations in process simulations in the future. In this code we use the idea of Lucia et al., [^3] and Dennes et al [^4], who minimizes the Gibbs free energy of a mixture combining a flash (with a given global composition) and applying material balances to them. The method allows to predict the LLL phase equilibria solely from an initial global composition by first analyzing the miscibilities of each pair and then attemting to 

<p align="center">
  <img src="Assets/3L-predict.png" alt="triliquid prediction" width="100%">
  <figcaption>Figure 3: Prediction method for the LLLE .</figcaption>
</p>

The complete works are compiled in the Undergraduate Theses of Octavio Barría [^5] and Nicolás Díaz [^6]. Please check them out for more information. The links to the repository with those theses are can be found below:
  - UdeC Repository: [https://repositorio.udec.cl/items/c98879ec-649d-48d6-8b43-3d8f5e04b8df](https://repositorio.udec.cl/search?spc.page=1&query=)
  - GitHub Repository for the LLLE code: [![LLLE Repository](https://img.shields.io/badge/GitHub-LLLE_Code-blue?logo=github&style=for-the-badge)](https://github.com/nicodiazfp/CodigosMT)
  
Additionally, some codes and tutorials are shared in here to teach how to calculate these particular phase equilibria with SGTpy:
  - **Recommended Start:** [VLLE prediction with SGTpy](Tutorials/SAFT-VLLE-Tutorial).
  - **4-phase equilibria:** _Soon to be released._ - requires modification of the vlleb function from sgtpy to accept ternary mixtures


[^1]: Papaioannou, V., Lafitte, T., Avendaño, C., Adjiman, C.S., Jackson G., Müller, E.A., Amparo G. (2014) .Group contribution methodology based on the statistical associating fluid theory for heteronuclear molecules formed from Mie segments. J. Chem. Phys. 140: 054107
[^2]: Mejía, A. E.A. Müller, G. Chaparro, (2021) SGTPy: A Python Code for Calculating the Interfacial Properties of Fluids Based on the Square Gradient Theory Using the SAFT-VR Mie Equation of State. J. Chem. Inf. Model. 61: 1244-1250.
[^3]: Lucia, A., Padmanabhan, L., and Venkataraman, S. (2000). Multiphase equilibrium flash calculations. Comp. Chem. Eng., 24(11):2557–2569.
[^4]: Denes, F., Lang, P., & Lang-Lazi, M. (2006). Liquid–liquid–liquid equilibrium calculations. In Symposium Series No. 152. IChemE
[^5]: Barría, O (2025). Optimización del Proceso de Deshidratación de Bio-Butanol con Hidrocarburos. Undergraduate Thesis, Universidad de Concepción
[^6]: Díaz, N (2025). Predicción del Equilibrio Multifásico Líquido-Líquido-Líquido Usando Modelos de Coeficientes de Actividad. Undergraduate Thesis, Universidad de Concepción




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

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
