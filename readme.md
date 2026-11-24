<div align="center">

# 📊 Big Data Analytics & Machine Learning

### Распределённая обработка данных и машинное обучение в Apache Spark

**Учебный курс «Технологии и инструментарий анализа больших данных»**

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Apache Spark](https://img.shields.io/badge/Apache%20Spark-3.5+-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)](https://spark.apache.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-Academic-blue?style=for-the-badge)](./LICENSE)

[![Status](https://img.shields.io/badge/Status-Completed-success?style=flat-square)]()
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey?style=flat-square)]()

</div>

---

## 📖 О проекте

Репозиторий содержит комплекс выполненных практических работ по дисциплине **«Технологии и инструментарий анализа больших данных»**. 

В рамках работ был пройден полный цикл распределённой обработки данных: от развертывания локального кластера Spark и анализа физических планов выполнения запросов до построения моделей машинного обучения и прогнозирования поведения пользователей.

### 🎯 Ключевые возможности

| | Модуль | Описание |
|---|---|---|
| 📥 | **Staging** | Извлечение данных из SQLite/CSV и подготовка к распределённой обработке |
| ⚙️ | **Spark SQL & DataFrame** | Трансформации, агрегации, JOIN-ы и анализ схем данных |
| 🚀 | **Spark UI & Explain** | Исследование партиций, Shuffle, Sort Merge Join и Broadcast Join |
| 🤖 | **Spark MLlib** | Построение Pipeline, One-Hot Encoding и обучение моделей |
| 🧠 | **Регрессия и Классификация** | Линейная регрессия, Random Forest, предсказание времени прослушивания |

---

## 🏗️ Структура и Архитектура

**Схема обработки данных:**

*   **📥 Источники данных:** SQLite (ecommerce), CSV (подкасты)
*   **⚙️ Подготовка:** Извлечение через Pandas -> Staging-каталог
*   **🔥 Spark Cluster:** Развертывание локальной SparkSession (`local[*]`)
*   **🧹 Обработка:** DataFrame API и Spark SQL
    *   *Практика №3:* Аналитика интернет-магазина (JOIN, агрегации, Parquet)
    *   *Практика №4:* Анализ физических планов (Broadcast Join, Shuffle, Spark UI)
    *   *Практика №5:* Машинное обучение (MLlib)
*   **🤖 ML Pipeline:** 
    *   Датасет: Подкасты (предсказание `Listening_Time`)
    *   Модели: Линейная регрессия и Random Forest
    *   Результат: Оценка метрик MAE, RMSE, R²

---

## 📝 Детали выполненных работ

### 📌 Практическая работа №3. Распределенная модель обработки
**Цель:** Освоить базовый цикл распределённой обработки табличных данных.
*   **Данные:** База данных интернет-магазина (`ecommerce.sqlite`).
*   **Задачи:** Чтение данных, явное задание схемы (`StructType`), обработка пропусков, агрегации, JOIN-ы и сохранение в Parquet.
*   **Результат:** Построена аналитическая витрина по категориям товаров и штатам клиентов.

### 📌 Практическая работа №4. Задачи обработки в распределённых вычислениях
**Цель:** Исследовать физический механизм выполнения задач в Spark.
*   **Задачи:** Анализ партиций, перекосов данных (data skew), сравнение `repartition` и `coalesce`. Изучение стратегий JOIN (Sort Merge vs Broadcast).
*   **Результат:** Проведён бенчмарк влияния количества партиций на время выполнения, проанализированы стадии и задачи (Stages/Tasks) в Spark UI.

### 📌 Практическая работа №5. Машинное обучение в Spark MLlib
**Цель:** Построить полный Pipeline машинного обучения.
*   **Основной датасет:** Классификация (Online Shoppers), Регрессия (Seoul Bike), Кластеризация (KMeans).
*   **Самостоятельная работа:** Прогнозирование времени прослушивания подкаста (`Listening_Time`).
*   **Задачи:** Обработка категориальных признаков (`StringIndexer`, `OneHotEncoder`), сборка вектора (`VectorAssembler`), масштабирование (`StandardScaler`) и обучение.
*   **Результат:** **Random Forest** показал лучшее качество (R² = 0.65, MAE = 12.52 мин) по сравнению с Линейной регрессией (R² = 0.55, MAE = 13.34 мин), что подтверждает нелинейный характер зависимости.

---

## 🚀 Как запустить проект локально

1. Клонируйте репозиторий:
   `git clone https://github.com/FedNirvanous451/tiabd.git`

2. Создайте виртуальное окружение и установите зависимости:
   `python -m venv .venv`
   `.venv\Scripts\activate` (Для Windows)
   `pip install pyspark pandas numpy matplotlib seaborn scikit-learn jupyter`

3. Запустите Jupyter:
   `jupyter notebook`

---
*Работа выполнена в рамках учебного курса. Все данные, использованные в проекте, находятся в открытом доступе (UCI Machine Learning Repository) или предоставлены в учебных целях.*