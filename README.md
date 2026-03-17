# AI-Driven Urban Traffic Optimization Prototype

This project is a proof-of-concept for short-term urban traffic forecasting using a graph neural network (GNN). It models a small network of intersections as a graph, simulates realistic traffic patterns, and predicts congestion 15 minutes ahead. The goal is to demonstrate the technical feasibility of using AI to support smarter traffic operations and decision-making.

## Overview

Urban traffic is naturally connected. What happens at one intersection often affects nearby intersections. Because of that, a graph-based model is a strong fit for this problem.

In this notebook, I:

- Represent a road network as a graph of intersections and road segments
- Simulate traffic volumes with daily patterns, rush-hour spikes, neighbor effects, and random incidents
- Build a supervised learning dataset using historical traffic, time-of-day signals, and incident indicators
- Train a graph neural network in PyTorch to forecast traffic one step ahead
- Compare the model against a simple baseline
- Visualize results and discuss business value and next steps

## Project Goal

The purpose of this project is to show that graph-based machine learning can learn traffic structure better than a basic rule-based approach. This prototype is meant to bridge the gap between concept slides and a working technical demonstration.

## Tools and Technologies

- Python
- PyTorch
- NumPy
- Matplotlib
- Jupyter Notebook

## Model Summary

The model uses a simple graph neural network architecture that allows each intersection to learn from both its own recent traffic behavior and the behavior of neighboring intersections.

### Inputs
Each node includes:

- Four lagged traffic volume values
- Time-of-day sine feature
- Time-of-day cosine feature
- Incident flag

### Output
- Predicted traffic volume for the next 15-minute interval at each intersection

## Evaluation

The model is evaluated against a naïve baseline that simply repeats the last observed traffic value. In testing, the GNN consistently outperforms the baseline, showing that it is learning meaningful spatial and temporal traffic patterns rather than just copying recent history.

## Visualizations

The notebook includes:

- Predicted vs. actual traffic volume for a sample intersection
- A heatmap view showing traffic behavior across multiple nodes over time

These visuals help make the model’s performance easier to interpret for both technical and non-technical audiences.

## Business Relevance

This prototype highlights how AI could support:

- Traffic signal timing adjustments
- Congestion monitoring
- Dynamic traffic management
- Deployment recommendations for operators
- Reduced delay and improved corridor efficiency

With real-world traffic feeds, this concept could be extended into an operational decision-support tool for transportation agencies or smart city platforms.

## Next Steps

Possible future improvements include:

- Replacing simulated data with real DOT or probe vehicle data
- Expanding to multi-step forecasting
- Testing deeper GNN architectures
- Integrating predictions into a dashboard for operations staff
- Measuring business outcomes such as delay reduction and travel-time reliability

## File

- `SEAS6505_HW6_Paul_Christopher.ipynb` — full notebook containing data simulation, model training, evaluation, visualizations, and analysis

## Note

This project was originally developed as graduate coursework and is being shared as part of my technical portfolio to demonstrate applied machine learning, graph modeling, and business-oriented AI thinking.

## Author

Christopher Paul
