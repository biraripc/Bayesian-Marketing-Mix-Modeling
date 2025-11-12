# Bayesian Mixed Media Model (MMM) for Marketing Attribution

A fully probabilistic Bayesian Mixed Media Model implementation for quantifying and comparing the sales effectiveness of different marketing channels. This project helps optimize budget allocation by robustly estimating both the incremental contribution and return on investment (ROI) of each channel, while accounting for carry-over effects, saturation, and uncertainty.

## Overview

This project implements a Bayesian hierarchical model that incorporates adstock (carry-over) effects, trend, and seasonality to capture both immediate and lagged impacts of marketing spend across multiple channels. The model provides full posterior uncertainty quantification and credible intervals for explainable marketing attribution.

## Features

- **Bayesian Inference**: Full posterior distributions for all parameters using MCMC
- **Adstock Effects**: Channel-specific carry-over effects with decay rates
- **Saturation Modeling**: Non-linear channel response curves
- **Uncertainty Quantification**: Credible intervals for all estimates
- **ROI Analysis**: Channel-specific return on investment calculations
- **Attribution Analysis**: Individual and joint channel contributions
- **Visualization**: Comprehensive plots for model diagnostics and insights

## Model Components

- **Channel Coefficients** (β_m): Efficacy/effectiveness per channel
- **Decay/Adstock Rates** (λ_m): Carry-over effect per channel
- **Saturation Parameters**: Non-linear channel response
- **Baseline/Intercept** (α): Base sales not attributable to marketing
- **Controls**: Trend and seasonality effects
- **Observation Noise** (ε_t): Unexplained factors

## Data Structure

The model expects weekly data with the following structure:
- `start_of_week`: Date column for weekly periods
- `revenue`: Weekly sales revenue (target variable)
- `spend_channel_1` to `spend_channel_7`: Weekly marketing spend by channel

## Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd bayesian-mmm
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. **Data Preparation**: Ensure your data follows the expected format with weekly revenue and channel spend data.

2. **Run the Analysis**: Open and execute the Jupyter notebook:
```bash
jupyter notebook solution.ipynb
```

3. **Model Training**: The notebook includes:
   - Data loading and exploration
   - Model specification with priors
   - MCMC sampling for parameter estimation
   - Posterior predictive checks

4. **Results Interpretation**: The analysis provides:
   - Channel contribution analysis
   - ROI estimates with uncertainty
   - Model fit diagnostics
   - Budget optimization insights

## Key Outputs

- **Channel Contributions**: Posterior mean and credible intervals for sales attributed to each channel
- **ROI Analysis**: Revenue per unit of spend for each channel with uncertainty quantification
- **Model Diagnostics**: Posterior predictive checks, RMSE/MAE metrics
- **Visualizations**: Time series plots of channel contributions and model fit

## Technical Details

- **Framework**: PyMC for Bayesian modeling
- **Adstock Transformation**: Geometric decay with channel-specific rates
- **Saturation**: Logistic saturation curves
- **Priors**: Weakly informative, domain-based priors for regularization
- **Inference**: MCMC sampling with diagnostic checks

## Model Evaluation

The model is evaluated through:
- **Posterior Predictive Checks**: Comparing observed vs. predicted revenue
- **Uncertainty Calibration**: Fraction of observations within credible intervals
- **Business Metrics**: ROI rankings and channel effectiveness comparisons

## Files Structure

```
├── data/
│   └── MMM_test_data.csv          # Marketing spend and revenue data
├── solution.ipynb                 # Main analysis notebook
├── Report.docx                    # Detailed analysis report
├── README.md                      # This file
└── requirements.txt               # Python dependencies
```

## Dependencies

- Python 3.8+
- PyMC Marketing
- PyMC
- ArviZ
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Plotly

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Citation

If you use this code in your research, please cite:

```bibtex
@software{bayesian_mmm,
  title={Bayesian Mixed Media Model for Marketing Attribution},
  author={[Your Name]},
  year={2024},
  url={[Repository URL]}
}
```

## Support

For questions or issues, please open an issue on GitHub or contact [biraripc@gmail.com].