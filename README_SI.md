# The Stage Café & Cake Bar — අලුත් Website එක

## මේ package එකේ තියෙන්නේ
- `index.html` — අලුත් responsive website එක (phone සහ computer දෙකටම)
- `assets/stage-cafe-logo.jpg` — ඔයා එවපු restaurant logo එක
- `assets/menu.json` — කලින් menu file එකෙන් ගත් categories සහ menu items 103
- `assets/category-images.json` — category image links
- `supabase/schema.sql` — orders table එක හදන SQL

## GitHub Pages එකට upload කරන විදිහ (Android phone)
1. ZIP එක extract කරන්න.
2. GitHub repository එකට යන්න: https://github.com/thestagecafemenu-wq/The-stage-cafe-menu-
3. `Add file` → `Upload files` තෝරන්න.
4. ZIP එක ඇතුළේ තියෙන `index.html`, `assets` folder එක සහ `supabase` folder එක upload කරන්න. `index.html` repository එකේ root එකේම තිබිය යුතුයි.
5. පැරණි `index.html` එක replace කරනවා නම් Commit changes කරන්න.
6. Repository Settings → Pages තුළ branch `main`, folder `/ (root)` ලෙස තෝරා Save කරන්න (දැනට GitHub Pages සක්‍රිය නම් මේ පියවර අවශ්‍ය නැහැ).

## සැබෑ online orders සඳහා Supabase සම්බන්ධ කිරීම
Website design එක, menu, cart සහ checkout සූදානම්. නමුත් සැබෑ order database එකට යැවීමට Supabase project එකක් අවශ්‍යයි.

1. Supabase project එකක් සාදන්න.
2. Supabase Dashboard → SQL Editor → New query වෙත ගොස් `supabase/schema.sql` එකේ SQL run කරන්න.
3. Project Settings → API (හෝ Connect) වෙතින් Project URL සහ anon/public key ගන්න.
4. `index.html` තුළ පහත දෙක replace කරන්න:
   - `YOUR_SUPABASE_PROJECT_URL`
   - `YOUR_SUPABASE_ANON_PUBLIC_KEY`
5. වෙනස් කළ `index.html` එක නැවත GitHub එකට commit කරන්න.

**ආරක්ෂාව:** `service_role` key එක කිසිවිටෙක website එකට දාන්න එපා. Public anon key එක පමණක් භාවිතා කරන්න. SQL policy එකෙන් customer website එකට order insert කිරීමට පමණක් අවසර දී ඇත; public read access නැත.

## Order ක්‍රමය
- Payment: Cash on Delivery
- Fulfilment: Delivery හෝ Pickup
- Supabase credentials දාපු පසු checkout එකෙන් orders `orders` table එකට යවයි.
- Supabase setup කරන තුරු checkout එක order සුරැකෙන්නේ නැති බව පැහැදිලි message එකක් පෙන්වයි.

## තවම ඇතුළත් කර නැති දේ
- Delivery fee / delivery areas සහ branch contact details (තවම තහවුරු කරලා නැති නිසා)
- Restaurant WhatsApp number
- Admin dashboard / order status management
