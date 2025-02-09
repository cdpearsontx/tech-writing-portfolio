# Common Website Accessibility Issues (And How to Fix Them Fast)

**Why Accessibility Matters**

- Accessibility matters because it ensures everyone can access and use digital products, which includes people with disabilities. 

- Americans with Disabilities Act (ADA) is a law that protects people with disabilities from discrimination from many aspects of public life.

- Failing to comply with ADA can result in lawsuits and other penalties

- Accessible websites are good for SEO.

*Website accessibility mistakes are usually the result of lack of education or training.*

## 1. Missing or Poor Alt Text for Images
**The Problem:**
- Many images lack **alt text**, making them inaccessible to screen readers.
- Do not include "Picture of website, or photo of, or image of."

**The Fix:**
- Write meaningful alt text.
- Keep it concise but descriptive.
- Do not include personal commentary about the image


**Good vs. Bad ALT Text Examples**

- **Bad:** `"Screenshot1234.jpg"`
- **Good:** `"University website homepage showing navigation menu and search bar."`

## 2. Poor Color Contrast
**The Problem:**
- Low contrast makes text unreadable for visually impaired users.
- Common mistake: Light gray text on white backgrounds.

**The Fix:**
- Check contrast ratios (mention WebAIM Contrast Checker).
- Example of bad vs. good contrast.
- Use WCAG-compliant colors (4.5:1 for normal text, 3:1 for large text).

## 3. Lack of Keyword Navigation Support
**The Problem:**
- Some websites are designed only for mouse users, making them difficult or impossible to navigate with a keyboard.
- Example: Forms, dropdowns, and buttons not accessible via Tab key.

**The Fix:**
- Test using only the keyboard (Tab, Shift+Tab, Enter, Spacebar).
- Ensure [all interactive elements are focusable](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Keyboard)  (`<button>, <a>`)
- Use skip links (`<a href="#main-content">Skip to Content</a>`). 

## 4. Missing or Improper Use of Heading
**The Problem:**
- Many sites skip heading levels (`<h1>` to `<h3>` with no `<h2>` in between)
- **Bad Example**: Using `<span>` or `<div>` instead of proper headings

**The Fix:**
- Use proper heading structure (`h1` for the main title, `<h2>` for subsections, etc)
- Never skip heading levels

## 5. Videos without Captions
**The Problem:**
- No captions = no access for deaf / hard-of-hearing users
- Auto-generated captions (like YouTube) are often inaccurate

**The Fix:**
- Always provide captions (use tools like YouTube Studio or Kapwing).
- Provide a transcript if captions aren’t possible.

## Conclusion: Accessibility is Good for Everyone
- Correcting these 5 issues makes your site better for all users.
- Accessibility isn't just legal compliance--it improves UX for everyone.
- Use tools like SiteImprove, WAVE and NVDA to test for accessibility
