# SGbyGP-OpenMods-ID-000001 - 🛒 Automatyczne przeliczanie zawartości koszyka po zmianie ilości 

**Modyfikacja dla ShopGold – wersja natychmiastowa (bez opóźnienia)**

## 📘 Opis

Natywnie system **ShopGold** nie posiada funkcji automatycznego przeliczania wartości koszyka po zmianie ilości produktu.
Dzięki tej modyfikacji w prosty i szybki sposób można dodać tę funkcjonalność, co znacząco ułatwia zakupy Twoim klientom — nie muszą oni już ręcznie klikać „Przelicz koszyk”.

Kod jest oznaczony komentarzami:

```html
<!-- MOD GREPO START -->
...
<!-- MOD GREPO STOP -->
```

Dzięki temu łatwo go odnaleźć i przenieść przy aktualizacji sklepu lub zmianie szablonu.

---

## 📍 Instalacja

### Opcja 1 – wklejenie bezpośrednio w szablonie

Wklej poniższy kod w pliku:

```
/szablon/twoj_szablon/strona_glowna.tp
```

tuż **przed zamknięciem znacznika `</head>`**.

```html
<!-- MOD GREPO START -->
<script>
    $(document).ready(function () {
        $(".InputPrzeliczKoszyk").on("change", function () {
            PrzeliczCalyKoszyk();
        });
    });
</script>
<!-- MOD GREPO STOP -->
```

---

### Opcja 2 – przez panel administratora

1. Zaloguj się do **Panelu Administratora**.
2. Wejdź w:
   `Integracje → Integracje własne → Kod w nagłówku strony w sekcji <head> (wyświetlany zawsze)`
3. Wklej powyższy kod i kliknij **Zapisz zmiany**.

---

## ✅ Efekt

Po każdej zmianie ilości produktu w koszyku, system automatycznie przeliczy wartość całkowitą – bez potrzeby odświeżania strony ani klikania w przycisk „Przelicz”.

To prosta, ale bardzo użyteczna modyfikacja, poprawiająca wygodę użytkownika i UX sklepu.
