# React + TypeScript + Vite

Este proyecto se configuró con plantilla inicial para aplicaciones React utilizando TypeScript y Vite. Incorpora herramientas para mejorar la calidad del código y el flujo de trabajo de desarrollo.

### Dependencias Clave

- **_Vite:_** Un servidor de desarrollo rápido y un bundler para aplicaciones web modernas.
- **_React:_** La biblioteca de JavaScript más popular para construir interfaces de usuario.
- **_TypeScript:_** Un superconjunto de JavaScript que añade tipado estático para mejorar la mantenibilidad del código.
- **_ESLint:_** Un linter de código que ayuda a identificar y corregir errores comunes y problemas de estilo.
- **_Prettier:_** Un formateador de código que asegura un estilo de código consistente en todo el proyecto.
- **_Husky:_** Una herramienta para gestionar Git hooks, que nos permite ejecutar scripts en diferentes momentos del ciclo de vida de Git.
- **_Lint-Staged:_** Optimiza la ejecución de linters como ESLint y Prettier, aplicándolos solo a los archivos que están siendo preparados para el commit.
- **_Commitlint:_** Un linter para mensajes de commit que verifica si siguen las convenciones establecidas.
- **_@commitlint/config-conventional:_** Configuración de Commitlint que aplica las reglas de Conventional Commits.

## Flujo de Trabajo de Git (Gitflow)

Este proyecto sigue un flujo de trabajo de Git basado en las convenciones de Conventional Commits y utiliza Husky para automatizar tareas de control de calidad.

### Ramas principales:

- **_main:_** La rama principal donde se encuentran las versiones estables y listas para producción.
- **_develop:_** La rama principal de desarrollo donde se integran nuevas funcionalidades y correcciones.

### Flujo de trabajo típico:

1. **_Crea una nueva rama:_** A partir de develop, crea una nueva rama para tu funcionalidad o corrección (git checkout -b feature/nueva-funcionalidad o git checkout -b fix/corregir-error).

2. **_Desarrolla:_** Realiza tus cambios en la nueva rama.

3. **_Commits:_** Realiza commits frecuentes y descriptivos siguiendo las convenciones de Conventional Commits (por ejemplo, feat(login): agregar autenticación con Google).
4. **_Push:_** Sube tus cambios a la rama remota (git push origin feature/nueva-funcionalidad).
5. **_Pull Request:_** Crea un Pull Request desde tu rama hacia develop.
6. **_Revisión y aprobación:_** El código es revisado y, si es aprobado, se fusiona en develop.
7. **_Despliegue en producción:_** Cuando se tiene una versión estable lista para producción, se fusiona develop en main y se realiza el despliegue.

### Automatización con Husky:

- **_Pre-commit:_** Antes de cada commit, se ejecutan ESLint y Prettier para asegurar que el código cumple con los estándares de calidad y estilo.
- **_Commit-msg:_** Antes de cada commit, se verifica que el mensaje del commit siga las convenciones de Conventional Commits.

### Comandos útiles:

- `npm run dev:` Inicia el servidor de desarrollo.
- `npm run build:` Compila el proyecto para producción.
- `npm run lint:` Ejecuta ESLint para verificar el código.
- `npm run format:` Formatea el código con Prettier.

### Contribuciones:

¡Las contribuciones son bienvenidas! Si encuentras algún error o quieres sugerir mejoras, por favor abre un issue o envía un Pull Request.

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default {
  // other rules...
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module',
    project: ['./tsconfig.json', './tsconfig.node.json', './tsconfig.app.json'],
    tsconfigRootDir: __dirname,
  },
};
```

- Replace `plugin:@typescript-eslint/recommended` to `plugin:@typescript-eslint/recommended-type-checked` or `plugin:@typescript-eslint/strict-type-checked`
- Optionally add `plugin:@typescript-eslint/stylistic-type-checked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and add `plugin:react/recommended` & `plugin:react/jsx-runtime` to the `extends` list
