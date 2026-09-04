# Instructions for AI Assistant: Portfolio Video Backgrounds & View Transitions

**Context:** I am building a highly polished UX Designer portfolio using pure HTML, CSS, and vanilla JS (no external CSS files, no React, no heavy libraries). The aesthetic is premium and "Framer-like," utilizing spring physics (`cubic-bezier(0.16, 1, 0.3, 1)`) and a mathematically precise masonry bento grid. 

Please apply the following three major updates to my existing files. Ensure you do not break the existing grid mathematics or responsive breakpoints. Keep all CSS inside the `<style>` tags of the respective HTML files.

## Task 1: Add Video Background to the Clinical Card in `index.html`

**Target File:** `index.html`

1. Inside the `<style>` block, add the following CSS to style the new video background with a frosted vignette edge blur:
```css
.clinical-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
    opacity: 0.65;
    transition: transform 1s var(--spring-easing), opacity 0.4s ease;
}

.clinical-card:hover .clinical-video {
    transform: scale(1.05);
    opacity: 0.85;
}

.clinical-video-overlay {
    position: absolute;
    inset: 0;
    z-index: 2;
    pointer-events: none;
    background: radial-gradient(circle at center, transparent 30%, rgba(10, 90, 80, 0.7) 100%);
    box-shadow: inset 0 0 30px rgba(10, 90, 80, 0.5);
}

.clinical-edge-blur {
    position: absolute;
    inset: 0;
    z-index: 2;
    pointer-events: none;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    -webkit-mask-image: radial-gradient(circle at center, transparent 45%, black 95%);
    mask-image: radial-gradient(circle at center, transparent 45%, black 95%);
}