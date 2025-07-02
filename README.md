# Predykcja wyników meczów NBA  

## Cel projektu  
Głównym celem projektu było opracowanie modelu uczenia maszynowego przewidującego wynik meczu NBA na podstawie statystyk drużyn (gospodarzy i gości). Model umożliwia ocenę prawdopodobieństwa zwycięstwa oraz poziomu pewności predykcji.  

### Kluczowe zadania:  
- Identyfikacja kluczowych statystyk wpływających na wynik meczu  
- Przygotowanie i przetworzenie danych  
- Porównanie skuteczności różnych algorytmów ML  
- Budowa i optymalizacja modelu (hiperparametry, kalibracja)  
- Ocena jakości modelu (metryki, analiza błędów, generalizacja)  

## Dane  
- **Źródło**: Oficjalne API NBA (sezony 2022–2023 i 2023–2024)  
- **Wybrane cechy**: Punkty (PTS), skuteczność rzutów (FG_PCT, FG3_PCT), zbiórki (REB), asysty (AST), bilans punktowy (PLUS_MINUS) oraz efektywność (EFF).  
- **Przetwarzanie**: Imputacja braków, skalowanie, selekcja cech (SelectKBest).  

## Metody  
- **Główny model**: Random Forest Classifier (z optymalizacją GridSearchCV, RandomizedSearchCV)  
- **Inne metody**:  
  - Kalibracja (CalibratedClassifierCV)  
  - Ensemble learning (VotingClassifier, StackingClassifier)  
- **Walidacja**: Krzyżowa walidacja, bootstrap, analiza ważności cech.  

## Wyniki  
- **Skuteczność modelu**:  
  - Accuracy: 78.1% (test), 76.0% (sezon 2023–24)  
  - ROC AUC: 0.863 (test), 0.838 (sezon 2023–24)  
- **Najważniejsze cechy**: PLUS_MINUS, PF, PTS, FT_PCT, EFF.  
- **Optymalny próg klasyfikacji**: 0.40 (Recall: 92%, F1: 0.81).  

## Wnioski  
- Model Random Forest wykazał wysoką stabilność i interpretowalność.  
- Dobre wyniki generalizacji na nowe dane (sezon 2023–2024).  
- Zastosowane techniki (bootstrap, kalibracja) zwiększyły wiarygodność predykcji.  

**Użyteczność**: Model może służyć do prognozowania wyników meczów NBA z uwzględnieniem kluczowych statystyk drużyn.  
