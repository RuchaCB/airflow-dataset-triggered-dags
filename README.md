# ⚡ Airflow Dataset-Triggered DAGs

This project demonstrates **event-driven scheduling** in **Apache Airflow** using the `Dataset` feature introduced in Airflow 2.4+.  
It implements a **producer-consumer pattern**, where one DAG updates datasets, and another DAG is automatically triggered when those datasets are modified.

Everything runs inside Docker containers using **Docker Compose** for easy setup and reproducibility.

---

## 🚀 What This Project Does

1. The **producer DAG** writes to two datasets (files).
2. The **consumer DAG** is triggered when any of those datasets are updated.
3. This showcases **declarative DAG dependencies** — no manual triggers or sensors required.

---

## 🛠️ Tech Stack

- **Apache Airflow 2.9.0**
- **Python**
- **Docker + Docker Compose**
- **Airflow Datasets (event-driven scheduling)**

---

## 🧩 DAG Structure

### 🟩 Producer DAG (`producer.py`)
- Runs on a daily schedule
- Writes to:
  - '/tmp/my_file.txt'
  - '/tmp/my_file_2.txt'
- Declares these files as **dataset outlets**

### 🟨 Consumer DAG (`consumer.py`)
- Has no time-based schedule
- Declares the two files as **dataset inputs**
- Automatically triggered when either file is updated

---

## 📸 Output

Here are some screenshots showcasing the key outputs and results from running the pipeline.
![datasets_screenshot](https://github.com/user-attachments/assets/b617bb6a-500c-41c1-b132-c63387256199)

---

## 📚 Acknowledgment

This project is based on a learning exercise from the Udemy course:  
**[The Complete Hands-On Course to Master Apache Airflow](https://www.udemy.com/course/the-complete-hands-on-course-to-master-apache-airflow/)** by *Marc Lamberti*.

I recreated and extended the project for practice and personal learning. All credits for the original project structure and logic go to the course instructor.



