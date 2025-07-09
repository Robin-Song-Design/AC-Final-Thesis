### **Weekly Report: Development and Validation of a Simulation Framework for Office Egress Analysis**

**Reporting Period**: June 30, 2025 
**Research Topic**: The Impact of Office Element Layout (e.g., Desks) on Evacuation Efficiency 
**Primary Objective for this Period**: To validate and select a stable and realistic computational model for simulating office evacuation scenarios, and to finalize the construction of a parametric simulation tool based on this model.

#### **1. Introduction: Research Challenge and Methodological Approach**

The core challenge of this research lies in the unique geometric properties of office spaces, which feature a high density of discrete, compact obstacles (desks, partitions, etc.). This places stringent demands on the **stability and realism** of any pedestrian simulation algorithm. Therefore, before proceeding with a comparative analysis of different layouts, a rigorous **selection and validation of the simulation engine** is paramount to ensure the scientific credibility of the research findings. The work this week was focused entirely on this critical prerequisite.

#### **2. Model Validation

To identify the most suitable computational core for this thesis, a series of models were systematically tested and evaluated:

- **Model 1: `CollisionFreeSpeedModel` (Original Version)**
    
    - **Observation**: It was discovered that this model produced a significant distortion: towards the end of the simulation, the last few agents would move exceptionally slowly, even in an open, uncrowded environment.
        
    - **Assessment**: This phenomenon was not a result of realistic physical congestion but rather an algorithmic limitation of the model at low densities. It systematically and non-physically inflates the total evacuation time, creating a severe bias in our primary research metric.
        
    - **Conclusion**: **Rejected**. Unsuitable for research requiring the precise measurement of total evacuation time.
        
- **Model 2: `SocialForceModel`**
    
    - **Observation**: While this is an industry-standard model, it proved to be highly sensitive to boundary conditions. When simulating compact layouts like office desks, the powerful repulsive forces calculated as agents approached obstacles led to numerical instability, frequently triggering a fatal `Point is outside of accessible area` error and halting the simulation.
        
    - **Assessment**: Although fine-tuning parameters (e.g., `obstacle_scale`) could potentially mitigate this issue, doing so for every layout scenario would drastically reduce research efficiency and the general applicability of the findings.
        
    - **Conclusion**: **Rejected**. For research that requires the rapid iteration of numerous geometric layouts, this model proved to be too fragile and inefficient.
        
- **Final Selection: `CollisionFreeSpeedModelV2` (Second-Generation Collision-Free Speed Model)**
    
    - **Observation**: Upon switching to the `V2` version, both of the critical issues encountered previously were resolved:
        
        1. Agents at the end of the simulation proceeded to their exits at their expected desired speed, eliminating the "tailing" distortion.
            
        2. The simulation demonstrated high stability near compact boundaries, with no reoccurrence of the "out of bounds" error.
            
    - **Assessment**: The `V2` model has clearly undergone algorithmic improvements and optimizations that address the shortcomings of its predecessor. It achieves an optimal balance between computational speed, numerical stability, and behavioral realism in complex boundary and variable-density environments.
        
    - **Conclusion**: **Validated and Selected**. `CollisionFreeSpeedModelV2` is confirmed as the **most suitable simulation engine for this thesis research**. It provides a fair, reliable, and robust computational foundation for the subsequent comparative analysis of layout schemes.
        

#### **3. Significance for the Thesis Research**

The most critical outcome of this week's work was not merely "writing code," but completing a crucial step in the **research methodology: the validation and establishment of the computational model.**

Through a rigorous and reproducible process of elimination, we have demonstrated that `CollisionFreeSpeedModelV2` is the most scientific and appropriate tool to support the conclusions of this thesis. This ensures that all subsequent research is built upon a solid and credible foundation. **This section can directly form a core argument within the "Methodology" chapter of the final thesis**, showcasing the due diligence performed to guarantee the validity of the study.

**Next Steps**: With the `CollisionFreeSpeedModelV2` validated and the parametric Grasshopper tool finalized, the project will now proceed to the core research phase: the systematic experimentation with different office layouts and the subsequent collection and analysis of performance data.

