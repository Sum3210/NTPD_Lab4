#NTPD_Lab4

Aplikacja API wykorzystująca model uczenia maszynowego (Logistic Regression) do klasyfikacji irysów. Zaimplementowana w Flask, uruchamiana w kontenerze Docker, z opcjonalnym wykorzystaniem Redis.

## Uruchamianie aplikacji

### Uruchomienie lokalne (bez Dockera)

1. **Zainstaluj zależności:**
   ```bash
   pip install -r requirements.txt
   ```
2. **Uruchom aplikację:**
   ```bash
   python app.py
   ```
3. **Testowanie API:**
   ```bash
   curl -X POST http://localhost:5000/predict -H "Content-Type: application/json" -d '{"features": [5.1, 3.5, 1.4, 0.2]}'
   ```

---

### Uruchomienie w Dockerze

1. **Zbuduj obraz Dockera:**
   ```bash
   docker build -t iris-api .
   ```
2. **Uruchom kontener:**
   ```bash
   docker run -p 5000:5000 iris-api
   ```
3. **Testowanie API:**
   ```bash
   curl -X POST http://localhost:5000/predict -H "Content-Type: application/json" -d '{"features": [5.1, 3.5, 1.4, 0.2]}'
   ```

---

### Uruchomienie przez Docker Compose

1. **Uruchom aplikację:**
   ```bash
   docker-compose up --build -d
   ```
2. **Sprawdzenie kontenerów:**
   ```bash
   docker ps
   ```
3. **Testowanie API:**
   ```bash
   curl -X GET http://localhost:5000/health
   ```
4. **Zatrzymanie aplikacji:**
   ```bash
   docker-compose down
   ```

---

## Konfiguracja

- **Zmienne środowiskowe:**
  - `FLASK_ENV=production` – uruchomienie aplikacji w trybie produkcyjnym
  - `REDIS_HOST=redis` – host bazy Redis
  - `REDIS_PORT=6379` – port bazy Redis  

- **Wymagane zasoby:**
  - **CPU**: min. 1 vCPU  
  - **RAM**: min. 512 MB  
  - **Dysk**: ~200 MB na obraz Dockera  
  - **Porty**: 5000 (aplikacja), 6379 (Redis)  

---

## Struktura projektu
```
    ml-docker-app
├── app.py            # Plik aplikacji Flask
├── requirements.txt  # Lista zależności
├── Dockerfile        # Plik do budowy obrazu Docker
├── docker-compose.yml # Konfiguracja Docker Compose
└── README.md         # Dokumentacja projektu
```

---

## 📌 Repozytorium GitHub
Repozytorium dostępne pod adresem: [https://github.com/TwojNick/ml-docker-app](https://github.com/TwojNick/ml-docker-app)

---

## 📞 Kontakt
Jeśli masz pytania, skontaktuj się na email: **twojemail@example.com**

