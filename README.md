# NUS APEX – Past Sessions

Source for the Past Sessions page of the NUS APEX Google Site.

- Live page: https://www.sunfengfei.com/apex-sessions/
- Embedded in Google Sites by URL; no republishing needed after updates.

## Files

| File | Purpose |
|---|---|
| `sessions.json` | All session data. **This is the only file you normally edit.** |
| `index.html` | Layout, styles, field filter. Loads `sessions.json` on every visit. |

## Adding a session

1. Open `sessions.json` on GitHub and click the pencil icon to edit.
2. Add an entry at the **top** of the right semester's `sessions` list (newest first):

   ```json
   {
     "date": "2026-11-06",
     "author": "Name",
     "affiliation": "NUS",
     "title": "Paper title",
     "fields": ["IndustrialOrganization"],
     "abstract": "Plain text abstract."
   },
   ```

3. Commit to `main` (or open a pull request). The page updates within a few minutes.

For a new semester, add a block at the **top** of the file:

```json
{
  "semester": "2027 Spring",
  "sessions": [ ... ]
},
```

## Field keys

Use these exact keys in `fields`:

| Key | Label |
|---|---|
| `BehavioralandExperiment` | Behavioral & Experiment |
| `Development` | Development |
| `EconomicHistory` | Economic History |
| `EnvironmentalandResource` | Environmental & Resource |
| `Health` | Health |
| `IndustrialOrganization` | Industrial Organization |
| `InnovationandGrowth` | Innovation & Growth |
| `LaborandEducation` | Labor & Education |
| `PublicandPoliticalEconomy` | Public & Political Economy |
| `TransportandUrban` | Transport & Urban |

To add a new field, edit `index.html` in two places: add a `.chip` button in the filter bar and a `.tag-<Key>` color rule in the `<style>` block.

## Troubleshooting

- **"Sessions could not be loaded"**: `sessions.json` has a syntax error, usually a missing or extra comma or an unmatched quote. Paste the file into https://jsonlint.com to find it.
- **Change not showing**: wait a few minutes for GitHub Pages to deploy (see the repo's **Actions** tab), then hard-refresh (Ctrl+Shift+R / Cmd+Shift+R).
