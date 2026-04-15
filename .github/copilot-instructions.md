# Project Guidelines

## Mandatory Development Checklist

Before finishing any code change, run all three:

- [ ] Lint: `dotnet format --verify-no-changes SocOps/SocOps.csproj`
- [ ] Build: `dotnet build SocOps/SocOps.csproj`
- [ ] Test: `dotnet test`

If tests are not present yet, still run `dotnet test` and report that no tests were discovered.

## Build and Run

- Run app: `dotnet run --project SocOps/SocOps.csproj`
- Local URL: `http://localhost:5166`
- SDK: .NET 10+

## Architecture

- App type: Blazor WebAssembly (`SocOps`)
- UI: `SocOps/Components/` and `SocOps/Pages/Home.razor`
- State orchestration: `SocOps/Services/BingoGameService.cs`
- Core bingo logic: `SocOps/Services/BingoLogicService.cs`
- Game content: `SocOps/Data/Questions.cs`

## Conventions

- Keep changes minimal and aligned with existing component/service split.
- Use dependency injection registration in `SocOps/Program.cs` for app services.
- Use existing utility CSS classes in `SocOps/wwwroot/css/app.css` before adding new styles.
- For UI redesign work, follow `.github/instructions/frontend-design.instructions.md`.

## Pitfalls

- Dev server can remain running after task interruption; verify with `curl -I http://localhost:5166` and `lsof -i :5166`.
- Deployment rewrites base href for GitHub Pages; local dev behavior should assume root `/`.

## Reference Docs

- Project overview and quick start: `README.md`
- Workshop flow: `workshop/GUIDE.md`
- Contribution process: `CONTRIBUTING.md`
- CSS utility guidance: `.github/instructions/css-utilities.instructions.md`