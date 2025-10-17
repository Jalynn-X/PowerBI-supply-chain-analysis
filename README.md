# Supply Chain Analysis with PowerBI

This project helps businesses make **data-driven sourcing decisions**, whether to manufacture components internally or purchase them externally, by combining three interactive analytical reports: **Supplier Selection Analysis**, **Scenario Analysis**, and **Make vs Buy Analysis**.


## Objective
Deliver an **interactive and scalable decision-support tool** that enables supply chain and operations professionals to:
-   Quantify trade-offs between **in-house manufacturing** and **outsourcing**
-   Visualize **cost trends**, **break-even points**, and **supplier competitiveness**
-   Support **strategic sourcing** and **production planning** with data-driven insights


## Project Overview
The project combines **three key analytical reports** to provide a comprehensive view of sourcing strategies:

1.  **Supplier Selection:** 
-   Automatically identifies the **supplier with the lowest cost** based on filters.
-   Evaluates detailed cost components, including **Non-Recurring Cost (NRC)**, **Unit Cost**, and **Full Cost**, across different volumes and suppliers.
![Supplier Selection Dashboard](https://github.com/Jalynn-X/PowerBI-supply-chain-analysis/blob/main/images/Supplier%20Selection%20Dashboard.PNG)

2.  **Scenario Planner:**  
-   Simulates **cost trends** under varying production volumes for the Buy option.
-   Highlights the **lowest-cost supplier** interactively based on filters, enabling quick identification of optimal sourcing partners.
![Scenario Planner Dashboard](https://github.com/Jalynn-X/PowerBI-supply-chain-analysis/blob/main/images/Scenario%20Planner%20Dashboard.PNG)
    
3.  **Make vs Buy:**  
-   Compares **total costs** of Make (internal manufacturing) versus Buy (external procurement).
-   Identifies the **most cost-effective sourcing strategy** under different business assumptions and conditions.
![Make vs Buy Dashboard](https://github.com/Jalynn-X/PowerBI-supply-chain-analysis/blob/main/images/Make%20versus%20Buy%20Dashboard.PNG)

## Custom Measures
The Power BI model includes **custom DAX measures** to calculate and compare costs across scenarios:
-   **Extended Cost:**  
    Calculates **Unit Cost × Production Volume**, representing the total variable cost for a given production quantity.
-   **Full Cost:**  
    Combines **Non-Recurring Cost (NRC)** and **Extended Cost** to provide a complete view of overall expenditure.
-   **Buy Scenario Full Cost:**  
    Calculates the total cost of purchasing components for a given scenario volume based on supplier quotes.
    -   Identifies the **applicable quote tier** according to scenario volume
    -   Adjusts for each supplier’s **yield rate**
    -   Includes **Non-Recurring Expenses (NRE)** in the total cost
        
-   **Additional Unit Capacity Required:**  
    Calculates the **extra production capacity** needed to meet a scenario’s volume by comparing required volume against existing machine capacity.
    
-   **Capital Investment Required (Make):**  
    Calculates the **capital investment** needed for internal manufacturing to cover additional capacity.
    
-   **Make Scenario Full Cost:**  
    Computes the **total internal manufacturing cost** by combining capital investment with **variable production costs** based on scenario volume.
    
-   **Cost Avoidance:**  
    Calculates the **absolute cost difference** between Make and Buy options to measure potential savings or extra expenditure.
    
-   **Make vs Buy:**  
    Determines the **preferred sourcing option** based on total costs:
    
    -   Returns Make if internal manufacturing is cheaper or equal
    -   Returns Buy if external procurement is cheaper
    -   Returns blank if no internal manufacturing data exists for the scenario

