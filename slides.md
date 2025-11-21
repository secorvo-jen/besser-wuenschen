---
theme: default
title: LLM Prompting Intro
info: Einstieg in den Dialog mit Large Language Models
author: Kai Jendrian
colorSchema: dark
drawings:
  persist: false
transition: slide-left
mdc: true
fonts:
  sans: Acme
  serif: Acme
  mono: JetBrains Mono
#  fallbacks: false
#  sans: Special Elite
#  serif: Special Elite
#  sans: Barriecito
#  serif: Barriecito
---
<div class="text-center">
<div style="font-size: 300%;">
Workshop <span style="color: yellow">"Besser wünschen"</span>
</div>

<div class="h-12"></div>
<div class="flex flex-col gap-y-4">

<div style="font-size: 200%;">
<span style="color: grey;">TechniKA</span>
</div>

<i><span style="color: grey; font-size: 150%">Ein</span> <span style="color: orange; font-size: 150%">Einstieg</span> <span style="color: grey; font-size: 150%">in den konstruktiven Dialog mit LLMs</span></i>
</div>
<div class="h-12"></div>
<span style="color: red;">Kai Jendrian</span> (✉️ kai.jendrian@secorvo.de)
</div>

<!--

-->

---
layout: default
title: Alchemie
---
<img src="/assets/alchemy.jpg" style="display:block; margin:0 auto; width:50%; height:auto;" />
<div class="h-6"></div>
<v-clicks>
<div class="text-center" style="font-size: 110%;">
LLM-Prompting: Alchemie oder Wissenschaft?
</div>
</v-clicks>

---
layout: default
title: Fragen
---
<div class="text-center" style="font-size: 150%;">
Ein paar Fragen zum Warmwerden
</div>


<div class="text-center">
<v-clicks>

Wer von Euch nutzt KI-Chatbots?

Welche KI-Chatbots kennt Ihr?

Wofür nutzt Ihr KI-Chatbots?

Wie zufrieden seid Ihr mit den Ergebnissen?

</v-clicks>
</div>
---
layout: default
title: Grundlagen für einen effizienten Umgang mit Large Language Models (LLM)
---
<div class="text-center" style="font-size: 120%;">
Grundlagen für einen effizienten Umgang mit Large Language Models (LLM)</div>
<div class="h-6"></div>
<v-clicks>
<img src="/assets/sams_cover.jpg" style="display:block; margin:0 auto; width:55%; height:auto;" />
</v-clicks>
---
layout: default
title: Adam und Eva
---
<div class="text-center" style="font-size: 120%;">
Ein bisschen Theorie zum Einstieg - Adam und Eva der LLMs</div>
<div class="h-6"></div>
<div class="h-2"></div>
<img src="/assets/adam_eva.png" style="display:block; margin:0 auto; width:80%; height:auto;" />

---
layout: default
title: Fine Web
---
<img src="/assets/fine_web.png" style="display:block; margin:0 auto; width:100%; height:auto;" />
<div class="h-2"></div>
<div class="text-center">
<v-clicks>

Die Grundlage für Sprachmodelle ist ganz ganz viel Text.

(Große) Sprachmodelle heißen auch (Large) Language Model oder (L)LM.

Der [Fine-Web Datensatz](https://huggingface.co/spaces/HuggingFaceFW/blogpost-fineweb-v1) auf [Hugging Face](https://huggingface.co/) hat einen Umfang von ca. 44TB.

Eine Alternative dazu ist [Common Crawl](https://commoncrawl.org/).

</v-clicks>
</div>
---
layout: default
title: Tokenizing
---
<img src="/assets/tiktokenizer.png" style="display:block; margin:0 auto; width:50%; height:auto;" />
<div class="text-center">
<v-clicks>

LLMs arbeiten mit Tokens und nicht mit Wörtern. Texte werden in Token zerlegt.

GPT-4 hat ein Vokabular von ca. 100.000 Tokens.

Mehr Infos zu Tokens auf Youtube von [Chris Hay](https://youtu.be/NMoHHSWf1Mo). Ausprobieren kann man Tokenizing mit dem [TikTokenizer](https://tiktokenizer.vercel.app/).
</v-clicks>
</div>
<!--

-->
---
layout: default
title: Embedding

---
<img src="/assets/embedding_projector.png" style="display:block; margin:0 auto; width:50%; height:auto;" />
<div class="text-center">
<v-clicks>

Und eigentlich arbeiten LLMs auch nicht mit Token sondern Vektoren.

In GPT-3 ist jedes Token ein Vektor mit 12.288 Dimensionen. Spoiler: Schon 4 Dimensionen überfordern uns.

Vektoren, die nahe beieinander liegen, haben ähnliche Bedeutungen.

Man kann mit Embeddings "rechnen": `"König" - "Mann" + "Frau" ≈ "Königin"`

Einen Eindruck von einem fertigen Embedding kann man sich mit einem [Embedding Projector](https://projector.tensorflow.org/) verschaffen.

Noch mehr Details zu den Interna von LLMs finden sich bei [3blue1brown](https://www.youtube.com/watch?v=wjZofJX0v4M)
</v-clicks>
</div>
---
layout: default
title: LLM Visualization
---
<img src="/assets/llm_inspect.png" style="display:block; margin:0 auto; width:80%; height:auto;" />

<div class="text-center">
<v-clicks>

Ein LLM ist letztendlich eine ziemlich komplizierte mathematische Formel um das nächste Token vorherzusagen.

Vielleicht wagt Ihr einen [Blick unter die Haube](https://bbycroft.net/llm).

</v-clicks>
</div>
---
layout: default
title: Base Model
---
<img src="/assets/base_model_test.png" style="display:block; margin:0 auto; width:70%; height:auto;" />

<div class="text-center">
<v-clicks>

Ein Beispiel mit dem Base Model [Meta-Llama-3-8B](https://huggingface.co/meta-llama/Meta-Llama-3-8B)

Fällt Euch hier schon etwas auf?

</v-clicks>
</div>


---
layout: default
title: Wo stehen wir jetzt?
---
<div class="text-center" style="font-size: 150%;">
Wo stehen wir jetzt?
</div>


<div class="text-center">
<v-clicks>

Texte sind in Token zerlegt und das LLM hat die Texte "gelernt".

Token sind in einem komplexen Vektorraum angeordnet.

Token, die im Embedding nahe beeinander liegen haben Ähnlichkeiten.

Wir haben ein sogenanntes "Base Model".

Ein Base Model ist in der Lage, Texte auf Basis des gelernten Wissens
fortzusetzen.
Damit ist das "Pre Training" abgeschlossen.

Im nächsten Schritt muss das LLM lernen, sich wie ein Assistent zu verhalten.

Der nächste Schritt heißt "Supervised Fine Tuning" (SFT).


</v-clicks>
</div>
---
layout: default
title: Wie baut man einen Chat GPT
---
<div class="h-12"></div>
<div class="text-center">
<div style="font-size: 300%;">
Wie könnte man ein Base Model trainieren, damit es sich wie ein hilfreicher Assistent oder eine hilfreiche Assistentin verhält und uns Fragen beantwortet?
</div>
</div>



---
layout: default
title: Viele Lehrer für ein LLM
---
<img src="/assets/viele_lehrer.png" style="display:block; margin:0 auto; width:80%; height:auto;" />

<div class="text-center">
<v-clicks>

In der Praxis werden die Base Models beim SFT mit ganz vielen Beispieldialogen trainiert.

</v-clicks>
</div>
---
layout: default
title: SFT Trainingsdatensätze
---
<img src="/assets/open_assist.png" style="display:block; margin:0 auto; width:80%; height:auto;" />

<div class="text-center">
<v-clicks>

[OpenAssist](https://huggingface.co/datasets/OpenAssistant/oasst1/viewer) ist ein Beispiel für einen SFT-Trainingsdatensatz.

</v-clicks>
</div>
---
layout: default
title: Chatbot
---
<div class="text-center">
Und damit haben wir einen Chatbot:
</div>
<div class="h-4"></div>
<v-clicks>
<img src="/assets/chatbot.png" style="display:block; margin:0 auto; width:80%; height:auto;" />
</v-clicks>

---
layout: default
title: Chatbot
---

# Base Model vs. Chat Model

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

### Base Model:
```
Input: "Erkläre mir Schwerkraft"
```

```
Output: "Erkläre mir Schwerkraft in
einfachen Worten für Kinder.
Schwerkraft ist..."
```

→ Vervollständigt nur!

</v-clicks>
</div>
<div>
<v-clicks>

### Nach SFT (Chat Model):
```
User: "Erkläre mir Schwerkraft"
```

```
Assistant: "Gerne erkläre ich Dir
Schwerkraft! Schwerkraft ist eine
Kraft, die alle Objekte mit Masse..."
```

→ Versteht Anweisungen!

→ Arbeitet aber weiterhin als Textvervollständigung!

</v-clicks>

</div>
</div>

---
layout: default
title: Prompting
---
<div class="text-center" style="font-size: 200%; color: red">
GENUG THEORIE</div>

<v-clicks>

<div>
<div class="h-6"></div>
<img src="/assets/gemini_prompt.png" style="display:block; margin:0 auto; width:55%; height:auto;" />
<div class="h-6"></div>
<div class="text-center" style="font-size: 200%; color: yellow">
Auf ans Prompten!</div>
</div>

</v-clicks>

---
title: Prompting - Die Kunst des Wünschens
---


<div class="text-center text-2xl mt-8">

# 🎨 Prompting - Die Kunst des richtigen Wünschens

<v-clicks>

<div class="my-8">
<div class="grid grid-cols-2 gap-8">

<div class="border rounded p-6">
<div class="text-red-400 text-3xl mb-2">❌</div>
<div class="font-bold">Schlechter Prompt</div>
<div class="text-sm mt-2">"Schreib was über Hunde"</div>
</div>

<div class="border rounded p-6">
<div class="text-green-400 text-3xl mb-2">✅</div>
<div class="font-bold">Guter Prompt</div>
<div class="text-sm mt-2">"Schreibe einen kurzen Steckbrief über Golden Retriever für Kinder"</div>
</div>

</div>
</div>

## Im Folgenden: Ein paar **Prompting-Techniken** von einfach bis komplex

</v-clicks>

</div>
---
layout: default
---

<div class="text-center text-2xl mt-8">

# Was ist ein Prompt eigentlich?

<v-clicks>

- Dein Startschuss: Der Prompt ist alles, was Du der KI fütterst, um sie zum Leben zu erwecken.

- Mehr als nur Googeln: Du suchst nicht nach Antworten, Du baust sie. Dein Prompt ist der Bauplan in Deinen eigenen Worten.

- Volle Kontrolle: Du gibst den Ton an. Du setzt den Kontext, verteilst die Aufgaben und entscheidest, was am Ende rauskommt.
</v-clicks>

</div>
---
layout: default
---

# 📝 Level 1: Direkte Anweisungen (Zero-Shot)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?


Die **einfachste** Form des Promptings
- Klare, direkte Anweisung
- Keine Beispiele nötig
- Für Standard-Aufgaben

### Struktur:

```
"Anweisung" + "Optional: Details"
```

## 🎨 Beispiele:

```
"Übersetze ins Englische: Guten Morgen"

"Erkläre Photosynthese in 2 Sätzen"

"Schreibe ein Haiku über den Winter"
```

</v-clicks>

</div>

<div>

<v-clicks>

## 💡 Tipps für gute Anweisungen


### ✅ DO:
- Sei **spezifisch**: "Schreibe 3 Sätze" statt "Schreib was"
- Nenne **Format**: "als Liste", "als Tabelle"
- Definiere **Zielgruppe**: "für Kinder", "für Experten"

### ❌ DON'T:
- Zu vage: "Erzähl mir was über Tiere"
- Widersprüchlich: "Kurz, aber sehr detailliert"
- Mehrdeutig: "Mach das besser"

### 🎯 Übung:
**Verbessere:** "Schreib über Computer"

→ **Besser:** "Erkläre einem 10-Jährigen in 3 Sätzen, wie ein Computer funktioniert"

</v-clicks>

</div>

</div>

---
layout: default
title: Prompting Level 2 - One-Shot Learning
---

# 🎯 Level 2: One-Shot Learning (Ein Beispiel)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

Du gibst **ein Beispiel** für das gewünschte Format

### Warum?
- LLM versteht **Muster** aus Beispielen
- Besser als lange Erklärungen
- Für spezielle Formate/Stile

### Struktur:
```
Beispiel:
[Input] → [Output]

Jetzt Du:
[Neuer Input] →
```

</v-clicks>

</div>

<div>

<v-clicks>

## 🎨 Beispiele

### Stimmungstest:
```
Beispiel:
Satz: "Ich liebe diesen Film!"
Stimmung: Positiv

Jetzt Du:
Satz: "Das war langweilig."
Stimmung:
```

### Textstil:
```
Beispiel:
Normal: "Der Hund läuft schnell."
Poetisch: "Behände eilt der Vierbeiner dahin."

Jetzt Du:
Normal: "Es regnet stark."
Poetisch:
```

</v-clicks>

</div>
</div>

---
layout: default
title: Prompting Level 3 - Few-Shot Learning
---

# 🎓 Level 3: Few-Shot Learning (Mehrere Beispiele)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

Gib **2-5 Beispiele** für besseres Verständnis

### Warum mehrere Beispiele?
- LLM erkennt **konsistente Muster**
- Reduziert Missverständnisse
- Für komplexe Aufgaben

### Faustregel:
- **1 Beispiel**: Einfache Formate
- **2-3 Beispiele**: Standard-Aufgaben
- **4-5 Beispiele**: Komplexe Muster

</v-clicks>

</div>

<div>

<v-clicks>

## 📊 Beispiel: Klassifikation

```
Klassifiziere die Programmiersprache:

1. "print('Hallo')" → Python
2. "console.log('Hallo')" → JavaScript
3. "System.out.println('Hallo')" → Java
4. "echo 'Hallo'" → Bash

Jetzt Du:
5. "puts 'Hallo'" →
```

**Vorteil:** LLM sieht verschiedene Muster!

### 🧪 Experiment:
**Teste daheim mit 1 vs. 3 Beispielen:**
- Welche Genauigkeit?
- Welche Konsistenz?

</v-clicks>

</div>

</div>

---layout: center
layout: default
title: Prompting Level 4 - Chain-of-Thought (CoT)
---

# 🧠 Level 4: Chain-of-Thought (Gedankenkette)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

LLM soll **Denkschritte** zeigen

### Schlüssel-Phrase:
```
"Denke Schritt für Schritt"
"Erkläre Deinen Gedankengang"
```

### Warum wirkt das?
- LLM "überlegt" länger
- Fehler werden sichtbar
- Bessere Ergebnisse bei Logik/Mathe

### Wann verwenden?
- ✅ Mathematik, Logik-Rätsel
- ✅ Komplexe Entscheidungen
- ❌ Einfache Fakten

</v-clicks>

</div>

<div>

<v-clicks>

## 🔢 Beispiele

### Ohne CoT:
```
"Was ist 23 * 47?"
→ "1081" (oft falsch!)
```

### Mit CoT:
```
"Was ist 23 * 47? Denke Schritt für Schritt."

→ "Lass mich das ausrechnen:
1. 23 * 40 = 920
2. 23 * 7 = 161
3. 920 + 161 = 1081

Antwort: 1081"
```

### 🧩 Logik-Beispiel:
```
"Wenn alle A gleich B sind, und alle B
gleich C sind, was folgt daraus?
Denke Schritt für Schritt."
```

</v-clicks>

</div>

</div>

---
layout: default
title: Prompting Level 5 - Rollen-Prompting
---

# 🎭 Level 5: Rollen-Prompting (Persona)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

Weise dem LLM eine **Rolle/Identität** zu

### Struktur:
```
"Du bist [Rolle]. [Aufgabe]"
"Als [Experte], [mach etwas]"
```

### Warum?
- Ändert **Schreibstil**
- Aktiviert **Fach-Wissen**
- Passt **Komplexität** an

### Beliebte Rollen:
- Experte (Lehrer, Programmierer, ...)
- Zielgruppe (Kind, Anfänger, ...)
- Stil (Poet, Journalist, ...)

</v-clicks>

</div>

<div>

<v-clicks>

## 🎨 Beispiele

### Experten-Rolle:
```
"Du bist ein Physik-Professor. Erkläre
Quantenverschränkung für Studenten."
```

### Zielgruppen-Anpassung:
```
"Erkläre Photosynthese als wärst Du
ein begeisterter Biologie-Lehrer für
8-Jährige."
```

### Stil-Änderung:
```
"Du bist Shakespeare. Schreibe einen
Tweet über Programmieren."
```

### 💡 Kombiniere mit anderen Techniken:
```
"Du bist Mathe-Lehrerin. Löse 47*23
Schritt für Schritt für einen Schüler."
```

</v-clicks>

</div>

</div>

---
layout: default
title: Prompting Level 6 - System-Prompts
---

# ⚙️ Level 6: System-Prompts (Globale Anweisungen)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

**Grund-Einstellungen** für das gesamte Gespräch

### Unterschied:
```
System-Prompt: Grundverhalten
User-Prompt: Spezifische Aufgabe
```

### System-Prompt definiert:
- 🎭 Basis-Rolle
- 📏 Output-Regeln
- 🚫 Einschränkungen
- 🎨 Stil-Vorgaben

### In APIs:
```python
{
  "system": "Du bist hilfsbereit...",
  "user": "Erkläre Python"
}
```

</v-clicks>

</div>

<div>

<v-clicks>

## 📝 Beispiele

### Standard-System-Prompt:
```
"Du bist ein hilfreicher, ehrlicher und
harmloser KI-Assistent."
```

### Spezialisierter System-Prompt:
```
"Du bist ein Python-Tutor für Anfänger.
- Erkläre alles einfach
- Gib immer Beispiel-Code
- Verwende Emojis
- Antworte auf Deutsch
- Nie länger als 5 Sätze"
```

### Einschränkungen:
```
"Du bist Mathe-Helfer.
- Gib NIE direkt die Lösung
- Stelle Rückfragen
- Gib nur Hinweise"
```
</v-clicks>

</div>

</div>

---
layout: default
title: Prompting Level 7 - Kontext-Management
---

# 📚 Level 7: Kontext-Management (RAG-Prinzip)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist Kontext?

Alle **Informationen**, die das LLM sieht:
- Bisherige Nachrichten
- Eingefügte Dokumente
- System-Anweisungen

### Kontext-Fenster:
```
GPT-4: ~128k Token (~96k Wörter)
Claude: ~200k Token (~150k Wörter)
Gemini: ~1M Token (~750k Wörter)
```

### Wichtig:
- Kontext = Kosten 💰
- Kontext = Geschwindigkeit
- Mehr Kontext nicht immer bessere Antwort

</v-clicks>

</div>

<div>

<v-clicks>

## 🎯 Kontext richtig nutzen

### RAG (Retrieval Augmented Generation):
```
1. Finde relevante Infos
2. Füge sie dem Prompt hinzu
3. Stelle die Frage

"Hier ist der Artikel: [TEXT]

Beantworte basierend auf dem
Artikel: Wann wurde...?"
```

### ⚠️ Context Engineering:
```
✅ Relevante Infos zuerst
✅ Strukturiere mit Markdown
✅ Klare Trennungen
❌ Zu viel unwichtiger Text
❌ Redundante Informationen
```

### 📖 Vertiefung:
🔗 [Context Engineering Guide](https://www.promptingguide.ai/guides/context-engineering-guide)

</v-clicks>

</div>

</div>

---
layout: default
title: Kontext-Strategie - Best Practices
---

# 🎯 Kontext-Strategie: Best Practices

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Guter Kontext-Aufbau

### Struktur-Template:
```markdown
## Kontext:
[Relevante Hintergrund-Infos]

## Daten:
[Spezifische Daten/Dokumente]

## Aufgabe:
[Was soll gemacht werden?]

## Format:
[Wie soll das Ergebnis aussehen?]
```

### Warum strukturieren?
- LLM findet Infos schneller
- Weniger Verwirrung
- Bessere Ergebnisse

</v-clicks>

</div>

<div>

<v-clicks>

## 📊 Beispiel: Dokument-Analyse

### ❌ Schlechter Prompt:
```markdown
Hier ist ein Text [5000 Wörter]
Was ist wichtig?
```

### ✅ Guter Prompt:
```markdown
## Dokument:
[Text]

## Aufgabe:
Extrahiere die 3 Hauptaussagen über
Klimawandel.

## Format:
- Aussage 1: [...]
- Aussage 2: [...]
- Aussage 3: [...]

## Kontext:
Das Dokument ist für eine Schulpräsentation.
```
</v-clicks>

</div>

</div>

---
layout: default
title: Prompting Level 8 - Meta-Prompting
---

# 🔄 Level 8: Meta-Prompting (Selbst-Verbesserung)

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

<v-clicks>

## Was ist das?

LLM **verbessert seine eigenen Antworten**

### Techniken:
1. **Self-Critique**: "Prüfe Deine Antwort"
2. **Iteration**: "Verbessere Deine Antwort"
3. **Reflexion**: "Was könnte falsch sein?"

### Beispiel-Flow:
```
User: [Frage]
→ LLM: [Antwort]
→ User: "Prüfe auf Fehler"
→ LLM: [Korrigierte Antwort]
```

</v-clicks>

</div>

<div>

<v-clicks>

## 🧪 Praktische Beispiele

### Self-Critique:
```
"Erkläre Quantencomputer.

Prüfe jetzt Deine Erklärung:
1. Ist sie korrekt?
2. Ist sie verständlich?
3. Fehlt etwas Wichtiges?
Korrigiere falls nötig."
```

### Iterative Verbesserung:
```
"Schreibe einen Werbetext für
eine App.

Jetzt:
1. Bewerte den Text (1-10)
2. Identifiziere Schwächen
3. Schreibe eine bessere Version"
```

### 🎯 Tipp: Kombiniere mit CoT!

</v-clicks>

</div>

</div>

---
layout: center
title: Zusammenfassung Prompting-Techniken
---

# 📋 Prompting-Techniken: Zusammenfassung

<div class="text-sm">

| Level | Technik | Wann nutzen? | Komplexität |
|-------|---------|--------------|-------------|
| 1️⃣ | **Zero-Shot** | Standard-Aufgaben, klare Anweisungen | ⭐ |
| 2️⃣ | **One-Shot** | Spezielle Formate zeigen | ⭐⭐ |
| 3️⃣ | **Few-Shot** | Konsistente Muster vermitteln | ⭐⭐ |
| 4️⃣ | **Chain-of-Thought** | Mathe, Logik, komplexe Probleme | ⭐⭐⭐ |
| 5️⃣ | **Rollen-Prompting** | Stil/Expertise anpassen | ⭐⭐ |
| 6️⃣ | **System-Prompts** | Grundverhalten festlegen | ⭐⭐⭐ |
| 7️⃣ | **Kontext-Management** | Mit Dokumenten/Daten arbeiten | ⭐⭐⭐⭐ |
| 8️⃣ | **Meta-Prompting** | Höchste Qualität bei komplexen Aufgaben | ⭐⭐⭐⭐⭐ |

</div>

<v-click>

<div class="text-center mt-8 text-xl">
💡 **Kombination** verschiedener Techniken = Beste Ergebnisse!
</div>

</v-click>

---
layout: center
title: LLMs als Lernpartner
---

# 🤖 LLMs als Lernpartner: Best Practices

<div class="text-sm">

| # | Prinzip | Wie nutzen? | Achtung! |
|---|---------|-------------|----------|
| 1️⃣ | **Der Assistent** | Für Ideen, Gliederungen & Entwürfe | ⚠️ Macht Fehler & halluziniert |
| 2️⃣ | **Output-Prüfung** | Fakten checken & Quellen suchen | 🔍 Wirkt glaubwürdig, oft falsch |
| 3️⃣ | **Denkpartner** | "Erkläre mir..." statt "Löse für mich..." | 🧠 Copy & Paste verhindert Lernen |
| 4️⃣ | **Datenschutz** | Anonyme Aufgabenstellungen nutzen | 🛡️ Keine Namen oder privaten Daten! |
| 5️⃣ | **Schreibstil** | Feedback zu eigenen Texten einholen | ✍️ Behalte Deine eigene Stimme |

</div>

<v-click>

<div class="text-center mt-8 text-xl">
💡 **Merke:** Die KI ist der Co-Pilot, Du bist der Pilot!
</div>

</v-click>
---
layout: default
title: Bonus - LLM Hacking
---

# 🔓 Bonus: LLM Hacking & "Prompt Injection"


<div class="grid grid-cols-2 gap-6 mt-4">

<div>
<img src="/assets/gandalf.png" class="rounded-lg shadow-lg border border-gray-600 opacity-90" alt="Gandalf Interface" />
</div>

<div>
<div class="ml-8">

### Was ist "Prompt Injection"?
Der Versuch, die Sicherheitsregeln ("System Prompts") einer KI durch geschickte Eingaben zu umgehen.

- **Ziel:** Die KI dazu bringen, verbotene Dinge zu tun (z.B. Passwörter verraten).
- **Warum relevant?** Zeigt Sicherheitslücken aktueller Modelle auf.

<div class="mt-8 p-4 bg-red-900/20 border border-red-500/30 rounded-lg">
  <h3 class="text-xl text-white m-0">🧙‍♂️ Challenge: Gandalf</h3>
  <p class="text-sm mt-2 mb-2 opacity-80">
    Trainiere Deine Skills ("Red Teaming"). Deine Mission: Entlocke Gandalf das Passwort!
  </p>
  <a href="https://gandalf.lakera.ai/gandalf" class="font-mono text-blue-400 hover:text-blue-300">
    👉 gandalf.lakera.ai/gandalf
  </a>
</div>

</div>
</div>
</div>
---
layout: default
title: Weiterführende Quellen
---

# 📚 Futter fürs Gehirn: Weiterführende Quellen

<div class="grid grid-cols-2 gap-6 mt-4">

<div>

### 🎥 Verstehen & Staunen

- **[Die Maus: Wie schreibt KI?](https://kinder.wdr.de/tv/die-sendung-mit-der-maus/av/wie-schreibt-eine-ki-texte-100.html)**
  <br><span class="text-sm opacity-70 italic">"Erklärt es oft besser als Informatik-Professoren. Kein Witz."</span>

- **[3blue1brown (Transformers)](https://www.youtube.com/watch?v=wjZofJX0v4M)**
  <br><span class="text-sm opacity-70 italic">"Für alle, die Mathe nur mögen, wenn es schön tanzt. Visuell brillant."</span>

- **[Andrej Karpathy: Deep Dive](https://www.youtube.com/watch?v=7xTGNNLPyMI&t=18s)**
  <br><span class="text-sm opacity-70 italic">"Der Endgegner. Wirkt wie ein Semesterstudium in einem Video. Nur für Mutige."</span>

- **[Prompt Engineering Guide](https://www.promptingguide.ai/)**
  <br><span class="text-sm opacity-70 italic">"Die Bibel. Trocken wie Knäckebrot, aber extrem nahrhaft."</span>

</div>
<div>

### 🛠️ Ausprobieren & Meistern

- **[LM Arena (Chatbot Arena)](https://lmarena.ai/)**
  <br><span class="text-sm opacity-70 italic">"Battle Royale der KIs. Du chattest mit zwei anonymen Modellen und kürst den Sieger."</span>

- **[Teachable Machine](https://teachablemachine.withgoogle.com/)**
  <br><span class="text-sm opacity-70 italic">"Der 'Aha-Effekt'. Trainiere Deine eigene KI mit der Webcam. Ohne Code."</span>

- **[Hugging Face Playground](https://huggingface.co/playground)**
  <br><span class="text-sm opacity-70 italic">"Der Abenteuerspielplatz für Open-Source Modelle."</span>

- **[Soekia Chat](https://www.soekia.ch/gpt.html)**
  <br><span class="text-sm opacity-70 italic">"Datenschutzfreundlich. Perfekt, um nicht gleich seine Seele zu verkaufen."</span>

- **[Anthropic](https://docs.claude.com/) & [OpenAI Guides](https://academy.openai.com/)**
  <br><span class="text-sm opacity-70 italic">"Kochrezepte vom Chefkoch persönlich. RTFM lohnt sich hier."</span>

</div>
</div>
---
layout: center
---

<div class="flex flex-col items-center text-center">
  <div class="text-5xl mb-6 text-blue-400">
    📸
  </div>

  <h1 class="mb-12">Bildnachweis</h1>

  <div class="bg-gray-800/80 p-10 rounded-xl border border-gray-700 max-w-3xl backdrop-blur-sm">
    <div class="text-2xl text-gray-300 leading-relaxed">
      Alle Bilder in dieser Präsentation wurden generiert mit:
    </div>
    <div class="text-4xl font-bold mt-6 bg-gradient-to-r from-yellow-400 to-orange-500 bg-clip-text text-transparent">
      <a href="https://gemini.google/overview/image-generation/">Google Nano Banana</a>
    </div>
    <div class="mt-8 text-gray-500 italic text-lg">
      (Ausnahme: Cover des Buches "Das Sams")
    </div>
  </div>
</div>