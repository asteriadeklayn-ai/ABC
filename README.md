# ABConsult — Telegram Mini App

Avvalgi AST.KLY loyihasidan farqi:

1. **Tasdiqlash + login/parol**: Klient birinchi marta Telegram orqali ro'yxatdan o'tadi (ism, telefon, o'zi tanlagan parol). Bu so'rov "kutilmoqda" holatida turadi. Admin uni tasdiqlagach, klient endi **telefon raqam + parol** orqali kiradi — Telegram ichida ham, oddiy brauzerdan ham.
2. **Ko'p firma**: Bitta klientga bir nechta firma biriktirilishi mumkin. Klient kirganda barcha biriktirilgan firmalarining audit holatini ro'yxat ko'rinishida ko'radi.

## Ish jarayoni

1. Mijoz botni ochadi → Mini App → ism, telefon, parol kiritib ro'yxatdan o'tadi → "Tasdiqlash kutilmoqda" ekrani chiqadi.
2. Admin panelda **"Tasdiqlash"** bo'limida yangi so'rov ko'rinadi (yashil nuqta bilan sonini ko'rsatadi).
3. Admin so'rovni ochadi, kerakli firma(lar)ni belgilaydi (agar hali qo'shilmagan bo'lsa, avval "Firmalar" bo'limidan qo'shadi) va **"Tasdiqlash"** tugmasini bosadi. Firmalarni tanlamasdan ham tasdiqlash mumkin — keyin "Klientlar" bo'limidan biriktirsa bo'ladi.
4. Mijoz endi Mini App'ni ochganda (yoki istalgan brauzerdan) telefon+parol bilan kiradi va barcha biriktirilgan firmalarining audit holatini ko'radi.
5. Admin "Klientlar" bo'limida istalgan vaqtda klientning firmalar ro'yxatini o'zgartirishi (qo'shish/olib tashlash) mumkin.
6. Har bir firma uchun audit bosqichi (1-7) va hisobot fayllari (Word/Excel) avvalgidek qo'lda boshqariladi.

## O'rnatish

```bash
cd abconsult-mini-app
npm install
cp .env.example .env
```

`.env`da `BOT_TOKEN`, `CLIENT_JWT_SECRET`, `ADMIN_JWT_SECRET`ni to'ldiring.

```bash
npm run seed   # 7 ta admin hisobini yaratadi
npm start
```

- Klient Mini App: `http://localhost:3000/`
- Admin panel: `http://localhost:3000/admin`

Railway/production'ga joylashtirish AST.KLY loyihasidagi bilan bir xil — GitHub'ga yuklab, Railway'da ulash, Variables kiritish, domen olish, BotFather'da Mini App URL sozlash.
