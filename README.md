# Typebot Slide-Out Panel Demo

A simple, lightweight example demonstrating how to integrate a [Typebot](https://typebot.io) chat interface into a custom slide-out sidebar panel using vanilla HTML, CSS, and JavaScript.

## 🚀 Features

*   **Zero Framework Dependencies:** Built with plain HTML5, CSS3, and ES6 JavaScript.
*   **Custom Slide-out UI:** A smooth transition sidebar that slides in from the right.
*   **Expandable View:** Includes a toggle button to expand the panel width for better readability on desktop.
*   **Mobile Responsive:** Automatically adjusts to full-screen width on mobile devices.
*   **Typebot "Standard" Embed:** Uses the Standard embed method to render the bot inside a specific container rather than the default floating bubble.
*   **Accessibility:** Includes basic ARIA attributes and keyboard event listeners (ESC to close).

## 📂 Project Structure

For simplicity, this demo is contained in a single file, but it is structured to be easily split:

*   **`index.html`**: Contains the DOM structure, CSS styles (scoped variables), and JavaScript logic.

## 🛠️ Getting Started

1.  **Download the code**: Save the provided HTML code as `index.html`.
2.  **Open in Browser**: Double-click `index.html` to open it in your default web browser.
3.  **Interact**: Click the "Ask AI Helper" button to open the panel.

## ⚙️ Configuration

### Changing the Typebot
To load your own Typebot, locate the `<script type="module">` section at the bottom of the file and replace the `typebot` ID:

```javascript
Typebot.initStandard({
  typebot: "YOUR_TYPEBOT_ID_HERE", // e.g., "my-support-bot"
});
```

### Customizing Styles (CSS Variables)
The visual appearance is controlled by CSS variables defined in the `:root` of the `<style>` block. You can easily adjust colors and dimensions:

```css
:root {
  /* Dimensions */
  --ai-panel-width: 400px;       /* Default width */
  --ai-transition-speed: 0.4s;   /* Slide animation speed */
  
  /* Colors */
  --ai-panel-bg: #151515;        /* Sidebar background */
  --ai-text-color: #ffffff;      /* Header text color */
  --ai-panel-border: #333333;    /* Border color */
}
```

## 🧩 How it Works

1.  **HTML**: A hidden container (`#ask-ai-panel`) sits off-screen using `transform: translateX(100%)`. Inside is a `<typebot-standard>` element.
2.  **CSS**: Handles the smooth sliding animation and the "Expanded" state width changes.
3.  **JS (UI)**: Listens for clicks on the trigger button. Toggles the `.is-open` class on the panel to slide it in.
4.  **JS (Typebot)**: Imports the Typebot library from JSDelivr and initializes the bot into the standard element when the page loads.

## 📦 Dependencies

*   [Typebot Web JS SDK](https://github.com/baptisteArno/typebot.io/tree/main/packages/embeds/js) (via JSDelivr CDN).

## 📄 License

This project is open source and available under the [MIT License](LICENSE).