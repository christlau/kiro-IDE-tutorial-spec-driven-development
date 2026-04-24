Create a steering file at .kiro/steering/engineering-best-practices.md 
with the following rules that must always be followed throughout this project:

## Git Practices
- After completing each task from tasks.md, immediately run `git add .` and 
  `git commit -m "[descriptive message]"` even if no remote repository is configured
- Use conventional commit format: feat:, fix:, chore:, docs:
- Never leave uncommitted changes when moving to the next task

## Testing
- Write at least one unit test per utility function and one integration test 
  per API route
- Keep test files lean — maximum 3 test cases per file to conserve tokens
- Use Jest for unit tests and Playwright or Supertest for API tests
- Test files go in __tests__/ folder next to the file being tested

## Security
- At the end of the entire vibe coding session, perform a security review:
  check for hardcoded secrets, missing input validation, unprotected API routes, 
  and missing authentication middleware
- Never commit .env files
- Always validate and sanitize user inputs on the server side

## Documentation
- Maintain a README.md at the project root, updated after every major feature
- README must include: project description, tech stack, how to run locally, 
  environment variables needed, and folder structure overview

## Code Quality
- Always use TypeScript strict mode
- All components must be functional React components
- Use Tailwind CSS for all styling — no inline styles
- Primary UI language is Bahasa Indonesia; admin panel uses English labels
