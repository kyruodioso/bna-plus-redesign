# BNA+ Redesign | Enterprise Proof of Concept

![Next.js 16](https://img.shields.io/badge/Next.js-16-black?style=for-the-badge&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-Enabled-success?style=for-the-badge&logo=github-actions)

Este proyecto es un rediseño técnico nivel **Proof of Work** de la web app de **BNA+ (Banco Nación Argentina)**.

## Engineering Architecture

Como responsable técnico del proyecto, he implementado una arquitectura orientada a la mantenibilidad y la paridad de entornos:

- **Framework**: Next.js 16 (App Router) utilizando Server Components para optimización de performance.
- **Environment Control**: Dockerización completa (Multi-stage Builds).
- **Quality Gatekeepers**:
  - **Husky & Lint-staged**: Pre-commit hooks para asegurar que el código cumple con el linter y formato.
  - **Commitlint**: Estandarización de mensajes bajo la norma de _Conventional Commits_.
- **CI/CD Pipeline**: GitHub Actions automatizado que actúa como "Gatekeeper" validando tipos, linting y build de producción en cada Pull Request.

## Project Structure (Domain-Driven Design Lite)

El proyecto sigue una estructura modular para separar la lógica de negocio del framework:

```text
src/
├── app/          # Next.js Routing & Layouts
├── components/   # UI Library (Atomic Design)
├── core/         # Business Logic (Entities, Services, Use Cases)
├── hooks/        # Custom Shared Hooks
├── lib/          # External Configurations (Auth, DB)
└── store/        # State Management (Zustand)
```
