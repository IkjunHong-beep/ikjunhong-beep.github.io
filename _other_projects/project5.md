---
title: "Transformer Time-Series Forecasting"
excerpt: "OLED luminance degradation prediction over future time windows using a transformer-based time-series model. Delta luminance was incorporated to improve training stability and forecasting performance.<br/><img src='/images/project4.png'>"
permalink: /other_projects
---

**Challenge** - Predicting OLED luminance degradation over time is challenging because device behavior is nonlinear, noisy, and influenced by multiple operating variables such as voltage, current, and temperature. In addition, degradation evolves gradually, so simple regression models often fail to capture long-range temporal dependencies and changing dynamics across the device lifetime.

**Approach** - Built a transformer-based time-series forecasting pipeline to predict future OLED luminance from historical device measurements. The model takes sequential windows of prior observations and learns temporal relationships among luminance, voltage, current, and temperature. To improve training behavior, I used delta luminance as part of the learning target/feature formulation. The model was trained and evaluated on degradation trajectories, and its predictions were compared against ground-truth behavior across the train, validation, and test regions over the full lifetime curve.

**Techniques** - Transformer encoder for sequential regression, multivariate time-series forecasting, positional encoding, sliding-window sequence generation, train/validation/test splitting, feature normalization, loss-based optimization, delta-luminance modeling, and full-period prediction visualization.

**Hyperparameters**  
`SEQ_LEN = 40`    
`PRED_LEN = 1` 
`BATCH_SIZE = 16`  
`EPOCHS = 100`  
`LR = 5e-5`  

`D_MODEL = 32`  
`NHEAD = 4`  
`NUM_LAYERS = 1`  
`DROPOUT = 0.05`  

`TRAIN_RATIO = 0.7`  
`VAL_RATIO = 0.15`  
`TEST_RATIO = 0.15`
