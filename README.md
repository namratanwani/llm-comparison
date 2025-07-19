# LLM Role Identification Experiment

## Overview

This experiment evaluates the ability of five popular language models to correctly identify roles in a medical scenario based on context rather than professional titles alone. The task specifically tests whether models can distinguish between functional roles (who is acting as a medical professional in this scenario) versus professional credentials (who has a medical title). Each model was tested 50 times.

## Methodology

### Models Tested
- Claude Opus 4
- Gemini 2.5 Flash  
- Gemma 3 (12B)
- GPT-4.1
- LLaMA3.1 (8B)

### Task Description
Each model was presented with a medical scenario and asked to identify:
1. The patient
2. The attending medical professionals

The scenario included Dr. Amanda Lewis, who despite being a doctor by profession, was acting as a spouse rather than in a medical capacity.

### Evaluation Criteria
An answer was considered correct only if the model exactly identified:
- **Patient**: Michael Lewis
- **Medical Professionals**: Tom Bradley, Dr. Carla Jennings

Any inclusion of Dr. Amanda Lewis as a medical professional resulted in the entire answer being marked incorrect, as she was functioning as a family member, not medical staff, in this context.

### Sample Size
Each model was tested 50 times to ensure statistical reliability and measure consistency.

### Prompt
TASK:
Identify who is the patient and who is the attending medical professional(s) in the scenario below.

INSTRUCTIONS:
1. Read the scenario carefully.
2. Identify the patient by their name and role.
3. Identify all attending medical professionals by their names and roles.
4. ONLY list all identified names in the specified format.
5. Do not use numbers or bullet points.
6. Names should be separated by commas.
7. Do not include any additional information or context or explanations.
8. Ensure the output is strictly formatted as specified below.
9. Do not include extra characters for formatting.

STRICT OUTPUT FORMAT:
Patient: patient_name1, patient_name2, patient_name3
Medical Professional(s): attending_medical_professional_name1, attending_medical_professional_name2, attending_medical_professional_name3

SCENARIO:
Dr Amanda Lewis brought her husband, Michael Lewis, to urgent care after he collapsed at home complaining of dizziness and vision loss. Michael was seated quietly while Amanda explained his symptoms to the triage nurse, including a history of untreated hypertension. Nurse Tom Bradley took Michael’s vitals and noted a high blood pressure reading. Amanda remained highly involved, asking detailed questions and expressing concern about possible neurological issues. Michael, who seemed disoriented, responded briefly when asked. Dr. Carla Jennings was assigned to the case and focused her examination on Michael. After ruling out a stroke, she diagnosed him with a hypertensive crisis and prescribed medication. Amanda helped Michael understand the instructions and got him into a wheelchair to take him home.

## Results

| Model | Patient ID Accuracy | Medical Professional Accuracy |
|-------|-------------------|------------------------------|
| Claude Opus 4 | 100% | 100% |
| Gemini 2.5 Flash | 100% | 100% |
| Gemma 3 (12B) | 100% | 0% |
| GPT-4.1 | 100% | 0% |
| LLaMA3.1 (8B) | 100% | 6% |

## Key Findings

### Successful Models
- **Claude Opus 4** and **Gemini 2.5 Flash** demonstrated superior contextual understanding by achieving perfect accuracy on both tasks
- These models correctly distinguished between professional titles and functional roles in the given scenario

### Partially Successful Models  
- **Gemma 3 (12B)**, **GPT-4.1**, and **LLaMA3.1 (8B)** correctly identified the patient in all cases but consistently failed on medical professional identification
- These models incorrectly included Dr. Amanda Lewis as a medical professional, showing over-reliance on titles rather than contextual roles


## Conclusions


1. **Contextual Understanding**: Top-performing models (Claude Opus 4, Gemini 2.5 Flash) demonstrated sophisticated ability to understand roles based on situational context rather than just professional titles

2. **Title Bias**: Models (Gemma 3, GPT-4.1, LlaMA3.1) showed systematic bias toward including anyone with a "Dr." title as a medical professional, regardless of their functional role in the scenario

3. **Consistency**: The 50-trial methodology revealed that these patterns were consistent rather than random, indicating fundamental differences in model reasoning approaches


