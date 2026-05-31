# Image Optimization Guide

**Project:** ThePrinceEcho Landing Page  
**Goal:** Maintain high performance while preserving visual quality during refinement.

---

## Objectives

- Reduce image payload without sacrificing visual quality
- Improve Core Web Vitals (especially LCP and CLS)
- Establish consistent standards for future images
- Support the current visual refinement on `refine/landing-page-v2`

---

## Current State (May 2026)

- Multiple JPG banners in root (`banner-*.jpg`, `banner-*-v2.jpg`)
- Logo already delivered in WebP (`TPE_Logo_final.webp`)
- Limited use of `loading="lazy"`
- No systematic `srcset` usage
- No formal optimization process

---

## Optimization Standards

### 1. Format Priority

| Priority | Format | Use Case | Notes |
|----------|--------|----------|-------|
| 1        | WebP   | All new images | Primary format |
| 2        | JPG    | Fallback only  | When WebP is not supported |

### 2. Loading Strategy

- Use `loading="lazy"` on all images **below the fold**
- Hero / above-the-fold images should **not** use lazy loading
- Consider `fetchpriority="high"` on the main hero image

### 3. Responsive Images

Use `srcset` + `sizes` for important images (especially banners and hero visuals):

```html
<img
  src="banner-hero.webp"
  srcset="banner-hero-480.webp 480w,
           banner-hero-768.webp 768w,
           banner-hero-1200.webp 1200w"
  sizes="(max-width: 768px) 100vw, 1200px"
  alt="..."
  loading="eager"
  width="1200"
  height="630"
>
```

### 4. File Size Targets (Guidelines)

| Image Type       | Target Size | Notes |
|------------------|-------------|-------|
| Hero Banner      | < 150–200 KB | Critical for LCP |
| Secondary Banners| < 100 KB     | - |
| Decorative       | < 50 KB      | - |

---

## Workflow for New Images

1. Optimize / convert to WebP (recommended tools below)
2. Generate responsive versions if the image is important
3. Add proper `alt` text
4. Use `loading="lazy"` unless it's a hero image
5. Commit both original (if needed) and optimized versions
6. Update HTML with modern `<img>` attributes

---

## Recommended Tools

| Tool | Type | Recommendation |
|------|------|----------------|
| Squoosh (squoosh.app) | Web | Best for manual WebP conversion |
| ImageOptim (macOS)    | App | Excellent for batch optimization |
| Sharp (Node.js)       | CLI | Good for automation later |
| cwebp                   | CLI | Google’s official WebP encoder |

---

## Implementation Phases

### Phase 1 (Current)
- Convert key hero and section banners to WebP
- Add `loading="lazy"` to non-critical images
- Update important images with `srcset` where beneficial

### Phase 2 (Later)
- Create responsive image variants (480w, 768w, 1200w)
- Consider adding an image optimization step in CI
- Review and optimize remaining decorative assets

---

## Notes

- Keep original high-resolution files in `archive/` if needed for future editing
- Always maintain good `alt` text for accessibility
- Re-run Lighthouse after major image changes

---

*Last updated: May 2026*