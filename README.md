<img width="1024" height="559" alt="17820270065978019585162811965864" src="https://github.com/user-attachments/assets/a5c3b19b-2e8e-4b17-844e-d835279dc09d" />


**FYRE Kitchens is Matron Jade's LIVE cooking content on TikTok.**
Videos posted daily, recipes updated weekly for the community.

Hood fusion. WWII-era resourcefulness. East meets west. Cast iron always welcome.

## What this is

A single-page recipe book built live alongside Jade's TikTok cooking streams. Every recipe in here started as a photo of whatever was on the counter that day — and got built into a full recipe, cooked on camera, and added to the book.

No filler, no fluff. Just real recipes from a real kitchen.

## Live site

Deployed on Vercel: _add your live URL here once deployed_

## Structure

This is a single HTML file (`fyred-up-kitchens.html`) — no build step, no dependencies, no framework. Open it in a browser and it just works.

```
fyred-up-kitchens.html   ← the whole site
```

### Navigation

Recipes are organized into FYRE Army—themed sections:

| Section | What's in it |
|---|---|
| 🏕️ **Field Kitchen** | Everything, all recipes |
| 🍖 **Mess Hall** | Mains & dinners |
| 🍞 **Commissary** | Breads & staples |
| 🥬 **Chow Line** | Sides & salads |
| 🍍 **Sweet Relief** | Desserts & snacks |
| 🥤 **Canteen** | Drinks & wellness |

The homepage hero features **This Week's Rations** — whatever's newest gets pinned to the top automatically.

## Updating the recipe book

All recipes live in one JavaScript array near the bottom of the HTML file, inside the `<script>` tag:

```js
const recipes = [
  {
    id: 28,                          // next unused number
    section: 'sweet',                // mess | commissary | chow | sweet | canteen
    isNew: true,                     // true = shows in "This Week" + NEW badge
    date: 'June 27',
    tag: 'Dessert · Cookies',
    title: 'Recipe Name',
    desc: 'Short hook description, 1-2 sentences.',
    time: '~20 min',
    serves: '4',
    notes: "Jade's field notes — tips, swaps, warnings.",
    ingredients: ['1 cup flour', '2 eggs', '...'],
    steps: ['Step one.', 'Step two.', '...']
  },
  // ...rest of the recipes
];
```

**To add a new recipe each week:**

1. Pick the next `id` number (highest existing `id` + 1)
2. Set `isNew: true` on the new recipe
3. Set `isNew: false` on whatever was `true` last week (only the newest should be featured)
4. Paste the new recipe object into the array, in the right `section`
5. Save and redeploy

The recipe counts in the nav sidebar and the homepage stat number are calculated automatically from the array — no manual counting needed.

## Photos

Real counter shots from the live streams live alongside the HTML file:

```
hero.jpg
counter-naan.jpg
counter-ingredients.jpg
counter-ramen.jpg
```

Swap `hero.jpg` for whatever the current hero image should be — it's referenced directly in the CSS (`.hero-bg { background-image: url('hero.jpg'); }`).

## Deploying

This is a static site — no build step required.

**Vercel:**
1. Push this repo to GitHub
2. Import the repo in Vercel
3. Framework preset: **Other**
4. Output directory: leave blank (root)
5. Deploy

That's it. Every push to `main` auto-redeploys.

## License

Recipes and content © Matron Jade / FYRE Kitchens. Built live, one stream at a time. 🔥
