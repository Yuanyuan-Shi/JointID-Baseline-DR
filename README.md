# JointID-Baseline-DR

This repo contains the code for the "Demand-side Price-responsive Flexibility and Baseline Estimation through End-to-end Learning", https://arxiv.org/pdf/2109.00741.pdf

Fig 1 visualizes the proposed end-to-end joint baseline demand estimation and price-response model identification framework.
Specifically, the top green colored block in the Figure is the baseline demand forecast module that maps the demand forecast features to baseline demand prediction, where the ``Baseline Demand Forecast'' module is parameterized as a multiple-layer perception (MLP). 
The bottom green colored block is the ``Demand Response (DR) Agent Model'', which takes a time-varying incentive/price signal $\lambda :=\{\lambda_t\}_{t=1}^{T}$ and predicts the consumer's response $y^*:=\{y^*_t\}_{t=1}^{T}$. Specifically, we assume the DR agent model is an optimization problem, where the DR agent aims to minimize its total electricity bill and the personal discomfort subject to its energy usage flexibility constraints.
The summation of the baseline demand prediction $\hat{D}$ and the demand response prediction $y^*$ sum up to get the net demand prediction $(\hat{D} + y^{*})$, which is compared against the net demand observation $z$ as the model training loss function. 
\begin{figure}[htbp]
\centering
\includegraphics[width=3.2in]{diagram.png}
\caption{Illustration of the proposed end-to-end joint demand response identification and baseline demand estimation framework.} 
\label{fig:nn1}
\end{figure}
