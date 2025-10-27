# RIWI Sport

RIWI Sport is a project designed to analyze sports data using data analysis and visualization tools. This project uses a PostgreSQL database and Python libraries to perform queries and analysis.

## Requirements

Before starting, make sure you have the following requirements installed:

- Docker
- Python 3.8 or higher
- The dependencies listed in `requirements.txt`

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Jhosua-Lascarro/PLaceholder.git
   cd PLaceholder
   ```

2. Install the Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up the environment variables in a `.env` file for the PostgreSQL database:
   ```env
   POSTGRES_USER=your_user
   POSTGRES_PASSWORD=your_password
   POSTGRES_DB=your_database
   ```

## Using Docker

To start the PostgreSQL database with Docker, run the following command:

```bash
docker run -d \
  --name psql \
  --env-file .env \
  -p 5432:5432 \
  -v $(pwd)/data:/docker-entrypoint-initdb.d:ro \
  postgres:15
```

This command:
- Creates a container named `psql`.
- Uses the environment variables defined in `.env`.
- Exposes port 5432 to connect to the database.
- Mounts the `data` directory to initialize the database with the `RiwiSport.sql` file.

## Data Analysis

The data analysis is performed in the notebook `analisis_RIWI_Sport_Jhosua_David.ipynb`. This notebook includes:
- Connection to the PostgreSQL database.
- SQL queries to extract relevant data.
- Statistical analysis using pandas.
- Data visualization with matplotlib and seaborn.
