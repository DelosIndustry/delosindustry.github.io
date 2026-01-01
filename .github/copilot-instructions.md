# GitHub Copilot Instructions for DelosIndustry Blog

This repository hosts a Jekyll-based blog using the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme, deployed on GitHub Pages.

## 🏗 Project Architecture & Key Components

- **Core Framework**: Jekyll (Ruby-based static site generator).
- **Theme**: `minimal-mistakes` (configured as a remote theme in `_config.yml`).
- **Navigation**: Defined in `_data/navigation.yml`. This drives the sidebar menu.
- **Content Organization**:
  - `_posts/`: Blog entries following `YYYY-MM-DD-title.md`.
  - `_pages/`: Static pages and **category archive pages**.
  - `assets/`: Custom assets, primarily `css/main.scss` for theme overrides.

## 🧭 Navigation & Category Logic (Crucial Pattern)

The site uses a specific pattern to simulate hierarchical categories (Category > Subcategory) using a combination of **Categories** and **Tags**.

1.  **Sidebar Structure**: Defined in `_data/navigation.yml` under `sidebar-category`.
2.  **Archive Pages**: Located in `_pages/categories/`.
    - **Main Category Page** (e.g., `paper-review.md`): Filters posts by `category`.
    - **Subcategory Page** (e.g., `paper-review-cv.md`): Filters posts by **Main Category** AND **Specific Tag**.

**Example: "Paper Review > Computer Vision"**
- **Navigation**: URL `/categories/논문리뷰/CV/`
- **Page File**: `_pages/categories/paper-review-cv.md`
- **Liquid Logic**:
  ```liquid
  {% assign posts = site.posts
    | where_exp: "post", "post.categories contains '논문리뷰'"
    | where_exp: "post", "post.tags contains 'Computer Vision'"
    | sort: "date"
    | reverse
  %}
  ```
- **Post Front Matter**:
  ```yaml
  categories:
    - 논문리뷰
  tags:
    - Computer Vision
  ```

## 📝 Content Creation Workflow

### New Post Checklist
1.  Create file in `_posts/` with format `YYYY-MM-DD-english-slug.md`.
2.  **Front Matter Requirements**:
    ```yaml
    ---
    title: "Korean Title"
    date: YYYY-MM-DD
    categories:
      - MainCategoryName
    tags:
      - SubCategoryTag
      - OtherTag
    ---
    ```
3.  **Images**: Store in `assets/images/`. Use absolute paths or relative paths consistent with Jekyll.

### New Category/Page
1.  Create markdown file in `_pages/` (or `_pages/categories/`).
2.  Set `permalink` to match `_data/navigation.yml`.
3.  Enable sidebar:
    ```yaml
    sidebar:
      nav: "sidebar-category"
    ```

## 🎨 Styling & Theme Overrides

- **Do not edit theme files directly.**
- **Entry Point**: `assets/css/main.scss`.
- **Pattern**: Define SCSS variables *before* importing the theme.
  ```scss
  $max-width: 1680px; // Custom override
  @import "minimal-mistakes/skins/{{ site.minimal_mistakes_skin | default: 'default' }}";
  @import "minimal-mistakes";
  ```

## 🛠 Development Commands

- **Install Dependencies**: `bundle install`
- **Local Server**: `bundle exec jekyll serve` (Access at `http://localhost:4000`)
