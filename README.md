# DATA Team at DIENS Website

Welcome to the official repository of the DATA Team website. This site is collaboratively maintained by the team. If you're a team member, you can request access to this repository to pull and push changes. The website is built using [Jekyll](https://jekyllrb.com/) with [Bundler](https://bundler.io/), and hosted via the ENS server.

This README serves as a step-by-step guide for team members on how to modify and contribute to the website content. Below you'll find instructions for editing key sections of the site, including:

- The **Team** page
- The **Publications** page
- The **Jobs** page
- The **News** section on the home page

Make sure you have Ruby and Bundler installed before proceeding.

## How to Contribute

If you're a member of the team, request access to this repository. Once granted, you can simply pull the latest changes and push your updates directly to the repository.

Website deployment will eventually be automated. For now, if you make any updates that need to be reflected on the live site, please contact Alexandre Vérine.



## Editing the Team Page

To update or add members to the team page, edit the file `_data/team.yml`.

Each team member should be added using the following format:

```yaml
-
    lastname: Vérine    
    firstname: Alexandre
    url: https://www.alexverine.com
    profilepic: verine.png
    position: AI Reseach Fellow
    info: PSL
    category: postdoc
```

**Field descriptions:**
- `lastname`, `firstname`: The full name of the team member.
- `url`: Link to the member’s personal or professional website.
- `profilepic`: Path to the profile picture. This image should be formatted around 1800x1100 pixels (aspect ratio ~1.62), at 72 pixels/inch (or 28 pixels/cm). Place the image in `assets/img/team/lastname.png`.
- `position`: The academic or professional title (e.g., Professor, Researcher, PhD Student).
- `info`: Additional information such as institutional affiliation or funding source (e.g., CNRS, Collège de France).
- `category`: Use one of the following:
  - `feature` — for permanent team members
  - `postdoc`
  - `phd`
  - `intern`
  - `alumni`

**Note:** Only members with `category` set to `feature`, `postdoc`, or `phd` will have their profile pictures displayed on the website.


## Editing the Publications Page

To add a publication, insert a new BibTeX entry into the bibliography file (located in `_bibliography/papers.bib`). Use the following format:

```bibtex
@inproceedings{verine2025changetheloss,
	title     = {Improving Diversity in Language Models: When Temperature Fails, Change the Loss},
	author    = {Alexandre Verine and Florian Le Bronnec and Kunhao Zheng and Alexandre Allauzen and Yann Chevaleyre and Benjamin Negrevergne},
	booktitle = ICML,
	year      = {2025},
	url       = {https://icml.cc/virtual/2025/poster/45259},
	preview   = {2025-icmlverine.png}
}
```

### Field descriptions
- `@article` or `@inproceedings`: Choose based on the type of publication.
- `title`: Title of the paper.
- `author`: Authors, separated by `and`.
- `year`: Year of publication.
- `journal`: For `@article` entries, use one of the predefined strings below.
- `booktitle`: For `@inproceedings` entries (e.g., conference name).
- `url`: Link to the official page or repository.
- `code` (optional): URL to the code repository.
- `pdf` (optional): Direct link to the PDF (e.g., on arXiv).
- `preview`: Path to an image representing the paper (stored in `assets/img/publication_previews/`).

### Image Format
Images for the `preview` field should be placed in:
```
assets/img/publication_previews/
```
Use the naming format:
```
YYYY-conflastname.png
```
Example:
```
2025-icmlverine.png
```

### Predefined Conference and Journal Strings
Use the following predefined strings for `journal` or `booktitle` fields. You may also add new ones using:

```bibtex
@string{NEWCONF = {NEWCONF}}
```

Example predefined strings:
```bibtex
@string{ICML = {ICML}}
@string{NeurIPS = {NeurIPS}}
@string{ICCV = {ICCV}}
```


## Editing the Jobs Page

To update the Jobs page, directly edit the Markdown file located at `_pages/jobs.md`.

Job offers should be added as a bulleted list using `*`. Each entry should include:
- A descriptive text
- A date (if applicable)
- A link using `[text](url)` format
- Strike-through formatting (`~~text~~`) for fulfilled positions

### Example

```markdown
* [Postdoctoral Researcher in Machine Learning](https://example.com/job-postdoc) – Apply before October 1st, 2025
* ~~[Research Intern – Summer 2025](https://example.com/internship) – Position filled~~
```

would render as:

* [Postdoctoral Researcher in Machine Learning](https://example.com/job-postdoc) – Apply before October 1st, 2025
* ~~[Research Intern – Summer 2025](https://example.com/internship) – Position filled~~

Make sure to commit and push the changes once you're done editing.

## Editing the News Section (Home Page)

To add a news item that appears on the homepage, create a new Markdown file in the `news/` directory.

The filename must begin with the date in the format: `YYYY-MM-DD-title.md`

Example:
```
news/2025-06-11-website.md
```

### Post Template

Use the following template when creating a new post:

```markdown
---
layout: post
date: 2025-06-15 00:00:00-0400
inline: true
---

We are excited to announce the launch of our new website! The DATA team has been working hard to create a more user-friendly and visually appealing platform.
```

### Notes
- The `layout` must be set to `post`.
- The `date` should reflect the intended publication date.
- The `inline: true` tag ensures the news item is displayed on the homepage.
- The body of the file contains the announcement content in standard Markdown.

Once the file is added and committed, it will automatically appear in the news section on the homepage.
