# Ropero - Tienda de Segunda Mano

## Stack
- Astro 5 (static site)
- Tailwind CSS 4
- No framework (vanilla JS for filters)

## Commands
- `npm run dev` - Dev server on localhost:4321
- `npm run build` - Build to /dist
- `npm run preview` - Preview build

## Structure
- `src/data/products.json` - Product catalog (wife edits this)
- `src/pages/` - index, mujer, hombre
- `src/pages/producto/[id].astro` - Product detail with carousel
- `src/components/` - ProductCard, ProductGrid
- `src/layouts/Layout.astro` - Shared layout

## Product Schema
```json
{
  "id": number,
  "titulo": string,
  "descripcion": string,
  "talla": string,
  "precio": number (colones),
  "categoria": "tops" | "bottoms" | "zapatos" | "accesorios",
  "genero": "mujer" | "hombre",
  "imagen": string (URL - poster/main image),
  "imagenes": string[] (additional image URLs, optional - carousel shows poster + these),
  "vendido": boolean
}
```

## Notes
- No payment processing - orders via WhatsApp
- Shipping: ₡3,000 flat rate
- WhatsApp number in `src/pages/producto/[id].astro` needs to be updated
- Clicking a product card goes to `/producto/{id}` detail page
- Detail page has image carousel: poster image first, then `imagenes` array
- If `imagenes` is empty, detail page shows just the poster
- All text in Spanish
