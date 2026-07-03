# DUAL Group Website

This repository contains the website for the Distributed compUting, optimizAtion, and Learning (DUAL) Group at the University of Sydney.

The site is built with Jekyll and the al-folio theme runtime, with content managed through Markdown, BibTeX, and YAML data files.

## Main Content

- Home: `_pages/about.md`
- Research and publications: `_pages/publications.md` and `_bibliography/papers.bib`
- Projects: `_pages/projects.md` and `_projects/`
- People: `_pages/profiles.md` and `_members/`
- Contact: `_pages/contact.md`
- Images: `assets/img/`

## Local Preview

The recommended local workflow uses Docker:

```bash
docker compose pull
docker compose up
```

Then open `http://localhost:8080`.

## Deployment

The default deployment target is GitHub Pages:

```text
https://dual-grp.github.io/dual/
```

For this project-page deployment, `_config.yml` should use:

```yaml
url: https://dual-grp.github.io
baseurl: /dual
```

The future preferred institutional domain is `dual.sydney.edu.au`, pending University of Sydney DNS approval and configuration.
