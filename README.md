# Apple_carbon_emission_progress_report
![Apple_Carbon_Footprint - Copy1](https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/7479510d-3c4c-4682-8893-26b3c277ec18)


## Project Overview

This project aims to analyse the data provided by Apple in their Environmental Progress Report to visualize their progression towards becoming carbon neutral in 203

## Problem Statement
Apple unveiled its plan to become carbon neutral across its entire business, manufacturing supply chain, and product life cycle by 2030. Implying every Apple device sold will have net zero climate impact.
In its 2020 Environmental Progress Report Apple details its plans to reduce emissions by 75%setting their emissions for 2015 (38.4 million metric tons CO2e) as the baseline. While developing innovative carbon removal solutions for the remaining 25%(9.6 million metric tons CO2e)  of its comprehensive footprint.


## Data Source
The data was obtained as excel files from a secondary source. Following are the excel workbooks included:
  - `carbon_footprint_by_product.xlsx`:contains the emissions from the product life cycle of every baseline iPhone model released between 2015-2022.
  - `greenhouse_gas_emissions.xlsx`: contains the sources of Apple's greenhouse gas emissions from 2015 to 2022 divided by category (corporate & product life cycle), scope (direct scope 1 emissions & indirect scope 2 and 3 emissions), and type (emissions & removals)
  - `normalizing_factors.xlsx`: contains Apple's revenue, market cap, and employees during the same period.
- `data_dictionary.xlsx`: This workbook contains information about all the tables and the fields in them.


## Tools used 
- `Power query`: to connect to data sources, shape and transform the data,then load that model into Power BI desktop.
- `Power Bi`:For analysing and visualising the data and building the dashboard.

## Data Analysis
### Data Preprocessing 
Loading the dataset into the Power query editor then transforming the data, dealing with null, blank and inappropriate values.

### Data Visualization And Insights
Build various interactive charts and matrix visualizations to extract meaningful insights.
To enhance the analysis
#### Measures  created using Power Bi 
Custom measures for key CAGRs (Compound Annual Growth Rate) for market capitalization, Revenue,Employees and Reduction% in emission were created using Power BI, allowing for more sophisticated calculations and insights.

<pre><code>

(

CAGR  market cap = var growth = DIVIDE([Market cap max year],[Market cap min year],0)
 var years = MAX(normalizing_factors[Fiscal Year])-Min(normalizing_factors[Fiscal Year])
 var CAGR= POWER(growth,1/years)-1
 return
 FORMAT(CAGR,"+0.0%;-0.0%")

 CAGR  Revenue = var growth = DIVIDE([Revenue max year],[Revenue min year],0)
 var years = MAX(normalizing_factors[Fiscal Year])-Min(normalizing_factors[Fiscal Year])
 var CAGR= POWER(growth,1/years)-1
 return
 FORMAT(CAGR,"+0.0%;-0.0%")

 CAGR  employee = var growth = DIVIDE([employee max year],[employee min year],0)
 var years = MAX(normalizing_factors[Fiscal Year])-Min(normalizing_factors[Fiscal Year])
 var CAGR= POWER(growth,1/years)-1
 return
 FORMAT(CAGR,"+0.0%;-0.0%")

 Reduction % = var reduction = CALCULATE(([Reduction % max value]-[Reduction % min value])/[Reduction % min value])

 return
 FORMAT(reduction,"+0.0%;-0.0%")
)

</code></pre>

### Report Preview

<div align="center">
  <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/a02a5b8c-2b88-4e90-ae9f-705b09d3842d" />
</div>


### Insights
<table>
  <tr>
    <td valign="middle">
      <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/d6a9c57b-5a25-45a7-b4fb-772b1ff848e8" alt="Emissions by fiscal year" width="3000" height="200" />
    </td>
    <td valign="top">
      <strong>Steady Emission Decline Post-2019:</strong><br /><br />
      Apple has remarkably reduced its emissions by 47.2% in just seven years, almost reaching the 50% threshold.  2022 emissions stand at 20.3 million metric tones, with eight more years to meet our 2030 objective of 9.6 million metric tones. 
    </td>
  </tr>
</table>


<table>
  <tr>
    <td valign="top">
      <strong> carbonfootprint trends for different products:</strong><br /><br />
      With a carbon footprint of 79, the iPhone X was 46.30% more carbon-intensive than the iPhone 6s, which had the lowest carbon footprint of 54. Out of all these things, the iPhone X was accountable for 12.36% of the carbon footprint. The carbon footprint of each of the ten products ranged from 54 to 79, with some being more ecologically friendly than others.
    </td>
    <td valign="middle">
      <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/7bcdf01a-51a5-43cd-a3d9-ddfd8bfc446b" width="3000" height="200" />
    </td>
  </tr>
</table>


<table>
  <tr>
    <td valign="middle">
      <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/aed73193-b29d-4953-8618-db7e66c45a02" alt="image" width="3000" height="200" />
    </td>
    <td valign="top">
      <strong>Key Emission Contributors:</strong><br /><br />
      For emissions, there were fifteen distinct reporting types . After analysis  it was found more than 95% of all emissions were related to manufacturing, product transportation, and product use. Consequently, the remaining 12 emissions categories were combined into "Others" and retained the primary contributors as separate groups. Indicating that the majority of emission reductions were attributable to manufacturing. Finding that emissions from product consumption were stagnating but emissions from product transportation actually grew till 2022.
    </td>
  </tr>
</table>


<table>
  <tr >
     <strong>Tracking 7 years of Bussiness Success:</strong><br /><br />
      Counterintuitively,exponential reduction in carbon emissions has positively impacted the business. Revenue and market capitalization have been consistently increasing since 2015, reaching their zenith in 2022. This demonstrates that  company's commitment to sustainability aligns with financial growth. to take into account  the effect of compounding  key CAGRs (Compound annual growth rates) for market cap,revenue and employee growth have been calculated implying positive growth over 7 years.
    </tr>

  <tr>
    <td valign="middle">
      <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/76efcecc-4e18-4ab8-9f64-33a98389ba4f" alt="Emissions by fiscal year" width="700" height="200" />
    </td>
    <td valign="middle">
     <img src="https://github.com/deepanshak/Apple_carbon_emission_progress_report/assets/139687677/e7446530-f4da-4458-9afd-873a41bba543" alt="Emissions by fiscal year" width="501" height="300" />
    </td>
  </tr>
 
</table>

## Recommendations

Following are the recommendations made based on the analysis:
- They need to find a way to reduce transportation and product use emissions, or maybe prepare to raise the quota of the offsets that will be required to meet net zero.
- Create products with net zero carbon impact, prioritizing nature-based solutions,focusing on emissions reduction,making low-carbon products.
- Educate and incentivize customers to use products in an environmentally responsible manner. This may involve optimizing device settings, prolonging product lifecycles, use only recycled and renewable materials in products and packaging will be another great step towards sustinability.
- Transition entire product supply chain to reduce emissions associated with manufacturing.
  








