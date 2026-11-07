# Alternative Fuel Vehicle Adoption Dashboard

A Power BI dashboard analyzing the state of electric and alternative fuel vehicles in the U.S. It shows where EV adoption is highest and lowest, how large states compare, and which alternative fuels have a meaningful share, to help a transportation board think about where charging infrastructure planning should focus.

## Questions Answered

1. What share of vehicles in each state are EVs, PHEVs, and HEVs?
2. Which states have the highest EV adoption rates, and which lag behind?
3. How does EV adoption in California compare with other large states (Texas, Florida, New York, and Pennsylvania)?
4. Which alternative fuels (biodiesel, ethanol, and hydrogen) have a significant share of U.S. vehicles, and which are niche?
5. What share of U.S. vehicles are electrified (EV, PHEV, and HEV), and how does that compare with gasoline?
6. What do the gaps between states suggest for charging infrastructure planning?

## Tools Used

- Power BI (data model, calculations, and dashboard)

## Dataset

State-level vehicle registration counts by fuel type for 50 states and the District of Columbia (51 rows, about 287 million vehicles in total).

Fuel types: Electric (EV), Plug-In Hybrid (PHEV), Hybrid (HEV), Biodiesel, Ethanol/Flex (E85), Compressed Natural Gas, Propane, Hydrogen, Methanol, Gasoline, Diesel, and Unknown.


## Approach

1. **Checked data quality:** looked for missing values, zeros, and inconsistent state names.
2. **Calculated shares:** for each state, divided each fuel type's registrations by that state's total vehicles to get percentages.
3. **Calculated national shares from totals:** divided national registrations by total U.S. vehicles, instead of averaging or adding state percentages, which would give small states the same weight as large ones.
4. **Built the dashboard** with a KPI tile and charts for each question.

## Key Findings

**National picture (share of all U.S. vehicles)**

| Fuel type | Share |
|-----------|------:|
| Gasoline | 84.60% |
| HEV | 2.57% |
| EV | 1.24% |
| PHEV | 0.46% |
| **EV + PHEV + HEV combined** | **4.27%** |

**State leaders and laggards (EV share of registered vehicles)**

| Highest | EV % | Lowest | EV % |
|---------|-----:|--------|-----:|
| California | 3.41 | North Dakota | 0.13 |
| District of Columbia | 2.60 | Mississippi | 0.13 |
| Hawaii | 2.37 | Wyoming | 0.17 |
| Washington | 2.23 | South Dakota | 0.19 |
| Nevada | 1.85 | West Virginia | 0.19 |

**Large states**

| State | EV % |
|-------|-----:|
| California | 3.41 |
| Florida | 1.37 |
| New York | 1.16 |
| Texas | 0.89 |
| Pennsylvania | 0.69 |

**Alternative fuels:** ethanol/flex-fuel is the only alternative fuel with a significant share (**7.05%** of vehicles). Biodiesel is smaller (**0.98%**), and hydrogen is niche (**0.01%**).

**What this suggests for infrastructure planning**

- EV adoption is concentrated in a few coastal and western states, led by California, while many states sit below 1%.
- Two of the five largest states, Texas and Pennsylvania, are under 1% EV share, far behind California. Their large vehicle populations mean even modest growth would add many EVs.
- The lowest-adoption states are mostly rural and have small vehicle populations, so they carry less total demand.
- This is a snapshot of registrations, not a forecast, and it does not include charging station data, so it can show where adoption is and isn't, but not where chargers are missing.

## Dashboard Contents

- **KPI tile:** combined EV, PHEV, and HEV share of U.S. vehicles
- **% of EV Types by State:** stacked bars by state
- **Top 10 Highest and Lowest EV % by State**
- **EV % in Larger States:** California compared with Florida, New York, Texas, and Pennsylvania
- **Alternative Fuels:** national share of biodiesel, ethanol, and hydrogen
- **Gasoline vs Electrified Vehicles:** the split between those two groups only

## Data Notes

- **No missing values.** Several fuel types are zero in many states: methanol is zero everywhere, hydrogen is zero in all but one state, and propane and natural gas are zero in many states. These are real zeros, not errors, and they are why those fuels are treated as niche.
- **The District of Columbia is counted as a state,** so there are 51 rows.
- **The headline 4.27% includes hybrids.** Electric vehicles alone are 1.24%, so the dashboard labels the combined figure as EV + PHEV + HEV.
- **Percentages are not additive across states.** National figures use total counts, not sums or averages of state percentages.

## Limitations

- The data is a single snapshot, so it cannot show adoption trends over time.
- It measures registered vehicles, not charging stations or driving demand, so it cannot identify infrastructure gaps on its own.
- A recommendation on where to invest would need charging station data and population or traffic data.

## Possible Next Steps

- Add gasoline share by state to the stacked chart
- Add charging station counts per state and compare them with EV adoption
- Add a map of EV share by state
- Compare adoption over several years to forecast growth


## What I Learned

- Calculating shares correctly at the state and national levels, and why you can't add or average percentages across groups of different sizes
- Checking dashboard numbers against the raw data before sharing them
- Choosing chart types to answer specific business questions
