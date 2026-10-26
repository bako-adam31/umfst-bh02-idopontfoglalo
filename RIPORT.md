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
*Commit link:* https://github.com/bako-adam31/umfst-bh02-idopontfoglalo/commit/1926ad68ca5d87c4ed57a0d1731b2a2f2cd46594
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Kezzel teszteltem a bongeszoben
- **Tanulság / érintett alapelv:** 
mindig figyelni kell a relacios operatorok pontos hasznalatara

## 3. hiba
- **Hiba leírása és reprodukálása:** 
A rogzitett idopontok nem idorendi sorrendben jelentek meg a listaban
- **Gyökérok (sor + magyarázat):** 
Az `app.js` 16. soraban a `foglalasok.sort()` fuggveny komparatora boole ertket adott vissza a vart szam helyett.
- **Javítás (commit link):** 
*Commit link:* https://github.com/bako-adam31/umfst-bh02-idopontfoglalo/commit/789c4a4a2b14e9de7f24772723b14cac838acd98
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Kezzel teszteltem: keszitettem egy 10:00-s es egy 08:30-as foglalast
- **Tanulság / érintett alapelv:** 
Az `Array.prototype.sort()` komparatoranak mindig szamot kell visszaadnia.

## 4. hiba
- **Hiba leírása és reprodukálása:** 
a beteg nevekent egy HTML kodreszletet adtak meg
- **Gyökérok (sor + magyarázat):** 
Az `app.js` 22. soraban a `render()` az `innerHTML` hasznalta a HTML osszeallitasara. A bongeszo a beirt szoveget ervenyes HTML tagkent ertelmezte es futtatta.
- **Javítás (commit link):** 
*Commit link:* https://github.com/bako-adam31/umfst-bh02-idopontfoglalo/commit/36a36d73aea7ee7ad22cc941d0264595adf1aadc
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
Felvettem egy foglalast az XSS tartalmazo nevvel. A nev szovegkent jelent meg az oldalon, a JavaScript kod nem futott le, es a hatterszin sem valtozott meg.
- **Tanulság / érintett alapelv:** 
Felhasznaloi bevitelt soha nem szabad kozvetlenul `innerHTML`-be illeszteni

## 5. hiba
- **Hiba leírása és reprodukálása:** 
Torles akciot billentyuzetrol nem lehetett fokuszba hozni
- **Gyökérok (sor + magyarázat):** 
Az `app.js` `render()` a `Törlés` elem egy nem interaktiv `<span>` tagkent lett letrehozva.
- **Javítás (commit link):** 
*Commit link:* https://github.com/bako-adam31/umfst-bh02-idopontfoglalo/commit/f770c0d5a5810d53b1262b23c722fb56771c7fa6
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
a Tab billentyuvel elerhetove valt a `Törlés` gomb
- **Tanulság / érintett alapelv:** 
Minden felhasznaloi action-hez szemantikus `<button>` elemet kell hasznalni

## 6. hiba
- **Hiba leírása és reprodukálása:** 
Sok (50+) foglalas eseten az oldal renderelese erezhetoen belassult
- **Gyökérok (sor + magyarázat):** 
Az `app.js` `render()` fuggvenye minden elem beszurasakor kozvetlenul modositotta az aktiv DOM-ot, valamint a ciklus minden egyes gombra  eseménykezelot regisztralt.
- **Javítás (commit link):** 
*Commit link:* 
- **Hogyan tesztelted (kézi tesztlépések, konzolos ellenőrzés vagy egységteszt):** 
generaltam 50 foglalast a konzolbol `foglalasok` tombbe, majd meghivtam a `render()` fuggvenyt es a DevTools Performanceben ellenoriztem a renderelesi idot
- **Tanulság / érintett alapelv:** 
DOM-epitesnel mindig memoriabeli kontenert kell hasznalni

## Összegzés
- Mit tanultam: A bongeszeros webalkalmazasok fejlesztesekor a dinamikus adatkezeles, a tipusegyezoseg, a biztonsagos bemenet-kezeles elleni vedelem, valamint a hatekony DOM-kezeles
- Melyik alapelv sérült a leggyakrabban: A korabbi kod nem a megfelelo tipusu fuggvenyeket es HTML elemeket hasznalta, ami serulekenyseghez, teljesitmenyromlashoz vezetett.
