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
