# Phase 1 starter: shop loads from the database

What this does: the Mini App opens from a shop's bot, the server checks that the data really
came from Telegram, loads that shop and its products from Supabase, and shows them.

## Steps
1. Supabase > SQL Editor: run `supabase/schema.sql`.
2. Open `supabase/seed.sql`, replace YOUR_TEST_BOT_USERNAME and PASTE_TEST_BOT_TOKEN with your
   TEST bot (never a real shop's bot), and run it. This creates a shop with the slug `test`.
3. Copy these files into your repo (same paths), replacing the Vite defaults:
   `storefront/api/shop.ts`, `storefront/src/App.tsx`, `storefront/src/index.css`.
4. In the `storefront` folder:
   `npm install @supabase/supabase-js`
   `npm install -D @vercel/node`
5. Vercel: set the project's Root Directory to `storefront`. Add two environment variables:
   SUPABASE_URL and SUPABASE_SERVICE_KEY (Supabase > Project Settings > API: the secret key).
   The secret key must never go in the app code or in GitHub.
6. Push to GitHub. Vercel deploys by itself.
7. BotFather: set your test bot's menu button URL to `https://YOUR-APP.vercel.app/?shop=test`.
8. Open the bot in Telegram, tap the menu button. You should see Test Shop and four products.

## If it fails
- "Telegram data could not be verified": the token in `shop_bots` is not the token of the bot
  you opened the app from.
- "Shop not found": the slug in the URL does not match the `slug` in the `shops` table.
- Opening the page in a normal browser shows "Open this shop from Telegram." That is expected.

## Notes
- The bot token is stored as plain text for development. Encrypt it before real sellers join.
- This code was written without being run on your machine. Send me any error you get.
