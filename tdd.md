## TDD.md

/website-root/
|
├── index.html          <-- Home
├── about.html          <-- Thoughts/Expertise
├── projects.html       <-- Projects
├── resources.html      <-- Resources
|
└── /css/
    |
    └── style.css       <-- Global Styles

```

###2. Required Pages and Navigation Elements| Page Name | File Name | Unique Content | Navigation Link Text (Button) |
| --- | --- | --- | --- |
| **Home** | `index.html` | Introduction | Home |
| **Thoughts** | `about.html` | Expertise and long-form thoughts | Thoughts |
| **Projects** | `projects.html` | List of owner's projects | Projects |
| **Resources** | `resources.html` | List of helpful links | Resources |

**Navigation Bar Requirement:** The navigation element (`<nav>`) must be present and identical on all four pages, containing the four links listed above.

###3. Content Storage (The Static "Database" Schema)Since there is no dynamic data or database, all "data" (content) is stored directly within the HTML files as static text.

| Data Type | Storage Location | HTML Element Type | Examples of Stored Data |
| --- | --- | --- | --- |
| **Introduction Text** | `index.html` | `<p>` | "Hi, I'm [Name]. I build things." |
| **Thought/Expertise** | `about.html` | `<h1>`, `<p>` | "My Philosophy on design...", "My expertise area is..." |
| **Project List Item** | `projects.html` | `<li>` inside `<ul>` | "Project Alpha: Description of work." |
| **Resource Links** | `resources.html` | `<a>` inside `<li>` | "Resource 1: Link to external article." |
| **Global Style Rules** | `css/style.css` | CSS Selectors | `body { font-family: sans-serif; }` |

###4. Application Routes (Web Addresses)The application uses local, relative routing entirely based on file names.

| Route (URL Path) | Corresponds to File |
| --- | --- |
| `/` or `/index.html` | `index.html` |
| `/about.html` | `about.html` |
| `/projects.html` | `projects.html` |
| `/resources.html` | `resources.html` |

###5. Test Suite (TDD)Each file/feature must pass the following tests.

####A. Global Structure & Consistency Tests| Test ID | Feature | Description | Pass Condition |
| --- | --- | --- | --- |
| **G-01** | File Structure | All required files and folders are present. | `index.html`, `about.html`, `projects.html`, `resources.html` exist at root; `style.css` exists in `/css/`. |
| **G-02** | CSS Linkage | The stylesheet is correctly linked on every page. | Every HTML file contains `<link rel="stylesheet" href="css/style.css">` inside `<head>`. |
| **G-03** | Navigation | The navigation menu is consistent and functional. | The `<nav>` element is identical on all four HTML files, and all four links navigate correctly to their corresponding page. |
| **G-04** | Responsiveness | The layout adapts for small screens. | **CSS Test:** `style.css` includes at least one `@media screen and (max-width: ...)` block to adjust layout (e.g., stack navigation items). |

####B. Page Content Tests| Test ID | Page | Description | Pass Condition |
| --- | --- | --- | --- |
| **C-01** | Home | Page displays unique introductory content. | `index.html` has an `<h1>` and at least one `<p>` of introductory text. |
| **C-02** | Thoughts | Page displays content related to expertise. | `about.html` has an `<h1>` and a substantial section of placeholder text. |
| **C-03** | Projects | Page displays a clear list of projects. | `projects.html` has an `<h1>` and uses an unordered list (`<ul>`) to contain at least three project placeholders. |
| **C-04** | Resources | Page displays a list of external resources. | `resources.html` has an `<h1>` and uses an unordered list (`<ul>`) where each list item contains an external link (`<a href="http://...">`). |

####C. Constraint Tests| Test ID | Constraint | Description | Pass Condition |
| --- | --- | --- | --- |
| **X-01** | Technology | Checks for unauthorized code. | **No JavaScript:** No `<script>` tags exist in any of the four HTML files. |
| **X-02** | Contact | Checks for required contact methods. | **No Contact:** No `mailto:` links exist in any of the four HTML files. |

###6. Configuration (.env Placeholder)Since this project is pure static HTML/CSS, no server-side or front-end configuration variables are needed.

```
# This project is a barebones, static website using only HTML and CSS.
# Therefore, an .env file for dynamic configuration is **Not Applicable (N/A)**.

```

---