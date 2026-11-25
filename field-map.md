# Developments CRM — field plan

Plan for a HomesNI new-homes / developments admin: what each section holds and how records nest.

**Development → Phases → Property types → Units**  
(List price and availability are set on **units**, then roll up to the type and development.)

---

## Editor chrome (every screen)

- Development name + hero / thumbnail  
- Publish status (Draft · Live · Hidden)  
- Public listing URL (when live)  
- Save  
- Archive  

---

## Details

Identity, address, who sells it, visibility.

- Development name  
- Availability status (e.g. Coming soon · On release · Selling · Sold out)  
- Tenure  
- Summary (short rich text)  
- Tagline (one line under the address on the public page)  
- Address line 2  
- Town / city  
- County  
- Country  
- Selling agent(s)  
- Warranty / NHBC (or similar) badge on/off  
- Show on public site on/off  
- Archive  

## Description

Marketing copy for the **whole** development (not individual house types).

- Short description  
- Bullet / highlight list  
- Long description (rich text — lifestyle, specification, etc.)  

## Location

- Map pin (lat / lng)  
- Pin accuracy (exact · street · area · approximate)  
- Directions / how to find us  

## Photos

- Gallery  
- Upload, reorder, caption (optional)  
- Primary / cover image  

## Videos

- Video list (upload or embed URL)  

## Files

Brochures, PDFs, floor plans, etc.

- File list (name + file)  
- Upload / replace / remove  

## Site maps

- Site plan image(s)  
- Upload / manage  

## Show home times

- Opening hours / viewing schedule for the show home  

## Phases

Optional stages within a large site.

- Phase list (name, status, order)  
- Add / edit / remove phase  

## Property types

House types on the development (each can later have its own copy, media, and units).

- List: name, style, beds, from-price, units available, status, published  
- Add property type  
- Link to type detail (copy, photos, floor plans, units)  

### Property type detail (planned)

- Name, style, beds, bathrooms, receptions  
- Size (sq ft / sq m)  
- Short + long description  
- Spec / features  
- Photos, floor plans, files  
- Link to phase (optional)  

### Units (planned)

Individual plots / sites under a property type.

- Unit / plot reference  
- Asking price (or POA)  
- Status (available · reserved · sold · coming soon)  
- Show on public site on/off  
- Optional extras (parking, tenure override, etc.)  

## Notes

- Internal notes only (never public)  

## Microsite

Optional bespoke landing site for the development (beyond the standard HomesNI listing).

- Microsite on/off  
- Public URL / slug (e.g. `/developments/camowen` or a custom domain later)  
- Use standard listing content vs custom microsite content  
- Hero / branding overrides (logo, colours, cover — if custom)  
- Extra sections or blocks unique to this site (optional)  
- Preview + publish microsite  

## Publishing

Where and how the development appears.

- Live on HomesNI listing on/off  
- Microsite live on/off (see above)  
- Other outbound channels (if any)  
- Channel-specific status / last synced (if needed later)  

---

## Data model

| Entity | Belongs to | Purpose |
|---|---|---|
| **Development** | — | Overview listing: details, copy, location, media, notes, publish flags |
| **Microsite** | Development | Optional bespoke landing page config + overrides |
| **Phase** | Development | Optional grouping of types / units |
| **Property type** | Development (optional phase) | House style and type-level marketing |
| **Unit** | Property type | Plot, price, availability |
| **Media** | Development and/or property type | Photos, videos, files, site maps |

---

## Build order (suggested)

1. Development Details + Description + Location + publish flag  
2. Photos / files / site maps  
3. Property types list + type detail  
4. Units (pricing + availability)  
5. Phases, show-home times, notes, multi-agent  
6. Bespoke microsite  
7. Extra channels / feeds if required  
