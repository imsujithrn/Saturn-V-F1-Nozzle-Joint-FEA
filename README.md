# Saturn V Rocket Nozzle FEA Analysis

This project focuses on a **Finite Element Analysis (FEA)** of the Saturn V rocket's F1 engine nozzle, specifically analyzing the **bolted flange joint** connecting the mid and lower parts of the nozzle. The analysis is based on the curriculum of **MAE 4700/5700 Finite Element Analysis for Mechanical and Aerospace Design** at Cornell University.

## Problem Specification

The **Saturn V rocket** was used to launch humans to the moon, and its first stage was powered by five F1 engines. This analysis explores the safety of the bolted joint connecting the engine's **mid nozzle** and **lower nozzle** using ANSYS.

The objective is to:
- Analyze the stress and strain in the bolted flange joint.
- Identify the gaps that may form between the nozzle sections due to loading.
- Determine if the bolts can withstand the applied forces.

### Components:
- **Mid Nozzle**
- **Lower Nozzle**
- **100 Bolts (Flange Joint)**

### Visual Overview:
- Saturn V Rocket  
  ![Saturn V Rocket](images/saturn_v.jpg)
  
- F1 Engine Nozzle and Bolted Flange  
  ![F1 Engine Nozzle](images/f1_nozzle.jpg)

- ANSYS Model:  
  ![ANSYS Model](images/ansys_model.jpg)

## File Structure

Below is the structure of the repository:

Saturn-V-F1-Nozzle-Joint-FEA/
├── README.md
├── LICENSE
├── /images/
│   ├── saturn_v.jpg
│   ├── f1_nozzle.jpg
│   └── ansys_model.jpg
└── /FEA_Simulations/
    ├── SaturnV_F1_ANSYS_Model.wbpz
    ├── SaturnV_F1_Mesh.stl
    ├── SaturnV_F1_SimulationResults.rst
    └── SaturnV_F1_MaterialData.engd



### File Descriptions:
- **`SaturnV_F1_ANSYS_Model.wbpz`**: The ANSYS Workbench project file that contains the setup of the FEA model.
- **`SaturnV_F1_Mesh.stl`**: Geometry and meshing of the F1 nozzle and bolted flange.
- **`SaturnV_F1_SimulationResults.rst`**: The results file from running the analysis, which includes stress distributions, deformations, and safety margins.
- **`SaturnV_F1_MaterialData.engd`**: Material properties data used in the simulation, including Young's modulus, Poisson's ratio, and thermal expansion coefficients.

## Analysis Objective

We will simulate the bolted joint using **non-linear finite element analysis** in **ANSYS** to:
1. Evaluate the safety of the flange bolts.
2. Understand the behavior of the joint under different thermal and pressure conditions.
3. Investigate the gaps formed between the mid and lower nozzle.

## Material Properties

| Component | Material            | Young's Modulus (GPa) | Poisson Ratio | Coefficient of Thermal Expansion (µm/°C) |
| --------- | ------------------- | --------------------- | ------------- | --------------------------------------- |
| Nozzles   | 304 Stainless Steel  | 210                   | 0.27          | 16.4                                    |
| Bolts     | Inconel 718          | 200                   | 0.29          | 13.0                                    |

## Boundary Conditions and Assumptions

- **Pressure**: The pressure acting along the nozzle varies along its length. The exit pressure is set to **172.7 kPa**, while the pressure at the flange is **4,727 kPa**.
- **Temperature**: The thermal load on the nozzle reaches a maximum of **500°C**, which is critical for analyzing thermal expansion effects.
- **Bolted Joint**: We will analyze the forces acting on the bolts and the overall deformation of the joint.

## How to Use

1. **Clone the Repository**:
   - Open a terminal and run:
     ```bash
     git clone https://github.com/yourusername/SaturnV-FEA-Analysis.git
     ```
   - Navigate to the repository directory:
     ```bash
     cd SaturnV-FEA-Analysis
     ```

2. **Open the ANSYS Project**:
   - Open **ANSYS Workbench**.
   - In ANSYS, go to **File > Open** and select the `FEA_Simulations/SaturnV_F1_ANSYS_Model.ansyswb` file.

3. **Load the Geometry and Mesh**:
   - Ensure that the geometry and mesh file (`FEA_Simulations/SaturnV_F1_Mesh.agdb`) is properly linked within the project.
   - If needed, re-mesh the model based on the setup provided.

4. **Set the Material Properties**:
   - Import the material data from `FEA_Simulations/SaturnV_F1_MaterialData.xml` into your ANSYS Workbench project to apply the correct material properties.

5. **Run the Simulation**:
   - Set the boundary conditions for temperature and pressure as described in the problem specifications.
   - Run the simulation to generate the results.

6. **View Results**:
   - After the simulation completes, open the **Results** module in ANSYS Workbench.
   - Load the `FEA_Simulations/SaturnV_F1_SimulationResults.rst` file to review the stress, deformation, and safety margin results.

## Contributing

Contributions are welcome! If you'd like to contribute, feel free to fork the repository and submit a pull request. Ensure your changes are well documented.

images/: Contains the images related to the project, such as the Saturn V rocket, the F1 nozzle, and ANSYS model screenshots.
FEA_Simulations/: Contains the ANSYS simulation files, including:
.wbpz file for the Workbench project setup.
Geometry and mesh file (.stl) used in the analysis.
Simulation results file (.rst) for reviewing stress distribution and deformation.
Material data file (.engd) that defines the properties for the nozzle and bolts.
Results/: Contains any output results generated from the simulation, such as images or plots showing stress distribution and deformation of the nozzle.
docs/: Includes documentation files such as the detailed problem specification and references used in the analysis.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
