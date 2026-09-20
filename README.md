# Loan Prediction API

A machine-learning application that exposes a trained loan prediction
model through a FastAPI service.

## Overview

This project takes structured information about a loan applicant,
processes the input using a pre-trained machine-learning pipeline,
and returns a prediction through a REST API.

The project was built to move a machine-learning model beyond a
notebook and make it accessible as a reusable application.

## Architecture

Applicant data
        ↓
Pydantic input validation
        ↓
Preprocessing pipeline
        ↓
Trained ML model
        ↓
Prediction
        ↓
FastAPI response

## Project Structure

loan_service/
├── model/
│   ├── data/
│   └── loan_pipe.pkl
├── pipeline.py
├── main.py
└── schedule.py

## Technologies

- Python
- Pandas
- scikit-learn
- FastAPI
- Pydantic
- Joblib

## Key Components

### `pipeline.py`

Contains the machine-learning preprocessing/model pipeline.

### `main.py`

Creates the FastAPI application, loads the trained model and
defines the API input/output structures and endpoints.

### `schedule.py`

Contains the project's scheduling component.

### `model/loan_pipe.pkl`

Serialized trained machine-learning pipeline used to generate
predictions.

## Running the API

```bash
pip install -r requirements.txt
uvicorn main:app --reload
