# HBnB - Part 2

Business logic and API endpoints for the HBnB application, built with
Flask and flask-restx.

## Structure

- `app/api/v1/`: presentation layer (API endpoints)
- `app/models/`: business logic layer (User, Place, Review, Amenity)
- `app/services/`: the `HBnBFacade` that connects the layers
- `app/persistence/`: in-memory repository (replaced by a database in Part 3)
- `config.py`: application configuration
- `run.py`: entry point

## Setup

```
pip install -r requirements.txt
python3 run.py
```

The API documentation is then available at `http://127.0.0.1:5000/api/v1/`.
