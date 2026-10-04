# EnergyPulse Data Model

## 1. Modeling Approach

EnergyPulse will use dimensional modeling for the Gold analytical layer.

The primary modeling approach will be a star schema.

## 2. Dimensions

### dim_date

Contains calendar attributes.

Potential fields:

- date_key
- date
- year
- quarter
- month
- week
- day
- day_of_week

### dim_country

Contains country-level information.

Potential fields:

- country_key
- country_code
- country_name
- region

### dim_region

Contains geographic or market regions.

### dim_energy_source

Contains energy source classifications.

Examples:

- Solar
- Wind
- Hydro
- Nuclear
- Coal
- Natural Gas
- Oil

### dim_market

Contains energy and commodity market information.

### dim_weather_location

Contains weather observation locations.

## 3. Fact Tables

### fact_energy_generation

Grain:

One record per date, location, and energy source.

Potential measures:

- generation_mwh

### fact_energy_demand

Grain:

One record per date and location.

Potential measures:

- demand_mwh

### fact_energy_price

Grain:

One record per date, market, and energy product.

Potential measures:

- price
- currency

### fact_oil_price

Grain:

One record per date and oil benchmark.

Potential measures:

- price_usd

### fact_gas_price

Grain:

One record per date and gas market.

Potential measures:

- price
- currency

### fact_weather

Grain:

One record per observation time and weather location.

Potential measures:

- temperature
- precipitation
- wind_speed

## 4. Modeling Principles

- Clearly define table grain
- Use surrogate keys where appropriate
- Maintain referential integrity
- Separate facts from descriptive dimensions
- Optimize analytical queries
- Document transformations