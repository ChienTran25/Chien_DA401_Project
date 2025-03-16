Automotive Industry Analysis Post-2018 Tariffs
Overview
This project investigates the impact of Trump's 2018 steel and aluminum tariffs on the automotive industry. The primary objective is to assess how the tariffs affected key performance indicators—such as production, input costs, and employment—within the automotive sector relative to a control group of industries that are less dependent on steel and aluminum.

Data Sources and Variables
The analysis utilizes several datasets, which have been processed and aggregated for clarity and consistency. Below are the main variables and the corresponding data sources:

Datasets
RealGross
Source: Bureau of Economic Analysis (BEA)
Description: Real gross output data (in billions of 2017 dollars) for various manufacturing industries.

ValAdded
Source: Bureau of Economic Analysis (BEA)
Description: Real value added data (in billions of 2017 dollars) across the industries.

Input_P
Source: BEA (Intermediate Inputs)
Description: Real input price data (in billions of 2017 dollars) representing the cost of intermediate inputs.

Employment Data
Source: Various employment Excel files (e.g., Motor vehicles and parts, Chemical manufacturing, Machinery manufacturing, etc.)
Description: Quarterly employment figures for each industry. Data has been aggregated to provide a comprehensive quarterly time series for analysis.

Industry Groups
The analysis focuses on the following nine industries:

Motor vehicles, bodies and trailers, and parts (Treatment group)
Chemical products (Control group)
Machinery
Food and beverage and tobacco products
Plastics and rubber products
Wood products
Furniture and related products
Electrical equipment, appliances, and components
Paper products
Key Variables for Analysis
Industry:
Identifies the manufacturing sector.

RealGross:
Real gross output measured in billions of 2017 dollars.

ValAdded:
Real value added, also in billions of 2017 dollars.

InputPrice:
Real input prices indicating the cost of intermediate inputs.

Employment:
Quarterly employment figures aggregated by industry.

Treatment Indicators (for DiD analysis):

Treated: Equals 1 for the automotive industry (Motor vehicles, bodies and trailers, and parts) and 0 for the control industry (Chemical products).
Post: Equals 1 for dates after the tariffs were implemented (April 2018 onward) and 0 otherwise.
Methodology
Data Cleaning and Transformation:
The raw datasets are imported, filtered by industry, and cleaned (e.g., standardizing date formats and scaling numeric values). Employment data is aggregated into quarterly observations.

Visualization:
Line plots are generated to visualize trends over time for the key metrics—employment, real gross output, value added, and input prices—across industries.

Difference-in-Differences (DiD) Analysis:
A preliminary DiD model compares the automotive industry with a control group (Chemical products) before and after the tariff implementation to examine the differential impact on real gross output and input prices.

How to Run the Project
Prerequisites:
Ensure that the following R libraries are installed:

tidyverse
readxl
lubridate
ggplot2
Synth
plm
Data Files:
Place the Excel files in your working directory:

GrossOutput.xlsx
IntermediateInputs.xlsx
ValueAdded.xlsx
Employment data files (e.g., Motor vehicles and parts.xlsx, Chemical manufacturing.xlsx, etc.)
Execution:
Run the provided R script to load, clean, visualize the data, and conduct the DiD analysis.

Next Steps
Methodological Refinement:
Further refine the synthetic control method to establish a more robust control variable.

Robustness Testing:
Incorporate additional tests (e.g., placebo and sensitivity analyses) to validate the findings.

Extended Analysis:
Consider integrating additional macroeconomic or firm-level data to account for external factors such as the COVID-19 pandemic.
