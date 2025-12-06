# Shipi18n Demo

**See autonomous localization in action.** Fork this repo, add your API key, change a string, and watch translations appear automatically.

## Try it in 2 minutes

### 1. Fork this repo

Click the **Fork** button above.

### 2. Add your API key

1. Get a free API key at [shipi18n.com](https://shipi18n.com) (takes 30 seconds)
2. In your forked repo, go to **Settings > Secrets and variables > Actions**
3. Click **New repository secret**
4. Name: `SHIPI18N_API_KEY`
5. Value: Your API key from shipi18n.com

### 3. Make a change

Edit `locales/en/home.json` - change any text:

```json
{
  "hero": {
    "title": "Build something amazing"
  }
}
```

Change "Build something amazing" to anything you want.

### 4. Push and watch

Commit your change. Within a minute, a **Pull Request** will appear with Spanish, French, and German translations.

That's it.

---

## What just happened?

When you pushed a change to `locales/en/`, the GitHub Action:

1. Detected the changed files
2. Called Shipi18n API to translate them
3. Created `locales/es/`, `locales/fr/`, `locales/de/` folders
4. Opened a PR with all the translations

**This is autonomous localization.** Set it up once, never think about translations again.

---

## See the demo

Open `src/index.html` in your browser to see the translations in action. Click the language buttons to switch.

---

## Project structure

```
locales/
├── en/           # You edit these (source of truth)
│   ├── common.json
│   └── home.json
├── es/           # Auto-generated
├── fr/           # Auto-generated
└── de/           # Auto-generated
```

---

## Customize for your project

### Change target languages

Edit `.github/workflows/translate.yml`:

```yaml
target-languages: 'es,fr,de,ja,zh,pt,ko'  # Add any of 100+ languages
```

### Add more files

Just create new JSON files in `locales/en/`. The action will pick them up automatically.

### Direct commit instead of PR

```yaml
create-pr: 'false'  # Translations commit directly to your branch
```

---

## Learn more

- [Shipi18n Documentation](https://shipi18n.com/api)
- [GitHub Action Reference](https://github.com/Shipi18n/shipi18n-github-action)
- [Pricing](https://shipi18n.com/pricing) - Free tier: 100 keys, 3 languages

---

## Free tier limits

This demo uses 2 files x ~15 keys = ~30 keys, well within the free tier (100 keys).

Your free tier includes:
- 100 translation keys
- 3 target languages
- Unlimited API calls (keys cached for 90 days)

[Upgrade](https://shipi18n.com/pricing) when you need more.

---

## Use this in your real project

Copy `.github/workflows/translate.yml` to your project and update the paths:

```yaml
source-dir: 'src/locales/en'      # Your English folder
output-dir: 'src/locales'          # Where translations go
target-languages: 'es,fr,de'       # Languages you need
```

That's all it takes.

---

**Built with [Shipi18n](https://shipi18n.com)** - Autonomous localization for developers.
