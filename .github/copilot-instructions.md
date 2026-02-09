# Project Guidelines

## Code Style
- Follow Angular ESLint rules configured in [.eslintrc.json](.eslintrc.json), including `app-` selectors for components and `app` selectors for directives.
- TypeScript is configured with strict template checks in [tsconfig.json](tsconfig.json).

## Architecture
- Feature modules are organized by domain (owners, pets, vets, visits) with per-feature routing and a root router in [src/app/app-routing.module.ts](src/app/app-routing.module.ts).
- Shared UI and infrastructure live in the parts module in [src/app/parts/parts.module.ts](src/app/parts/parts.module.ts).
- HTTP error handling uses a central handler and interceptor registered in [src/app/error.service.ts](src/app/error.service.ts) and [src/app/app.module.ts](src/app/app.module.ts).
- Environment-specific API configuration lives in [src/environments/environment.ts](src/environments/environment.ts) and [src/environments/environment.prod.ts](src/environments/environment.prod.ts).

## Build and Test
- Install: `npm install`
- Dev server: `npm run start`
- Build: `npm run build`
- Unit tests: `npm run test` (or `npm run test-headless`)
- Lint: `npm run lint`
- E2E: `npm run e2e`

## Project Conventions
- Feature routing modules mirror their feature module structure (examples: [src/app/owners/owners-routing.module.ts](src/app/owners/owners-routing.module.ts), [src/app/pets/pets-routing.module.ts](src/app/pets/pets-routing.module.ts)).
- Global styles and scripts are managed in [angular.json](angular.json) and [src/styles.css](src/styles.css).

## Integration Points
- External UI and utility dependencies (Bootstrap, jQuery, Moment, Angular Material) are declared in [package.json](package.json) and wired via [angular.json](angular.json).
- Documentation is generated with Compodoc; see [README.md](README.md) and output in [docs/](docs/).

## Security
- Centralized HTTP error handling via interceptor in [src/app/error.service.ts](src/app/error.service.ts); keep auth or API error handling aligned with this path.
