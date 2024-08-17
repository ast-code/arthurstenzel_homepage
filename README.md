# Arthur Stenzel's Academic Homepage

Willkommen auf meiner persönlichen akademischen Homepage, die mit dem Hugo Academic Theme erstellt wurde! 🎉 Hier kannst du meine neuesten Publikationen durchstöbern und mehr über meine Lehrtätigkeiten erfahren. 🚀  
Die Seite wird über Netlify live geschaltet. Direkt zur Homepage geht es hier: [https://arthurstenzel-main.netlify.app/](https://arthurstenzel-main.netlify.app/)

In dieser Readme wird zuerst die Ordnerstruktur von Hugo erklärt und dann wird auf Details eingegangen.

## Ordnerstruktur von Hugo

Um die Struktur und Anpassungsmöglichkeiten deiner Hugo-Website besser zu verstehen, hier eine kurze Erklärung der wichtigsten Verzeichnisse:

- **`/content/`**: Hier liegen alle Inhalte deiner Seite, z. B. Blogposts, Seiten, Publikationen. Neue Inhalte werden hier als Markdown-Dateien organisiert.
  - **`/publication/`**: In diesem Unterverzeichnis legst du alle deine Publikationen ab. Jeder Ordner innerhalb dieses Verzeichnisses repräsentiert eine einzelne Publikation.
  - **`/teaching/`**: Enthält Inhalte, die mit dem Bereich "Teaching" verbunden sind. Hier kannst du Lehrveranstaltungen und Materialien verwalten.

- **`/layouts/`**: In diesem Verzeichnis liegen die Vorlagen (Templates), die bestimmen, wie deine Inhalte angezeigt werden. Wenn du das Design oder Layout ändern möchtest, bearbeite oder erstelle Dateien in diesem Verzeichnis.
  - **`/partials/`**: Enthält wiederverwendbare Teile von Templates, die auf verschiedenen Seiten eingebunden werden, z. B. Kopf- oder Fußzeilen.

- **`/static/`**: Alle Dateien in diesem Ordner werden unverändert in den `public`-Ordner kopiert. Hier liegen z. B. Bilder, PDFs, CSS- oder JavaScript-Dateien.

- **`/assets/`**: Hier kannst du Dateien ablegen, die Hugo während des Builds verarbeitet, wie z. B. SCSS-Dateien oder JavaScript-Module. Diese Dateien können komprimiert, kombiniert oder anderweitig verarbeitet werden, bevor sie in den `static`-Ordner kopiert werden.

- **`/data/`**: Enthält strukturierte Daten im YAML-, JSON- oder TOML-Format, die du in deinen Templates verwenden kannst. Beispielsweise könntest du hier eine Liste von Personen oder Projekten ablegen.

- **`/config/`**: Hier liegen die Konfigurationsdateien für deine Seite, meist in Form von `config.yaml`, `config.toml` oder `config.json`. Diese Dateien steuern allgemeine Einstellungen deiner Website wie Seitentitel, Sprachoptionen und Taxonomien.

Diese Struktur macht Hugo flexibel und leistungsfähig, da sie es dir erlaubt, Inhalt und Layout klar voneinander zu trennen und so Anpassungen einfach und effizient vorzunehmen.

### 1. Neue Publikation hinzufügen

Um ein neues Paper hinzuzufügen, gehe folgendermaßen vor:

1. **Neuen Ordner erstellen:** Erstelle einen neuen Ordner im Verzeichnis `/content/publication/`.
2. **Markdown-Datei erstellen:** Erstelle eine neue Markdown-Datei im neuen Ordner, z. B. `index.md`.
3. **Front Matter anpassen:** Fülle die `index.md` mit den entsprechenden Metadaten (Titel, Datum, Autoren, etc.). Hier ist ein Beispiel:

    ```yaml
    ---
    title: "Titel der Publikation"
    authors: 
        - with XYZ
    date: '2021-08-01T00:00:00Z'
    doi: '10.1016/j.jacceco.2021.101406'
    publication_types: ["Publication"] # Möglichkeiten sind hier: "Publication", "Working Paper" oder "Professional Publication"
    publication: "Journal of Accounting and Economics, 72(1) "
    publication_short: "J. Account. Econ."
    abstract: "Lorem Ipsum Dolor Sit amet"
    youtube_link: 'https://www.youtube.com/watch?v=SEPEqh_kFV8'
    tags: 
        - Tax Avoidance
    ---
    ```

4. **Optional: Weitere Dateien hinzufügen:** Füge zusätzliche Dateien wie PDF-Versionen oder BibTeX-Einträge in denselben Ordner hinzu.

### 2. Bereich "Teaching" anpassen

Um den Bereich "Teaching" zu aktualisieren:

1. **`_index.md` bearbeiten:** Gehe zum Verzeichnis `content` und öffne die Datei `_index.md`.
2. **Anpassungen vornehmen:** Passe den Inhalt an, um neue Kurse, Workshops oder Lehrmaterialien hinzuzufügen.

    ```yaml
    ---
    title: "Teaching"
    courses:
      - name: "Kurs 1"
        free_text: "Beschreibung von Kurs 1."
      - name: "Kurs 2"
        free_text: "Beschreibung von Kurs 2."
    ---
    ```

### 3. About-Widget aktualisieren

Um das About-Widget zu aktualisieren, gehe folgendermaßen vor:

1. **Konfigurationsdatei öffnen:** Gehe in das Verzeichnis `/content/admin` und öffne die Datei `_index.md`.
2. **Anpassungen vornehmen:** Passe die erforderlichen Abschnitte an.

### 3. Contact-Widget aktualisieren

Um das Contact-Widget zu aktualisieren, gehe folgendermaßen vor:

1. **Konfigurationsdatei öffnen:** Gehe in das Verzeichnis `/content/` und öffne die Datei `_index.md`.
2. **Contact-Widget-Sektion finden:** Scrolle ganz nach unten zu dem Abschnitt, der das `contact`-Widget definiert.
3. **Änderungen vornehmen:** Passe die erforderlichen Zeilen an.

### 4. Deployment

Nach den Änderungen musst du die Seite erneut deployen, damit sie live geschaltet wird.

Sobald die Änderungen gepusht sind, wird das Deployment automatisch auf Netlify ausgelöst.

### 5. Offizielle Dokumentation

The Hugo **Academic Resumé Template** empowers you to easily create your job-winning online resumé, showcase your academic publications, and create online courses or knowledge bases to grow your audience.

️**Trusted by 250,000+ researchers, educators, and students.** Highly customizable via the integrated **no-code, Hugo Blox Builder**, making every site truly personalized ⭐⭐⭐⭐⭐

Easily write technical content with plain text Markdown, LaTeX math, diagrams, RMarkdown, or Jupyter, and import publications from BibTeX.

[Check out the latest demo](https://academic-demo.netlify.app/) of what you'll get in less than 10 minutes, or [get inspired by our academics and research groups](https://hugoblox.com/creators/).

The integrated [**Hugo Blox Builder**](https://hugoblox.com) and CMS makes it easy to create a beautiful website for free. Edit your site in the CMS (or your favorite editor), generate it with [Hugo](https://github.com/gohugoio/hugo), and deploy with GitHub or Netlify. Customize anything on your site with widgets, light/dark themes, and language packs.

- 👉 [**Get Started**](https://hugoblox.com/templates/)
- 📚 [View the **documentation**](https://docs.hugoblox.com/)
- ⬇️ **Automatically import your publications from BibTeX** with the [Hugo Academic CLI](https://github.com/GetRD/academic-file-converter)
- 💡 [Suggest an improvement](https://github.com/HugoBlox/hugo-blox-builder/issues)
- ⬆️ **Updating?** View the [Update Guide](https://docs.hugoblox.com/reference/update/) and [Release Notes](https://github.com/HugoBlox/hugo-blox-builder/releases)
