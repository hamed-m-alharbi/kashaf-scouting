<p align="center">
  <img src="assets/logo.png" alt="Kashaf logo" width="360">
</p>

<h3 align="center">Who is the best player I can afford?</h3>

<p align="center">
  A data-driven football scouting tool for small and mid-size clubs.<br>
  <a href="https://kashaf-dashboard-350342337334.europe-west1.run.app"><b>Try the live app →</b></a>
</p>

---

## The idea

Big clubs have scouting departments. Smaller clubs have a budget and a lot of guesswork.

Kashaf compares each player's **performance** with his **market value** and ranks players by position and budget across the **top 5 European leagues**. The goal is simple: find the players who give the most on the pitch for the least money.

## What you can do

| Search Players | Similar Players |
|---|---|
| ![Search Players](assets/search-players.jpg) | ![Similar Players](assets/similar-players.jpg) |
| Players ranked by the **Undervalue Index**: how well they perform compared with what they cost, within their position. Filter by league, age, budget, minutes and contract. | Pick a player and find the closest profiles in the same position, with a similarity score, a radar and a side-by-side comparison. |

**Player Profile:** a radar of key metrics, stats coloured by percentile, market value, health and discipline, injury history, and season-by-season history.

![Player Profile](assets/player-profile.jpg)

## How it works

![Architecture](assets/architecture.png)

Kashaf runs as a full **ELT pipeline on Google Cloud**:

1. **Extract:** Python pulls player stats and injuries from API-Football and market values from Transfermarkt.
2. **Load:** raw files land in Cloud Storage, then in BigQuery raw tables.
3. **Transform:** dbt cleans the data, matches players across both sources, and builds the scores.
4. **Serve:** a Streamlit app, packaged with Docker and deployed on Cloud Run.

Airflow runs the whole pipeline every week, and Terraform builds the cloud resources as code.

## In numbers

| | |
|---|---|
| **1,605 / 1,605** | players matched across two sources with no shared ID |
| **85** | dbt models and tests |
| **3** | seasons of data, top 5 European leagues |
| **Weekly** | automatic refresh with Airflow |

## Tech stack

`Python` · `SQL` · `Apache Airflow` · `dbt` · `Google BigQuery` · `Google Cloud Storage` · `Terraform` · `Docker` · `Streamlit` · `Cloud Run`

## Roadmap

<p align="center">
  <img src="assets/roadmap.jpg" alt="Kashaf roadmap" width="520">
</p>

- ✅ **Phase 1:** built and shipped as our capstone at the SDA Data Engineering Bootcamp.
- ⏳ **Phase 2:** a full web app and our own Google Cloud project.
- ⏳ **Phase 3:** a new dataset focused on Saudi football: Roshn Saudi League, Yelo League and youth leagues.

## Team

Kashaf is an idea by **Hamed Alharbi**, built with his team during the Saudi Digital Academy Data Engineering Bootcamp (Le Wagon curriculum), October 2026.

| Member | Role | Links |
|---|---|---|
| **Hamed Alharbi** | Project Lead | [LinkedIn](https://www.linkedin.com/in/hamed-al-harbi-741604374/) · [GitHub](https://github.com/hmonaweribrahim-crypto) |
| **Fahad Alghamdi** | Team Member | [LinkedIn](https://www.linkedin.com/in/fahadghamdi/) · [GitHub](https://github.com/fahadrmd) |
| **Adel Albqmai** | Team Member | [LinkedIn](https://www.linkedin.com/in/adel-nawar-532537197/) · [GitHub](https://github.com/adelnoor1997-arch) |
| **Yara Alshammari** | Team Member | [LinkedIn](https://www.linkedin.com/in/yara-alshammari-aa9411254/) · [GitHub](https://github.com/Yara-l73) |

---

<p align="center">
  The source code is private. For a code walkthrough, feel free to reach out on
  <a href="https://www.linkedin.com/in/hamed-al-harbi-741604374/">LinkedIn</a>.
</p>
