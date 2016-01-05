# High performance in the critical rendering path (@nzgb)
**ponyfoo.com**

## Measure
### What is going on?
- Use devtools audits
- developers.google.com/speed/pagespeed/insights
- webpagetest.org (google)

## Automate
### Measure early. Measure often.
`npm install psi -g`

## Budgets
### Eforace a performance budget. Track impact of every commit.
[timkadlec.com/2014/11/performance-budget-metrics](Performance Budget Metrics)
- Milestone timings
    - load time, time to interact
- speedindex
    - average time at which parts of a page are displayed
- quantity based Metrics
    - request count, page weight, image weight
 - Rule based metrics
    yslow grade, pagespeed score, etc.

## Beyond Minification
TCP, HTTP(S), HTML, CSS, Fonts, Images, JS
TCP: Browser Networking from O'Reilly

increase initial TCP cwnd size
- sender-side limit for in-flight data (cwnd)
    - more data in first tcp roundtrip
    - accelerates connection ramp us

Disable slow-start restart (SSR)
    - long-lived, bursty TCP connections can't afford SSR
    - improve HTTP performance by disabling it
`sysctl -w net.ipv4.tcp_slow_start_after_idle = 0`

## HTTP: make less requests
- GZip all the text
- turn on keep-alive
- Add expires and ETag headers
- Use a CDN

## HTTPS/2! SPDY? **YES**
- Non-blocking multiplexing
    - Multiple requests per TCP connection
- One connection per origin
    - Don't have to resort to hacks
- Header compression
    - Invalidation only for changed objects
- Proactive Server Push

## Render server-side
*Become a single page app later*
Defer non-critical asset loading
Keep it accessible with *aria*

## Inline critical CSS
- Remove unused styles
- Avoid named domains. Be responsive.
- Concatenate and minify.
- Follow a style guide.

## Fonts
- Load async
- Use a fallback while fonts load
- Prevent FOIT using JS
- Use fewer fonts, avoid repaints
- Cache aggressively

## Images
### Minify and shrink
- Defer images below the fold
- Create spritesheets
- Try inlining tiny dynamic images
- Use CSS for simple icons

## Research and Tools
**FOIT**
**PSI on NPM**
**underscore-cli**
**gulp-yslow/yslow**
**gulp-perfbudget**
