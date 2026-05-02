# Web Performance

Performance -> Speed + Efficiency of website loads, renders and responds

[Github](https://github.com/toddhgardner/fundametals-of-web-performance)

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

### 2.1 Legacy Metrics

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

### 2.2 Core Web Vitals

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

First Input Delay (FID) -> deprecated (2020 - 2024)

INP replaces FID

FID -> Measured the first INP

- emphasized blocking time over processing time
- Users interact many times

Performance Metrics

Time to First Byte -> TTFB -> how quickly host responds -> server performance

Click -> (n) Redirect -> Service Worker Init -> Service Worker Fetch Event -> HTTP Cache -> DNS -> TCP -> Request -> Early Hint (103) -> Response -> Process -> Load

TTFB -> Good < 800ms, Improvement < 1800ms, > POOR

First Contentful Paint -> FCP -> how fast site visibly loads ui

TTFB  -> DCL (can be anywhere) -> FCP -> LCP -> L (can be anywhere)

FCP -> Good < 1.8s, Improvement < 3s, > POOR

LCP > FCP > TTFB

Capturing Metrics

Can get programmatically by Performance & PerformanceObserver

Performance

- .now()
- .getEntries()
- .mark()
- .measure()

.now() -> high-resolution timestamp relative to start of page

.timeOrigin -> high resolution timestamp start of page

.timeOrigin + .now() == Date.now()

The performance.now() method returns a high resolution timestamp in milliseconds. It represents the time elapsed since Performance.timeOrigin

.getEntries() -> timing information for

- page navigation
- resource requests
- performance events
- custom events

Performance -> Observer effect -> disturbance of observed system by the act of observation -> reduce performance due to observing

Performance Observer

observe performance entries when browser is idle

new PerformanceObserver(callback)

PerformanceObserver.observe({ type, buffered: true })

buffered => informed events happened before observing because PerformanceObserver listener is attached at the end

[web-vitals](https://github.com/GoogleChrome/web-vitals)

Browser Support

Browser Engines

Blink -> Chrome, Edge, Opera, Samsung, Brave, Arc
Webkit -> Safari, Mobile Safari, Chrome on iOS -> not support LCP, CLS, INP
Gecko -> Firefox -> not support CLS, INP

Be aware on Safari

## 3. Tests & Tools

- Testing Methods
- Common Tools
- Real User Monitoring

### 3.1 Testing Methods

depends on where we measure from -> different results

Lab Data with Test Device
Synthetic Data with Test Device
Field Data with Reporting Service

### 3.2 Statistics

average problems -> Average score -> can't determine due to very raw

use Percentiles -> get half way points -> p50, p75, p95, p99

lab data -> easier and diagnostic, field data -> more accurate, experience

### 3.3 Common Tools

- Google Lighthouse
- Device Toolbar
- Network Panel
- Performance Panel

Network Throttling, CPU Throttling

### 3.4 Web Vitals Extension

[web-vitals extension](https://chromewebstore.google.com/detail/web-vitals/illmkcoedmdanbkoihjpipllkaoakccm?hl=en)

### 3.5 Chrome User Experience Report

- Field Data
- Logged in Chrome Users
- Top 1M Public Websites
- Anonymous and Public
- 28 Day Rolling Average
- Google BigQuery

[speed check](https://requestmetrics.com/resources/tools/crux/)

[pagespeed](https://pagespeed.web.dev/)

[webpagetest](https://www.webpagetest.org/)

### 3.6 Real User Monitoring

- Field Data
- All Users
- Private sites
- Private details
- Realtime
- Custom Dashboard and Alerts

[browser-agent npm](https://www.npmjs.com/package/@request-metrics/browser-agent)

Enterprise RUM

- Akamai mPulse
- Dynatrace
- AppDynamics
- DataDog
- Sentry

Project RUM

- Request Metrics
- Speed Curve
- RUMVision
- Pingdom
- Raygun

## 4. Setting Goals

- How fast is enough
- Who gets to decide
- Understanding users

### 4.1 How fast is enough

The Psychology of Waiting

- People want to start
- Bored waits feel slower
- Anxious waits feel slower
- Unexplained waits feel slower
- Uncertain waits feel slower
- People will wait for value

User trusts -> Intentionally Slow

### 4.2 Who gets to decide

- User Experience
- Competitors
- SEO PageRank

User Experience -> Follow Business Metrics

- Bounce Rate
- Session Time
- Add-To-Cart Rate
- Cart Abandonment Rate
- Conversion Rate

Correlation !== Causation

Competitors -> 20% Faster

Weber's Law (20% Rule) -> 20% difference minimum for people to notice

SEO PageRank -> LCP, CLS, INP

### 4.3 Understanding Users

Device share -> Mobile, Desktop, Tablet

Screen Size -> 1920x1080

OS Share -> Android, iOS, Windows

Network Speed -> Download, Upload

## 5. Improving

Focus easy fixes for worst metric from real user data

Do Fewer Things

### 5.1 Improving TTFB

check RUM or Crux p75 data

- Compress HTTP Response
- Efficient Protocols
- Host Capacity
- Host Proximity

Compress HTTP Response -> Reduce the size of plain text files: html, css, javascript

use GZip and Brotli

[brotli](https://github.com/google/brotli)

Accept-Encoding: gzip, deflate, br

Efficient Protocols -> HTTP/1.1, 2, 3

HTTP/1.1 -> Request Response Cycle

HTTP/2 -> One TCP connection between client and server

HTTP/3 -> HTTP/2 with different connection protocols

UDP -> no guarantee -> faster

TCP -> guarantee -> slower
