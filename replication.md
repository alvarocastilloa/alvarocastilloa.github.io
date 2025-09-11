# Overview

This replication package contains the code used in both the aggregate and microdata analysis in this paper. For the aggregate analysis, all code and data (with the exception of the proprietary Consensus Economics forecasts) are included and can be run on a computer with Stata to reproduce the results of this analysis. For the microdata analysis, replicators will need to be approved for Statistics Sweden's secure MONA server in order to access the data and run the code. We provide the full code for the microdata analysis in this package, along with instructions for how to replicate the analysis from within the MONA server. 

# Data Availability and Provenance Statements

Some data cannot be made publicly available.

## Statement about rights

 - [x] I certify that the author(s) of the manuscript have legitimate access to and permission to use the data used in this manuscript.
 - [x] I certify that the author(s) of the manuscript have documented permission to redistribute/publish the data contained within this replication package. 

## License for data

The data are licensed under a Creative Commons/CC-BY-NC license. See LICENSE.txt for details.

## Summary of availability

 - [x] Some data cannot be made publicly available.

 - [x] Confidential data used in this paper and not provided as part of the public replication package will be preserved for at least five years after publication, in accordance with journal policies.

 - [x] Authors will provide reasonable assistance to requests for clarification and replication, in accordance with journal policies.
 

## Details on each data source & Dataset list

| Data Name                                                         | Data Files                                           | Location                                            | Provided |
| ----------------------------------------------------------------- | ---------------------------------------------------- | --------------------------------------------------- | -------- |
| Sweden Haver variables                                            | sweden_indicators_haver.dta                          | data/external                                       | Yes      |
| OECD Haver variables                                              | oecd_indicators_haver.dta                            | data/external                                       | Yes      |
| Misc. Haver variables                                             | misc_indicators_haver.dta                            | data/external                                       | Yes      |
| Riksbank Monetary Policy Reports                                  | Many files, e.g. data_1002eng.xls, mpu_data_1004.xls | data/external/riksbank_mprs                         | Yes      |
| Riksbank meeting dates                                            | riksbank_meeting_dates.xlsx                          | data/external                                       | Yes      |
| Prospera repo rate expectations                                   | Master.xlsx                                          | data/external/repo_expectations                     | Yes      |
| Consensus Economics, Inc. forecasts                               | consensus_forecasts_sweden.xlsx                      | data/external                                       | No\*     |
| Riksbank policy rate                                              | Daily-Repo-Rate.xlsx                                 | data/external                                       | Yes      |
| Euro-area 3-month Interbank rate                                  | euro_3mth_rate_fred.dta                              | data/external                                       | Yes      |
| Riksbank KIX-rate weights                                         | kix-vikter_eng2.xlsx                                 | data/external/kixrate                               | Yes      |
| Statistics Sweden debt-to-income series                           | household_debt_quarterly.xlsx                        | data/external/loans                                 | Yes      |
| World Trade Flows data                                            | wtf_bilateral_2007_rev_2.dta                         | data/external/trade                                 | Yes      |
| Statistics Norway unemployed for 1-4 weeks                        | Nor_Merge.csv                                        | data/external/layoffs_and_vacancies                 | Yes      |
| US unemployed less than 5 weeks, FRED series UEMPLT5              | US-unemployed_less_5_weeks.xls                       | data/external/layoffs_and_vacancies                 | Yes      |
| LFS redundancies rate for UK                                      | UK-redundencies.xls                                  | data/external/layoffs_and_vacancies                 | Yes      |
| Layoff measures for Denmark, Spain, France, Italy, and Portugal   | layoff_data.csv                                      | data/external/layoffs_and_vacancies                 | Yes      |
| OECD Job vacancies for Norway, Portugal, Spain, & Sweden          | Vacancy_Data.csv                                     | data/external/layoffs_and_vacancies                 | Yes      |
| New job vacancies for France, FRED series LMJVTTNVFRQ647S         | France-vacancies.xls                                 | data/external/layoffs_and_vacancies                 | Yes      |
| Eurostat employment for France                                    | france_employment.xlsx                               | data/external/layoffs_and_vacancies                 | Yes      |
| Barnichon & Garda (2016) estimated transition rates               | Transitions_rates.xlsx                               | data/external/layoffs_and_vacancies/forecastur_oecd | Yes      |
| Historical help-wanted index for US from Barnichon (2010)         | data_us.xls                                          | data/external/layoffs_and_vacancies/forecastur_oecd | Yes      |

\* Synthetic file included to show correct file layout

Below we described how each data source listed in the table above was constructed:

 - Sweden Haver variables: This dataset was downloaded from Haver Analytics containing the series listed below. Reproducing this data file requires access to the NORDIC and G10 Haver databases, or downloading the individual series from their original sources (e.g. Statistics Sweden).

| .dta variable name | Haver mnemonic  | Description                                                                  | Original Data Source                    |
| ------------------ | --------------- | ---------------------------------------------------------------------------- | --------------------------------------- |
| unemp              | H144ELUR@G10    | Unemployment rate (%)                                                        | Statistics Sweden                       |
| policyrate         | SENRREPV@NORDIC | Average repo rate, official policy rate of the Riksbank (%)                  | Riksbank                                |
| emp                | H144ELE@G10     | Employment level (hundreds)                                                  | Statistics Sweden                       |
| pop                | SENELPW@NORDIC  | Working age population (hundreds)                                            | Statistics Sweden                       |
| regunemp           | SESELUCR@NORDIC | Registered unemployment rate (%)                                             | Swedish Public Employment Service       |
| layoffs            | SESELRE@NORDIC  | Layoffs (persons)                                                            | Swedish Public Employment Service       |
| hpi                | SENPH002@NORDIC | Real estate prices: 1 & 2-dwelling buildings for permanent living (1981=100) | Statistics Sweden                       |
| natunemp           | SEAVELUR@NORDIC | NIER equilibrium unemployment rate estimate (%)                              | National Institute of Economic Research |
| overnightrate      | SENRIB1D@NORDIC | Interbank overnight interest rate (%)                                        | Riksbank                                |
| tb3myield          | SENRTB3M@NORDIC | 3-month Treasury bill yields (%)                                             | Riksbank                                |
| mort2yyield        | SENRM2@NORDIC   | 2-year mortgage bond yield (%)                                               | Riksbank                                |
| exchrate           | SENXUSE@NORDIC  | Exchange rate, end of month (kronor per 1 US$)                               | Riksbank                                |
| newhomeloanrate    | SENRQHM@NORDIC  | Interest rate on new housing loans to households (%)                         | Statistics Sweden & Riksbank            |
| existhomeloanrate  | SENRLHH@NORDIC  | Interest rate on outstanding housing loans to households (%)                 | Statistics Sweden & Riksbank            |
| consloanrate       | SENRLHC@NORDIC  | Interest rate on loans to households for consumption (%)                     | Statistics Sweden & Riksbank            |
| totalhhloans       | SENFLHH@NORDIC  | Total lending to households (Mil. Kronor)                                    | Statistics Sweden & Riksbank            |
| totalcorploans     | SENCN@NORDIC    | Total lending to non-financial corporations (Mil. Kronor)                    | Statistics Sweden                       |

 - OECD Haver variables: This dataset was downloaded from Haver Analytics containing the series listed below from the OECD Main Economic Indicators. Reproducing this file requires access to the OECDMEI Haver database or reconstructing from the OECD's published data series. 

| .dta variable name       | Haver mnemonic   | Description                                                                   | Original Data Source          |
| ------------------------ | ---------------- | ----------------------------------------------------------------------------- | ----------------------------- |
| cpi_sweden               | N144PC@OECDMEI   | Sweden: Consumer Price Index (NSA, 2015=100)                                  | OECD Main Economic Indicators |
| cpif_sweden              | N144PCXG@OECDMEI | Sweden: CPI: All Items excl Food and Energy [OECD Group] (NSA, 2015=100)      | OECD Main Economic Indicators |
| exports_sweden           | C144GSXC@OECDMEI | Sweden: GDP: Exports of Goods & Services (SA, Bil.Ch.SEK)                     | OECD Main Economic Indicators |
| fixedinv_sweden          | C144GIC@OECDMEI  | Sweden: GDP: Gross Fixed Capital Formation (SA, Bil.Ch.SEK)                   | OECD Main Economic Indicators |
| gdp_australia            | C193GDPC@OECDMEI | Australia: Real Gross Domestic Product (SA, Bil.Ch.A$)                        | OECD Main Economic Indicators |
| gdp_austria              | C122GDPC@OECDMEI | Austria: Real Gross Domestic Product (SA, Bil.Chn.Euros)                      | OECD Main Economic Indicators |
| gdp_belgium              | C124GDPC@OECDMEI | Belgium: Real Gross Domestic Product (SA/WDA, Bil.Ch.Euros)                   | OECD Main Economic Indicators |
| gdp_brazil               | C223GDPC@OECDMEI | Brazil: Gross Domestic Product (SA, Bil.Chn.Reais)                            | OECD Main Economic Indicators |
| gdp_canada               | C156GDPC@OECDMEI | Canada: Real Gross Domestic Product (SA, Bil.Chn.C$)                          | OECD Main Economic Indicators |
| gdp_chile                | C228GDPC@OECDMEI | Chile: Real Gross Domestic Product (SA, Bil.Ch.Pesos)                         | OECD Main Economic Indicators |
| gdp_china                | C924GDPC@OECDMEI | China: GDP Constant Prices (Bil.Chn.CNY)                                      | OECD Main Economic Indicators |
| gdp_colombia             | C233GDPC@OECDMEI | Colombia: Gross Domestic Product (SA, Bil.Ch.COP)                             | OECD Main Economic Indicators |
| gdp_costa_rica           | C238GDPC@OECDMEI | Costa Rica: Real Gross Domestic Product (SA, Bil.Chn.CRC)                     | OECD Main Economic Indicators |
| gdp_czech_republic       | C935GDPC@OECDMEI | Czech Rep: Real Gross Domestic Product (SA/WDA, Bil.Ch.Koruny)                | OECD Main Economic Indicators |
| gdp_denmark              | C128GDPC@OECDMEI | Denmark: Real Gross Domestic Product (SA, Bil.Chn.DKK)                        | OECD Main Economic Indicators |
| gdp_estonia              | C939GDPC@OECDMEI | Estonia: Gross Domestic Product (SA, Bil.Ch.EUR)                              | OECD Main Economic Indicators |
| gdp_eu                   | C997GDPC@OECDMEI | European Union: Gross Domestic Product, Constant Prices (SA, Bil.US$)         | OECD Main Economic Indicators |
| gdp_euro                 | C023GDPC@OECDMEI | Euro Area: Real Gross Domestic Product (SA/WDA, Bil.Chn.Euro)                 | OECD Main Economic Indicators |
| gdp_finland              | C172GDPC@OECDMEI | Finland: Real Gross Domestic Product (SA, Bil.Chn.Euros)                      | OECD Main Economic Indicators |
| gdp_france               | C132GDPC@OECDMEI | France: Real Gross Domestic Product (SA/WDA, Bil.Chn.Euros)                   | OECD Main Economic Indicators |
| gdp_germany              | C134GDPC@OECDMEI | Germany: Real Gross Domestic Product (SA/WDA, Bil.Chn.Euros)                  | OECD Main Economic Indicators |
| gdp_greece               | C174GDPC@OECDMEI | Greece: Real Gross Domestic Product (Bil.Chn.Euros)                           | OECD Main Economic Indicators |
| gdp_hungary              | C944GDPC@OECDMEI | Hungary: Real Gross Domestic Product (SA/WDA, Bil.Chn.Forints)                | OECD Main Economic Indicators |
| gdp_iceland              | C176GDPC@OECDMEI | Iceland: Real Gross Domestic Product (SA, Bil.Ch.ISK)                         | OECD Main Economic Indicators |
| gdp_india                | C534GDPC@OECDMEI | India: Real Gross Domestic Product (SA, Bil.Chn.Rupee)                        | OECD Main Economic Indicators |
| gdp_indonesia            | C536GDPC@OECDMEI | Indonesia: Gross Domestic Product (SA, Trillions.Rupiahs)                     | OECD Main Economic Indicators |
| gdp_ireland              | C178GDPC@OECDMEI | Ireland: Real Gross Domestic Product (SA, Bil.Chn.Euros)                      | OECD Main Economic Indicators |
| gdp_israel               | C436GDPC@OECDMEI | Israel: Real Gross Domestic Product (SA, Bil.Ch.ILS)                          | OECD Main Economic Indicators |
| gdp_italy                | C136GDPC@OECDMEI | Italy: Real Gross Domestic Product (SA/WDA, Bil.Chn.Euros)                    | OECD Main Economic Indicators |
| gdp_japan                | C158GDPC@OECDMEI | Japan: Real Gross Domestic Product (SA, Bil.Chn.Yen)                          | OECD Main Economic Indicators |
| gdp_latvia               | C941GDPC@OECDMEI | Latvia: Gross Domestic Product (SA, Bil.Ch.EUR)                               | OECD Main Economic Indicators |
| gdp_lithuania            | C946GDPC@OECDMEI | Lithuania: Gross Domestic Product (SA, Bil.Chn.EUR)                           | OECD Main Economic Indicators |
| gdp_luxembourg           | C137GDPC@OECDMEI | Luxembourg: Real Gross Domestic Product (SA, Bil.Chn.Euros)                   | OECD Main Economic Indicators |
| gdp_mexico               | C273GDPC@OECDMEI | Mexico: Real Gross Domestic Product (SA, Bil.Ch.Pesos)                        | OECD Main Economic Indicators |
| gdp_netherlands          | C138GDPC@OECDMEI | Netherlands:  Real Gross Domestic Product (SA/WDA, Bil.Chn.Euros)             | OECD Main Economic Indicators |
| gdp_new_zealand          | C196GDPC@OECDMEI | New Zealand: Real Gross Domestic Product (SA, Bil.Ch.NZ$)                     | OECD Main Economic Indicators |
| gdp_norway               | C142GDPC@OECDMEI | Norway: Real Gross Domestic Product (SA, Bil.Chn.NOK)                         | OECD Main Economic Indicators |
| gdp_poland               | C964GDPC@OECDMEI | Poland: Real Gross Domestic Product (SA, Bil.Ch.Zlotys)                       | OECD Main Economic Indicators |
| gdp_portugal             | C182GDPC@OECDMEI | Portugal: Real Gross Domestic Product (SA, Bil.Ch.Euros)                      | OECD Main Economic Indicators |
| gdp_russia               | C922GDPC@OECDMEI | Russia: Real Gross Domestic Product (SA, Bil.Roubles)                         | OECD Main Economic Indicators |
| gdp_slovakia             | C936GDPC@OECDMEI | Slovakia: Real Gross Domestic Product (SA, Bil.Ch.EUR)                        | OECD Main Economic Indicators |
| gdp_slovenia             | C961GDPC@OECDMEI | Slovenia: Real Gross Domestic Product (SA, Bil.Ch.Euros)                      | OECD Main Economic Indicators |
| gdp_south_africa         | C199GDPC@OECDMEI | South Africa: Gross Domestic Product (SA, Bil.Rand)                           | OECD Main Economic Indicators |
| gdp_south_korea          | C542GDPC@OECDMEI | Korea: Real Gross Domestic Product (SA, Bil.Chn.Won)                          | OECD Main Economic Indicators |
| gdp_spain                | C184GDPC@OECDMEI | Spain: Real Gross Domestic Product (SA/WDA, Bil.Ch.Euros)                     | OECD Main Economic Indicators |
| gdp_sweden               | C144GDPC@OECDMEI | Sweden: Real Gross Domestic Product (SA, Bil.Ch.SEK)                          | OECD Main Economic Indicators |
| gdp_switzerland          | C146GDPC@OECDMEI | Switzerland: Gross Domestic Product (SA, Bil.Ch.Francs)                       | OECD Main Economic Indicators |
| gdp_turkey               | C186GDPC@OECDMEI | Turkey: Real Gross Domestic Product (SA, Bil.Ch.N.Liras)                      | OECD Main Economic Indicators |
| gdp_uk                   | C112GDPC@OECDMEI | U.K.: Real Gross Domestic Product (SA, Bil.Ch.Pounds)                         | OECD Main Economic Indicators |
| gdp_us                   | C111GDPC@OECDMEI | U.S.: Real Gross Domestic Product (SAAR, Bil.Ch.US$)                          | OECD Main Economic Indicators |
| hpi_sweden               | S144HP@OECDMEI   | Sweden: Nominal House Price Index (SA, 2015=100)                              | OECD Main Economic Indicators |
| payemp_finland           | C172LFAA@OECDMEI | Finland: Total Employees (SA, Thous Persons)                                  | OECD Main Economic Indicators |
| payemp_germany           | C134LFAA@OECDMEI | Germany: Total Employees (SA, Thous Persons)                                  | OECD Main Economic Indicators |
| payemp_norway            | C142LFAA@OECDMEI | Norway: Total Employees (SA, Thous Persons)                                   | OECD Main Economic Indicators |
| payemp_sweden            | C144LFAA@OECDMEI | Sweden: Total Employees (SA, Thous Persons)                                   | OECD Main Economic Indicators |
| payemp_uk                | C112LFAA@OECDMEI | United Kingdom: Total Employees (SA, Thous Persons)                           | OECD Main Economic Indicators |
| payemp_us                | C111LFAA@OECDMEI | U.S.: Total Employees (SA, Thous Persons)                                     | OECD Main Economic Indicators |
| policyrate_australia     | C193FRUO@OECDMEI | Australia: Overnight Interbank Rate (% per annum)                             | OECD Main Economic Indicators |
| policyrate_austria       | C122FRUO@OECDMEI | Austria: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)              | OECD Main Economic Indicators |
| policyrate_belgium       | C124FRUO@OECDMEI | Belgium: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)              | OECD Main Economic Indicators |
| policyrate_brazil        | C223FRUO@OECDMEI | Brazil: Discount Rate [Proxy] (% p.a.)                                        | OECD Main Economic Indicators |
| policyrate_canada        | C156FRUO@OECDMEI | Canada: Overnight Money Market Financing Rate (% per annum)                   | OECD Main Economic Indicators |
| policyrate_chile         | C228FRUO@OECDMEI | Chile: Overnight Index Average (% per annum)                                  | OECD Main Economic Indicators |
| policyrate_china         | C924FRUO@OECDMEI | China: Bank Rate [Proxy] (% p.a.)                                             | OECD Main Economic Indicators |
| policyrate_colombia      | C233FRUO@OECDMEI | Colombia: Immediate Rates [<24 Hours] (% per annum)                           | OECD Main Economic Indicators |
| policyrate_costa_rica    | C238FRUO@OECDMEI | Costa Rica: Overnight Money Rate (%)                                          | OECD Main Economic Indicators |
| policyrate_czech_republi | C935FRUO@OECDMEI | Czech Republic: 1-Day PRIBOR (% p.a.)                                         | OECD Main Economic Indicators |
| policyrate_denmark       | C128FRUO@OECDMEI | Denmark: Overnight Interbank Rate (% per annum)                               | OECD Main Economic Indicators |
| policyrate_estonia       | C939FRUO@OECDMEI | Estonia: EONIA Euro Overnight Index Average [Proxy] (% p.a.)                  | OECD Main Economic Indicators |
| policyrate_euro          | C023FRUO@OECDMEI | Euro Area: Euro Overnight Index Average EONIA (%)                             | OECD Main Economic Indicators |
| policyrate_finland       | C172FRUO@OECDMEI | Finland: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)              | OECD Main Economic Indicators |
| policyrate_france        | C132FRUO@OECDMEI | France: Overnight Interbank Rate (% per annum)                                | OECD Main Economic Indicators |
| policyrate_germany       | C134FRUO@OECDMEI | Germany: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)              | OECD Main Economic Indicators |
| policyrate_greece        | C174FRUO@OECDMEI | Greece: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)               | OECD Main Economic Indicators |
| policyrate_hungary       | C944FRUO@OECDMEI | Hungary: Overnight Interbank Rate (% per annum)                               | OECD Main Economic Indicators |
| policyrate_iceland       | C176FRUO@OECDMEI | Iceland: Overnight REIBOR Rate (% per annum)                                  | OECD Main Economic Indicators |
| policyrate_india         | C534FRUO@OECDMEI | India: Central Bank Discount Rate [Proxy] (% p.a.)                            | OECD Main Economic Indicators |
| policyrate_indonesia     | C536FRUO@OECDMEI | Indonesia: Discount Rate [Proxy] (% p.a.)                                     | OECD Main Economic Indicators |
| policyrate_ireland       | C178FRUO@OECDMEI | Ireland: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)              | OECD Main Economic Indicators |
| policyrate_israel        | C436FRUO@OECDMEI | Israel: Overnight Index Average (% per annum)                                 | OECD Main Economic Indicators |
| policyrate_italy         | C136FRUO@OECDMEI | Italy: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)                | OECD Main Economic Indicators |
| policyrate_japan         | C158FRUO@OECDMEI | Japan: Uncollateralized Overnight Call Rate (EOP, % p.a.)                     | OECD Main Economic Indicators |
| policyrate_latvia        | C941FRUO@OECDMEI | Latvia: Interest Rate: Overnight RIGBOR Rate & Proxy EONIA EMU since 2014 (%) | OECD Main Economic Indicators |
| policyrate_lithuania     | C946FRUO@OECDMEI | Lithuania: Interest Rates: Immediate Rates: Call Money/Interbank Rate (%)     | OECD Main Economic Indicators |
| policyrate_luxembourg    | C137FRUO@OECDMEI | Luxembourg: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)           | OECD Main Economic Indicators |
| policyrate_mexico        | C273FRUO@OECDMEI | Mexico: CPP Rate [Proxy] (% p.a.)                                             | OECD Main Economic Indicators |
| policyrate_netherlands   | C138FRUO@OECDMEI | Netherlands: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)          | OECD Main Economic Indicators |
| policyrate_new_zealand   | C196FRUO@OECDMEI | New Zealand: Overnight Money Rate (% per annum)                               | OECD Main Economic Indicators |
| policyrate_norway        | C142FRUO@OECDMEI | Norway: Overnight NIBOR Rate (% per annum)                                    | OECD Main Economic Indicators |
| policyrate_poland        | C964FRUO@OECDMEI | Poland: Central Bank Rediscount Rate [Proxy] (% p.a.)                         | OECD Main Economic Indicators |
| policyrate_portugal      | C182FRUO@OECDMEI | Portugal: EMU EONIA Euro Overnight Index Average [Proxy] (% p.a.)             | OECD Main Economic Indicators |
| policyrate_russia        | C922FRUO@OECDMEI | Russia: Refinancing Rate [Proxy] (% p.a.)                                     | OECD Main Economic Indicators |
| policyrate_slovakia      | C936FRUO@OECDMEI | Slovakia: Overnight Interbank Rate (% per annum)                              | OECD Main Economic Indicators |
| policyrate_slovenia      | C961FRUO@OECDMEI | Slovenia: SIONIA/EONIA Overnight Index Average (% per annum)                  | OECD Main Economic Indicators |
| policyrate_south_africa  | C199FRUO@OECDMEI | South Africa: Discount Rate [Proxy] (% p.a.)                                  | OECD Main Economic Indicators |
| policyrate_south_korea   | C542FRUO@OECDMEI | Korea: Overnight Interbank Rate (% per annum)                                 | OECD Main Economic Indicators |
| policyrate_spain         | C184FRUO@OECDMEI | Spain: Overnight Interbank Rate (% per annum)                                 | OECD Main Economic Indicators |
| policyrate_sweden        | C144FRUO@OECDMEI | Sweden: Overnight Money Rate (% per annum)                                    | OECD Main Economic Indicators |
| policyrate_switzerland   | C146FRUO@OECDMEI | Switzerland: Overnight Interbank Rate (% per annum)                           | OECD Main Economic Indicators |
| policyrate_turkey        | C186FRUO@OECDMEI | Turkey: Overnight Interbank Rate (EOP, % per annum)                           | OECD Main Economic Indicators |
| policyrate_uk            | C112FRUO@OECDMEI | U.K.: Overnight Interbank Rate (% per annum)                                  | OECD Main Economic Indicators |
| policyrate_us            | C111FRUO@OECDMEI | U.S.: Federal Funds Rate (% p.a.)                                             | OECD Main Economic Indicators |
| ppi_sweden               | C144PYN@OECDMEI  | Sweden: PPI: Industrial Activities (NSA, 2015=100)                            | OECD Main Economic Indicators |
| unemp_euro               | C023LRCL@OECDMEI | Euro Area: Harmonized Unemployment Rate: All Persons All Ages (SA, %)         | OECD Main Economic Indicators |
| unemp_finland            | C172LRCL@OECDMEI | Finland: Harmonized Unemployment Rate: All Persons All Ages (SA, %)           | OECD Main Economic Indicators |
| unemp_france             | C132LRCL@OECDMEI | France: Harmonized Unemployment Rate: All Persons All Ages (SA, %)            | OECD Main Economic Indicators |
| unemp_germany            | C134LRCL@OECDMEI | Germany: Harmonized Unemployment Rate: All Persons All Ages (SA, %)           | OECD Main Economic Indicators |
| unemp_norway             | C142LRCL@OECDMEI | Norway: Harmonized Unemployment Rate: All Persons All Ages (SA, %)            | OECD Main Economic Indicators |
| unemp_sweden             | C144LRCL@OECDMEI | Sweden: Harmonized Unemployment Rate: All Persons All Ages (SA, %)            | OECD Main Economic Indicators |
| unemp_uk                 | C112LRCL@OECDMEI | U.K.: Harmonized Unemployment Rate: All Persons All Ages (SA, %)              | OECD Main Economic Indicators |
| unemp_us                 | C111LRCL@OECDMEI | U.S.: Harmonized Unemployment Rate: All Persons All Ages (SA, %)              | OECD Main Economic Indicators |
| vacancies_finland        | C172LFFH@OECDMEI | Finland: Unfilled Job Vacancies (SA, Number)                                  | OECD Main Economic Indicators |
| vacancies_germany        | C134LFFH@OECDMEI | Germany: Unfilled Job Vacancies (SA, Number)                                  | OECD Main Economic Indicators |
| vacancies_sweden         | C144LFFH@OECDMEI | Sweden: Unfilled Job Vacancies (SA, Number)                                   | OECD Main Economic Indicators |
| vacancies_uk             | C112LFFH@OECDMEI | U.K.: Unfilled Job Vacancies (SA, Number)                                     | OECD Main Economic Indicators |
| vacancies_us             | C111LFFH@OECDMEI | U.S.: Unfilled Job Vacancies (SA, Number)                                     | OECD Main Economic Indicators |

 - Misc. Haver variables: This dataset was downloaded from Haver Analytics containing additional indicators not present in either of the previous two datasets (series listed below). Reproducing this data file requires access to the NORDIC and GERMANY Haver databases, or downloading these series directly from their respective sources. 

| .dta variable name | Haver mnemonic   | Description                                                                     | Original Data Source      |
| ------------------ | ---------------- | ------------------------------------------------------------------------------- | ------------------------- |
| layoffs_finland    | FINVCNU@NORDIC   | Finland: Consumer Survey: Personal Threat of Unemployment Now (NSA, %Bal)       | Statistics Finland        |
| layoffs_germany    | DENTESTE@GERMANY | Germany: Workers Listed in Comp Notices of S-T Work: Econ Reasons (NSA,Persons) | Federal Employment Agency |

 - Riksbank Monetary Policy Reports: This data source contains the Monetary Policy Reports and auxiliary data files released by the Riksbank for each meeting over 1993--2019. The `riksbank_mprs` folder is organized by year and then month, with all of the files for a meeting contained in the folder for that meeting. For 1993--2016, the MPRs and data files were downloaded from this link (https://archive.riksbank.se/en/Web-archive/Published/Published-from-the-Riksbank/Monetary-policy/Monetary-Policy-Report/), and for 2017--2019 they were downloaded from this link (https://www.riksbank.se/en-gb/monetary-policy/monetary-policy-report/). 
 - Riksbank meeting dates: This spreadsheet was manually created by the authors, recording the months in which the Riksbank met and released a Monetary Policy Report. 
 - Prospera repo rate expectations: This data source contains the historical expectations collected by Prospera (originally downloaded from https://www.kantarsifo.se/erbjudande/prospera/inflation-expectations but now can be found at https://www.origogroup.com/riksbanken/). The `repo_expectations` folder contains the individual reports in either `.pdf` or `.xls` format, which the authors then collected into `Master.xlsx`. 
 - Consensus Economics, Inc. forecasts: We use monthly forecasts for GDP and inflation in Sweden from the Consensus Economics, Inc. G7 & Western Europe forecast reports. These forecast reports are proprietary and researchers can purchase access from http://www.consensuseconomics.com. To replicate our results, you will need to copy the annual growth rate forecasts for GDP and inflation for Sweden from each forecast report into the corresponding rows in consensus_forecasts_sweden.xlsx. We provide in this replication package a synthetic copy of consensus_forecasts_sweden.xlsx, with the same file layout as used in our analysis, but with randomly-generated data. 
 - Riksbank policy rate: This can be downloaded from the Riksbank through this link (https://www.riksbank.se/en-gb/statistics/interest-rates-and-exchange-rates/search-interest-rates-and-exchange-rates/?s=g2-SECBREPOEFF&a=D&from=1994-01-03&to=2025-04-23&fs=3#result-section). Note that the file in the replication package refers to the "repo rate" while the Riksbank website now refers to the "policy rate", these are the same series but the Riksbank changed terminology after the data were accessed. 
 - Euro-area 3-month Interbank rate: This data source is series IR3TIB01EZM156N on FRED (https://fred.stlouisfed.org/series/IR3TIB01EZM156N). 
 - Riksbank KIX-rate weights: This spreadsheet was downloaded from the Riksbank on this page (https://www.riksbank.se/en-gb/statistics/interest-rates-and-exchange-rates/explanations--interest-rates-and-exchange-rates/effective-exchange-rate-indices/), the direct link to the spreadsheet is https://www.riksbank.se/globalassets/media/statistik/vikter/kix-vikter_eng2.xlsx. 
 - Statistics Sweden debt-to-income series: This spreadsheet (reference number 000000ZF) was downloaded directly from Statistics Sweden through this link (https://www.statistikdatabasen.scb.se/sq/17386). 
 - World Trade Flows data: This dataset was downloaded from http://www.robertcfeenstra.com/wtf-data.html. 
 - Statistics Norway unemployed for 1--4 weeks: This series was downloaded from https://www.ssb.no/en/statbank/table/04552, with the following parameters: sex = both sexes, duration of job search = 1--4 weeks. 
 - US unemployed less than 5 weeks, FRED series UEMPLT5: This data source is series UEMPLT5 on FRED (https://fred.stlouisfed.org/series/UEMPLT5). 
 - LFS redundancies rate for UK: This data source was downloaded from here https://www.ons.gov.uk/employmentandlabourmarket/peoplenotinwork/redundancies/datasets/redundancieslevelsandratesnotseasonallyadjustedred01nsa, data column used: "People", subcolumn: "Level". 
 - Layoff measures for Denmark, Spain, France, Italy, and Portugal: Downloaded from Eurostat (https://ec.europa.eu/eurostat/databrowser/view/lfsq_ugad__custom_16351083/default/table?lang=en), Online data code: `lfsq_ugad`. Parameters: sex = total; age class = 15–74 years; duration = less than 1 month; unit of measure = thousand persons.
 - OECD Job vacancies for Norway, Portugal, Spain, & Sweden: Downloaded from https://data-explorer.oecd.org/vis?lc=en&df[ds]=dsDisseminateFinalDMZ&df[id]=DSD_OLAB%40DF_OIALAB_INDIC&df[ag]=OECD.SDD.TPS&dq=NOR.VAC_U.._Z.N..Q&pd=1955-Q1%2C2019-Q4&to[TIME_PERIOD]=false, with parameters: measure = unfilled vacancies, transformation = not applicable, adjustment = Neither seasonally adjusted nor calendar adjusted, institutional sector = total economy.
 - New job vacancies for France, FRED series LMJVTTNVFRQ647S: Downloaded from FRED (https://fred.stlouisfed.org/series/LMJVTTNVFRQ647S). 
 - Eurostat employment for France: Downloaded from https://ec.europa.eu/eurostat/databrowser/view/NAMQ_10_PE__custom_4108670/default/table. Online data code: namq_10_pe. Unadjusted quarterly data in thousands of persons, based on the national concept.
 - Barnichon & Garda (2016) estimated transition rates: This data source is taken from the replication files for Barnichon & Garda (2016), downloaded from https://data.mendeley.com/datasets/c3y8xskp76/1. 
 - Historical help-wanted index for US from Barnichon (2010): This data source is taken from the replication files for Barnichon & Garda (2016), downloaded from https://data.mendeley.com/datasets/c3y8xskp76/1. 

# Computational Requirements

The code to produce the aggregate results was run in Stata 19, but earlier versions of Stata will likely work as well. No additional packages are necessary to download, all of the packages used are bundled in this replication package. The code takes about 15 minutes to run all of the way through on a standard laptop. 

The microdata analysis was run on a MONA server with 80GB of memory and takes about 72 hours to run in total, see "README_microdata.pdf" for the full details. 

# Description of Codes & Instructions to Replicators

To reproduce the aggregate analysis for this paper, follow these steps:
1. Download the replication package and ensure that all files in `code`, `bin`, and `data/external` are present. 
2. (Only if reproducing Figures A3 & A5 or Table A1) Assemble Consensus Economics, Inc. forecasts - Researchers with access to the G7 & Western Europe forecast reports released by Consensus Economics, Inc. (http://www.consensuseconomics.com) will need to copy the annual growth rate forecasts for GDP and inflation in Sweden into `consensus_forecasts_sweden.xlsx`, following the file structure. 
3. Replace the global working directory `base_path` in line 8 of `profile.do` with the path to where you have downloaded the replication package. 
4. Open Stata in `AggregateAnalysis/code` and run `main.do`. This runs all of the analysis using aggregate data, and creates the monetary shock series used in the microdata analysis. `main.do` calls the following code files:
   - `profile.do` - This file sets up the environment and creates globals used in each code file. It also loads into the environment two user-created commands (`lagged_correlation.ado` and `x13.ado`), as well as external packages used in the analysis (`gtools`, `reghdfe`, `coefplot`, `estout`, `grc1leg`, `parmest`, and `texsave`). To avoid collisions with newer versions of these packages that users may have installed, `profile.do` sets the `PLUS` and `PERSONAL` directories to paths within this replication package. 
   - `build_*.do` These files clean the raw data files and assemble the datasets used in the analysis. 
   - `reg_baseline_rr.do` and `reg_baseline_event.do` - These files run the baseline analysis using Romer & Romer shocks and the event study specification respectively. The resulting estimates are stored in Stata estimate file format (`.ster` files) within `$path/est`, which are then imported in `descriptives_irfs.do` to create the figures and tables for the paper. 
   - `reg_alternate_specs.do`, `reg_forecasterror.do`, `placebo_consensus.do`, `placebo_crosscountry.do`, `placebo_eventstudy.do`, `taylor_rule.do` - These files run various robustness checks, and some of the files store their estimates in `.ster` files in `$path/est`. 
   - `descriptives_*.do` - These files create the figures and tables for the paper. To create the full set of figures and tables, you will need to run all previous files. 

To reproduce the microdata analysis for this project, you will need to be admitted access to Statistics Sweden's secure MONA server, and then you can follow the steps in "README_microdata.pdf" to run all of the microdata analysis. Microdata and code is preserved in the restricted-access location until 2031.

## License for code

The code is licensed under a MIT license. See LICENSE.txt for details.

# List of Figures/Tables and Programs

| Figure/Table | Program                                                                    | Output File                                                  | Microdata Server |
| ------------ | -------------------------------------------------------------------------- | ------------------------------------------------------------ | ---------------- |
| Figure 1     | AggregateAnalysis/code/descriptives_shocks.do                              | Romer-Shock-Baseline.pdf                                     |                  |
| Figure 2     | AggregateAnalysis/code/descriptives_irfs.do                                | event_study_baseline.pdf                                     |                  |
| Figure 3     | AggregateAnalysis/code/descriptives_irfs.do                                | counterfactuals_event.pdf                                    |                  |
| Figure 4a    | AggregateAnalysis/code/descriptives_irfs.do                                | split_shocks_left.pdf                                        |                  |
| Figure 4b    | AggregateAnalysis/code/descriptives_irfs.do                                | split_shocks_right.pdf                                       |                  |
| Figure 5a    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_lgdp.pdf                                      |                  |
| Figure 5b    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_lexports.pdf                                  |                  |
| Figure 5c    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_lfixedinv.pdf                                 |                  |
| Figure 5d    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_cpif_pctchg.pdf                               |                  |
| Figure 5e    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_ppi_pctchg.pdf                                |                  |
| Figure 5f    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_exchrateinv.pdf                               |                  |
| Figure 5g    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_lhpi.pdf                                      |                  |
| Figure 5h    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_existhomeloanrate.pdf                         |                  |
| Figure 5i    | AggregateAnalysis/code/descriptives_irfs.do                                | macro_outcomes_debt_to_income.pdf                            |                  |
| Figure 6     | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | Figure6_firm_ex_debt.pdf                                     | Yes              |
| Figure 7     | AggregateAnalysis/code/descriptives_crosscountry.do                        | crosscountry_unemp_Event_COMBINED.pdf                        |                  |
| Figure 8     | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | Figure8_MI_sni3_combined_unempl_fractionibnq2_diffonly.pdf   | Yes              |
| Figure 9     | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | Figure9_debt_by_institutions_firm.pdf                        | Yes              |
| Figure 10    | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | Figure10_unempl_distribution_cycle_figure_lag_2_sample.pdf   | Yes              |
| Figure A1    | AggregateAnalysis/code/descriptives_shocks.do                              | Sweden_actual_vs_predicted_3months.pdf                       |                  |
| Figure A2    | AggregateAnalysis/code/descriptives_shocks.do                              | Romer-Shock-Addl-Controls.pdf                                |                  |
| Figure A3a   | AggregateAnalysis/code/descriptives_shocks.do                              | Romer-Shock-Consensus.pdf                                    |                  |
| Figure A3b   | AggregateAnalysis/code/descriptives_shocks.do                              | Romer-Shock-Consensus-Annual.pdf                             |                  |
| Figure A4    | AggregateAnalysis/code/taylor_rule.do                                      | projections.pdf                                              |                  |
| Figure A5    | AggregateAnalysis/code/placebo_consensus.do                                | placebo_consensus.pdf                                        |                  |
| Figure A6    | AggregateAnalysis/code/placebo_eventstudy.do                               | localproj_ugap_placebo.pdf                                   |                  |
| Figure A7    | AggregateAnalysis/code/reg_forecasterror.do                                | forecasterror_unemp_gdpvaclayoff_all.pdf                     |                  |
| Figure A8    | AggregateAnalysis/code/descriptives_irfs.do                                | policyrate.pdf                                               |                  |
| Figure A9a   | AggregateAnalysis/code/descriptives_crosscountry.do                        | crosscountry_lgdp_Event_COMBINED.pdf                         |                  |
| Figure A9b   | AggregateAnalysis/code/descriptives_crosscountry.do                        | crosscountry_unemp_rr_COMBINED.pdf                           |                  |
| Figure A10a  | AggregateAnalysis/code/descriptives_crosscountry.do                        | crosscountry_unemp_Event_us.pdf                              |                  |
| Figure A10b  | AggregateAnalysis/code/descriptives_crosscountry.do                        | crosscountry_lgdp_Event_us.pdf                               |                  |
| Figure A11a  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA11_unempl_fraction.pdf                                | Yes              |
| Figure A11b  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA11_empl_fraction.pdf                                  | Yes              |
| Figure A11c  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA11_empl_int.pdf                                       | Yes              |
| Figure A12a  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA12_firm_yoy_employees_full_sym.pdf                    | Yes              |
| Figure A12b  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA12_firm_firm_exit_full_sym.pdf                        | Yes              |
| Figure A13   | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA13_distribution_figure_full.pdf                       | Yes              |
| Figure A14a  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA14_realearnings_distribution.pdf                      | Yes              |
| Figure A14b  | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA14_ear_if_mon_distribution.pdf                        | Yes              |
| Figure A15   | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA15_MI_sni3_controlled_unempl_fractionibn_sni2time.pdf | Yes              |
| Figure A16   | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA16_mechanisms_UE_duration_samesni.pdf                 | Yes              |
| Figure A17   | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | FigureA17_unempl_distribution_figure_lag_2.pdf               | Yes              |
| Table A1     | AggregateAnalysis/code/descriptives_irfs.do                                | robustness_table_panel_shocks.tex                            |                  |
| Table A2     | AggregateAnalysis/code/descriptives_irfs.do                                | robustness_table_panel_controls.tex                          |                  |
| Table A3     | AggregateAnalysis/code/reg_baseline_event.do                               | event_interest_rates.tex                                     |                  |
| Table A4     | MicroAnalysis/do/revision2023/create_tableA4                               | TableA4.tex                                                  | Yes              |
| Table A5     | AggregateAnalysis/code/descriptives_shocks.do                              | Romer-Regression-Table.tex                                   |                  |
| Table A6     | AggregateAnalysis/code/descriptives_shocks.do                              | Table-Shock-Outlook.tex                                      |                  |
| Table A7     | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | TableA7.tex                                                  | Yes              |
| Table A8     | MicroAnalysis/do/revision2023/Figures-for-Draft-Replication_noromeronly.do | TableA8.tex                                                  | Yes              |
| Table A9     | MicroAnalysis/do/revision2023/create_tableA9                               | TableA9.tex                                                  | Yes              |
| Table A10    | MicroAnalysis/do/revision2023/create_tableA10                              | TableA10.tex                                                 | Yes              |
