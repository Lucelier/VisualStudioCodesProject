# Storyplan: Titel deines Spiels

## Szenenübersicht
- S1: Dwelling Neglected

---

## Szene: S1 – Dwelling Neglected

**Description**  
You wake up. In a neglected dwelling. At first, you think it's a dream. But when you touch the edge of your bed, you realise: it is no dream. It is pure reality.You see the dark atmosphere around you. The windows in your room are black, and you can't see outside. You don't know where you are. Slowly, you stand up.

**Optionen:**
1. **Tür öffnen**
   - **Konsequenz:** Eine Monstergestalt springt heraus → Kampf beginnt
   - **Folge-Szene:** S2A
   - **Flags gesetzt:** `monster_angegriffen = true`
2. **Fenster durchsuchen**
   - **Konsequenz:** Du findest einen alten Schlüssel
   - **Folge-Szene:** S2B
   - **Flags gesetzt:** `hat_schluessel = true`
3. **Weg zurückgehen**
   - **Konsequenz:** Du gehst zurück in den Wald, verpasst die Hütte
   - **Folge-Szene:** S3 (alternativer Weg)
   - **Flags gesetzt:** `hutze_verpasst = true`

---

## Szene: S2A – Kampf mit Monster
**Ort:** Alte Hütte  
**Charaktere:** Spieler, Monster  
**Ziel der Szene:** Überleben oder Flucht

**Beschreibung:**  
Das Monster greift dich an, du musst kämpfen oder fliehen.

**Optionen:**
1. **Kämpfen**
   - **Konsequenz:** HP reduzieren, Monster besiegen
   - **Folge-Szene:** S3
   - **Flags gesetzt:** `monster_besiegt = true`
2. **Fliehen**
   - **Konsequenz:** Monster folgt dir, Chance auf Verletzung
   - **Folge-Szene:** S3
   - **Flags gesetzt:** `flucht_erfolgreich = true`

---

## Szene: S2B – Schlüssel gefunden
**Ort:** Alte Hütte, Fensterbereich  
**Charaktere:** Spieler  
**Ziel der Szene:** Schlüssel einsammeln, Rätsel vorbereiten

**Beschreibung:**  
Hinter dem Fenster liegt ein alter Schlüssel, verstaubt aber funktionstüchtig.

**Optionen:**
1. **Schlüssel nehmen**
   - **Konsequenz:** Du hast nun ein wichtiges Item
   - **Folge-Szene:** S3
   - **Flags gesetzt:** `hat_schluessel = true`
2. **Schlüssel liegen lassen**
   - **Konsequenz:** Du verlierst diese Möglichkeit, zukünftige Tür bleibt verschlossen
   - **Folge-Szene:** S3
   - **Flags gesetzt:** `schluessel_nicht_genommen = true`

---

## Szene: S3 – Finale
**Ort:** Waldlichtung / Hütte  
**Charaktere:** Spieler, Monster (optional)  
**Ziel der Szene:** Storyabschluss

**Beschreibung:**  
Abhängig von deinen Entscheidungen kommst du zu unterschiedlichen Enden.

**Optionen & Konsequenzen:**  
- Wenn `monster_besiegt = true` → Monster besiegt, sichere Flucht → Happy End  
- Wenn `hutze_verpasst = true` → Du verpasst Schlüsselmöglichkeit → Schlechteres Ende  
- Wenn `hat_schluessel = true` → Du öffnest die geheime Kammer → Bonus-Ende