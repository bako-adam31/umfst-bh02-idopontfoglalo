# A rakoncátlan időpontfoglaló – hibariport

Repó: https://github.com/<bako-adam31>/umfst-bh02-idopontfoglalo
Készítette: <Bako Adam-Attila>, <INFO LM>

## 1. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
Az `app.js` 12. soraban a `foglalt(ido)` fuggveny a `foglalasok.indexOf(ido)` metodust hivta meg. Mivel a `foglalasok` tombben objektumok (`{ nev, ido }`) vannak tarolva, a sima sztring keresese mindig `-1` erteket adott vissza,
- **Javítás (commit link):** 
*Commit link:* https://github.com/bako-adam31/umfst-bh02-idopontfoglalo/commit/773a36400ba41965877e549cfbf722d14b1c40d5
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Kezzel teszteltem: felvettem egy foglalast 09:00-ra, majd megprobaltam ujra foglalni 09:00-ra.

- **Tanulság / érintett alapelv:** 
A tomb primitiv keresofuggvenyei (`indexOf`) helyett a keresofuggvenyeket (`some`) kell hasznalni.

## 2. hiba
- **Hiba leírása és reprodukálása:** 
beallitott 8 fos napi limit ellenere a rendszer engedte a 9. beteg regisztraciojat is
- **Gyökérok (sor + magyarázat):** 
Az `app.js` 35. soraban a feltetel hibasan `foglalasok.length > MAX_NAPI` volt. A 8. elemnel a `8 > 8` feltetel hamis eredmenyt adott, igy a 9. elem is bekerult a tombbe.
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Kezzel teszteltem a bongeszoben
- **Tanulság / érintett alapelv:** 
mindig figyelni kell a relacios operatorok pontos hasznalatara

## 3. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 4. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 5. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## 6. hiba
- **Hiba leírása és reprodukálása:** 
- **Gyökérok (sor + magyarázat):** 
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
- **Tanulság / érintett alapelv:** 

## Összegzés
- Mit tanultam: 
- Melyik alapelv sérült a leggyakrabban: 
