---
title: "Citing Your Papers in Web Pages/Posts"
subtitle: "For Lab Members"
redirect_from:
  - /resources-for-research/citing-your-papers-in-web-pages-posts/
---

<!-- Rewritten for the Jekyll site. The old page described the WordPress Papercite plugin, which no longer applies. -->

The old WordPress site used the Papercite plugin (`[bibshow]` / `[bibcite]` shortcodes). On this site, citations are plain Markdown:

1. **Put the PDF in the repo** (optional) under `assets/papers/`, named after its BibTeX key, e.g. `assets/papers/garcia2022.pdf`. Use long, specific keys to avoid name collisions.
2. **Cite in the text** with a numbered link to the reference list at the bottom of the page:

   ```markdown
   We found that our approach was awesome [[1]](#ref-garcia2022).
   ```

3. **Add a References section** at the end of the page, giving each entry an anchor that matches the link:

   ```markdown
   ## References

   1. <a id="ref-garcia2022"></a>Dan Garcia and Armando Fox. “Title of the Paper.” *SIGCSE 2022*, 2022. [PDF]({% raw %}{{ site.baseurl }}{% endraw %}/assets/papers/garcia2022.pdf)
   ```

See the [Faded Parsons project page]({{ site.baseurl }}/projects/faded-parsons/) for a working example. The source of every page is in the site's GitHub repository, under `content/`.
