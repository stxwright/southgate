# Southgate Cycling Club Website

A modern, high-performance Hugo-based website for Southgate Cycling Club.

## 🚀 Quick Start

1. **Start the local server:**
   ```powershell
   ./start.ps1
   ```
2. **View your site:**
   Open [http://localhost:1313](http://localhost:1313) in your browser.

---

## 🛠️ Content Management

### 📅 Managing Rides (The Calendar)
All rides are stored in `content/rides/`.
1. **Add a new ride**: Copy an existing `.md` file in that folder.
2. **Name the file**: Use the date format `YYYY-MM-DD-ride-name.md`.
3. **Link a Route**: In the frontmatter, set `route: "route-X"` (e.g., `route: "route-7"`) to automatically pull in the map and distance from the Route Library.
4. **Visibility**: Rides remain visible on the site from **6 days ago** through all future dates.

### 🗺️ Managing the Route Library
Routes are managed as a "repository" via a central spreadsheet.
1. **Update list**: Edit `routes.csv`.
2. **Sync changes**: Run the generator:
   ```powershell
   python generate_routes.py
   ```
3. This will create/update the numbered files in `content/routes/`. These pages are simple stats + RideWithGPS links.

### 📰 Adding Gazette Articles
1. Create a new markdown file in `content/gazette/`.
2. Ensure you include a `title`, `date`, `author`, and `image` path in the frontmatter.
3. These will automatically appear on the Gazette news page.

---

## 📸 Images & Galleries

All images are stored locally in `static/images/` to avoid external dependencies.
*   `/gallery/` - General club photos.
*   `/hillclimb/` - Photos for the dedicated Hill Climb page.
*   `/kit/` - Club jersey and gear photos.
*   `/history/` - Historical heritage photos.
*   `/gazette/` - Images for news articles.

**Lightbox**: Images in the Gallery, Kit, and Hill Climb sections automatically support full-screen viewing when clicked.

---

## 📁 Key File Structure
- `content/` - The core content (Rides, Routes, Gazette, History, etc.).
- `layouts/` - HTML templates defining the design.
- `static/` - All static files (Images, CSS, and the `hugo.exe` binary).
- `hugo.toml` - The main configuration file (Menu management, Site metadata, Social links).
- `generate_routes.py` - Script to turn the CSV into route pages.

---

## 🚢 Deployment
The site is built for **GitHub Pages**.
1. Commit your changes to the `main` branch.
2. The GitHub Action will automatically build the site and deploy it.

---
Content © Southgate Cycling Club. Established 1882.
