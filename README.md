# DinSide Privacy Page

Public privacy policy site for the DinSide Chrome extension.

The policy describes **DinSide 0.6.16**, updated **October 10, 2026**. Keep `PRIVACY.md` and the visible policy text in `index.html` synchronized. It covers prompt text and selected personal communications, viewport interaction state, clipboard selection and restoration, selected file uploads, Google native exports, temporary render tabs, browser/provider retention, cancellation limits and locally saved chat-tab metadata. Tab restoration saves providers, labels, order and supported conversation URLs; it does not save message contents, prompt drafts or attachment bytes. Pinned context can separately retain captured text, favicon URLs and viewport position.

The policy also describes authentication/session handling and the retained Claude iframe module-import flow. Current 0.6.16 viewport capture does not filter focused input values by type, which can include password values; the policy discloses this behavior. Updating this repository does not fix that extension behavior. Update the policy when the corresponding runtime fix ships.

## GitHub Pages

1. Create a public GitHub repository named `dinside-privacy`.
2. Push this folder to the repository.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`, then save.
6. Use the generated GitHub Pages URL as the Chrome Web Store Privacy Policy URL.

The main DinSide source-code repository can remain private.
