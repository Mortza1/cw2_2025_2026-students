# 🚀 Project Execution and Environment Setup

This project is built around two primary Jupyter Notebooks: `part-1.ipynb` and `part-2.ipynb`.

## Running Experiments

To maximize efficiency and utilize the available **GPU resources**, we adopted a parallel processing strategy:

* Each notebook (`part-1.ipynb` and `part-2.ipynb`) was zipped individually.
* These ZIP files were then imported and run concurrently on **multiple Google Colab instances** using different team members' accounts.

> **Note on Tooling:** We used **ChatGPT** to assist with formatting some of the print statements and experiment objects, as well as to quickly reference the necessary Linux `zip` commands for packaging the files.

---

## 🛑 Important: Model Saving and Scoring

We encountered significant difficulties when trying to save and reuse the trained model files.

1.  **Corruption Issue:** Initial attempts to download the model files after an iteration, followed by re-uploading them, consistently resulted in **corrupted files**.
2.  **Workaround:** To ensure we captured results without file corruption, we established the following flow:
    * Run the training experiment.
    * Immediately execute the `test.py` script **within the same Colab instance** to calculate and retrieve the **BLEU score**.
    * Manually record the resulting score.

While subsequent runs within the same instance meant the model file was overwritten, this method successfully avoided corruption and allowed us to complete all required assignments.

---

***

*This README section was generated with assistance from Gemini.*