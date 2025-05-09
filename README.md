MeinProjekt - GitHub Repository Setup und Workflow

1. GitHub Repository Setup

Repository erstellen:
1. Anmelden bei GitHub.
2. Klicke oben rechts auf "+" und wähle "New repository".
3. Namen "MeinProjekt", lasse die anderen Optionen unverändert.
4. Klicke auf "Create repository".
5. Notiere die Repository-URL:
   https://github.com/Stanzl86/MeinProjekt.git

2. SSH-Schlüssel erstellen

Überprüfen, ob ein SSH-Schlüssel existiert:
ls ~/.ssh/

Erstelle einen neuen:
ssh-keygen -t rsa -b 4096 -C "deine_email@beispiel.com"

Drücke ENTER für den Standard-Speicherort.
Passwort leer lassen.

Öffentlichen Schlüssel anzeigen:
cat ~/.ssh/id_rsa.pub

Kopiere den Schlüssel und füge ihn auf GitHub unter "Settings → SSH and GPG keys" ein.

3. Lokales Repository einrichten und Workflow

Repository klonen:
git clone git@github.com:Stanzl86/MeinProjekt.git
cd MeinProjekt

Git konfigurieren:
git config user.name "Konstantin Beckel"
git config user.email "konstantinbeckel@arcor.de"

Erste Datei erstellen & initial commit:
touch main.py
git add main.py
git commit -m "Initialer Commit"

Neuen Branch erstellen:
git checkout -b feature

Neue Datei hinzufügen & committen:
mkdir -p utils
touch utils/database.py
git add utils/database.py
git commit -m "Neue Funktion hinzugefügt"

Hauptdatei bearbeiten & committen:
echo "# Hauptdatei Code" >> main.py
git add main.py
git commit -m "Hauptdatei aktualisiert"

Zurück zum `master`-Branch wechseln:
git checkout master

Änderungen auf `master` committen:
echo "# Weitere Änderungen auf master" >> main.py
git add main.py
git commit -m "Hauptdatei aktualisiert"

`feature`-Branch in `master` mergen:
git merge feature

Falls ein Merge-Konflikt auftritt:
- Öffne `main.py` und löse den Konflikt manuell.
- Wähle die gewünschte Änderung und speichere die Datei.
- Führe dann aus:
  git add main.py
  git commit -m "Merge-Konflikt behoben"

4. Abgabe zur Bewertung

Dokumentation:
README.md erstellen:
touch README.md
Alle durchgeführten Schritte dokumentieren.
git add README.md
git commit -m "README Datei mit Dokumentation"

Repository auf GitHub pushen:
git push origin master


