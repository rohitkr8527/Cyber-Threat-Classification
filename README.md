### **Cyber Threat Classification Using Transformers**

#### Training Configuration

- **Epochs**: 1 
- **Batch Size**: 8  
- **Learning Rate**: 1e-5  
- **Weight Decay**: 0.01  
- **fp16**: Enabled for GPU (if available)  

---

#### Evaluation Results

| Model       | Eval Loss | Inference Output             | Confidence |
|-------------|-----------|------------------------------|------------|
| DistilBERT  | 0.376     | `high` label on SHA256 IOC   | 97.5%      |
| SecBERT     | 0.411     | `high`                       | 98.9%      |
| SecureBERT  | 0.420     | `high`                       | 99.1%      |
| CTI-BERT    | 0.418     | `high`                       | 98.9%      |


---

#### Sample Input Data Format

Each threat indicator is structured as a JSON object, typically received from platforms like **OpenCTI**. Below is a sample:

<details>
  <summary>Example Record</summary>

```json
{
  "id": "878763d1-c7ad-47f8-bc79-7484c050bd78",
  "name": "be12e55c7b524947e974677557fc1fda52083891b6aa9bbf9b17341fd9480f5a",
  "description": "",
  "pattern": "[file:hashes.'SHA-256' = 'be12e55c7b524947e974677557fc1fda52083891b6aa9bbf9b17341fd9480f5a']",
  "created": "2025-02-05T09:20:18.682Z",
  "modified": "2025-02-05T10:33:03.350Z",
  "confidence": 100,
  "x_opencti_score": 85
}
