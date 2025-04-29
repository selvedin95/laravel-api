# Laravel Customers & Invoices API

Ovo je API aplikacija napravljena u Laravelu koja omogućava rad sa korisnicima (customers) i fakturama (invoices), uključujući autentifikaciju pomoću Laravel Sanctum-a.

## ✅ Zahtjevi

-   PHP >= 8.1
-   Composer
-   MySQL ili druga podržana baza
-   Laravel >= 10

---

## 🚀 Instalacija

1. **Kloniraj repozitorij:**

    ```bash
    git clone https://github.com/selvedin95/laravel-api
    cd laravel-api

    ```

2. **Instaliraj PHP zavisnosti:**
   composer install

3. **Kopiraj .env fajl i generiši ključ aplikacije:**
   cp .env.example .env
   php artisan key:generate

4. **Podesi .env fajl (baza, e-mail itd.):**
   DB_DATABASE=laravel_api
   DB_USERNAME=root
   DB_PASSWORD=

5. **Migriraj bazu podataka:**
   php artisan migrate

6. **Pokreni development server:**
   php artisan serve


🛠 Kreiranje Admin korisnika i tokena

Da bi aplikacija radila ispravno, kreiraj admin korisnika i generiši API tokene:

Otvori u browseru:
http://localhost:8000/

Nakon što otvoriš ovu rutu:

- Kreira se korisnik admin@admin.com ako ne postoji

- Prijavljuje se

- Generišu se 3 tokena:

 - admin-token – (create, update, delete)

 - update-token – (create, update)

 - basic-token – (samo read)

🔐 Autentifikacija

Svi API pozivi zahtijevaju Bearer token:
Authorization: Bearer <your-token>

📬API Rute

Metoda                  Ruta                        Opis
GET                     /api/v1/customers           Lista korisnika (auth)
POST                    /api/v1/customers           Kreiranje korisnika (auth)
GET                     /api/v1/invoices            Lista faktura (auth)
POST                    /api/v1/invoices/bulk       Masovno dodavanje faktura
