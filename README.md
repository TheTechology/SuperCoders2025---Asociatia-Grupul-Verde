# 🧠 SuperCoders – Ediția 14  
**Asociația Grupul Verde** · *program finanțat de [Fundația Orange](https://fundatiaorange.ro/)*  

[![Status](https://img.shields.io/badge/status-activ-brightgreen)](#) 
[![Vârste](https://img.shields.io/badge/vârste-9--14-ff69b4)](#) 
[![Tech](https://img.shields.io/badge/tehnologii-Arduino%20%7C%20Scratch%20%7C%20Web-blue)](#)

---

## 🌍 Descriere
**SuperCoders – Ediția 14** este o aventură educațională dedicată copiilor din România, unde învățăm să gândim ca niște creatori, nu doar utilizatori ai tehnologiei.  
În această ediție, **Asociația Grupul Verde** din Adjud (Vrancea) promovează gândirea logică, creativitatea și lucrul în echipă prin mini-proiecte educative bazate pe **Arduino**, **Scratch** și **programare vizuală**.

> 🎯 Obiectiv: să transformăm curiozitatea în cunoaștere – de la „Ce-ar fi dacă?” la „Uite, funcționează!”

---

## 🎓 Obiectivele educaționale
1. Dezvoltarea gândirii algoritmice și logice.  
2. Introducere prietenoasă în electronica de bază și programare.  
3. Exersarea creativității și colaborării în echipă.  
4. Responsabilitate și conștientizare a impactului tehnologiei asupra mediului.  
5. Incluziune digitală pentru copii între 9 și 14 ani.

---

## 🚀 Rezultate așteptate
- 6–10 **prototipuri** realizate de echipe mixte.  
- 60–120 **participanți** inițiați în gândire logică și prototipare.  
- Crearea unui **mic portofoliu online** cu idei și demo-uri vizuale.

---

## 📘 Structura programului
| Sesiune | Activitate | Scop principal |
|----------|-------------|----------------|
| **S1** | Descoperim Arduino | Ce este, la ce folosește, reguli de siguranță |
| **S2** | Logica proiectelor | „Dacă... atunci...”, simulări și idei |
| **S3** | Storyboard creativ | Planificarea unui mini-proiect |
| **S4** | Demo & feedback | Prezentarea proiectelor în echipă |

---

## 💡 Proiecte demonstrative propuse
- 💡 LED care clipește („Salut, lume!”)  
- 🚦 Semafor inteligent  
- 🌱 Planta care „cere apă” (senzor umiditate)  
- 📏 Parcare cu sonar  
- 🌙 Lampă de noapte automată  
- 🎹 Mini-pian cu butoane  
- ☁️ Mini stație meteo

---

## ⚙️ Demo #1 – Blink (Arduino)

```cpp
// SuperCoders – Ediția 14 (Asociația Grupul Verde)
// Demo 1: LED "Blink" pe pinul 13 (LED-ul de pe placă)
const int LED = 13;

void setup() {
  pinMode(LED, OUTPUT);
}

void loop() {
  digitalWrite(LED, HIGH); // aprinde
  delay(500);
  digitalWrite(LED, LOW);  // stinge
  delay(500);
}
🚦 Demo #2 – Mini-semafor (Arduino)
// SuperCoders – Ediția 14
// Proiect demonstrativ – Semafor pentru pietoni
const int RED = 8, YELLOW = 9, GREEN = 10;

void setup() {
  pinMode(RED, OUTPUT);
  pinMode(YELLOW, OUTPUT);
  pinMode(GREEN, OUTPUT);
}

void loop() {
  digitalWrite(RED, HIGH);    delay(1500);
  digitalWrite(RED, LOW);

  digitalWrite(YELLOW, HIGH); delay(700);
  digitalWrite(YELLOW, LOW);

  digitalWrite(GREEN, HIGH);  delay(1500);
  digitalWrite(GREEN, LOW);   delay(400);
}

Demo #3 – Simulator web (fără placă Arduino)

Salvează fișierul de mai jos ca web-demos/demo-simulator.html și deschide-l în browser.
<!doctype html>
<html lang="ro"><meta charset="utf-8">
<title>SuperCoders • Simulator LED</title>
<style>
  body{font-family:system-ui,Arial;background:#0b0f2a;color:#eef;margin:0;display:grid;place-items:center;height:100vh}
  .card{background:#12183f;border:1px solid #ffffff22;border-radius:16px;padding:20px;width:320px;text-align:center;box-shadow:0 6px 24px #0007}
  .led{width:26px;height:26px;border-radius:50%;margin:10px auto;background:#2a2a2a;box-shadow:0 0 0 #0000;transition:.2s}
  .led.on{background:#ff4d4d;box-shadow:0 0 16px #ff4d4d}
  button{padding:10px 14px;border:0;border-radius:12px;font-weight:800;cursor:pointer;
         background:linear-gradient(180deg,#6cf,#1487ff);color:#021b35}
  p{color:#bcd}
</style>
<div class="card">
  <h1>LED „Blink” – Simulator</h1>
  <div id="dot" class="led"></div>
  <p id="status">Oprit</p>
  <button id="start">Pornește</button>
</div>
<script>
  let on=false, timer=null;
  const dot=document.getElementById('dot');
  const status=document.getElementById('status');
  const btn=document.getElementById('start');
  btn.onclick=()=>{
    if(timer){
      clearInterval(timer); timer=null; on=false;
      dot.classList.remove('on'); status.textContent='Oprit'; btn.textContent='Pornește'; return;
    }
    btn.textContent='Oprește';
    timer=setInterval(()=>{
      on=!on; dot.classList.toggle('on', on);
      status.textContent = on ? 'Aprins' : 'Stins';
    }, 500);
  };
</script>
</html>
🧩 Instalare și rulare (Arduino)

Instalează aplicația Arduino IDE.

Conectează placa (UNO / Nano / Mega) la portul USB.

Deschide fișierul .ino din folderul proiectului.

Selectează placa și portul (Tools → Board / Port).

Apasă Upload pentru a încărca codul.

supercoders-ed14/
├─ README.md
├─ arduino/
│  ├─ Blink/
│  │  └─ Blink.ino
│  └─ Semafor/
│     └─ Semafor.ino
├─ web-demos/
│  └─ demo-simulator.html
└─ media/
   └─ logo-grupul-verde.png   (opțional)

