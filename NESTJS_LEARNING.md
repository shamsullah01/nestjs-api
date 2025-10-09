## NestJS Learning Guide

A compact learning checklist and reference for important NestJS topics, short examples, and mini-exercises you can use while learning the framework.

## Goal / Contract
- Inputs: Basic TypeScript and Node.js knowledge
- Outputs: Understand NestJS building blocks and be able to build a small API with DI, validation, guards, pipes, interceptors, and tests
- Error modes: missing TypeScript types, runtime DI errors, validation errors

## Suggested learning path (high priority first)
1. Project setup & CLI
2. Modules, Controllers, Providers (Services)
3. Dependency Injection (scopes, custom providers)
4. DTOs & Validation (class-validator / class-transformer)
5. Pipes (validation/transformation)
6. Guards (authentication / authorization)
7. Interceptors (logging, response mapping, caching)
8. Middleware
9. Exception filters and error handling
10. Configuration management (ConfigModule)
11. Logging and monitoring
12. Testing: unit and e2e (Jest)
13. Database integration (TypeORM / Prisma / Mongoose)
14. Microservices, WebSockets, GraphQL (optional / advanced)
15. Deployment & performance tuning

## Quick topic checklist (use this as a study checklist)
- [ ] Install Nest CLI and scaffold a project
- [ ] Create a module, controller, and service
- [ ] Add a DTO and validate input with ValidationPipe
- [ ] Implement a simple Guard (e.g., API key)
- [ ] Create an Interceptor that logs request/response time
- [ ] Use ConfigModule and environment variables
- [ ] Write unit tests for a service and an e2e test for a controller

## Small examples (conceptual snippets)

Controller + Service (pattern)

```ts
// src/hello/hello.controller.ts
// ...existing code...
// Controller should call the service and return results
```

DTO + Validation

```ts
// src/hello/dto/create-hello.dto.ts
// class CreateHelloDto { @IsString() name: string }
```

Guard (simple API key)

```ts
// src/auth/api-key.guard.ts
// Implement CanActivate and check header or env
```

Interceptor (timing)

```ts
// src/common/interceptors/timeout.interceptor.ts
// Measure start/end and log duration
```

Notes: The snippets above are conceptual placeholders — expand them in your project under `src/` when practicing. If you want, I can add working example files to this repo.

## Mini exercises (hands-on)
1. Hello API
   - Create `HelloModule`, `HelloController` with GET /hello returning {message: 'hello'}
   - Add `HelloService` that returns the message
   - Acceptance: curl localhost:3000/hello returns JSON

2. Create user endpoint with validation
   - POST /users with DTO { name: string; age?: number }
   - Use ValidationPipe globally
   - Acceptance: invalid payload returns 400 with validation errors

3. API key guard
   - Add a Guard that requires header `x-api-key` to match an env var
   - Protect POST /users with the guard

4. Unit tests
   - Write a unit test for `HelloService` using Jest
   - Write an e2e test for GET /hello

5. Interceptor
   - Implement an interceptor that appends `X-Response-Time` header with ms

## Where to go next (resources)
- Official docs: https://docs.nestjs.com
- Bookmarked topics: Pipes, Guards, Interceptors, Exception Filters, DI, Testing
- Libraries commonly used: class-validator, class-transformer, @nestjs/config, @nestjs/typeorm, @nestjs/jwt

## Try it locally
1. Install deps: `npm install`
2. Start dev server: `npm run start:dev` (or `npm run start`)
3. Run tests: `npm test` (or `npm run test:e2e` if configured)

## Exercises acceptance & checks
- Build should run without TypeScript errors
- Validation should return HTTP 400 with errors
- Guard should return 401/403 when missing or wrong key
- Tests should run and pass locally

## Next steps I can take for you
- Create working example files under `src/hello` for exercises (controllers, services, DTOs, tests)
- Wire up ValidationPipe and a sample Guard in `src/main.ts`
- Add CI job that runs TypeScript build and tests

---
Created: NESTJS_LEARNING.md — a compact learning plan and checklist. Reply and I can add concrete example files to the repo if you'd like.
