# GithubactionsAngular - **Guía para Configurar GitHub Actions para Despliegues Automáticos**

## **1. ¿Qué es GitHub Actions?**
GitHub Actions es una herramienta de integración y entrega continua (CI/CD) integrada en GitHub. Permite automatizar tareas como pruebas, builds y despliegues cada vez que se realizan cambios en un repositorio.

---

## **2. Requisitos Previos**
Antes de configurar GitHub Actions, asegúrate de cumplir con los siguientes requisitos:

- **Acceso de escritura** al repositorio donde se configurarán los workflows.
- **Conocimiento básico de YAML**, ya que los workflows de GitHub Actions se definen en este formato.
- **Acceso al repositorio relacionado (Laravel, en este caso)**.
- **Node.js instalado localmente** si necesitas probar manualmente el build de Angular.

---

## **3. Configuraciones Iniciales**

### **3.1 Crear el Archivo de Workflow**
1. En el repositorio de Angular:
   - Crea un directorio llamado `.github/workflows/` en el nivel raíz del repositorio:
     ```bash
     mkdir -p .github/workflows
     ```
   - Dentro de esa carpeta, crea un archivo YAML para definir el flujo de trabajo:
     ```bash
     touch .github/workflows/deploy-angular-to-laravel.yml
     ```

2. Abre el archivo y define un flujo básico:
   ```yaml
   name: Build and Deploy Angular to Laravel
   on:
     push:
       branches:
         - main