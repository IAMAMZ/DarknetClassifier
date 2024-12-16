# Machine Learning-based Detection of Darknet Traffic

## Project Overview
This project implements machine learning models to detect and classify darknet traffic, specifically focusing on:
1. Network protocol detection (Tor, non-Tor, VPN, and non-VPN traffic)
2. Communication type classification (web browsing, video streaming, VoIP, P2P, etc.)

Using the CIC-Darknet2020 dataset, the project achieved 98% accuracy in protocol detection and 93% accuracy in communication type classification through careful feature selection and model optimization.

## Key Features
- Protocol detection (Tor/VPN/Regular traffic)
- Communication type classification
- Feature selection and importance analysis
- Class imbalance handling using SMOTE
- Model optimization through grid search
- Comprehensive visualization of results

## Technical Implementation
### Data Processing
- Dataset: 158,616 rows across 89 columns
- Handling of data quality issues including:
  - Negative duration values
  - Infinite values
  - Invalid protocol specifications
  - Header length exceeding IP protocol limits

### Feature Selection
Selected top 10 most predictive features for each model:

Protocol Detection Features:
- FWD Init Win Bytes
- Idle Max
- Dest Port
- Packet Length Max
- Forward Seg Size Min
- Bwd Packets/s
- Fwd packet length max
- Forward packets/s
- Ack flag count
- Bwd Init win Bytes

Communication Type Features:
- Src Port
- Dst Port
- Flow Duration
- Bwd Packet Length Min
- Packet Length Min
- Packet Length Mean
- Subflow Fwd Packets
- FWD Init Win Bytes
- Bwd Init Win Bytes
- Idle Max

## Results
### Protocol Detection
- Overall Accuracy: 98%
- Perfect detection of Non-Tor traffic
- High precision and recall for VPN and Tor traffic

### Communication Type Classification
- Overall Accuracy: 93%
- Perfect classification of P2P traffic
- Strong performance across most communication types
- Slightly lower performance on VOIP traffic (F1-score: 0.70)

## Challenges and Solutions
1. **Large Dataset Management**
   - Implemented parallel processing
   - Optimized data types for memory efficiency

2. **Class Imbalance**
   - Applied SMOTE for minority class oversampling
   - Maintained original test set for realistic evaluation

3. **Feature Selection**
   - Reduced from 89 to 10 most important features
   - Maintained high accuracy with reduced complexity

## Requirements
- Python 3.x
- scikit-learn
- pandas
- numpy
- imbalanced-learn



## Future Improvements
1. Enhanced visualization of decision trees
2. Alternative feature selection approaches
3. Additional model architectures
4. Real-time classification capabilities

## References
1. A. Habibi Lashkari, G. Kaur, and A. Rahali, "DIDarknet: A Contemporary Approach to Detect and Characterize the Darknet Traffic using Deep Image Learning"
2. CIC-Darknet2020 dataset documentation
3. scikit-learn documentation
