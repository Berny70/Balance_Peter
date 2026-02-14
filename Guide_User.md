## 📖 GUIDE UTILISATEUR SMARTPHONE

Créer un document séparé identique au guide frelon mais adapté :

### **Procédure simplifiée**
```
1. Appuyer bouton "Relevé" sur balance
2. Smartphone → WiFi "Balance-Ruche" (mdp: ruche2026)
3. Navigateur → 192.168.4.1
4. Voir poids actuel + graphique
5. Exporter données CSV si besoin
```

---

## 🔧 CALIBRATION INITIALE

### **Étape 1 : Tare à vide**
```
1. Plateau vide
2. Appuyer bouton TARE 3 secondes
3. Attendre 5 secondes
4. Vérifier poids = 0 kg
Étape 2 : Calibration avec poids connu
cpp// Via interface web:
1. Poser poids connu (ex: 20 kg)
2. Noter valeur affichée (ex: 18.5 kg)
3. Calculer facteur: 
   nouveau_facteur = ancien_facteur * (poids_reel / poids_affiché)
   = -7050 * (20 / 18.5) = -7621

4. Mettre à jour dans le code:
   #define CALIBRATION_FACTOR -7621.0

📊 FORMAT DONNÉES CSV
csvtimestamp,poids,batterie,temperature
3600,45.23,3.95,22.5
7200,45.18,3.92,23.1
10800,45.31,3.89,24.2
Colonnes :

timestamp : Secondes depuis boot
poids : Poids en kg
batterie : Tension batterie (V)
temperature : Température °C


🎨 AMÉLIORATIONS POSSIBLES
Version avancée

RTC externe (DS3231) : Horodatage précis
Capteur température/humidité (DHT22) : Conditions météo
Notification push : Alerte variation poids > 5kg
Multi-ruches : Plusieurs balances sur même réseau
Stockage cloud : Backup automatique données
