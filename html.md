<link rel="stylesheet" href="./style.css">

# HTML Interview Preparation Guide (0–3 years)

## Contents:

**Section A — Basic (≈ 30 Q&A)**

**Section B — Medium (≈ 40 Q&A)**

**Section C — Advanced (≈ 40 Q&A)**

**Section D — Practical coding tasks (with short sample answers)**

**Section E — Quick Revision Sheet (one-page style)**

**Section F — Practice resources & further reading**

# Section A — Basic HTML

1. What is HTML?

    HTML (HyperText Markup Language) is the standard markup language for creating web pages. It describes the structure and content of a page using elements (tags). Browsers parse HTML to render the page.

    **Why it matters:** It’s the skeleton — without correct HTML, accessibility, SEO and CSS/JS behaviors suffer.
    Example:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <title>My Page</title>
    </head>
    <body>
        <h1>Hello, world</h1>
        <p>This is HTML.</p>
    </body>
</html>
```

2.  What does `<!DOCTYPE html>` do?

    Declares the document as HTML5 and instructs browsers to render in standards mode (not quirks mode). Put it at the top of the document. No closing tag.

3.  What is the basic structure of an HTML document?

    `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`. The `<head>` contains metadata (title, meta tags, links), and `<body>` contains visible content.

4.  What is a tag vs an element vs an attribute?

    Tag: the markup like `<p>` or `</p>`.

    Element: the start tag, content, and end tag together (e.g., `<p>text</p>`).

    Attribute: extra information inside a start tag `<img src="pic.png" alt="...">`.

5.  What are semantic elements? Give examples.
    Semantic elements convey meaning about their contents to browsers and assistive tech: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`. Use them instead of generic `<div>` to improve accessibility and SEO.

6.  What is the difference between block and inline elements?

    Block-level elements (e.g., `<div>`, `<p>`, `<h1>`) start on a new line and can have width/height.

    Inline elements (e.g., `<span>`, `<a>`, `<strong>`) do not break the flow and usually only occupy as much width as their content.

7.  What is an HTML attribute? Provide common examples.

    Attributes provide additional info about an element. Examples: id, class, src, alt, href, title, data-_, aria-_.
    Example:

    ```html
    <img src="avatar.png" alt="User avatar" width="50" height="50" />
    ```

8.  What is the alt attribute and why is it important?

    alt provides alternative text for images for screen readers and when images fail to load. Critical for accessibility and SEO.

9.  What is the difference between id and class?

    id should be unique in the page and often used for single elements or JavaScript hooks. class can be reused on multiple elements and is mainly for styling and grouping.

10. How do you create a hyperlink?

    ```html
    <a href="https://example.com" target="_blank" rel="noopener noreferrer"
        >Visit</a
    >
    ```

    `target="\_blank"` opens in a new tab; `rel="noopener noreferrer"` prevents security issues and avoids giving the new page access to the opener window.

11. How do you include an image?

    ```html
    <img src="image.jpg" alt="Description" width="300" />
    ```

    Prefer relative or absolute URLs and always include alt.

12. What is the difference between `<b>` and `<strong>`; `<i>` and `<em>`?

    `<b>` and `<i>` are purely presentational (bold/italic). `<strong>` and `<em>` are semantic — they indicate importance/emphasis and are preferred for meaning and accessibility.

13. How to make a list? Ordered and unordered.

    ```html
    <ul>
        <li>Item</li>
    </ul>
    ```

    ```html
    <ol>
        <li>First</li>
        <li>Second</li>
    </ol>
    ```

14. How to make a table? When should you use tables?

    Use `<table>` for tabular data only (not for layout).
    Example:

    ```html
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Age</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Yash</td>
                <td>25</td>
            </tr>
        </tbody>
    </table>
    ```

15. What are form elements: basic tags?

    `<form>`, `<input>`, `<textarea>`, `<select>`, `<option>`, `<button>`, `<label>`. Use label with for to link to input id for accessibility.

16. Explain input types: text, email, password, number, checkbox, radio, file, hidden.

    Input type defines allowed content and browser behavior (e.g., email validates format, number shows numeric keyboard on mobile). Use appropriate types to improve UX and reduce JS validation.

17. How do you associate a `<label>` with an `<input>`? Why?

    Use for attribute on label:

    ```html
    <label for="username">Username</label>
    <input id="username" name="username" type="text" />
    ```

    This improves accessibility — clicking the label focuses the input; screen readers announce the label.

18. What is the `required` attribute on forms?

    `required` makes an input mandatory and triggers browser validation before form submission.

19. What is `placeholder` vs `label`?

    `placeholder` is temporary hint text inside the field; a `label` is permanent and accessible. Rely on labels, not placeholders, for accessibility.

20. Explain `method="GET"` vs `method="POST"` in forms.

    `GET` : appends form data to URL (suitable for non-sensitive queries, bookmarkable).

    `POST` : sends data in request body (suitable for sensitive data or large payloads).

21. What is a meta charset tag and why include it?

    `<meta charset="utf-8">` sets character encoding to UTF-8 to ensure correct display of characters. Put it near top of `<head>`.

22. What is viewport meta tag and why important for mobile?

    ```html
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    ```

    ensures the page scales to device width, crucial for responsive design.

23. What is the difference between `<head>` and `<body>`?

    `<head>` contains metadata, links to styles/scripts, and `<title>`. `<body>` contains content rendered on the page.

24. How do you include external CSS and JavaScript?

    CSS: `<link rel="stylesheet" href="styles.css">` inside `<head>`.
    JS: `<script src="app.js"></script>` (place before `</body>` or use defer/async).

25. What is the `rel` attribute on `<link>`? Example values.

    `rel` describes relationship between current document and linked resource (e.g., stylesheet, icon, manifest, preload).

26. What is an HTML comment?

    `<!-- This is a comment -->`. Not shown in the rendered page.

27. What is the purpose of the `<title>` element?

    Sets the page title shown in the browser tab and used by search engines.

28. What is the difference between `<div>` and `<span>`?

    `<div>` is block-level; `<span>` is inline. Both are non-semantic and used for layout/styling.

29. What is `data-\*` attribute for?

    Custom data attributes to store extra info on DOM elements (`data-id="123"`). Useful for JS without polluting semantics.

30. What is accessibility (a11y) in HTML? What are ARIA roles?

    Accessibility ensures content is usable by people with disabilities. ARIA roles/attributes (e.g., `role="navigation", aria-label, aria-hidden`) enhance semantics for assistive technologies when native elements aren’t sufficient.

# Section B — Medium HTML

31. How do you include a favicon?

    ```html
    <link rel="icon" href="/favicon.ico" type="image/x-icon" />
    ```

    you can provide apple-touch-icon and SVG icons too.

32. Explain absolute vs relative URLs.

    **Absolute**: full URL `https://example.com/img.png`.

    **Relative**: relative to page location `/images/img.png` or `../img.png`.

33. What is the `picture` element and when to use it?

    `<picture>` allows responsive images and art direction. It contains multiple `<source>` elements with media queries and a fallback `<img>`. Use when you want different crops/art for different sizes.

    ```html
    <picture>
        <source media="(min-width: 800px)" srcset="large.jpg" />
        <source media="(min-width: 400px)" srcset="medium.jpg" />
        <img src="small.jpg" alt="Example" />
    </picture>
    ```

34. Explain `srcset` and `sizes`.

    `srcset` provides multiple image files with width descriptors (e.g., image-400.jpg 400w).

    `sizes` tells the browser how wide the image will be in different viewport conditions so it can choose the best source. This saves bandwidth.

35. How do you make an element focusable?
    Use interactive elements `<a>`, `<button>`, `<input>` or add `tabindex="0"` to make it focusable; `tabindex="-1"` makes it focusable programmatically but not via Tab key.

36. Explain download attribute on `<a>`.

    download tells the browser to download the linked resource instead of navigating to it:

    ```html
    <a href="/files/resume.pdf" download="Yash_Resume.pdf">Download</a>
    ```

37. What is progressive enhancement vs graceful degradation?

    Progressive enhancement: build a basic, functional baseline and layer on advanced features for capable browsers.

    Graceful degradation: build for modern browsers then ensure fallbacks for older ones. Progressive enhancement is usually preferred.

38. How to embed a video/audio in HTML?

    ```html
    <video controls>
        <source src="video.mp4" type="video/mp4" />
        Your browser does not support video.
    </video>
    ```

    ```html
    <audio controls>
        <source src="audio.mp3" type="audio/mpeg" />
    </audio>
    ```

    Include multiple formats for broader compatibility.

39. What are web storage options in HTML5?
    A
    `localStorage` (persistent), `sessionStorage` (per tab), and `IndexedDB` (structured storage). They are used from JS — not direct HTML tags, but expect interviews to ask about them.

40. How to make a link open in a new tab securely?

    Use `target="\_blank"` and `rel="noopener noreferrer"` to prevent the new page from accessing the opener via window.opener.

41. Explain `defer` and `async` attributes on script tags.

    **defer** : loads script in the background and executes after HTML parsing finishes, maintaining order.

    **async** : loads in background and executes as soon as it’s ready (order is not guaranteed).

    Both help performance vs blocking scripts.

42. What are `meta` tags for SEO and social sharing?

    Basic SEO tags:`<meta name="description" content="...">`,

    Open Graph tags `<meta property="og:title" content="...">` for social previews, Twitter Card tags.

43. How does the `rel="preload"` or `preconnect` help performance?

    `preload` hints browser to fetch a resource early;

    `preconnect` opens connections to critical domains early to reduce latency. Use for fonts, critical images, or third-party resources.

44. How to implement `lazy-loading` of images?

    Use native `loading="lazy"`:

    ```html
    <img src="large.jpg" loading="lazy" alt="..." />
    ```

    For complex scenarios use Intersection Observer in JS.

45. How do you implement forms with validation?

    Use HTML5 validation attributes `required`, `min`, `max`, `pattern`, `type="email"` and supplement with JS for custom validation and server-side checks to be safe.

46. What is method override in forms?

    HTML forms support only `GET` and `POST`. To use PUT/DELETE, servers sometimes accept a hidden input \_method and treat the request accordingly. This is server convention, not HTML standard.

47. Explain `rel="noopener noreferrer"` — why both?

    `noopener` prevents window.opener assignment (security).

    `noreferrer` also prevents sending the Referer header. Some older browsers only support noreferrer.

48. What is `CORS` and does it relate to HTML?

    `CORS` (Cross-Origin Resource Sharing) is a server-side policy that allows or denies cross-origin requests. It’s not an HTML feature but affects resources loaded from other origins (AJAX, fonts, images in some cases). You may encounter it when loading cross-origin assets.

49. What is the purpose of `<noscript>`?

    Content inside `<noscript>` is shown if JS is disabled. Useful to show fallback messages or basic functionality when JS is unavailable.

50. Explain microdata, RDFa, or JSON-LD structured data.

    These are ways to add semantic metadata for search engines (rich snippets). JSON-LD is recommended (placed in `<script type="application/ld+json">`), e.g., structured info for articles, products, events.

51. How to handle file uploads in an HTML form?

    Use `<input type="file" name="file">` and set `<form enctype="multipart/form-data" method="POST">`. Server handles files.

52. What is the form attribute on form-associated elements?

    Elements like `<input>` can be associated with a `<form>` by `form="myFormId"`, enabling inputs to live outside the form markup but still submit with it.

53. How to disable autocomplete on a form field?

    `<input autocomplete="off">`. Note browsers may ignore it for password managers.

54. What are HTML templates?

    `<template>` holds markup not rendered until cloned via JS. Useful for client-side templating:

    ```HTML
    <template id="item">
        <li class="item"></li>
    </template>
    ```

55. Explain the picture-in-picture or Fullscreen APIs at high level.

    Browser APIs accessible via JS: Fullscreen API (element.requestFullscreen()), Picture-in-Picture for videos. Not pure HTML but often asked at higher levels.

# Section C — Advanced HTML

56. What are custom elements / Web Components?

    Web Components are browser standards (Custom Elements, Shadow DOM, HTML Templates) that let you build reusable custom HTML elements with encapsulated styles and behavior. Example:

    ```js
    class MyButton extends HTMLElement {
        connectedCallback() {
            this.innerHTML = `<button>Click</button>`;
        }
    }

    customElements.define("my-button", MyButton);
    ```

    Then use `<my-button></my-button>` in HTML.

57. What is Shadow DOM and why use it?

    Shadow DOM provides encapsulation for a component’s DOM and styles so styles don’t leak in or out. Useful in web components to avoid CSS collisions.

58. Explain Content Security Policy (CSP) basics.

    CSP is a security header (Content-Security-Policy) that restricts sources for scripts, styles, images to mitigate XSS. It’s configured server-side but impacts what HTML can do (e.g., inline scripts/styles may be blocked).

59. What is the `rel="noopener"` vulnerability?

    Without `noopener`, pages opened via `target="\_blank"` can access the opening window through window.opener and manipulate it (phishing risk). noopener prevents this.

60. How do you make SEO-friendly HTML?

    Use semantic tags, unique `<title>` and `<meta description>`, structured data, proper heading hierarchy (`<h1>` once per page), meaningful anchor text, alt attributes, and server-side rendering for dynamic content where necessary.

61. Explain hydration and server-side rendering at a high level (HTML-related).

    SSR sends HTML from the server so content is visible on first load; hydration is client-side JS attaching event handlers to that server-rendered HTML. This relates to HTML since SSR produces initial HTML that improves perceived performance and SEO.

62. What is ARIA? What problems does it solve?

    ARIA (Accessible Rich Internet Applications) attributes (role, `aria-\*`) enhance accessibility for custom widgets or where semantics are missing. Use cautiously — prefer native HTML semantics whenever possible.

63. How do you handle language localization in HTML?

    Set `<html lang="en">`. For multilingual elements, use lang on subsections. Use hreflang in links for alternative language pages.

64. Explain `prefetch` vs `preload` vs `prerender`.

    **preload** : fetch a resource needed soon (e.g., fonts, key images).

    **prefetch** : fetch resources likely needed for next navigation (low priority).

    **prerender** : browser renders an entire page in background (heavy and limited).

    Use with care to optimize perceived performance.

65. Explain `meta charset` and why it should be early in `<head>`.

    Browsers need to know encoding early to parse content correctly — place `<meta charset="utf-8">` near start of `<head>`.

66. What are the performance implications of large DOM?

    Very large DOM increases memory usage, layout and paint costs, slows JS traversals and reflows. Keep DOM shallow and virtualize long lists if needed.

67. How to prevent clickjacking using HTML-related approaches?

    Use X-Frame-Options or CSP frame-ancestors header to restrict framing. These are server headers but directly protect HTML from being embedded maliciously.

68. Describe how responsive HTML should be structured for mobile-first design.

    Build base styles for small screens, then use `@media (min-width: ...)` to progressively enhance for larger screens. Semantic HTML and fluid units `(%, em, rem, vh, vw)` help.

69. How do you handle cross-browser feature detection in HTML?

    Use Modernizr (or @supports in CSS) or JS feature detection (if ('querySelector' in document)), rather than UA sniffing.

70. Explain `rel="noopener"` and `rel="noreferrer"` differences again and compatibility.

    `noopener` blocks window.opener. `noreferrer` blocks referer header and may also block window.opener in some browsers. Use both for broad compatibility.

71. What is the link `rel="manifest"` used for?

    PWA web app manifest describes app metadata (icons, name, start URL) used when installing a site as an app.

72. How are fonts included in HTML pages?

    via `@font-face` in CSS or `link rel="stylesheet"` to a font provider (Google Fonts). Use font-display to control rendering behavior (swap, fallback).

73. What is the picture element’s `type` attribute in `<source>`?

    `type` indicates MIME type (e.g., image/webp), allowing browsers to pick supported formats.

74. How to secure form submissions?

    Use HTTPS, CSRF tokens, server-side validation, HTML attributes (autocomplete disabled where needed), and input sanitization server-side. Client-side validation is for UX only.

75. Explain `http-equiv="X-UA-Compatible" content="IE=edge"`. Is it still needed?

    Historically forced IE to use latest rendering engine. Not needed for modern browsers but might be included for legacy support.

76. What is resource timing and how can HTML help measure it?

    Resource Timing API (JS) measures loading times for fetches. In HTML you can add `link rel="preload"/preconnect` to improve timing. Tools like Lighthouse leverage these.

77. What is the picture element used for art direction?

    Yes — when you need different crops or different images entirely depending on viewport, picture is recommended compared to srcset, which is mostly for resolution switching.

78. How to serve different HTML to crawlers vs users? Is it okay?

    Serving different HTML (cloaking) can be penalized by search engines. Use server-side rendering that keeps content consistent and progressive enhancement — ensure content parity.

79. What is accessibility testing for HTML?

    Use screen readers, keyboard navigation, automated tools (axe, Lighthouse), and manual checks (labels, roles, contrast, tab order).

80. Explain platform differences: mobile browsers vs desktop browsers for HTML features.

    Mobile browsers have touch events, different viewport, and performance constraints. Some APIs may not be available or behave differently. Test thoroughly on devices.

# Section D — Practical coding tasks (common interview live tasks)

**For each task I’ll give the prompt, the small sample solution (concise), and a short explanation.**

**Note: In a live interview you may be expected to code in an editor for ~10–30 minutes. These are mini challenges; practice typing them.**

### Task 1 — Center a div both horizontally and vertically inside a parent (unknown size)

**Prompt: Center .child inside .parent.**

**Solution (flex):**

```html
<div class="parent">
    <div class="child">Centered</div>
</div>
```

```css
.parent {
display: flex;
justify-content: center;
align-items: center;
height: 300px;
}

.child {
    /_ optional styling _/
    }
```

Explanation: Flexbox centers both axes. Works when parent has a height.

### Task 2 — Create a responsive 3-column layout that becomes 1 column on small screens

**Solution (CSS Grid):**

```html
<div class="grid">
    <div>1</div>
    <div>2</div>
    <div>3</div>
</div>

<style>
    .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 16px;
    }

    @media (max-width: 600px) {
        .grid {
            grid-template-columns: 1fr;
        }
    }
</style>
```

Explanation: Grid makes columns equal; media query stacks them.

### Task 3 — Create a responsive navigation bar (hamburger on mobile)

**Solution (sketch / simple):**

```html
<nav class="nav">
    <button class="menu-toggle" aria-expanded="false" aria-controls="nav-list">
        ☰
    </button>
    <ul id="nav-list" class="nav-list">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
    </ul>
</nav>

<style>
    .nav-list {
        display: flex;
        gap: 16px;
        list-style: none;
        padding: 0;
        margin: 0;
    }
    @media (max-width: 600px) {
        .nav-list {
            display: none;
            flex-direction: column;
        }
        .nav-list.open {
            display: flex;
        }
    }
</style>

<script>
    const btn = document.querySelector(".menu-toggle");
    const list = document.getElementById("nav-list");
    btn.addEventListener("click", () => {
        const open = list.classList.toggle("open");
        btn.setAttribute("aria-expanded", open);
    });
</script>
```

Explanation: Toggle class shows/hides nav for mobile; aria-expanded for accessibility.

### Task 4 — Build a card component with image ratio 16:9 and text below

**Solution:**

```html
<div class="card">
    <div class="card-media" style="background-image:url('img.jpg')"></div>
    <div class="card-body">
        <h3>Title</h3>
        <p>Summary</p>
    </div>
</div>

<style>
    .card {
        width: 300px;
        border: 1px solid #ccc;
        border-radius: 8px;
        overflow: hidden;
    }
    .card-media {
        width: 100%;
        padding-top: 56.25%;
        background-size: cover;
        background-position: center;
    }
    .card-body {
        padding: 12px;
    }
</style>
```

Explanation: padding-top hack preserves 16:9 ratio (56.25% = 9/16 \*100).

### Task 5 — Create an accessible modal dialog (short sample)

**Key points: Focus trap, aria-modal="true", role="dialog", close on Esc, and restore focus later. Full sample is long; interview expects basic structure and mention of accessibility.**

### Task 6 — Create a two-column layout with left column fixed width and right column fluid

**Solution (CSS Grid):**

```css
.container {
    display: grid;
    grid-template-columns: 250px 1fr;
    gap: 16px;
}
```

### Task 7 — Create a simple form with client-side validation for email and password (min 8 chars)

**Solution:**

```html
<form>
    <label>Email <input type="email" name="email" required /></label>
    <label
        >Password
        <input
            type="password"
            name="password"
            pattern=".{8,}"
            title="8+ characters"
            required
    /></label>
    <button type="submit">Submit</button>
</form>
```

### Task 8 — Make an image responsive and maintain aspect ratio

**Solution:**

```css
img {
    max-width: 100%;
    height: auto;
    display: block;
}
```

### Task 9 — Create a multi-level dropdown (hover) — minimal CSS

**Solution (sketch):**

```html
<ul class="menu">
    <li>
        Item
        <ul class="submenu">
            <li>Sub</li>
        </ul>
    </li>
</ul>

<style>
    .menu,
    .submenu {
        list-style: none;
        margin: 0;
        padding: 0;
    }
    .menu > li {
        position: relative;
    }
    .submenu {
        position: absolute;
        left: 0;
        top: 100%;
        display: none;
    }
    .menu > li:hover > .submenu {
        display: block;
    }
</style>
```

**Note: For accessibility, prefer focus handling and JS.**

### Task 10 — Center inline elements with space between (flex)

**Solution:**

```css
.container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

### Task 11 — Build a simple tooltip on hover using CSS

```html
<span class="tooltip"
    >Hover me
    <span class="tooltiptext">Tooltip text</span>
</span>

<style>
    .tooltip {
        position: relative;
        cursor: help;
    }
    .tooltiptext {
        display: none;
        position: absolute;
        bottom: 100%;
        left: 50%;
        transform: translateX(-50%);
        white-space: nowrap;
    }
    .tooltip:hover .tooltiptext {
        display: block;
    }
</style>
```

### Task 12 — Implement a badge (notification dot) on an icon

```html
<button class="icon">
    <svg>...</svg>
    <span class="badge">3</span>
</button>

<style>
    .icon {
        position: relative;
    }
    .badge {
        position: absolute;
        top: 0;
        right: 0;
        transform: translate(50%, -50%);
        background: red;
        color: white;
        border-radius: 50%;
        padding: 2px 6px;
        font-size: 12px;
    }
</style>
```

### Task 13 — Create collapsible accordion without JS (CSS checkbox hack)

**Solution (checkbox hack) — not ideal for production but acceptable quick demo:**

```html
<input id="acc1" type="checkbox" hidden />
<label for="acc1">Title</label>
<div class="content">Panel content</div>

<style>
    #acc1 ~ .content {
        max-height: 0;
        overflow: hidden;
        transition: max-height 0.3s;
    }
    #acc1:checked ~ .content {
        max-height: 200px;
    }
</style>
```

### Task 14 — Implement a sticky header

```css
header {
    position: sticky;
    top: 0;
    z-index: 1000;
}
```

**Note: position: sticky works relative to scroll container.**

## Task 15 — Make an element appear on top of everything else (z-index)

```css
.element {
    position: relative;
    z-index: 9999;
}
```

### Task 16 — Build a responsive image gallery (masonry-like) using CSS columns

```css
.gallery {
    column-count: 3;
    column-gap: 16px;
}

.gallery img {
    width: 100%;
    display: block;
    margin-bottom: 16px;
}

@media (max-width: 800px) {
    .gallery {
        column-count: 2;
    }
}
@media (max-width: 500px) {
    .gallery {
        column-count: 1;
    }
}
```

### Task 17 — Implement smooth scrolling to anchors in CSS

```css
html {
    scroll-behavior: smooth;
}
```

### Task 18 — Create a skeleton loader for content

```html
<div class="skeleton title"></div>
<style>
    .skeleton {
        background: linear-gradient(90deg, #eee, #f5f5f5, #eee);
        background-size: 200% 100%;
        animation: shimmer 1.2s infinite;
        border-radius: 4px;
    }
    @keyframes shimmer {
        from {
            background-position: 200% 0;
        }
        to {
            background-position: -200% 0;
        }
    }
</style>
```

### Task 19 — Build a responsive table (stack rows on small screens)

**Strategy: Use CSS to display rows as blocks at small widths and label them with data-label pseudo elements. Solution is verbose but known pattern.**

### Task 20 — Fix a common layout bug: parent not expanding for floated children

**Solution: Clearfix:**

```css
.parent::after {
    content: "";
    display: table;
    clear: both;
}
```

### Task 21 — Build a badge that is visually hidden but accessible (screen readers only)

```css
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}
```

### Task 22 — Use srcset for responsive images example

```html
<img
    src="small.jpg"
    srcset="small.jpg 400w, medium.jpg 800w, large.jpg 1200w"
    sizes="(max-width:600px) 100vw, (max-width:1000px) 50vw, 33vw"
    alt="Responsive image"
/>
```

### Task 23 — Implement a keyboard-accessible custom dropdown

**Outline: Use button as toggle, ul as list with role="menu", handle Arrow keys and Enter in JS. Provide aria-expanded and aria-haspopup.**

### Task 24 — Create a print stylesheet

```html
<link rel="stylesheet" href="print.css" media="print" />
```

**In print.css, hide navigation, adjust font sizes, avoid background images.**

### Task 25 — Create a CSS-only star rating (input radio + labels)

**Overview: Create 5 radio inputs and style labels using :checked sibling selectors. Works but JS offers better UX.**

# Section E — Advanced HTML explanations and patterns

## A. Semantic structure & SEO

Use `<main>`, `<nav>`, `<article>`, `<h1>` for page title, `<h2>` for sections. Avoid multiple `<h1>` unless intentionally for multiple independent articles. Use descriptive anchor text. Provide meta description and structured data.

## B. Accessibility (A11y) concerns

Use label for forms, alt for images. Ensure focus order with logical DOM ordering. Use skip links `<a href="#main">Skip to content</a>` for keyboard users. Avoid onclick without keyboard handler. Prefer native controls for built-in accessibility.

## C. Progressive enhancement

Build baseline functionality without JS. E.g., forms should submit even if JS fails. Enhance with JS for better UX, but don't rely solely on it for core functions.

## D. Performance-oriented HTML

Use `link rel="preload"` for critical fonts/scripts, `loading="lazy"` for images, `defer` for scripts, compression (gzip/brotli) server-side. Keep DOM light.

## E. Security-related HTML

Ensure forms post to HTTPS. Avoid inline scripts/styles where CSP forbids them. Use `rel="noopener noreferrer"` and set Content-Security-Policy to mitigate XSS.

## F. Progressive Web App basics

`manifest.json`, service worker (registered in JS), and proper meta tags allow installability. Use theme-color meta to set status bar color on mobile.

## G. Modern features & progressive adoption

Web components are useful for library-agnostic UI components, but consider complexity for your app. Use Shadow DOM for encapsulation if building a third-party widget.

# Section F — Quick Revision Sheet (one page condensed)

### Document skeleton:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width,initial-scale=1" />
        <title>Page</title>
    </head>
    <body>
        <header>..</header>
        <main>..</main>
        <footer>..</footer>
    </body>
</html>
```

**Semantic tags**: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`.

**Form basics** : `<form method="POST" enctype="multipart/form-data">`, label for, input required, type="email", pattern.

**Image best practices** : `<img srcset sizes alt loading="lazy">`, or `<picture>` for art direction.

**Accessibility basics** : `label`, `alt`, `role`, `aria-\*`, `tabindex`.

**Links/security** : `target="\_blank"` `rel="noopener noreferrer"`.

**Mobile meta** : `<meta name="viewport" content="width=device-width, initial-scale=1">`.

**Performance hints** : `preload fonts`, `defer scripts`, `loading="lazy"`, `compress assets`, keep DOM small.

**Useful attributes** : `data-\*`, `hidden`, `download`, `autocomplete`.

**SEO basics** : `unique <title>`, `<meta name="description">`, structured data JSON-LD, semantic headings.

**Progressive enhancement** : baseline HTML → CSS → JS.

# Section G — More Practical Interview Questions (rapid-fire)

1. What is the default display value of `<button>`?

    inline-block (browsers vary; treat as inline-block for styling).

2. Why should you set `rel="noopener"` for external links opened with `target="\_blank"`?

    Security: prevents window.opener.

3. How do you hide content visually but keep it accessible?

    Use the .sr-only pattern: small 1px clip rectangle.

4. How to ensure images have width that scales on responsive layout?

    `max-width:100%;`
    `height:auto;`

5. How to stop images from being draggable?

    `draggable="false"` or `img { user-drag: none; }` (vendor pref).

6. What does autofocus in an input do?

    Focuses on load (use sparingly to avoid UX issues).

7. How to disable an input?

    disabled attribute (not submitted with form).

8. How to make a link open in the same tab?

    Default behavior; `target="\_self"`.

9. What are meta robots tags?

    `<meta name="robots" content="noindex, nofollow">` to control indexing.

10. Why is heading hierarchy important?

    Screen reader navigation and SEO rely on logical heading structure.

11. How to make an image retina-ready?

    Provide higher-resolution (2x) sources via srcset or use SVG.

12. What is `rel="canonical"`?

    Tells search engines preferred page URL to avoid duplicate content issues.

13. What is `aria-live` used for?

    Announcing dynamic content changes to assistive technologies (e.g., `aria-live="polite"`).

14. What is `role="presentation"`?

    Tells assistive tech the element is purely presentational.

15. What’s the difference between `aria-hidden="true"` and `display:none`?

    `aria-hidden` hides from screen readers but element may still render visually; `display:none` hides visually and from screen readers.

16. How to set default language?

    `<html lang="en">`.

17. What does `rel="noopener noreferrer"` fix besides security?

    noreferrer prevents referrer header from being sent.

18. How to add keyboard shortcuts?

    Use accesskey (but avoid — inconsistent) or JS keydown handlers. Announce in UI for accessibility.

19. How to set up offline fallback page?

    Service Worker caches and serves offline assets. (PWA topic)

20. How to reduce CLS (Cumulative Layout Shift)?

    Reserve space for images/fonts/ads (width/height or CSS aspect ratio), avoid inserting content above existing content.

# Section H — Common interview pitfalls & tips

**1. Don’t overuse `<div>` and `<span>` — prefer semantic tags.**

**2. Always add alt to `<img>` — never omit for content images.**

**3. Test keyboard navigation and focus order when building interactive components.**

**4. When asked to build UI, explain your accessibility and responsiveness decisions aloud.**

**5. If asked to explain a bug, first reproduce mentally: what changed, what’s expected, error messages?**

**6. For styling tasks, prefer Flexbox/Grid over floats for modern layout.**

**7. Remember: HTML is not only for visuals — it’s for meaning and machine-readability.**

# Section I — Extra Practical Tasks & Short Solutions

### Task A — Create a responsive card grid with equal height cards

use CSS Grid with align-items: start and let card content grow. Or display:flex; flex-direction:column; with .card { display:flex; flex-direction:column; } .card-body { flex:1 }.

### Task B — Create accessible tabs

use role="tablist", role="tab", role="tabpanel", manage aria-selected, keyboard arrows, and focus.

### Task C — Real-time character count under textarea

JS listens to input event and updates text.

### Task D — CSS-only vertical center for unknown height

display:flex; align-items:center; justify-content:center; for parent.

### Task E — Make an element unselectable (no text highlight)

user-select: none; but prefer not to block user selection unnecessarily.

### Task F — Simple breadcrumb navigation

```html
<nav aria-label="breadcrumb">
    <ol>
        <li>Home</li>
        ...
    </ol>
</nav>
```

with separators via CSS.

### Task G — Responsive typography

use clamp():

```css
h1 {
    font-size: clamp(1.5rem, 2.5vw, 3rem);
}
```

### Task H — Preventing layout shift for web fonts

use font-display: swap; to avoid invisible text.

### Task I — Lightbox image gallery

clickable thumbnails, overlay with larger image, close on Esc and overlay click. Manage focus.

### Task J — Accessible inline form errors

use aria-describedby to link input to error element and update live region aria-live="polite".

# Section J — Where to practice and learn more (links)

Here are high-quality resources to practice HTML and interview questions. Bookmark them and practice daily.

MDN Web Docs (HTML & accessibility) — https://developer.mozilla.org/en-US/docs/Web/HTML

MDN CSS — https://developer.mozilla.org/en-US/docs/Web/CSS

Frontend Interview Handbook — https://www.frontendinterviewhandbook.com
(HTML & CSS question lists)

CSS-Tricks (guides, examples) — https://css-tricks.com/

freeCodeCamp (interactive exercises) — https://www.freecodecamp.org/

W3Schools (quick reference/tutorials) — https://www.w3schools.com/

A11y Project (accessibility checklist) — https://www.a11yproject.com/

Google Web Fundamentals (performance & best practices) — https://web.dev/

Can I use (browser support) — https://caniuse.com/

Frontend Mentor (real-world UI challenges) — https://www.frontendmentor.io/

CodePen (playground & examples) — https://codepen.io/

LeetCode / HackerRank — mostly algorithmic, but sometimes frontend tasks appear — https://leetcode.com/
and https://www.hackerrank.com/

Practice interview platforms: Pramp, Interviewing.io, or TopTal trial interviews for live practice.

# Final tips for interview preparation

Practice building UIs quickly. Pick a mockup and implement it under time pressure (30–60 mins).

Explain your thinking as you code: accessibility, responsiveness, performance, and edge cases.

Be honest if you don’t know something; explain how you’d find the answer. Interviewers appreciate problem-solving.

Show familiarity with developer tools. Inspect elements, use color contrast and Lighthouse reports.

Prepare 3–5 projects you can talk about: explain what you built, how you structured HTML, challenges, and lessons.
