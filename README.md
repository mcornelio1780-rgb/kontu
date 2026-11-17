# Kontu · web (landing + plataforma)

Sitio estático. Kontu es una marca de Limly LLC. Idiomas: español, inglés, portugués y francés.

## Archivos
- `index.html` — landing
- `plataforma.html` — plataforma (login, onboarding, documentos, preguntas, escenarios, facturación)
- `vercel.json` — URLs limpias, redirecciones y cabeceras de seguridad
- `404.html`, `robots.txt`, `.gitignore`

## Subir a GitHub y Vercel
1. Crea un repositorio vacío en GitHub (por ejemplo `kontu-web`).
2. "Add file" → "Upload files" y arrastra **los archivos** (no la carpeta). `index.html` debe quedar en la raíz.
3. En Vercel: "Add New… → Project" → importa el repo → Framework: **Other** → Deploy (sin build command).
4. Tu web: `https://<tu-proyecto>.vercel.app` · plataforma: `https://<tu-proyecto>.vercel.app/plataforma`

## Después: pagos y base de datos
Funciona completa sin pagos ni base de datos. Cuando tengas los datos, edita los bloques de configuración (o envíalos a Claude para un zip nuevo):

**index.html → `const CONFIG`**: `payLinks` (links de checkout de cada plan), `supabaseUrl`, `supabaseAnonKey`, `whatsapp` (vacío = se oculta el botón), `formEndpoint` (opcional).

**plataforma.html → `const KCFG`**: `supabaseUrl`, `supabaseAnonKey`, `portalUrl` (portal de cliente), `payLinks`.

URL de éxito para los checkouts: `https://<tu-proyecto>.vercel.app/plataforma?pago=ok`

Cada vez que reemplaces un archivo en GitHub, Vercel publica solo en ~1 minuto.
