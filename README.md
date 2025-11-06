# ISORHUM Project - Excel Tool

## Installation

To get started, clone the repository and open the Excel file:

```bash
git clone https://github.com/maximestph/Glaser-Predictor.git
cd mon-projet
```

## Introduction
This Excel file was developed as part of the ISORHUM project within the OMBREE program.  It was created through a collaboration between the PIMENT laboratory (University of La Réunion) and the IMAGREEN consulting firm. It is based on work carried out by all the partners involved in the ISORHUM project.

This workbook offers an a priori prediction of condensation risks over one year within an insulating wall, using the Glaser model.

The Glaser model is limited to describing the steady-state regime, unlike coupled heat, air, and moisture (HAM) models, which account for transient phenomena. This limitation should be considered, especially when two layers with high resistance to water vapor diffusion are stacked. In such cases, wall desorption is delayed, preventing the rapid attainment of the steady-state regime.

This document in no way replaces official reference texts, whether regulatory (laws, decrees, orders, etc.), normative (standards, DTUs, professional rules, RAGE and PACTE recommendations, or calculation rules), or codified (technical approvals, technical specifications guides, etc.), which must be consulted. The CSTB declines all responsibility for any direct or indirect consequences of any kind that may result from any misinterpretation of the content of this document.

**Author contact :** maxime.stephan-phd@protonmail.com	

## Color code

A color code is used in worksheets to identify different cell functions :
![Code couleur des cellules](./images/color_code.png)

## Wall definition

The PAROI_GLASER worksheet allows users to build a custom composite insulating wall layer by layer. The user interface is shown in the following picture :

![Code couleur des cellules](./images/paroi_glaser.png)

A maximum of six layers can be defined, with layer 1 corresponding to the interior face of the room. Materials are selected using a drop-down list that refers to the Materials sheet (see link above). This sheet is editable, allowing new materials to be added or existing ones to be modified. Each layer is assigned a thickness that must be specified. All properties of the layer are then automatically retrieved and calculated.

A surface thermal resistance coefficient (Rth in m²·K/W) must be assigned to the interior and exterior surfaces, describing the resistance to convective heat transfer.

It has been experimentally shown that metal sheets placed on roofs exhibit a surface temperature significantly different from the ambient air temperature: higher during the day due to solar radiation, and lower at night because of radiative exchanges with the cold sky. Thus, when a metallic material (λ > 20 W/m·K) is used on the surface, the surface temperature is considered instead of the outdoor air temperature. In this case, the thermal resistance of the exterior surface has no significant effect.

When fewer than six layers are used, the remaining layers must be defined with the material named "Rien" (placed at the top of the list) and a zero thickness, as illustrated in the picture above. 

## Glaser calculation on a single time step

On the PAROI-GLASER sheet, the "Date" entry, visible in the picture bellow, allows selecting a date from the climate file, extracting the boundary conditions, and then calculating the temperature and vapor gradients for that time step.

![Code couleur des cellules](./images/date_entry.png)

The gradients computed using Glaser Model are shown on the graph to the right of the sheet, visible bellow. Condensation is detected when the calculated vapor pressure of water exceeds the saturation vapor pressure.

![Code couleur des cellules](./images/gradients.png)

On this graph, the different layers of the wall are shown in gray. The critical zone, indicated in purple, must be specified in the dedicated cells (visible in the wall definition picture). It defines a range of distances within the wall where condensation is problematic. Outside this range, condensation may be detected but will not trigger the criticality indicator.

## Climate data

Climate data constitute the boundary conditions for the Glaser model. They must be entered in the CLIMAT worksheet. Two climatic conditions need to be specified:

**- External conditions:** 

Several locations are pre-recorded in this workbook with their associated climate conditions. However, it is possible to unlock cells to enter custom data (duration: 1 year, time step: 1 hour, i.e. 8.760 time steps).

**- Internal condition :**







