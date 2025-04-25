# 🔧 Ollama installeren op Windows via Chocolatey + DeepSeek-Coder

Met Chocolatey kun je Ollama snel en eenvoudig installeren op Windows.

---

## 🧠 Conclusie vooraf: Welk model past bij jouw systeem?

Op basis van je systeeminformatie (Intel i5-1135G7, 8 GB RAM, geen dedicated GPU) raden we aan om **DeepSeek-Coder 1.3B** te gebruiken. Dit model:

- Is licht genoeg voor jouw systeem (3–5 GB modelgrootte)
- Draait op CPU, zonder zware GPU-eisen
- Past binnen je RAM-limiet, zolang andere zware apps gesloten zijn

Vermijd grotere modellen zoals 6.7B of 33B, deze zijn te zwaar voor je huidige setup.

---

## ✅ Stap 1: Installeer Chocolatey (als je dat nog niet hebt)

Open PowerShell **als Administrator** en voer dit commando uit:
```ps1
Set-ExecutionPolicy Bypass -Scope Process -Force; `
[System.Net.ServicePointManager]::SecurityProtocol = `
[System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
---

## ✅ Stap 2: Installeer Ollama

Na installatie van Chocolatey, installeer je Ollama met:

```ps1
choco install ollama
```
Chocolatey downloadt en installeert Ollama automatisch.

---

## 🔄 Updaten van Ollama

Als je Ollama in de toekomst wilt bijwerken naar de nieuwste versie:
```
choco upgrade ollama
```
---

## 🚀 DeepSeek-Coder draaien met Ollama

Na installatie kun je het DeepSeek-Coder model downloaden en draaien met:

```ps1
ollama pull deepseek-coder:1.3b  
ollama run deepseek-coder:1.3b
```

Dit opent een interactieve prompt waarin je codegerelateerde vragen kunt stellen.

---

## 📚 Extra: GUI met Open WebUI (optioneel)

Wil je een webinterface gebruiken? Installeer Open WebUI met Docker:

```ps1
docker run -d -p 3000:3000 -v open-webui:/app/backend/data --name open-webui --restart=always ghcr.io/open-webui/open-webui:main
```
Daarna kun je de interface openen op:  
http://localhost:3000

---

## ℹ️ Meer info

- Chocolatey package: https://github.com/splch/ollama-chocolatey-package  
- Ollama site: https://ollama.com