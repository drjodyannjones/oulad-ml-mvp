# Student Success Predictive Analytics MVP

This repository presents an end-to-end pipeline for predicting at-risk students using public educational data. The solution demonstrates scalable, cloud-native machine learning operations, including data preprocessing, model training, deployment, and infrastructure as code. This MVP provides a strong foundation for data-driven student success initiatives, showcasing the ability to rapidly implement a predictive analytics platform that can scale and evolve over time.

## Overview

- **Objective:** Quickly identify students at risk of failing or dropping out, enabling timely interventions.
- **Data Source:** Open University Learning Analytics Dataset (OULAD).
- **Cloud Native:** Amazon SageMaker for training and inference, S3 for data storage.
- **Infrastructure as Code:** Terraform is used to provision and manage AWS resources.
- **MLOps Readiness:** Modular codebase, basic CI/CD integration, and unit tests for reliability.

## Key Components

- **Data Pipeline:** Scripts to preprocess raw OULAD files, transforming them into feature-rich datasets.
- **Model Training:** A baseline XGBoost model trained and tuned via SageMaker.
- **Deployment:** Automated creation of a SageMaker endpoint for real-time inference.
- **Testing & CI:** Basic test harness ensures code quality. Configuration supports easy integration of CI/CD workflows.

## Getting Started

1. **Clone & Setup:**
   ```bash
   git clone https://github.com/your-username/student-success-ml-mvp.git
   cd student-success-ml-mvp
   python3 -m venv venv
   source venv/bin/activate
   pip install -r src/requirements.txt
   ```

2. **Provision Infrastructure:**
   ```bash
   cd infra
   terraform init
   terraform apply
   ```
   Once complete, necessary AWS resources (e.g., S3 bucket) are ready.

3. **Data Preparation:**
   - Place OULAD CSV files in `data/raw/`.
   - Run preprocessing scripts to produce processed data in `data/processed/` and upload to S3.

4. **Model Training & Inference:**
   - Use `src/train.py` to launch a SageMaker training job.
   - Deploy the model with `src/deploy.py`.
   - Test predictions using `src/inference.py`.

## Future Directions

- **Automated ETL & Feature Store:** Integrate AWS Glue for automated data pipelines.
- **Model Monitoring:** Add model drift detection and performance tracking.
- **API Integration:** Introduce API Gateway and Lambda for a streamlined external inference interface.
- **Advanced CI/CD:** Expand test coverage and pipeline automation for continuous improvement.

---
