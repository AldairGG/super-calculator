# Super Calculator

## Project overview
Angular 19 calculator app built as a teaching exercise. Students implement
three missing methods and write unit tests to make the full test suite pass.

## Tech stack
- Angular 19 (standalone components, no NgModules)
- TypeScript 5.7
- Karma + Jasmine for unit tests
- Node.js 18.x or 20.x required (Angular 19 does not support Node 22+)

## How to run
- Install dependencies: `npm install`
- Dev server: `npm start` → http://localhost:4200
- Run tests: `npm test`
- Production build: `npm run build`

## Project structure
- `src/app/app.component.ts` — all calculator logic (display, operators, exercises)
- `src/app/app.component.html` — button grid and display template
- `src/app/app.component.css` — dark mode styles + light mode overrides (Exercise 3)
- `src/app/app.component.spec.ts` — full unit test suite (Karma + Jasmine)
- `requirements.md` — student exercise instructions

## Exercises
Three methods in `app.component.ts` were intentionally left empty for students:
1. `pressToggleSign()` — flips the sign of the displayed number (5 → -5)
2. `pressPercent()` — divides the displayed number by 100 (50 → 0.5)
3. `toggleTheme()` — toggles `isLightMode` boolean; CSS in `app.component.css`
   uses the `.light` class (already bound in template) to apply light mode colors

## Coding conventions
- Standalone Angular components (no NgModule)
- Component state via class properties (`display`, `firstOperand`, `operator`, etc.)
- All calculator logic lives in `AppComponent` — no services or child components
- Tests call component methods directly (`component.pressDigit('5')`) then
  call `fixture.detectChanges()` before asserting on the DOM
