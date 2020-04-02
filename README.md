# Rab5 spatial stochastic model

This repository hosts the Rab5 activation stochastic model development, which supports the Loose and Saunders lab project with tentative title **"Stochastic nucleation events trigger collective Rab GTPase activation"**.

The basic model was implemented with [Smoldyn](http://www.smoldyn.org/) stochastic simulator. 

## Smoldyn

[Smoldyn](http://www.smoldyn.org/) is a particle based stochastic simulator, which alows detailed spatial simulations of reaction-diffusion systems. Smoldyn was created by Steve Andrews (Seattle University). You can find out more in:
*  Andrews, S.S., Addy, N.J., Brent, R., and Arkin, A.P. (2010). Detailed simulations of cell biology with Smoldyn 2.1. PLoS Comput. Biol. 6, e1000705.

**Instalation and running models**
To install Smoldyn:
1.  Download pre-compiled install package from the [website](http://www.smoldyn.org/download.html).
2. Extract the zip file to the desired location.
3. Open “Command Prompt” as administrator.
4. Change directories to the newly extracted Smoldyn directory (e.g. type `cd C:\Users\username\Downloads\smoldyn-2.xx-windows)`.
5. Type “install”. This copies all of the Smoldyn executable files to a Smoldyn subdirectory inside your “C:\Program Files” directory.

To run Smoldyn:
1.  Navigate Command prompt to Smoldyn instalation folder (e.g. \Program Files\Smoldyn)
2.  run with `smoldyn "model_filepath.txt"` 

## Model

The basic model includes the following reactions:

```
reaction rxn_1_1 Rab5GDP:GDI(fsoln) <-> Rab5GDP(fsoln) + GDI(fsoln) k_1 k_2
reaction rxn_1_2 Rab5GDP(front) + GDI(fsoln) -> Rab5GDP:GDI(fsoln) k_8
reaction rxn_2 Rab5GTP(front) -> Rab5GDP(front) k_3
reaction rxn_3_1 Rab5GDP(front) + RR(fsoln) -> Rab5GTP(front) + RR(fsoln) k_4
reaction rxn_3_2 Rab5GDP(front) + RR(front) -> Rab5GTP(front) + RR(fsoln) k_4
reaction rxn_4_1 Rab5GTP(front) + RR(fsoln) <-> Rab5GTP:RR(front) k_5 k_6
reaction rxn_4_2 Rab5GTP(front) + RR(front) <-> Rab5GTP:RR(front) k_5 k_6
reaction rxn_5_2 Rab5GTP:RR(front) + Rab5GDP(front) -> Rab5GTP:RR(front) + Rab5GTP(front) k_7
```