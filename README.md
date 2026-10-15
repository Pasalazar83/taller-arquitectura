# taller-arquitectura — EventFlow

Repositorio del taller de Arquitectura de Software (UMB). Sirve para simular un ciclo DevOps completo sobre "EventFlow", un sistema simple de venta de entradas.

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El "monolito". Contiene *code smells* **intencionales** (CSS mal anidado, JavaScript en línea, código duplicado) para que SonarCloud los reporte como deuda técnica. |
| `.github/workflows/ci.yml` | Pipeline de CI/CD en GitHub Actions: `build` → `test` → despliegue simulado. Corre en cada push a `main`. |
| `main.tf` | Infraestructura como código (Terraform): VPC, regla de firewall y una VM `e2-micro` en Google Cloud. Solo se ejecutan `terraform init` y `terraform plan`, nunca `apply`. |

## Cómo reproducir

1. Haz un cambio en `index.html` (por ejemplo, cambia el año del copyright a 2026) y haz commit en `main`.
2. Abre la pestaña **Actions** y observa cómo corren `build` y `test`.
3. Importa el repo en [SonarCloud](https://sonarcloud.io) para ver los *code smells*.
4. En Google Cloud Shell, clona el repo y ejecuta:

```bash
terraform init
terraform plan
```
