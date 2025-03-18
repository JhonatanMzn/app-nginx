# app-nginx

Este repositorio contiene una aplicación web simple servida con Nginx en una instancia EC2 de AWS, con despliegue automatizado mediante GitHub Actions.

## Contenido
- `index.html` y `./public/style.css`: Página web estática.
- `.github/workflows/deploy.yml`: Flujo de trabajo para desplegar cambios en EC2.

## Despliegue Automático
Cada push a `main` ejecuta un flujo de trabajo que:
1. Accede a la instancia EC2 por SSH.
2. Realiza `git pull` en `/var/www/html/`.
3. Reinicia Nginx.

### Configuración
En los secretos de GitHub, define:
- `EC2_PUBLIC_IP`: IP de la instancia.
- `EC2_USER`: Usuario SSH.
- `EC2_SSH_PRIVATE_KEY`: Clave SSH.