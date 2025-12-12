---
output:
  pdf_document: default
  html_document: default
---
# BassettGRHowey
ENV 872 Course Project: Sara Bassett, Xia Meng Howey, Maeve Gualtieri-Reed

## Summary

These datasets were prepared for ENV 872 in Fall 2025 by Sara Bassett, Xia Meng Howey, Maeve Gualtieri-Reed.

The datasets included are Air Quality Data in Texas from 2019 to 2023, eGRID annual reports from 2019 to 2023 and precipitation data from Harris and Dallas county from NOAA for 2019-2023. It investigates air quality levels in Texas through three analyses: correlation between Texas county air quality and power plant emissions, air quality and emission trends over time in Harris county, and correlation between county precipitation and air quality. The results did not indicate a significant relationship between precipitation or power plant emissions and air quality but provides an interesting look into local air quality.

## Investigators

Sara Basset, Xia Meng Howey, Maeve Gualtieri-Reed

## Keywords

Emissions, Air Quality, Power Plant, Precipitation, Texas

# Database information and meta data

## Air Quality Data
Data was downloaded here: https://www.epa.gov/outdoor-air-quality-data/download-daily-data
The following selections were made: 
* PM2.5 and Ozone (Pollutant)
* 2019, 2020, 2021, 2022, 2023 (Year)
* Texas (Geographic Area)
* Download CSV (spreadsheet)

Saved in the following format: StatePollutantYear.csv 
*example: TXOzone19.csv

State, County, Site.Latitude, Site.Longitude are self explanatory

Date: m/d/y

Daily.AQI.Value: Air quality rating value
* 0-50: Good
* 51-100: Moderate
* 101-150: Unhealthy for sensitive groups
* 151-200: Unhealthy
* 201-300: Very unhealthy
* 301-500: Hazardous

AQS.Parameter.Description: Type of pollutant (Ozone or PM2.5)

Local.Site.Name: Name of monitor site

## eGRID data
2023 data was downloaded here: https://www.epa.gov/egrid/detailed-data
2019 - 2022 data was downloaded here: https://www.epa.gov/egrid/historical-egrid-data

"PLNT" tab was extracted and converted to .csv. Formatting was cleared to ensure numeric values were imported correctly

Saved according to the downloaded data name + "_PLNT"
* egrid2019_data_PLNT.csv
* eGRID2020_Data_v2_PLNT.csv
* eGRID2021_data_PLNT.csv
* egrid2022_data_PLNT.csv
* egrid2023_data_rev2_PLNT.csv

Data.Year, Plant.state.abbreviation, Plant.county.name, Plant.latitude, Plant.longitude are self explanatory

Plant.name: Name of plant reporting

Plant.primary.fuel: Primary fuel to power the plant. Information found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

* AB = Agricultural byproduct
* BFG = Blast furnace gas
* BIT = Bituminous coal
* BLQ = Black liquor
* COG = Coke oven gas
* DFO = Distillate fuel oil, light fuel oil, diesel oil
* GEO = Geothermal steam
* H2 = Hydrogen
* JF = Jet fuel
* KER = Kerosene
* LFG = Landfill gas
* LIG = Lignite coal
* MSW = Municipal solid waste
* MWH = Electricity used for energy storage (megawatt hour)
* NG = Natural gas
* NUC = Nuclear material
* OBG = Other biomass gas
* OBL = Other biomass liquid
* OBS = Other biomass solid
* OG = Other gas
* OTH = Other (unknown)
* PC = Petroleum coke
* PG = Gaseous propane
* PRG = Process gas
* PUR = Purchased fuel (unknown)
* RC = Refined coal
* RFO = Residual fuel oil, heavy fuel oil, petroleum
* SGC = Coal-derived synthetic gas
* SLW = Sludge waste
* SUB = Subbituminous coal
* SUN = Sun
* TDF = Tire-derived fuel
* WAT = Water
* WC = Waste coal
* WDL = Wood, wood waste liquid
* WDS = Wood, wood waste solid
* WH = Waste heat
* WND = Wind
* WO = Waste oil

Plant.annual.NOx.emissions..tons: Total annual NOx emissions estimated for the plant in tons. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.SO2.emissions..tons: Total annual SO2 emissions estimated for the plant in tons. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.CO2.emissions..tons:Total annual CO2 emissions estimated for the plant in tons. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.CH4.emissions..lbs:Total annual CH4 emissions estimated for the plant in pounds. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.N2O.emissions..lbs:Total annual N2O emissions estimated for the plant in pounds. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.CO2.equivalent.emissions..tons: Total annual equivalent CO2 emissions estimated for the plant in tons. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)

Plant.annual.Hg.emissions..lbs: Total annual Hg emissions estimated for the plant in pounds. Methods for estimation found in the eGRID 2023 Technical Guide (https://www.epa.gov/system/files/documents/2025-01/egrid2023_technical_guide.pdf)


## Precipitation data
Data was downloaded here: https://www.ncdc.noaa.gov/cdo-web/
The following selections were made: 
* Select Weather Observation Type/Dataset: Daily Summaries
* Select Date Range: 01/01/2019 - 12/31/2023
* Search For: Counties
* Search Term: Harris, TX and Dallas, TX
* Download CSV (spreadsheet)

Saved in the following format: CountyCoRain.csv 

## Folder structure, file formats, and naming conventions 
All raw data is stored in \BassetGRHowey\Data and wrangled directly in this file. Code fragments are stored in \BassetGRHowey\Rmd and the final complete code, called TexasEmissionsAQI.Rmd is stored \BassetGRHowey\FinalProduct. The final knitted pdf version of this .Rmd is in the same folder called TexasEmissionsAQI.pdf. The source image used in the report is stored in \BassetGRHowey\Figures.
