# SGbyGP-OpenMods-ID-000002 - 🛒 Automatyczne przeliczanie zawartości koszyka po zmianie ilości z opóźnieniem czasowym

**Modyfikacja dla ShopGold – wersja z opóźnieniem czasowym**

## 📘 Opis

Domyślnie **ShopGold** nie przelicza koszyka automatycznie po zmianie ilości produktów.
Ta modyfikacja wprowadza automatyczne przeliczanie z krótkim opóźnieniem (domyślnie 1 sekunda), co zapobiega zbyt częstemu wywoływaniu funkcji w przypadku szybkiego wprowadzania wielu zmian przez klienta.

Kod został oznaczony komentarzami:

```html
<!-- MOD GREPO START -->
...
<!-- MOD GREPO STOP -->
```

aby łatwo było go odnaleźć i przenieść przy aktualizacjach sklepu lub szablonu.

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
    let przeliczTimeout;
    $(document).ready(function () {
        $(".InputPrzeliczKoszyk").on("change", function () {
            clearTimeout(przeliczTimeout);
            przeliczTimeout = setTimeout(function () {
                PrzeliczCalyKoszyk();
            }, 1000); /* czas w milisekundach – 1000 = 1 sekunda */
        });
    });
</script>
<!-- MOD GREPO STOP -->
```

📌 **Po zapisaniu zmian pamiętaj, aby odświeżyć pamięć podręczną sklepu (cache)**
W panelu administratora kliknij:
`Odśwież pamięć podręczną sklepu (cache)`

---

### Opcja 2 – przez panel administratora

1. Zaloguj się do **Panelu Administratora**.
2. Wejdź w:
   `Integracje → Integracje własne → Kod w nagłówku strony w sekcji <head> (wyświetlany zawsze)`
3. Wklej powyższy kod i kliknij **Zapisz zmiany**.

---

## ✅ Efekt

Po każdej zmianie ilości produktu w koszyku, system automatycznie przeliczy jego wartość — z krótkim opóźnieniem.
To rozwiązanie sprawdza się szczególnie przy wolniejszych łączach lub gdy klient szybko edytuje kilka pozycji w koszyku.

---

💡 *Prosta i skuteczna modyfikacja, która zwiększa wygodę użytkowników Twojego sklepu ShopGold!*
