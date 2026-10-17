# IPL PREDICTOR

A simple IPL match outcome prediction project with a Streamlit web app and a REST API. The project includes notebooks used for data exploration, model training, and evaluation, and exposes a user-friendly prediction UI and an API for programmatic access.

Live demo
- Streamlit app: https://ipl-predictor-app-ukt9.onrender.com/
- API: https://ipl-predictor-qosd.onrender.com/

Table of contents
- About
- Features
- How it works
- Demo / Usage
  - Web app
  - API (example)
- Run locally
- Notebooks & code
- Contributing
- License
- Contact

## About
This repository demonstrates an end-to-end workflow for predicting IPL match outcomes. It contains Jupyter notebooks for data cleaning, feature engineering and model training, plus the code used to deploy a Streamlit frontend and a backend API.

## Features
- EDA and feature engineering notebooks
- Trained model for match outcome prediction
- Streamlit UI for easy, non-technical usage
- REST API for integration into other apps or services
- Lightweight deployment (Render)

## How it works (high level)
1. Dataset: historical IPL match data is used to extract match-level features (teams, venue, toss info, current score/overs, etc.).
2. Feature engineering: relevant features are engineered from raw match records and transformed for the model.
3. Model training: a classification/regression model (see notebooks) is trained to predict the match outcome (winning team / win probability).
4. Deployment: the trained model is served behind a simple API and a Streamlit UI calls that API to show predictions.

## Demo / Usage

### Web app
- Open the Streamlit UI: https://ipl-predictor-app-ukt9.onrender.com/
- Enter match details and get an immediate prediction and probability.

### API (example)
- Base URL: https://ipl-predictor-qosd.onrender.com/
- Example (generic) curl request — adjust the JSON fields to match the API contract in the repo/notebooks:

  curl -X POST "https://ipl-predictor-qosd.onrender.com/predict" \
    -H "Content-Type: application/json" \
    -d '{
      "team1": "MI",
      "team2": "CSK",
      "venue": "Wankhede",
      "toss_winner": "MI",
      "toss_decision": "bat",
      "overs": 10,
      "team1_score": 90,
      "team2_score": 85
    }'

- The API returns predicted winner and associated probability or score estimate. Replace the endpoint path and fields with the exact contract used in this project if they differ.

## Run locally
1. Clone the repo:
   git clone https://github.com/SarthakSaxena12/IPL-PREDICTOR.git
2. Create a virtual environment and install dependencies:
   python -m venv .venv
   source .venv/bin/activate  # or .venv\Scripts\activate on Windows
   pip install -r requirements.txt
3. Start the Streamlit app:
   streamlit run app.py
   (or run the specific notebook / script used to launch the app)
4. Start the API server:
   python api/app.py
   (or use the command used in the repo's deployment configuration)

## Notebooks & code
- The repository is notebook-heavy (Jupyter Notebooks). Look for notebooks that contain:
  - data exploration and visualization
  - feature engineering
  - model training and evaluation
- If available, the trained model artifact and a script to serve it will be in the repo.

## Contributing
Contributions, issues and feature requests are welcome. Please open an issue or submit a PR with a clear description of the change.

## License
This project is provided as-is. Add a LICENSE file (for example, MIT) to make licensing explicit.

## Contact
Project owner: SarthakSaxena12
Deployed Streamlit app: https://ipl-predictor-app-ukt9.onrender.com/
Deployed API: https://ipl-predictor-qosd.onrender.com/

## Notes / Next steps
- If you want, I can:
  - Add this README.md directly to the repository (committed to main), or
  - Update the README with exact API endpoints and request/response examples after you confirm the API contract and any preferred license/badges.
