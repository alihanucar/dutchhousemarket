
# Dutch House Market Analysis - CBS.NL 

Following my discovery of the robust Dutch housing market, I set out to develop a series of automated indicators using the Netherlands Statistics Bureau (also known as CBS) Python open data API. This API can be installed using the guidance provided at https://pypi.org/project/cbsodata/. My work was inspired by research reports from several Dutch mortgage loan asset management companies, such as Dynamic Credit and DMFCO. 

However, I would like to express my concern about the inconsistent date value structure of the CBS data. Each table has a unique format, with some containing information such as the year and quarter (e.g. 2021 3rd quarter), while others only have the month (e.g. 2022 November). This makes the automation process more complex, as each table requires different cleaning and handling codes. I kindly request that if someone from the CBS reads this research, they standardize the date values and make the data available for download with parameters for YoY change, MoM change, and YTD change. This is a feature that is available from the Turkish Central Bank Data Bank (EVDS).

With this in mind, I have prepared six charts, each of which I will explain in detail below. I may update the scripts in time with new charts. 



![Logo](https://lh3.googleusercontent.com/p/AF1QipP7XFj0fz3hLvon8o9HUVs1igaayaF7lWJpzDR_=s1360-w1360-h1020)


## 1) Rent increase dwellings by region with heatmap graph:

The purpose of the code is to create a heatmap of the YoY rent increase rates by region using data from the CBS.

The code first imports the required libraries (pandas, seaborn, and matplotlib) and sets some configurations to make the graph look better. It then defines the CBS data source for the rent increase rates, retrieves the data using the cbsodata library, and converts the values to a percentage format.

Next, the code creates a pivot table with regions as the index and periods (years) as the columns, and uses the Seaborn library to plot the pivot table as a heatmap


## 2) Netherlands Consumer Confidence Index Rate:

The purpose of the code is to visualize the Netherlands Consumer Confidence Index data over time. It uses the pandas and matplotlib libraries to process and plot the data.

It loads the data using the cbsodata library and filters the data to only include data between the start and end dates. The resulting data is then plotted as a line graph using the ax.plot() function from the matplotlib library. The y-axis of the graph is limited to the minimum and maximum values using the ax.set_ylim() function, and the x-axis is represented by dates. A horizontal line is added to the graph to indicate the zero mark, and the title and y-axis label of the graph are set. The graph is displayed using the plt.show() function.


## 3) Expenditures of households:

"82608ENG" This table provides figures on the expenditures of households in values and volume. The figures are divided in domestic consumption and final consumption by households. When examining consumer confidence, it’s important to consider whether the pessimism has materialized in the economy. We use volume values on our visualization to understand consumption by households. The purpose of the code is to plot a bar graph of the volume changes metric for domestic consumption by households in the Netherlands from January 2019 to December 2022


## 4) House Price Index (HPI) and numbers of the quarterly sold properties:

The purpose of the code is to plot the Dutch House Price Index (HPI) and the number of dwellings sold in a quarterly basis from 2015 to 2022. The code uses the CBS Open Data API to retrieve the data for the HPI and filters it for the specified periods. The data is then grouped and unstacked to separate the data for new own homes and existing own homes. The HPI is plotted on a line graph, while the number of dwellings sold is plotted on a stacked column chart. Both charts are combined into one plot with two y-axes and a legend is added to distinguish between the two.


## 5) House Price Index values for European Countries with openBB:

The purpose of this code is to retrieve house price index data for six European countries (Netherlands, Germany, France, Belgium, Sweden, and Spain) and compare their data using a line plot. The data is obtained using the openbb_terminal.sdk library's economy.macro function, which is imported as openbb. The data is filtered to include only the house price index (HOU) and only the data within the time frame of 2009-01-01 to 2022-07-01. The first value of each series is divided by 100 to get the rate, and this rate is applied to each data point to normalize the data. The line plot is created using the matplotlib library, and the title of the plot is set to "European Countries House Price Index Comparison." Finally, the data is saved to an Excel file named "nethouse.xlsx". If you wonder how to install openBB SDK library here is the link https://docs.openbb.co/sdk/quickstart/installation . They group the data queried from the EconDB database.


## 6) Netherlands Residential Building Permits (YoY %):

The purpose of the code is to analyze and visualize the Netherlands Residential Building Permits YoY rate data over a specified date range, starting from 2012-01-30 to 2022-11-30. The data is obtained from CBS Open Data using the "cbsodata" library and is stored in a Pandas DataFrame. The date range is created using the "pd.date_range" function and the YoY rate is calculated using the "pct_change" method of the Pandas DataFrame. After cleaning and manipulating the data, it is saved in an Excel file. Finally, a bar chart is created to visualize the YoY rate of residential building permits in the Netherlands over time. 



    
