# Mini Component Reusable UI

A lightweight, CSS-only component library built with custom properties (CSS variables). No frameworks required — just drop the stylesheet into your project and start using the class names.

---

## Setup

Link the stylesheet in your HTML `<head>`:

```html
<link rel="stylesheet" href="styles.css" />
```

Make sure to include the Poppins and Inter fonts (used for headings and body respectively):

```html
<link
  href="https://fonts.googleapis.com/css2?family=Inter&family=Poppins:wght@400;500;700;900&display=swap"
  rel="stylesheet"
/>
```

---

## Navbar

A horizontal navigation bar with links.

```html
<div class="navbar">
  <h5>Home</h5>
  <a href="#">Products</a>
  <a href="#">About Us</a>
  <a href="#">Contact</a>
</div>
```

**Notes:**

- Uses `--backgroundColor` and `--border-color` for styling.
- Stacks vertically on mobile (`< 600px`) and stays horizontal on tablet (`< 1024px`).

---

## Buttons

Three button variants: primary, secondary, and disabled.

```html
<div class="button-container">
  <button class="button-primary">Primary</button>
  <button class="button-secondary">Secondary</button>
  <button class="button-disabled" disabled>Disabled</button>
</div>
```

| Class              | Use Case                         |
| ------------------ | -------------------------------- |
| `button-primary`   | Main call-to-action (orange)     |
| `button-secondary` | Alternate actions (light orange) |
| `button-disabled`  | unavailable actions              |

**Notes:**

- Wrap buttons in `.button-container` for consistent spacing and alignment.
- All buttons have hover states .

---

## Input Fields

An input group with a label, text field, and optional error state.

**Default input:**

```html
<div class="input-group">
  <label>Email</label>
  <input class="input" type="text" placeholder="Enter your email" />
</div>
```

**With error state:**

```html
<div class="input-group">
  <label>Email</label>
  <input class="input input-error" type="text" placeholder="Enter your email" />
  <span class="error-text">Please enter a valid email.</span>
</div>
```

| Class         | Purpose                             |
| ------------- | ----------------------------------- |
| `input-group` | Wraps label + input + error message |
| `input`       | Base input styling                  |
| `input-error` | Red border for validation errors    |
| `error-text`  | Red error message below the input   |

---

## Card

A content card with a title and description.

```html
<div class="card-container">
  <div class="card">
    <h3>Card Title</h3>
    <p>This is a description or supporting text for the card content.</p>
  </div>
</div>
```

**Notes:**

- Wrap in `.card-container` for proper sizing and layout.
- Cards use `--backgroundColor`, `--border-color`, and `--border-radius-lg`.

---

## Badges

Small status indicators for inline labeling.

```html
<div class="badge-container">
  <span class="badge-success">Success</span>
  <span class="badge-warning">Pending</span>
  <span class="badge-error">Failed</span>
</div>
```

| Class           | Color        | Use Case                     |
| --------------- | ------------ | ---------------------------- |
| `badge-success` | Green        | Completed, active, approved  |
| `badge-warning` | Yellow/amber | Pending, in progress, review |
| `badge-error`   | Red          | Failed, rejected, error      |

---

## Alerts

Full-width alert banners for feedback messages. Each variant has its own content structure.

**Success alert:**

```html
<div class="alert-container">
  <div class="alert-success">
    <div class="content-container">
      <!-- Icon (optional) -->
      <span></span>
      <span class="text">Your changes have been saved successfully.</span>
    </div>
    <span class="cancel-icon">✕</span>
  </div>
</div>
```

**Warning alert:**

```html
<div class="alert-container">
  <div class="alert-warning">
    <div class="content-containerr">
      <span></span>
      <span class="textt">Your session is about to expire.</span>
    </div>
    <span class="cancell-icon">✕</span>
  </div>
</div>
```

**Error/Failed alert:**

```html
<div class="alert-container">
  <div class="alert-failed">
    <div class="content-containeerr">
      <span></span>
      <span class="texxtt">Something went wrong. Please try again.</span>
    </div>
    <span class="cancell-iccon">✕</span>
  </div>
</div>
```

| Alert Class     | Text Class | Container Class       | Icon Class      |
| --------------- | ---------- | --------------------- | --------------- |
| `alert-success` | `text`     | `content-container`   | `cancel-icon`   |
| `alert-warning` | `textt`    | `content-containerr`  | `cancell-icon`  |
| `alert-failed`  | `texxtt`   | `content-containeerr` | `cancell-iccon` |

> ⚠️ **Note:** Each alert variant uses slightly different class names for its inner elements (e.g., `textt`, `texxtt`). Be careful to use the correct class for each alert type.

---

## 🪟 Modal

A centered modal card, typically used for confirmations or focused content.

```html
<div class="modal-container">
  <div class="modal-content">
    <div class="image">
      <img src="your-icon.png" alt="Modal icon" />
    </div>
    <div class="teexts">
      <h3>Confirm Action</h3>
      <p>Are you sure you want to proceed? This action cannot be undone.</p>
    </div>
    <div class="button-container">
      <button class="button-primary">Confirm</button>
      <button class="button-disabled">Cancel</button>
    </div>
  </div>
</div>
```

**Notes:**

- `.modal-container` handles the outer sizing.
- `.modal-content` is the visible card — centered content with rounded corners.
- `.teexts` wraps the heading and body text inside the modal.
- Use alongside an overlay/backdrop (not included) to build a full modal dialog.

---

## CSS Variables Reference

You can customize the design system by overriding variables in `:root`:

| Variable             | Default   | Description                         |
| -------------------- | --------- | ----------------------------------- |
| `--color-primary`    | `#e27017` | Primary brand color                 |
| `--color-secondary`  | `#fdad6e` | Secondary/accent color              |
| `--color-accent`     | `#1f3a5f` | Dark accent (navy blue)             |
| `--border-radius`    | `8px`     | Default border radius               |
| `--border-radius-lg` | `16px`    | Large border radius (cards, alerts) |
| `--font-heading`     | `Poppins` | Font for headings                   |
| `--font-body`        | `Inter`   | Font for body text                  |

---

## Responsive Breakpoints

| Breakpoint | Behavior                                               |
| ---------- | ------------------------------------------------------ |
| `< 1440px` | Full desktop layout                                    |
| `≤ 1024px` | Tablet: navbar full width, inputs at 70%, cards at 50% |
| `≤ 600px`  | Mobile: all components stack vertically, full width    |
