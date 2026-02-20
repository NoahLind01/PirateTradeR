**Pirate Trade Network**

Pirate Trade Network is an interactive R Shiny dashboard built to simulate a dynamic, living economy for tabletop RPGs and pirate-themed D&D campaigns. It tracks the supply, demand, and fluctuating prices of various maritime commodities across a 3x3 grid of interconnected regions and 36 distinct merchants. Designed as a tool for Dungeon Masters, the app automatically calculates localized price shifts based on player trades, propagates economic "ripples" to adjacent islands over time, and features built-in God-tools to trigger random market crashes, lucrative shortages, and natural seasonal price cycles.


**Features**

    Living Economy: Prices aren't static. They naturally drift along randomized sine-wave cycles (simulating seasonality) and feature daily organic jitter (simulating NPC trades and weather).

    Spatial Arbitrage Tracker: A real-time visual chart (powered by Plotly) showing the price of a selected commodity across the entire world, sorted by physical distance. Perfect for feeding players "rumors" about where to sell their loot for maximum profit.

    Ripple Effects: Time progression buttons ("Advance Day" and "Advance Week") propagate supply and demand shifts from single vendors to their local islands, and eventually across the seas to adjacent map squares.

    Volume Sensitivity: The central map (2,2) is a highly volatile hub where even small trades move the needle. Corner maps represent deep, established markets requiring bulk crate trades to shift prices.

    DM "God-Tools": Instantly trigger global or localized "Shortages" or "Surpluses" with the click of a button to throw the players a curveball.

    State Persistence: Save and load the entire state of your world's economy to a local CSV file between sessions.

    Dark Mode: Integrated toggle to save your eyes during late-night DMing sessions.


**Prerequisites & Installation**

  To run this application, you will need R and optionally RStudio installed on your machine.

    Clone or download this repository.

    Open the R console (or RStudio) and install the required packages by running:

    install.packages(c("shiny", "shinydashboard", "dplyr", "tidyr", "DT", "readr", "plotly"))


  Open app.R in RStudio and click "Run App", or run the following command in your R console:

    shiny::runApp("path/to/directory/containing/app.R")


**How it Works (For the DM)**

  The map is arranged in a 3x3 grid (Maps 1 through 9). Each map contains 4 unique merchants.
  Currently tracked commodities include: Rum, Oil, Pearls, Fish, Crabs, and Salt.

  Transaction Rules

    Previewing Trades: Use P. Buy and P. Sell to quickly calculate the exact gold cost/yield and see the predicted price shift before finalizing a trade.

    Buying: Players buy from the vendor. The vendor's supply drops. Prices go UP.

    Selling: Players sell to the vendor. The vendor's supply rises. Prices go DOWN.

  **Time Progression**

    Advance Day: Ripples a percentage of a single vendor's price movements to the other 3 shops on the same island. Prices also drift slightly toward their current seasonal cycle base.

    Advance Week: Merchant ships propagate price changes across the grid. Islands average out their changes and ripple them to adjacent map squares (North, South, East, West).

    The Market Arbitrage Tracker

  When a commodity is selected, the bar chart visualizes every merchant in the world sorted by distance from the currently selected merchant.

    Green Bars: Lower price than the current merchant.

    Blue Bars: Selected or identical price.

    Red Bars: Higher price than the current merchant.

    Tip: If the players are looking to offload cargo, check the chart for massive Red spikes far away and have a tavern NPC drop a hint!
