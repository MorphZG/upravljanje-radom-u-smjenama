---
date: 
tags:
  - webdev
  - coding
  - project
title: Web app za izradu rasporeda rada
type: project
URL: 
---

# Web app za izradu rasporeda rada

### 1. Postavljanje projekta i ovisnosti

- **Kreiranje projekta:**
  - Stvorite novi direktorij za projekt i inicijalizirajte dva poddirektorija: `client` za React aplikaciju i `server` za Node.js backend.
  - Inicijalizirajte `package.json` datoteku u korijenu projekta i dodajte potrebne ovisnosti: React, ReactDOM, Express, Mongoose (za interakciju s MongoDB), Nodemon (za automatsko ponovno pokretanje servera pri promjenama).
- **Postavljanje MongoDB baze:**
  - Instalirajte MongoDB i pokrenite bazu podataka.
  - Kreirajte bazu podataka za projekt i kolekcije za zaposlenike i rasporede.

### 2. Razvoj backend-a (Node.js, Express.js, MongoDB)

- **Model podataka:**
  - Definirajte Mongoose sheme za modele `Employee` i `Schedule`.
  - Svaki zaposlenik će imati ime, prezime, dostupnost i druge relevantne podatke.
  - Svaki raspored će sadržavati datum, popis zaposlenika i njihove smjene.
- **Rute:**
  - Kreirajte Express rute za:
	- Dohvaćanje svih zaposlenika
	- Dohvaćanje pojedinog zaposlenika
	- Kreiranje novog zaposlenika
	- Ažuriranje podataka o zaposleniku
	- Dohvaćanje svih rasporeda
	- Kreiranje novog rasporeda
	- Ažuriranje postojećeg rasporeda
	- Izračunavanje satnice za određeni raspored
	- Izvoz rasporeda u CSV formatu
- **Logika poslovnog procesa:**
  - Implementirajte logiku za:
	- Validaciju podataka primljenih od frontend-a
	- Spremanje podataka u MongoDB
	- Dohvaćanje podataka iz MongoDB
	- Izračunavanje satnice na temelju rasporeda i radnog vremena
	- Generiranje CSV datoteka s podacima o rasporedu

### 3. Razvoj frontend-a (React.js)

- **Komponente:**
  - Kreirajte React komponente za:
	- Unos zaposlenika
	- Unos radnog vremena
	- Prikaz rasporeda (tablica, kalendar)
	- Formu za filtriranje i pretraživanje rasporeda
	- Gumb za izvoz rasporeda
- **State management:**
  - Koristite React Hook ili state management biblioteku (npr. Redux) za upravljanje stanjem aplikacije (npr. trenutno prikazani raspored, podaci o zaposlenicima).
- **Interakcija s backend-om:**
  - Koristite `fetch` API ili biblioteku kao što je Axios za slanje HTTP zahtjeva na backend i dohvaćanje podataka.
- **Izgled:**
  - Koristite CSS ili CSS-in-JS biblioteku (npr. styled-components) za oblikovanje aplikacije.

### 4. Integracija frontend-a i backend-a

- **Pokretanje servera:** Pokrenite Node.js server.
- **Konfiguracija React aplikacije:** Konfigurirajte React aplikaciju da se poveže s backend API-jem.

### 5. Testiranje i optimizacija

- **Jedinični testovi:** Napisati jedinične testove za backend logiku i React komponente.
- **Integracijski testovi:** Testirati interakciju između frontend-a i backend-a.
- **Optimizacija performansi:** Optimizirati upite u bazu podataka i renderiranje React komponenti.

### Dodatne napomene

- **Autentifikacija:** Ako želite dodati autentifikaciju, možete koristiti biblioteke kao što su Passport.js.
- **Autorizacija:** Implementirajte mehanizme za kontrolu pristupa različitim dijelovima aplikacije.
- **Skalabilnost:** Razmislite o korištenju cloud platformi kao što su AWS, Google Cloud ili Azure za skaliranje aplikacije.
- **Sigurnost:** Zaštitite aplikaciju od uobičajenih sigurnosnih prijetnji.

---

## Frontend

Za dizajn frontenda aplikacije za izradu radnog rasporeda, možeš koristiti moderne web dizajn pristupe i komponente kako bi postigao preglednost i jednostavno korisničko iskustvo. Evo osnovnih koraka i preporuka za dizajn frontend-a aplikacije:

### 1. Postavljanje strukture layouta

*   **Header:** Sadrži navigaciju s poveznicama kao što su "Početna", "Zaposlenici", "Raspored" i "Izvještaji".
*   **Sidebar (po izboru):** Za opcije poput filtriranja, pretraživanja zaposlenika i brzo pristupanje različitim funkcijama.
*   **Glavni prikaz (Main Content):** Prikazuje informacije o rasporedima, zaposlenicima, ili omogućuje unos podataka o radnim smjenama.
*   **Footer:** Informacije poput autorskih prava ili brzih poveznica.

### 2. Odabir boja i fontova

*   Odaberi jednostavnu paletu boja s naglaskom na čitljivost i preglednost. Primjer: svijetle boje za pozadinu (poput svijetlosive ili bijele) i tamnije boje za tekst.
*   Koristi lako čitljive fontove, poput "Roboto" ili "Arial", koji su standardni za poslovne aplikacije.

### 3. Komponente

*   **Forma za unos zaposlenika:**
    *   Polja za unos imena, prezimena, dostupnosti i drugih potrebnih informacija.
    *   Gumbi za spremanje ili resetiranje podataka.
*   **Prikaz rasporeda:**
    *   **Tablica ili kalendar:** Omogućuje prikaz po danima, tjednima, ili mjesecima.
    *   Svaki dan prikazuje popis zaposlenika i njihove smjene.
    *   Dodaj boje za različite smjene kako bi ih vizualno odvojio.
*   **Filtar i pretraga:**
    *   Pretraživanje po imenu zaposlenika, smjeni, ili datumu.
    *   Filtar za prikaz samo određenih smjena, zaposlenika ili datuma.
*   **Gumb za izvoz rasporeda:**
    *   Omogućuje korisnicima preuzimanje rasporeda u CSV formatu.
*   **Notifikacije i potvrde:**
    *   Prikaz kratkih poruka (npr. „Uspješno spremljeno” ili „Pogreška”) pomoću modal prozora ili obavijesti (toasts).

### 4. Upravljanje stanjem aplikacije (state management)

*   Koristi `useState` i `useEffect` React Hookove za upravljanje lokalnim stanjem, kao što su trenutno prikazani raspored i podaci o zaposlenicima.
*   Za složenije stanje, kao npr. rad s više kolekcija zaposlenika i rasporeda, možeš koristiti Redux ili Context API.

### 5. Interakcija s backend-om

*   Koristi Axios ili `fetch` za dohvaćanje podataka s backend-a.
*   Implementiraj loading indikatore za vrijeme dok se podaci dohvaćaju ili šalju.
*   U slučaju pogrešaka (npr. ako dohvaćanje podataka ne uspije), prikaži poruku o grešci.

### 6. Responzivan dizajn (Responsive Design)

*   Koristi CSS grid i flexbox za prilagodljiv layout koji će omogućiti dobar prikaz na mobilnim uređajima.
*   Dodaj breakpoint-e kako bi se elementi prilagodili manjim zaslonima – na primjer, raspored se može prikazati u obliku kartica umjesto tablice na mobilnim uređajima.

### 7. CSS i biblioteke za stilizaciju

*   **Tailwind CSS:** Za brzu i jednostavnu stilizaciju pomoću utility klasa.
*   **Material-UI ili Ant Design:** Nude unaprijed definirane komponente kao što su tablice, kalendari, i forme koje možeš prilagoditi svojim potrebama.
*   **Styled-components:** Ako želiš koristiti CSS-in-JS pristup za bolju organizaciju stilova po komponentama.

### 8. Primjer komponenti s osnovnim CSS kodom

#### Primjer komponenta za unos zaposlenika (React + Tailwind CSS)

```jsx
// EmployeeForm.js
import React, { useState } from "react";

const EmployeeForm = ({ onSubmit }) => {
  const [name, setName] = useState("");
  const [surname, setSurname] = useState("");
  const [availability, setAvailability] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    onSubmit({ name, surname, availability });
  };

  return (
    <form onSubmit={handleSubmit} className="p-4 bg-white rounded shadow">
      <h2 className="text-lg font-semibold mb-4">Dodaj zaposlenika</h2>
      <label className="block mb-2">
        Ime:
        <input
          type="text"
          value={name}
          onChange={(e) => setName(e.target.value)}
          className="block w-full p-2 border rounded mt-1"
          required
        />
      </label>
      <label className="block mb-2">
        Prezime:
        <input
          type="text"
          value={surname}
          onChange={(e) => setSurname(e.target.value)}
          className="block w-full p-2 border rounded mt-1"
          required
        />
      </label>
      <label className="block mb-2">
        Dostupnost:
        <input
          type="text"
          value={availability}
          onChange={(e) => setAvailability(e.target.value)}
          className="block w-full p-2 border rounded mt-1"
          required
        />
      </label>
      <button type="submit" className="bg-blue-500 text-white p-2 rounded mt-4">
        Dodaj zaposlenika
      </button>
    </form>
  );
};

export default EmployeeForm;
```

---

## React router


