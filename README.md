VitalLink — Health Intelligence Platform

> **Hackathon project** · Tema: *"Be the Middlemen"*

VitalLink este o platformă medicală inteligentă care acționează ca **intermediar** între pacienți, medici și persoanele de încredere — procesând date din smartwatch-uri și dispozitive wearable, un LLM conectat în timp real și istoricul medical al utilizatorului.

---

## Conceptul

Ideea centrală: **tu ești nodul central al unei rețele de sănătate**. Platforma conectează:

- **Datele tale biologice** (smartwatch, smart ring, telefon) — BPM, tensiune, SpO2, somn, HRV, stres, glucoză
- **Un AI personal (Vita)** — căruia îi dai update-uri zilnice despre cum te simți, ce ai mâncat, cum ai dormit, ce te doare
- **Trusted persons** — persoane alese de tine, fiecare cu acces granular la datele tale
- **Medicii tăi** — care au dashboard dedicat cu toate datele și pot colabora între ei
- **Servicii de urgență** — contactate automat cu datele tale medicale pre-completate

---

## Features implementate

### Autentificare cu 2 tipuri de conturi
- **Client** — utilizatorul care poartă dispozitivul wearable
- **Specialist (Medic)** — are atât dashboard propriu de pacient, cât și panou de management al pacienților

### Trusted Person Network
- Fiecare utilizator poate fi în același timp:
  - **Trusted person** pentru altcineva (vizibil în secțiunea "Sunt trusted person pentru")
  - Poate adăuga **propriile trusted persons**
- La adăugare, configurezi **granular ce poate vedea** persoana:
  - Date cardiace (BPM, tensiune, SpO2)
  - Alerte de urgență
  - Date somn
  - Activitate fizică
  - Medicație
  - Istoric medical
  - Locație (doar la SOS)
  - 
### Dashboard customizabil
- **Slide între date proprii și datele trusted person-ului** 
- **Editare metrici** — buton Editează → poți adăuga/elimina orice măsurătoare:
  - BPM, Tensiune, SpO2, Somn, HRV, Temperatură, Nivel stres, Glucoză, Calorii, Greutate
- Date live animate (BPM fluctuează în timp real)

### AI Health Assistant (Vita)
- Conectat la vitals în timp real
- **Detecție urgență** — când detectează cuvinte cheie (`mor`, `ajutor`, `112`, `nu respir`, `atac`, `infarct`, `lesin` etc.) activează **modul urgență** cu UI roșu + 3 butoane de acțiune rapide
- Răspunsuri contextuale bazate pe istoricul medical și vitals curente

### Protocol SOS
- Buton SOS vizibil permanent în header
- Modal cu date medicale pre-completate automat (locație, vitale, medicație, alergii)
- Apel direct 112 + contactare medic pe WhatsApp

### Integrare WhatsApp
- Buton pe fiecare contact și medic → redirect direct la `wa.me/[număr]` cu mesaj pre-completat
- Integrare în thread-urile de mesaje

### Mesagerie
- Conversații separate cu medicul, familia, prietenii
- Specialist are conversații cu pacienții și contactele personale
- Buton "Vitale" direct din conversație cu pacientul (specialist)

### Documente medicale
- Upload PDF/imagini din ambele conturi
- Listă cu data, sursa și opțiune de ștergere

### Dashboard Specialist
- Listă pacienți cu status în timp real (Alertă / Monitorizare / Normal)
- Click pe pacient → panel detaliat cu:
  - Vitale live
  - Recomandare AI contextualizată
  - Detecție conflict medicamentos (ex: Bisoprolol + Alprazolam)
  - Medicație și alergii
- Mesagerie directă cu pacienții
- Propriul tab "Sănătatea mea" cu metrici și trusted persons proprii

### UI Responsive
- **Desktop**: phone frame (393×852px) cu efect de telefon real pentru contul client
- **Mobile**: full screen nativ
- Specialist: layout full-width cu top navigation

---

## Structura proiectului

```
hackaton/
├── index.html      # Single-page app — tot frontend-ul
└── README.md       # Documentație
```

Proiectul este un **single-page app** pur HTML/CSS/JS — zero dependențe externe, zero build step. Se deschide direct în browser.

---

## Cum rulezi

```bash
# Clonează repo-ul
git clone https://github.com/[username]/vitallink.git
cd vitallink

# Deschide direct în browser
open index.html
# sau
npx serve .   # dacă vrei un local server
```
