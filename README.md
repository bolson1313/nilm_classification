# NILM Classification Project

Projekt realizujący klasyfikację urządzeń w systemie NILM (Non-Intrusive Load Monitoring) przy użyciu algorytmów uczenia maszynowego (Random Forest) oraz głębokiego uczenia (Deep Neural Network).

Celem projektu jest identyfikacja aktywnych urządzeń domowych na podstawie parametrów w stanie ustalonym.

## Funkcjonalności

- **Przetwarzanie danych:** Wczytywanie plików CSV z polskim formatem liczbowym, automatyczne czyszczenie artefaktów (np. "CAP"/"IND" w Power Factor).
- **Feature Engineering:** Implementacja **Mocy Deformacji wg teorii Budeanu ($D$)** jako kluczowej cechy rozróżniającej urządzenia nieliniowe.
- **Klasyfikacja Multi-Label:** System rozpoznaje wiele urządzeń działających jednocześnie (np. Lodówka + TV).
- **Modele:**
  - **Random Forest Classifier:** Odporny model zespołowy z natywną obsługą wielu etykiet.
  - **Deep Neural Network (TensorFlow/Keras):** Sieć neuronowa z mechanizmem **ważenia klas** (`class_weight`) dla rzadkich urządzeń oraz **Early Stopping** zapobiegającym przeuczeniu.

## Instalacja i konfiguracja środowiska

Aby uruchomić projekt na nowym komputerze, zaleca się skorzystanie z menedżera **Conda**.

### Wymagania wstępne
- [Anaconda](https://www.anaconda.com/products/distribution) lub [Miniconda](https://docs.conda.io/en/latest/miniconda.html).
- Git.

### 1. Klonowanie repozytorium
```bash
git clone https://github.com/bolson1313/nilm_classification
cd nilm_classification
```
### 2. Utworzenie i aktywacja środowiska Conda
Automatycznie instaluje Python, biblioteki systemowe i pakiety Python.
```bash
conda env create -f environment.yml
conda activate classification
```

## Struktura projektu
```
nilm_classification/
├── data/
│   └── stan_ustalony.csv       # Dane pomiarowe
├── nilm_classification.ipynb   # Główny kod (Preprocessing, RF, DNN)
├── environment.yml             # Pełna konfiguracja środowiska (Conda)
├── requirements.txt            # Lista pakietów (Pip)
├── .gitignore                  # Pliki ignorowane przez Git
└── README.md                   # Dokumentacja
```