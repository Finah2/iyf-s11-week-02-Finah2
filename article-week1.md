# Semantic HTML & Accessibility — What I Learned in My First Week of Web Dev

I just finished my first week of learning web development as part of the IYF Season 11 program. Honestly I didn't expect to learn as much as I did, so I figured I'd write it down while it's still fresh.

---

## What even is Semantic HTML?

When I started, I thought HTML was just about making stuff appear on screen. So naturally I used `<div>` for everything — the header, the nav, the footer, all divs. It worked, so I didn't think twice about it.

Then I learned about semantic HTML. Tags like `<header>`, `<nav>`, `<main>`, `<article>`, and `<footer>` don't just sit there — they tell the browser and screen readers what each section actually *means*. A screen reader going through a page full of divs is basically lost. Give it proper semantic tags and it knows exactly where it is and what it's reading.

Here's the difference:

```html
<!-- What I was doing before -->
<div class="header">
  <div class="nav">
    <div class="nav-item">Home</div>
  </div>
</div>

<!-- What I should have been doing -->
<header>
  <nav>
    <ul>
      <li><a href="#">Home</a></li>
    </ul>
  </nav>
</header>
```

Same visual result. Completely different meaning. The second version actually communicates what the code is doing.

---

## Accessibility issues I found in my own code

After building my first portfolio page I ran a Lighthouse accessibility audit and found five things I'd done wrong:

**1. Missing alt text on images** — My profile image had no `alt` attribute at all. Screen readers had nothing to say about it. Fixed it by adding something descriptive like `alt="Photo of Finah Nyamwaya"`.

**2. Broken heading hierarchy** — I jumped from `h1` straight to `h3` in one section without thinking. Screen readers use headings to navigate a page, so skipping levels messes up that structure. Fixed by going `h1 → h2 → h3` in the right order.

**3. Vague link text** — I had a link that just said "click here". That's useless when read out of context. Changed it to "Check out MDN Web Docs" so the destination is actually clear.

**4. Missing lang attribute** — The `<html>` tag didn't have `lang="en"` on it. Without this, screen readers can't tell which language to use for pronunciation. A one-second fix.

**5. Placeholders instead of labels** — I was using placeholder text to describe form inputs. The problem is placeholders disappear the moment you start typing. Added proper `<label>` elements linked to each input using `for` and `id` attributes.

---

## The thing that surprised me most

I thought deploying a website to the internet would be some complicated process. It's not. GitHub Pages does it in about three clicks.

You push your code, go to Settings → Pages, pick your branch, wait two minutes. Then you have an actual live URL anyone can visit.

The first time I opened my site in the browser and it was *actually on the internet* — that felt like something. It made the whole week feel real.

---

## Check it out

[View my Week 1 portfolio live](https://Finah2.github.io/iyf-s11-week-01-Finah2)

If you're just starting out with HTML, audit your own pages with Lighthouse — it'll find things you didn't even know were wrong. That's how I learned half of what I wrote here.
