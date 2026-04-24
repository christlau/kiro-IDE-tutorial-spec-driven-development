Build a full-stack web application using Next.js 14 (App Router) and Tailwind CSS 
called MBG (Mari Beli Gitar) — an Indonesian guitar product showcase website.

## Public Storefront
- A homepage with a hero section, brand tagline, and featured guitar products
- A product listing page displaying guitar products in a responsive card grid
- Each product card shows: product image gallery (multiple photos), product name, 
  short description, and price in IDR
- Each product card has two CTA buttons: "Beli di Tokopedia" (placeholder: 
  https://tokopedia.com/mbg) and "Beli di Shopee" (placeholder: https://shopee.co.id/mbg)
- A persistent floating widget fixed at the bottom-right corner of every page 
  with a WhatsApp icon that opens wa.me/6281234567890 in a new tab

## Admin Panel
- A protected /admin route with a simple login form (username + password)
- On successful login, the admin is redirected to a product management dashboard
- The dashboard displays a table of all existing products
- Admin can add new products via a form: name, description, price, 
  and upload multiple product images
- Admin can delete existing products
- Authentication state should persist via a session cookie or JWT

## Technical Requirements
- Use Next.js 14 App Router with TypeScript
- Use Tailwind CSS for all styling
- Store product and admin data in a SQLite database via Prisma ORM
- Product images stored locally in /public/uploads
- Mobile responsive design throughout
- Bahasa Indonesia as the primary UI language
- English field labels in the admin panel
