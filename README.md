# QuickBlazorSample

A minimal **Blazor WebAssembly** app that can be hosted entirely on **GitHub Pages**.

## How it works

- `dotnet publish` produces static files under `build/wwwroot`.
- The GitHub Actions workflow builds the app on every push to **main** and
  deploys those static files to the **Pages** environment.
- All C# runs in the browser via WebAssembly; no server required.

## One‑click setup

1. **Fork or clone** this repo.
2. Push to `main`.
3. In the repo Settings → Pages, choose **GitHub Actions** as the source.
4. Wait for the workflow to finish; your site will be live at

```
https://<your‑username>.github.io/<repo‑name>/
```

### Base href

If you’re deploying to **user** pages (`<username>.github.io`) keep `<base href="/" />` in *wwwroot/index.html*.

For **project** pages (`<username>.github.io/<repo>`), change it to

```html
<base href="/<repo>/" />
```

(or set `<StaticWebAssetBasePath>` in the `.csproj`).

## Local run

```bash
dotnet run
# or
dotnet watch run
```

Then open http://localhost:5000
