# PaperPulse — Cancer Cell Biology Feed

A personal research paper feed that pulls the latest publications from selected journals and bioRxiv preprint categories. Built as a single HTML file, hosted on GitHub Pages.

**Live site:** `https://yourusername.github.io/paperpulse`

---

## How to Add a New Journal

Open `index.html` in any text editor and find the section near the top of the `<script>` block.

### Standard journals (PubMed-indexed)

Find the line that reads `const PUBMED_JOURNALS` and add a new entry inside the array, following this pattern:

```js
{ id:'nejm', name:'NEJM', search:'"N Engl J Med"[ta] AND (cancer[tiab] OR tumor[tiab])', color:'#ff7043', textColor:'#ff7043', bg:'rgba(255,112,67,0.08)' },
```

| Field | What it does |
|---|---|
| `id` | A unique short identifier, no spaces (e.g. `nejm`) |
| `name` | Display name shown on cards and filter buttons |
| `search` | PubMed query. `[ta]` is the journal abbreviation — look it up at [ncbi.nlm.nih.gov/nlmcatalog](https://www.ncbi.nlm.nih.gov/nlmcatalog) |
| `color` | Hex color for the journal badge |
| `bg` | Same color at low opacity, e.g. `rgba(255,112,67,0.08)` |

**Tip:** To find the correct PubMed abbreviation for any journal, search its full name at [ncbi.nlm.nih.gov/nlmcatalog](https://www.ncbi.nlm.nih.gov/nlmcatalog) and look for the *"Abbreviated Title"* field.

---

### bioRxiv preprint categories

Find the line that reads `const BIORXIV_CATS` and add a new entry:

```js
{ id:'biorxiv-cellbio', name:'bioRxiv · Cell Bio', category:'cell biology', color:'#ce93d8', textColor:'#ce93d8', bg:'rgba(206,147,216,0.08)', isPreprint:true },
```

The `category` field must exactly match one of bioRxiv's official subject categories (lowercase). Browse the full list at [biorxiv.org/collection](https://www.biorxiv.org/collection).

---

## How to Update the Site After Editing

1. Go to this repository on GitHub
2. Click `index.html` → click the **pencil (Edit) icon**
3. Make your changes directly in the browser
4. Click **Commit changes**

GitHub Pages will rebuild automatically within 1–2 minutes. The URL does not change.

---

## Current Sources

**Journals**
- Nature, Cell, Science
- Nature Cell Biology, Nature Biotechnology
- Cell Metabolism, Cancer Cell
- PNAS, Journal of Cell Biology, Biophysical Journal

**bioRxiv Preprints**
- Cancer Biology, Biophysics, Synthetic Biology

---

## Notes

- Papers are fetched live on page load via the PubMed E-utilities API and bioRxiv API — both free, no API key required.
- Covers the last 30–60 days of publications.
- Clicking **Open Paper** goes directly to the official journal page via DOI.
- Dates shown are the online publication date, not the print issue date.
