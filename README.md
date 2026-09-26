# Șeptica online

Joc de Șeptica pentru 2–4 prieteni, în browser. Pagina e găzduită pe GitHub Pages,
iar mesele și mutările se sincronizează prin Firebase (planul gratuit ajunge din plin).

## 1. Firebase (o singură dată)
1. Intră pe https://console.firebase.google.com și creează un proiect (Google Analytics nu e necesar).
2. **Build → Authentication → Get started → Sign-in method → Anonymous → Enable.**
3. **Build → Firestore Database → Create database** (mod „production”, orice locație din Europa).
4. În Firestore, tab-ul **Rules**: înlocuiește tot cu conținutul din `firestore.rules` și apasă **Publish**.
5. **Project settings (rotița) → General → Your apps → iconița `</>`**: înregistrează o aplicație web
   și copiază obiectul `firebaseConfig`.
6. În `index.html`, înlocuiește valorile din `FIREBASE_CONFIG` cu cele copiate.

Cheia `apiKey` din config nu e secretă: e normal să fie publică. Protecția vine din regulile Firestore.

## 2. GitHub Pages
1. Creează un repository nou (public) pe GitHub, de exemplu `septica`.
2. Urcă fișierele `index.html`, `firestore.rules` și `README.md` (Add file → Upload files → Commit).
3. **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main`, folder `/ (root)` → Save.**
4. După 1–2 minute jocul e la `https://NUMELE-TAU.github.io/septica/`.
5. În Firebase, **Authentication → Settings → Authorized domains**, adaugă `NUMELE-TAU.github.io`.

## Cum se joacă
Unul creează o masă și le trimite celorlalți linkul și codul de 4 litere. Când s-au strâns 2–4 jucători,
gazda împarte cărțile. Fiecare browser e recunoscut automat, așa că la reîncărcarea paginii revii la aceeași masă
din lista „Mesele tale”. Modul „Exersează cu calculatorul” merge și fără Firebase.
