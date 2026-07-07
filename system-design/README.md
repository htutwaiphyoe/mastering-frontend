# Frontend System Design

[Github](https://github.com/EvgeniiRay/fundamentals-of-frontend-system-design)

- API Communication
- State Management
- UI Interaction
- Assets Management

1. Core Fundamentals
2. DOM APIs
3. Web APIs for Complex UI Patterns
4. Virtualization
5. Application State Design
6. Network
7. Web Application Performance
8. Bonus

## 1. Core Fundamentals

### 1.1 Box Model

Every HTML element is a box

Box Anatomy -> 4 layers

Content -> content of the block

Padding -> Space round the content

Border -> space of border

Margin -> external space outside of the border

Box Properties -> Size and Type

size -> intrinsic, restricted

intrinsic -> contents determines the space

restricted -> rules determines the space

- css -> width, height
- parent element -> flex, grid, percentage, aspect-ration, children

type -> block, inline, anonymous

block

- 100% of parent container width
- height is intrinsic
- top to bottom rendered
- Block Context Formatting (BCF)

anonymous -> element without tag -> block level

Mathematic of block elements

box-sizing: content-box, border-box

inline

- render as a string, left to right, top to bottom
- Inline Formatting Context (IFC)
- generate inline level boxes

Mathematic of inline elements

- ignore with and height
- ignore vertical margins
- inline padding does not change height of inline element

### 1.2 Browser Formatting Context

- an independent layout environment in a web page

Key ideas

- isolation
- scalability
- predictability

Formatting Context Family

- Flex
- Grid
- Inline
- Block

### 1.3 Browser Positioning System

- Normal Flow

css position -> alter normal flow -> static, relative, absolute, sticky, fixed

static -> default

relative -> normal flow

- offset applied relative to itself based on top, right, bottom, left
- offset does not affect the position of other elements
- the space remain the same
- create a new stacking context when z-index is not auto

containing block -> reference point

- browser viewport
- html
- body
- div with relative

absolute -> remove from normal flow

- no space is reserved
- positioned relative to its closed positioned ancestor
- based on top, right, bottom, and left
- create a new stacking context when z-index is defined

stacking context -> z-index -> 3D

- layering
- performance optimization

### 1.4 Reflow

DOM + CSSOM -> Render tree -> Reflow -> Repaint

Reflow -> JS + Style -> Layout -> Paint -> Composite

[reflow](https://gist.github.com/paulirish/5d52fb081b3570c81e3a/565c05680b27c9cfd9f5e971d295cd558c3e1843)

[csstriggers](https://csstriggers.com/)

### 1.5 Composition Layers

old browser -> CPU -> Rendering Engine -> Paint

modern browser -> CPU + GPU -> Rendering Engine -> Paint

### 1.6 Browser Rendering

Demo

## 2. DOM APIs

window, document

### 2.1 DOM Querying

HTML template tag -> store te html in memory

[DocumentFragment](https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment)

## 2.2 DOM Performance
