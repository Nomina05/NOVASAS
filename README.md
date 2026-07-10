# SaaS Multiempresa de Facturación

Arquitectura preparada para comercialización usando:

- Frontend: Next.js / React
- Hosting: Vercel
- Base de datos: Supabase PostgreSQL
- Auth: Supabase Auth
- Seguridad: Row Level Security por empresa
- Almacenamiento: Supabase Storage para logos, firmas, comprobantes y facturas

## Flujo multiempresa

1. El usuario inicia sesión.
2. El sistema consulta en qué empresas participa.
3. El usuario selecciona empresa activa.
4. Todas las consultas usan `empresa_id`.
5. Supabase RLS impide ver datos de otra empresa.

## Instalación

```bash
npm install
cp .env.example .env.local
npm run dev
```

## Variables de entorno

Configurar en `.env.local` y en Vercel.

```env
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=
```

## Supabase

Ejecutar el archivo:

```text
supabase/schema.sql
```

Luego activar RLS y políticas incluidas.

## Despliegue

1. Subir proyecto a GitHub.
2. Conectar repositorio en Vercel.
3. Agregar variables de entorno.
4. Publicar.
