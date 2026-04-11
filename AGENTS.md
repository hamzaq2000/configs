# General
- Don't run full builds after trivial changes.
- Unless otherwise stated, do not care _at all_ about backwards compatibility; do not add fallbacks etc. in code in the name of backwards compability. 

# SwiftUI
- Be careful with `@Query`. It is good for a view's primary, owned state, but avoid using it for unrelated or secondary data sources just for derived/cosmetic behavior.
  Do not use `@Query` for high-churn data. High-churn sources should be fetched explicitly, cached in plain state if needed, and refreshed only at deliberate times.
  Example: if scrolling a screen triggers prefetching or snapshot updates, a separate view using `@Query` on that same data can be invalidated repeatedly, causing recomputation/reloads and hurting scroll performance.

# Python
- For Python projects, always use `uv` with Python version 3.13
- For one off Python scripts, make sure to use `python3` instead of `python`
- For one off Python scripts that need dependancies (other than standard ones), use `uv` with the `--with` option, or a temp venv with Python version 3.13 if there are a non-trivial amount of dependancies.
- Only deviate from Python version 3.13 to a version lower if there is some dependancy that doesn't support 3.13 yet, or other such dependancy related problems caused by too new a Python version.
