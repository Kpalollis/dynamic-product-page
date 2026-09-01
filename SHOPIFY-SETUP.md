# 🛍️ Shopify Custom Navbar Setup

Ένας **πλήρης custom navbar** για Shopify με dropdown menus, δυναμικό περιεχόμενο και mobile responsiveness.

## 📋 Αρχεία

- **navbar-shopify.liquid** - Ο κύριος κώδικας που χρησιμοποιείται στο Shopify
- **navbar.css** - CSS styling (εναλλακτικά, αν θέλεις ξεχωριστό αρχείο)
- **navbar-component.liquid** - Απλή HTML/Liquid έκδοση (μη-Shopify)

---

## 🚀 Πώς να εγκαταστήσεις στο Shopify

### **Option 1: Ως Section (Προτεινόμενο)**

1. **Πήγαινε στο Shopify Admin** → Theme Editor (Customize)
2. **Edit Code** (στο κάτω αριστερό μέρος)
3. **Δημιούργησε νέο αρχείο:**
   - Κάνε κλικ στο **"Add a new file"**
   - Βάλε το path: `sections/navbar-custom.liquid`
   - Αντίγραψε το περιεχόμενο από `navbar-shopify.liquid`

4. **Πρόσθεσε το section στο theme:**
   - Πήγαινε σε **theme.liquid** (ή **header.liquid**)
   - Βάλε αυτόν τον κώδικα στο `<body>`:
   ```liquid
   {% section 'navbar-custom' %}
   ```

5. **Customize στο Theme Editor:**
   - Πήγαινε στο **Customize** (Customize theme)
   - Θα δεις την **"Custom Navbar"** section
   - Ρύθμισε το logo, menu, κτλ.

---

### **Option 2: Ως Snippet (Αν δεν θέλεις section)**

1. **Edit Code**
2. **Δημιούργησε:** `snippets/navbar-custom.liquid`
3. Αντίγραψε το περιεχόμενο (χωρίς το `{% schema %}`)
4. Σε `layout/theme.liquid` ή `header.liquid`:
   ```liquid
   {% include 'navbar-custom' %}
   ```

---

## ⚙️ Ρυθμίσεις (Settings)

Στο Theme Editor, μπορείς να ρυθμίσεις:

| Ρύθμιση | Περιγραφή |
|--------|-----------|
| **Logo** | Φόρτωσε το logo του καταστήματος |
| **Menu** | Επέλεξε ποιο menu θα εμφανιστεί (default: main-menu) |
| **Search Label** | Κείμενο του κουμπιού αναζήτησης |
| **Login Label** | Κείμενο του κουμπιού σύνδεσης |
| **Account Label** | Κείμενο του κουμπιού λογαριασμού |
| **Cart Label** | Κείμενο του κουμπιού καλαθιού |

---

## 🎨 Προσαρμογή Χρωμάτων

Άνοιξε το αρχείο `navbar-shopify.liquid` και ψάξε τα χρώματα:

```css
/* Χρώματα που μπορείς να αλλάξεις: */
#1a1a2e   /* Dark blue background */
#16213e   /* Gradient end color */
#00d4ff   /* Cyan accent color */
#0f3460   /* Dropdown background */
#ff4444   /* Cart badge color */
```

---

## 🔄 Δυναμικά Χαρακτηριστικά

✅ **Shopify Integration:**
- `{{ shop.name }}` - Όνομα καταστήματος
- `{{ routes.cart_url }}` - Σύνδεσμος καλαθιού
- `{{ routes.account_url }}` - Σύνδεσμος λογαριασμού
- `{{ cart.item_count }}` - Αριθμός προϊόντων στο καλάθι
- `{{ customer }}` - Πληροφορίες πελάτη (αν συνδεδεμένος)
- `linklists[menu]` - Δυναμικό menu από τις ρυθμίσεις του Shopify

---

## 📱 Mobile Responsive

- ✅ Hamburger menu για mobile
- ✅ Touch-friendly dropdowns
- ✅ Αυτόματη προσαρμογή σε < 768px
- ✅ Smooth animations

---

## 🔧 Troubleshooting

| Πρόβλημα | Λύση |
|---------|------|
| Το menu δεν εμφανίζεται | Βεβαιώσου ότι έχεις δημιουργήσει ένα menu στο Shopify (Navigation menu) |
| Το dropdown δεν δουλεύει | Χρησιμοποίησε Shopify's built-in theme structure |
| Σφάλμα στο CSS | Αν βάλεις σε ξεχωριστό αρχείο, χρησιμοποίησε `{{ 'navbar.css' \| asset_url \| stylesheet_tag }}` |

---

## 💡 Tips

1. **Δημιούργησε ένα navigation menu στο Shopify:**
   - Admin → Menus
   - Δημιούργησε "Main Menu" με links

2. **Πρόσθεσε το navbar σε όλες τις σελίδες:**
   - Βάλε το `{% section 'navbar-custom' %}` στο `layout/theme.liquid`

3. **Εξάρτησε το cart badge:**
   - Το cart count ενημερώνεται αυτόματα μέσω Shopify

---

## 📚 Resources

- [Shopify Liquid Reference](https://shopify.dev/api/liquid)
- [Shopify Theme Development](https://shopify.dev/themes)
- [Shopify Sections](https://shopify.dev/themes/architecture/sections)

Καλή τύχη με το navbar! 🚀
