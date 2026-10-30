HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 9.2 — Responsive Typography & Images</title>
    <!-- Link to External Stylesheet -->
    <link rel="stylesheet" href="article-style.css">
</head>
<body>

    <!-- --- 1 & 5. Article Container with Readable Max-Width --- -->
    <main class="article-container">
        
        <!-- --- 2. Article Header --- -->
        <header class="article-header">
            <span class="category-tag">Web Design & Typography</span>
            <!-- 3. Uses clamp() for fluid, responsive heading scaling -->
            <h1>Mastering Responsive Typography and Fluid Images in Modern CSS</h1>
            <p class="article-meta">Published on October 30, 2026 • By Design Engineering Team</p>
        </header>

        <!-- --- 2 & 4. Article Featured Image --- -->
        <div class="image-wrapper">
            <img src="https://images.unsplash.com/photo-1507238691740-187a5b1d37b8?w=900&auto=format&fit=crop&q=80" alt="Developer working on responsive web design" class="fluid-img">
            <figcaption>Figure 1: Clean responsive layouts ensure optimal readability across all viewports.</figcaption>
        </div>

        <!-- --- 2. Article Body Content --- -->
        <div class="article-body">
            <p>
                In the early days of web design, typography was rigid and static. Designers relied on fixed pixel values that often resulted in text overflowing on mobile screens or appearing disproportionately tiny on ultra-wide desktop displays. Today, modern CSS empowers developers with relative units like <code>rem</code>, fluid math functions like <code>clamp()</code>, and robust image constraints.
            </p>

            <h2>The Power of Relative Units and Clamp()</h2>
            <p>
                By anchoring our font sizes to root elements using <code>rem</code> and establishing fluid scaling ranges with <code>clamp()</code>, text sizes adapt seamlessly as the browser width changes without requiring dozens of media queries.
            </p>

            <blockquote>
                "Good typography is invisible; it guides the reader effortlessly through content without drawing unnecessary attention to itself."
            </blockquote>

            <h2>Protecting Layout Integrity with Fluid Images</h2>
            <p>
                Images that exceed their container boundaries can easily break mobile layouts. Applying <code>max-width: 100%</code> and <code>height: auto</code> ensures that images scale proportionally down to smaller screens while preserving their natural aspect ratios.
            </p>
        </div>

    </main>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Responsive Typography Lab. All rights reserved.</p>
    </footer>

</body>
</html>
File 2: article-style.css
CSS
/* --- Global Reset & Design Tokens --- */
:root {
    --primary-color: #0f172a;
    --accent-color: #2563eb;
    --bg-color: #f8fafc;
    --card-bg: #ffffff;
    --text-main: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-main);
    /* 6. Improved line length and comfortable vertical spacing */
    line-height: 1.8;
    font-size: 1rem; /* Base root font size */
    padding: 2rem 1rem;
}

/* ==========================================
   5. CONTENT CONTAINER MAX-WIDTH & PADDING
   ================================---------- */
.article-container {
    max-width: 720px;               /* Restricts line length for optimal readability */
    margin: 0 auto;
    background-color: var(--card-bg);
    border: 1px solid var(--border-color);
    border-radius: 12px;
    padding: 2.5rem 2rem;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.02);
}

/* --- Article Header --- */
.article-header {
    margin-bottom: 2rem;
    text-align: left;
}

.category-tag {
    display: inline-block;
    background-color: #dbeafe;
    color: #1e40af;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 0.25rem 0.75rem;
    border-radius: 50px;
    text-transform: uppercase;
    margin-bottom: 1rem;
}

/* --- 3. Responsive Typography using clamp() --- */
.article-header h1 {
    font-size: clamp(1.75rem, 4vw, 2.5rem); /* Scales fluidly between mobile and desktop */
    color: var(--primary-color);
    line-height: 1.25;
    margin-bottom: 0.75rem;
}

.article-meta {
    font-size: 0.85rem;
    color: var(--text-muted);
}

/* --- 4. Fluid Images (`max-width: 100%` & `height: auto`) --- */
.image-wrapper {
    margin: 2rem 0;
}

.fluid-img {
    width: 100%;                    /* 4. Ensures image never exceeds container width */
    height: auto;                   /* 4. Preserves aspect ratio automatically */
    display: block;
    border-radius: 8px;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

.image-wrapper figcaption {
    font-size: 0.85rem;
    color: var(--text-muted);
    text-align: center;
    margin-top: 0.5rem;
    font-style: italic;
}

/* --- Article Body & Typography Spacing --- */
.article-body {
    display: flex;
    flex-direction: column;
    gap: 1.25rem;                   /* Consistent paragraph spacing */
}

.article-body p {
    font-size: 1.05rem;             /* Uses relative rem sizing */
    color: #475569;
}

.article-body h2 {
    font-size: clamp(1.3rem, 2.5vw, 1.6rem); /* Fluid subheading scaling */
    color: var(--primary-color);
    margin-top: 1.5rem;
    margin-bottom: 0.5rem;
}

/* Inline code formatting */
.article-body code {
    background-color: #f1f5f9;
    color: var(--accent-color);
    padding: 0.2rem 0.4rem;
    border-radius: 4px;
    font-size: 0.9em;
}

/* Styled Blockquote */
blockquote {
    border-left: 4px solid var(--accent-color);
    background-color: #f8fafc;
    padding: 1rem 1.25rem;
    font-style: italic;
    color: var(--primary-color);
    border-radius: 0 6px 6px 0;
    margin: 1.5rem 0;
}

/* --- Footer --- */
footer {
    text-align: center;
    margin-top: 3rem;
    color: var(--text-muted);
    font-size: 0.85rem;
}