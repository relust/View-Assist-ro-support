# View Assist – Timers, Alarms & Reminders în limba română 🇷🇴

Acest ghid explică cum să adaugi suport complet pentru limba română
în View Assist (Home Assistant), pentru **timere**, **alarme** și **remindere**,
inclusiv expresii vocale imperfecte generate de STT.

---

## 1️⃣ Instalare fișier traducere

Copiază fișierul [ro.json](https://github.com/relust/View-Assist-ro-support/blob/main/Translations/Timers/ro.json) în următoarea locație:

`/config/custom_components/view_assist/js_modules/translations/timers/ro.json`


După copiere, repornește Home Assistant.

---

## 2️⃣ Automatizare / Blueprint

După ce imporți blueprintul View Assist:

### Varianta A – din interfață
- Deschide automatizarea
- Înlocuiește comenzile în limba engleză cu cele în limba română de [aici](https://github.com/relust/View-Assist-ro-support/blob/main/Translations/Timers/automation_ro_trigger_sentences)
- Salvează

### Varianta B – YAML (recomandat)
- Deschide meniul cu trei puncte (dreapta sus)
- Selectează **Take control**
- Intră în **Editare în YAML**
- Înlocuiește secțiunea `triggers:` cu cea din [acest fișier](https://github.com/relust/View-Assist-ro-support/blob/main/Translations/Timers/automation_ro_trigger_sentences)
- Salvează
---

## 3️⃣ Exemple de comenzi vocale acceptate

### ⏰ Alarme
- „Setează o alarmă pentru ora 7:30”
- „Setează o alarmă pentru ora 7:30 de minute”
- „Setează alarma pentru mâine la ora șapte și treizeci”
- „Setează o alarmă să mă trezesc la ora 7:30”

### ⏱️ Timere
- „Setează un timer pentru cinci minute”
- „Pornește temporizatorul pentru două ore și treizeci de minute”

### 🔔 Remindere
- „Reamintește-mi peste zece minute să beau cafeaua”
- „Adu-mi aminte mâine la ora 9 să sun la service”

---

## 4️⃣ De ce este nevoie de acest fișier

Motoarele STT pot transcrie ora în mai multe moduri:
- `7:30`
- `7 30`
- `șapte și treizeci`
- `7:30 de minute`

Fișierul `ro.json` este adaptat pentru a **accepta toate aceste variante**
și a evita erorile de tip:

> „Nu s-a putut interpreta timpul sau intervalul setat”

---

## 5️⃣ Observații

- Expresii gramatical incorecte sunt acceptate intenționat
- Scopul este robustețea, nu purismul lingvistic
- Funcționează cu mai multe motoare STT

---

Contribuțiile sunt binevenite 🙂
