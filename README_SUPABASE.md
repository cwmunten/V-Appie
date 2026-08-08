# Vappie + Supabase (veilige overgang)

Deze versie blijft **altijd eerst lokaal opslaan** in dezelfde `localStorage` als de huidige Vappie. Supabase is optioneel. Zonder configuratie werkt de app daarom hetzelfde als voorheen.

## Supabase klaarzetten
1. Maak een Supabase-project.
2. Open **SQL Editor** en voer `supabase_setup.sql` uit.
3. Maak via **Authentication > Users** minimaal één gebruiker aan voor Team Verenigingen.
4. Deploy deze Vappie-versie op Vercel.
5. Open Vappie > icoon **Data & back-up** > **Supabase koppelen**.
6. Vul de **Project URL** en **Publishable key** in. Op oudere projecten werkt ook de **anon public key**. Gebruik nooit een Secret- of service_role-key.
7. Meld aan met de Supabase-gebruiker.
8. Kies bij de eerste synchronisatie **Lokale Vappie → Supabase**. Daarmee blijft de huidige dataset het startpunt.

Daarna worden wijzigingen eerst lokaal opgeslagen en vervolgens naar Supabase gestuurd. Iedere 2 minuten haalt Vappie de centrale dataset opnieuw op. Als Supabase niet bereikbaar is, blijven lokale gegevens staan en blijft Vappie bruikbaar.

## Belangrijk
Deze eerste koppeling synchroniseert bewust één complete Vappie-dataset. Dat is de minst ingrijpende manier om de bestaande app werkend te houden. Bij veel gelijktijdige bewerkingen kan later een tweede stap worden gemaakt naar aparte Supabase-tabellen voor verenigingen, diensten en jaren.
