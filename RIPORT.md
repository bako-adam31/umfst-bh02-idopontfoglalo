# A rakoncátlan időpontfoglaló – hibariport

Repó: https://github.com/<bako-adam31>/umfst-bh02-idopontfoglalo
Készítette: <Bako Adam-Attila>, <INFO LM>

## 1. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
Az `app.js` 12. soraban a `foglalt(ido)` fuggveny a `foglalasok.indexOf(ido)` metodust hivta meg. Mivel a `foglalasok` tombben objektumok (`{ nev, ido }`) vannak tarolva, a sima sztring keresese mindig `-1` erteket adott vissza,
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Kezzel teszteltem: felvettem egy foglalast 09:00-ra, majd megprobaltam ujra foglalni 09:00-ra.

- **Tanulság / érintett alapelv:** 
A tomb primitiv keresofuggvenyei (`indexOf`) helyett a keresofuggvenyeket (`some`) kell hasznalni.

## 2. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 3. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 4. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 5. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 6. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## Összegzés
- Mit tanultam: 
- Melyik alapelv sérült a leggyakrabban: 
