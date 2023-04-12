# Demand-side Price-responsive Flexibility and Baseline Estimation through End-to-end Learning

This repo contains the code for the "Demand-side Price-responsive Flexibility and Baseline Estimation through End-to-end Learning", https://arxiv.org/pdf/2109.00741.pdf


![Illustration of the proposed end-to-end joint demand response identification and baseline demand estimation framework.](diagram.png width="600")


Fig 1 visualizes the proposed end-to-end joint baseline demand estimation and price-response model identification framework.
Specifically, the top green colored block in the Figure is the baseline demand forecast module that maps the demand forecast features to baseline demand prediction, where the ``Baseline Demand Forecast'' module is parameterized as a multiple-layer perception (MLP). 


The bottom green colored block is the ``Demand Response (DR) Agent Model'', which takes a time-varying incentive/price signal and predicts the consumer's response. Specifically, we assume the DR agent model is an optimization problem, where the DR agent aims to minimize its total electricity bill and the personal discomfort subject to its energy usage flexibility constraints.

The summation of the baseline demand prediction and the demand response prediction sum up to get the net demand prediction, which is compared against the net demand observation as the model training loss function. 
In the training process, the objective function tries to minimize the difference between the net demand forecasting (predicted baseline demand + predicted demand response) and the actual net demand, will be back-propagated through both the downstream optimization module (an OptNet Module) and the load forecasting neural network. 
