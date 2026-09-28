# Práctica DevOps CI/CD

Aplicación HTML sencilla servida por Nginx en Docker, con integración continua mediante GitHub Actions.

## Requisitos
- Git
- Docker Desktop (Windows)
- Cuenta de GitHub

## Uso local

```bash
docker compose up -d --build
```

Abre http://localhost:8080

Para detener:

```bash
docker compose down
```

## CI/CD

Cada `push` a `main` dispara el workflow `.github/workflows/ci-cd.yml`:
1. **test**: verifica que `index.html` existe y contiene el texto esperado.
2. **build**: construye la imagen Docker (solo si `test` pasó).

## Primer despliegue a GitHub

```bash
git init
git add .
git commit -m "Primera versión de la aplicación DevOps"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/practica-devops-cicd.git
git push -u origin main
```
