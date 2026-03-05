# Web Performance

Performance -> Speed + Efficiency of website loads, renders and responds

Table of content

1. Importance
2. Measuring
3. Tests & Tools
4. Setting Goals
5. Improvement

## 1. Importance

1. User Experience
2. SEO
3. Online Ads

### 1.1 User Experience

API -> within 2 seconds

0.1 sec -> instant
1.0 sec -> notice
10 sec -> frustration

40% -> 3 seconds
75% -> slow

### 1.2 SEO

help search engines and rank your content

Page Rank -> hight traffic

same content -> faster performance wins

### 1.3 Ads

bounce rate -> performance

100ms improvement -> 1% incremental revenue

## 2. Measuring

1. Legacy Metrics
2. Core Web Vitals
3. More Metrics
4. Capturing Metrics
5. Browser Support

## 2.1 Legacy Metrics

Waterfall Charts -> measure time (ms)

HTML Document -> Blue
Stylesheets -> Purple
JavaScript -> Yellow
Images -> Green
Fonts -> Blue green
Fetch/Others -> Brown

DOMContentLoaded -> HTML downloaded and  scripts executed (Image not included)

Load -> all downloaded and rendered (Lazy-loaded not included)

DCL & L events does not work with CSR SPA

## 2.2 Core Web Vitals

1. How fast site visibly loads
2. how smooth things load
3. how quickly users can interact

Largest Contentful Paint (LCP)

- How fast site visibly loads the most important element
- important === largest element in pixel
- largest element === img, video, css bg image, text
- factors === opacity > 0, size < 100%, low entropy images < 0.05
- entropy -> no of bits / visible pixel
- lcp measurement stops after first user interaction
- lcp Good < 2.5 sec, Improvement < 4 sec, Poor > 4 sec

Cumulative Layout Shift (CLS)

- how smooth and predictably elements load in page
- shifty.site
- layout shift = impact fraction x distance fraction
- impact fraction = impact / viewport (w, h)
- distance fraction = distance / viewport (w, h)
- cumulative = sum of all layout shifts (excluding shifts from user action < 500ms)
- CLS < 0.1 Good, < 0.25 Improvement, > 0.25 Poor
- CSR make worse CLS
- Canvas does not make CLS
- Skeleton does not make CLS
- Content inside iframe does not make CLS

Flame Charts

flame chart -> performance of js -> measuring execution time (ms)

Browser Task -> Grey
Parse HTML -> Blue
Layout & Paint -> Purple
Evaluate & Compile Scripts -> Yellow
JavaScript Execution -> Light Yellow
Extensions -> Green

Interaction to Next Paint (INP)

INP -> how quickly user can interact

interaction -> click, drag, touch, keypress (NOT Scroll) -> pick worst one

considerations

- no interaction, no INP
- don't know the worst one until user leaves
- heavily influenced by device capability

INP -> Good < 200, Improvement 500ms > Poor
