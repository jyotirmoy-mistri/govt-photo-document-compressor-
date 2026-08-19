## 2024-08-19 - Fix DOM XSS in Toast Notifications
**Vulnerability:** Found a Cross-Site Scripting (XSS) vulnerability in `index.html` where `triggerToast` was dynamically rendering `msg` variable inside `toast.innerHTML = \`<span>${icon}</span> <span>${msg}</span>\`;`.
**Learning:** This existed because of convenience of template literals rendering inner HTML.
**Prevention:** Use DOM elements creation (`document.createElement`) and setting `textContent` instead of raw `.innerHTML` for elements representing text that could originate from user inputs or uncontrolled sources.
