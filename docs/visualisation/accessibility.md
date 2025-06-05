# ♿ Accessibility Guidelines

Ensuring our data and analytics outputs are accessible is essential to serve all users, including people with disabilities. This document outlines key principles and practices to create inclusive, usable content.

## Why Accessibility Matters

- Legal compliance with [UK Equality Act 2010](https://www.legislation.gov.uk/ukpga/2010/15/contents) and other standards  
- Ethical responsibility to provide equal access  
- Improved usability for everyone, including keyboard users, screen reader users, and those with visual impairments

## Standards and Frameworks

We follow the [Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/) as our gold standard. Aim for at least **Level AA** compliance.

## Principles

- **Perceivable**: Information must be presentable in ways users can perceive.  
- **Operable**: User interface components must be operable by all means, including keyboard.  
- **Understandable**: Information and operation must be clear and predictable.  
- **Robust**: Content must be robust enough to be interpreted reliably by assistive technologies.

## Colour and Contrast

- Maintain a minimum contrast ratio of **4.5:1** for normal text, **3:1** for large text.  
- Do not rely on colour alone to convey information — use shapes, patterns, or labels as well.  
- Use our [NHS-approved colour palette](./colour-palettes.md) for consistency and accessibility.

## Typography and Layout

- Use clear, legible fonts with sufficient size (minimum 12pt/16px for body text).  
- Ensure adequate line spacing (1.5x line height recommended).  
- Use headings properly (e.g., `<h1>` to `<h6>`) to structure content.  
- Avoid justified text blocks to prevent uneven spacing.

## Data Visualisations

- Provide descriptive titles, labels, and legends on charts.  
- Supplement colour differences with patterns or textures where possible.  
- Provide alternative text or data summaries for charts and complex visuals.  
- Avoid flashing or blinking elements that can trigger seizures or distractions.

## Keyboard and Screen Reader Support

- Ensure all functionality is available via keyboard navigation alone.  
- Use semantic HTML or accessible components (e.g., ARIA roles where appropriate).  
- Provide visible focus indicators to help users track keyboard navigation.

## Testing and Tools

Regularly test your outputs using:  
- Automated tools like [Axe](https://www.deque.com/axe/), [WAVE](https://wave.webaim.org/), and [Lighthouse](https://developers.google.com/web/tools/lighthouse).  
- Screen readers such as NVDA (Windows) and VoiceOver (macOS/iOS).  
- Keyboard-only navigation tests.

## Additional Resources

- [WCAG 2.1 Guidelines](https://www.w3.org/TR/WCAG21/)  
- [UK Government Accessibility Guidance](https://www.gov.uk/guidance/accessibility-requirements-for-public-sector-websites-and-apps)  
- [Inclusive Design Principles](https://inclusivedesignprinciples.org/)  
- [The A11Y Project](https://www.a11yproject.com/)

By following these guidelines, we ensure our work is accessible, inclusive, and high-quality for all users.
