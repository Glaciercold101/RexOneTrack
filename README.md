# Rex One Track website

This folder contains the separate, framework-free GitHub Pages site. `docs/index.html` is self-contained: styles and interactive-preview behavior are inline, and it uses no remote assets, third-party runtime dependencies, tracking, file uploads, or network calls. It is not the application's UI; keep the package-root `index.html`, `bin/index.html`, wrapper sources, and bundle artifacts unchanged.

## Configure the Windows download

Publish the complete Windows app bundle as an asset on a GitHub Release. The repository's `bin` path is not a downloadable asset path when GitHub Pages is published from `/docs`. A convenient release asset is a ZIP with the contents of `bin` at its root, preserving `html-wrapper.exe`, `index.html`, and `ffmpeg\bin\ffmpeg.exe` plus `ffmpeg\bin\ffprobe.exe` side by side in the package layout.

In `docs/index.html`, set the single `RELEASE_DOWNLOAD_URL` constant near the bottom to the direct HTTPS URL of that release asset, for example the URL copied from the published asset's download link. The download button stays clearly disabled until the value is a GitHub URL; no owner, repository, or release URL is assumed.

## Publish with GitHub Pages

1. Push the site files to the repository's default branch.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the default branch and the `/docs` folder, then save.
5. Wait for the Pages deployment to finish and open the site URL shown in the Pages settings.

Publishing steps do not publish the Windows app automatically. Attach the app bundle to a GitHub Release separately, then configure the constant above. This site has not been deployed by this package.
