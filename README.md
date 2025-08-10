# EPUB → PDF přes GitHub Actions (bez skrytých složek při uploadu)

Tento balíček je upraven tak, abys ho mohl **celý nahrát přes webové rozhraní GitHubu**.
Po nahrání je potřeba **ještě vytvořit workflow soubor** (GitHub web neumí jednoduše nahrát skrytou složku `.github`).

## Krok 1 — Nahraj tento balíček
1. Na GitHubu vytvoř nový public repozitář.
2. Klikni **Add file → Upload files** a přetáhni sem **obsah** tohoto ZIPu (složky `epub/`, `pdf/`, `WORKFLOWS_upload_here/` a soubory v kořeni včetně `index.html`).

## Krok 2 — Vytvoř workflow soubor ručně (jednou, 30 sekund)
1. V repozitáři klikni **Add file → Create new file**.
2. Do pole pro název souboru napiš přesnou cestu:  
   `.github/workflows/convert_epub.yml`
3. Otevři soubor `WORKFLOWS_upload_here/convert_epub.yml` (je součástí tohoto balíčku), zkopíruj jeho obsah a vlož do editoru na GitHubu.
4. Dole klikni **Commit new file**.

> Tip: Pokud chceš, můžeš místo tohoto kroku použít Git (příkazovou řádku) a nahrát originální `.github/workflows/...` přímo. Tohle je ale nejrychlejší čistě přes web.

## Krok 3 — Zapni GitHub Pages
- V **Settings → Pages** nastav *Deploy from a branch* → Branch `main` → Folder `/(root)` → Save.  
- URL bude `https://<username>.github.io/<repo>/` a `index.html` zobrazí PDF z `/pdf/`.

## Krok 4 — Nahraj EPUBy
- Otevři složku **epub/** → **Upload files** → nahraj `.epub` → **Commit changes**.  
- Workflow se spustí automaticky, výsledky budou v **pdf/** + manifest `pdf/pdf_list.json`.

Hotovo. 
