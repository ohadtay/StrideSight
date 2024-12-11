# StrideSight: Analysis of Running Biomechanics

## Project Overview

StrideSight is a comprehensive tool designed to analyze the biomechanics of running. It combines advanced data processing techniques with datasets from professional studies to investigate the joint kinematics, moments, and forces during running. This tool is aimed at researchers, sport scientists, and enthusiasts seeking insights into running performance and biomechanics.

The purpose of StrideSight is to provide a user-friendly platform for analyzing running patterns, comparing novice and elite runners, and identifying biomechanical changes due to prolonged or repetitive motion. **It is not a replacement for medical analysis or clinical diagnosis.**

## Features

- Analysis of stride variability and joint kinematics.
- Utilization of advanced biomechanical models for joint kinematic predictions.
- Comparison of pre- and post-run biomechanics.
- Frame-level analysis to visualize and validate model predictions.

## Dataset and Tools

This project incorporates datasets from the following published studies:

1. **"Complexity of Running and Its Relationship with Joint Kinematics during a Prolonged Run"** by Siddhartha Bikram Panday et al. ([Read the full paper](https://doi.org/10.3390/ijerph19159656)).
2. **"Dataset of Lower Extremity Joint Angles, Moments and Forces in Distance Running"** by Qichang Mei et al. ([Read the full paper](https://doi.org/10.1016/j.heliyon.2022.e11517)).

### Tools and Libraries

- **Python**: For interpolation, data analysis, and visualization.
- **Azure Storage and Kusto**: For secure data storage and querying, utilizing Azure storage accounts and Kusto clusters.
- **Mediapipe Pose Landmarker**: The Mediapipe Pose Landmarker is an advanced computer vision model developed by Google AI ([Learn more](https://ai.google.dev/edge/mediapipe/solutions/vision/pose_landmarker)). It detects and tracks 33 key landmarks on the human body, enabling precise pose analysis during dynamic activities such as running. This model provides a robust foundation for analyzing biomechanical data by capturing spatial and temporal features of movement.

### About the Model

The Mediapipe Pose Landmarker is a state-of-the-art solution designed for pose estimation and motion tracking. It operates in real-time and accurately identifies 33 pose landmarks, including key joints such as shoulders, elbows, knees, and ankles. By leveraging deep learning, this model processes video frames or static images to deliver highly detailed biomechanical insights.

This model is particularly advantageous for biomechanics analysis because:

1. **Real-Time Efficiency**: Enables immediate feedback and visualization.
2. **High Accuracy**: Captures complex movements with minimal error.
3. **Cross-Platform Usability**: Compatible with various devices and environments, ensuring adaptability for different use cases.

## Installation and Usage Instructions

```bash
# Prerequisites
- Azure credentials are required to access storage accounts and Kusto clusters.
- The current implementation uses internal Azure resources (storage accounts and Kusto clusters). Users must configure their own Azure resources for storage and querying to run the analysis effectively.

# Clone the Repository
$ git clone https://github.com/ohadtay/StrideSight
$ cd StrideSight

# Running the Analysis
- Open the notebook (`StrideSight.ipynb`) in Google Colab or Jupyter Notebook.
- Follow the steps outlined in the notebook for each stage of the analysis.
- Each step must be executed sequentially to ensure the workflow is complete and accurate.
```

## Results and Observations

Based on the studies and tools integrated into StrideSight:

- Elite runners demonstrate lower variability in stride width and length during prolonged runs compared to novices.
- Novice runners exhibit greater joint kinematic variability, especially in ankle and knee movements, as a compensatory mechanism for stability.
- Prolonged running results in notable changes in joint angles and forces, highlighting the need for proper pacing and training.

## Analysis Overview

### Approach

The analysis in StrideSight leverages the Mediapipe Pose Landmarker and Azure Kusto queries to process and analyze biomechanical data. Key steps include:

1. Extracting and preprocessing pose data from video frames.
2. Aggregating kinematic information for each detected joint.
3. Querying and visualizing results to identify patterns and anomalies in running biomechanics.

### Queries and Their Purpose

1. **Stride Variability Analysis**:
   - We analyze step width, step length, and temporal stride patterns to assess variability. 
   - As noted in Panday et al. (2022), increased stride variability can indicate compensatory mechanisms, particularly in novice runners.

2. **Joint Kinematics Tracking**:
   - By focusing on specific joints like the knee and ankle, we evaluate their range of motion and variability over time.
   - This is critical for identifying biomechanical inefficiencies or risk factors for injury (Mei et al., 2022).

3. **Other Queries**:
   - Analysis of ground reaction forces and their distribution over time to detect biomechanical efficiency or asymmetries.
   - Evaluation of temporal gait parameters (e.g., stance time, swing time) to investigate their influence on joint stability and overall performance.
   - Tracking inter-limb symmetry to identify potential imbalances or risks of overuse injuries, based on findings in Mei et al. (2022).

Each query was designed to address specific aspects of running biomechanics, providing users with actionable insights grounded in established research.

## Future Implementations

1. **Integration of Wearable Sensors**:
   - Incorporate real-time accelerometer and gyroscope data to analyze running dynamics in the field.
2. **Advanced Machine Learning**:
   - Apply deep learning techniques to classify running styles and predict injuries.
3. **Personalized Recommendations**:
   - Develop algorithms for personalized feedback on running posture and footwear.
4. **Expanded Dataset**:
   - Include data from different demographics, running surfaces, and footwear types.

## Disclaimer

**StrideSight is not a replacement for medical analysis.** The tool is designed for biomechanical research and should not be used for clinical diagnosis or treatment. If you experience pain or discomfort during running, please consult a healthcare professional.

## Citations

If you use StrideSight or its components in your research, please cite the following:

1. Siddhartha Bikram Panday, Prabhat Pathak, Jeheon Moon, and Dohoon Koo. *Complexity of Running and Its Relationship with Joint Kinematics during a Prolonged Run.* Int. J. Environ. Res. Public Health, 2022.
2. Qichang Mei, Justin Fernandez, Liangliang Xiang, et al. *Dataset of Lower Extremity Joint Angles, Moments and Forces in Distance Running.* Heliyon, 2022.

