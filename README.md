# Compras Agro 🌾

Sistema de gestión de compras e insumos agropecuarios.

## Stack
- HTML + JS vanilla (sin frameworks)
- [Supabase](https://supabase.com) — base de datos + autenticación
- [Vercel](https://vercel.com) — deploy automático

## Módulos
- **Dashboard** — stock actual, cobertura por artículo, alertas de reposición
- **Compras** — registro de órdenes de compra con factura y remito
- **Inventario** — carga mensual de stock físico, cálculo automático de consumo
- **Artículos** — ABM de insumos con proveedores (solo admin)
- **Proveedores** — ABM de proveedores (solo admin)

## Roles
| Rol | Permisos |
|-----|----------|
| `compras` | Ver dashboard, registrar compras, cargar inventario |
| `admin` | Todo lo anterior + gestionar artículos y proveedores |

## Setup inicial

### 1. Supabase
Ejecutar los scripts SQL en orden (ver carpeta `/sql`).

### 2. Crear el primer usuario admin
En Supabase → Authentication → Users → "Invite user" con el email del administrador.
Luego en SQL Editor:
```sql
insert into perfiles (id, nombre, rol)
values ('<uuid-del-usuario>', 'Nombre Admin', 'admin');
```

### 3. Deploy en Vercel
Conectar este repositorio en [vercel.com](https://vercel.com) y hacer deploy.
No requiere variables de entorno — las credenciales están en `index.html`.

## Actualizar el sistema
1. Reemplazar `index.html` en este repo
2. Vercel hace el deploy automáticamente en ~30 segundos
