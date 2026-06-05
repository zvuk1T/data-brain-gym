# Captain's Log — Stardate 20260531
**Date:** 31 May 2026
**Project:** data-brain-gym
**Session:** #2 — Environment Configuration

---

## 🎯 SESSION GOAL

Verify that the shared Python virtual environment exists and configure VS Code to use it for this workspace.

---

## ✅ WHAT WE ACCOMPLISHED TODAY

- Confirmed that the shared `.venv` exists at `/Users/zeal.v/Desktop/vs_code/.venv` (Python 3.11.11)
- Created `.vscode/settings.json` to register the shared `.venv` as the default Python interpreter for this workspace

### `.vscode/settings.json`
```json
{
  "python.defaultInterpreterPath": "/Users/zeal.v/Desktop/vs_code/.venv/bin/python",
  "python.analysis.typeCheckingMode": "off"
}
```

---

## 🧠 DECISIONS MADE

- One shared `.venv` for all projects under `vs_code/` — no need to create a new one per project
- Exception: if a project becomes very large or has specific/conflicting dependencies, it gets its own `.venv` inside its own folder
- `.vscode/settings.json` is the mechanism that tells VS Code which interpreter to use per workspace

---

## 🧩 BONUS — Kernel / Interpreter Terminology

Naučili smo razliku između termina koji se koriste u VS Codeu:

| Pojam | Šta znači |
|---|---|
| **Python interpreter** | Konkretni Python executable koji pokreće kod |
| **Virtual environment (.venv)** | Izolovano okruženje s vlastitim paketima |
| **Kernel** | Termin koji Jupyter koristi — jezgro koje izvršava ćelije u `.ipynb` fajlovima |
| **Kernel picker / interpreter selector** | Dropdown u VS Codeu gdje biraš koji Python/kernel koristiti |

**Pravilo:**
- Za `.ipynb` fajlove → biraš **kernel** (gornji desni ugao notebooka)
- Za `.py` fajlove → biraš **interpreter** (donji desni ugao u status baru)
- Oboje pokazuju na isti `.venv`

**Tačan kernel/interpreter koji koristimo:**
```
.venv (3.11.11) (Python 3.11.11)  ~/Desktop/vs_code/.venv/bin/python  Virtual Env
```

---

## 🔜 NEXT STEP

1. Migrate manufacturing-process content to `sql/problems/manufacturing-process/`
2. Update `repo-architecture.md` in `know-thyself-data`
3. Archive/delete `mock-interviews` and `manufacturing-process-sql-analysis` repos on GitHub

---

## 📝 NOTES

- `python.defaultInterpreterPath` in `.vscode/settings.json` is workspace-local — it overrides any global VS Code setting for this project only
- The shared venv path: `/Users/zeal.v/Desktop/vs_code/.venv/bin/python`
