# assignment-3-IOT451
data analytics on childrens health inequality

My Analysis:
The bar chart demonstrates the disparities in health perceptions across the selected boroughs. More affluent boroughs, such as Richmond upon Thames and Kingston upon Thames report the highest percentages of teens describing their general health as excellent, whilst less affluent areas like Tower Hamlets and Hackney have lower percentages. This emphasises how more poverty-stricken boroughs tend to have more health implications, possibly due to fewer aiding facilities available to children. It may seem conflicting how  affluent boroughs display higher percentages of residents with long-term illnesses or disabilities, however this could be due to these areas having more private healthcare and access to doctors, thus leading to fast treatment and services. These findings highlight the need for targeted public health interventions for children in less affluent boroughs to address disparities and promote equitable health outcomes.

Code:

import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

#Load the dataset
data = pd.read_csv('borough.csv')

#areas we are looking at
filtered_areas = ["Tower Hamlets", "Newham", "Hackney","Kingston upon Thames", "Richmond upon Thames", "Bromley"]

#indicators i focused on
filtered_indicators = ["Percentage reporting general health as excellent","Percentage of those with a long-term illness, disability or medical condition diagnosed by a doctor"]

#filter the dataset for the relevant areas and indicators
filtered_data = data[(data["Area Name"].isin(filtered_areas)) & (data["Indicator"].isin(filtered_indicators))]

#Create a bar chart
bar_width = 0.30  # width of the bars
index = np.arange(len(pivot_data.index))  # borough positioning

#show a bar for each indicator
fig, ax = plt.subplots(figsize=(9, 7))
for i, indicator in enumerate(indicators_of_interest):
    ax.bar(
        index + i * bar_width,
        pivot_data[indicator],
        bar_width,
        label=indicator
    )

#design of the plot
ax.set_title("Reported Health Comparison by Borough", fontsize=14)
ax.set_xlabel("Borough", fontsize=12)
ax.set_ylabel("Percentage", fontsize=12)
ax.set_xticks(index + bar_width / 2)
ax.set_xticklabels(pivot_data.index, rotation=45, fontsize=10)
ax.legend(fontsize=10)
ax.grid(axis='y', linestyle='-', alpha=0.7)

#Show the plot
plt.tight_layout()
plt.show()

