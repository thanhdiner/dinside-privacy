# DinSide Privacy Page

Public privacy policy site for the DinSide Chrome extension.

The policy describes **DinSide 0.6.21**, updated **October 20, 2026**. Keep `PRIVACY.md` and the visible policy text in `index.html` synchronized. It covers prompt text, selected communications, viewport state, clipboard selection/restoration, file uploads, Google exports, temporary tabs, retention and chat-tab metadata. Conversation transfer additionally saves captured transcript text, roles, notes, attachment references and prepared text in local IndexedDB until the user clears it; confirming Continue & send submits the reviewed context to the selected provider. Original attachments are not transferred. DinSide accounts, checkout and cloud sync are disabled, and the identity permission is absent. Existing development account/cloud records are preserved but inactive.

The policy also describes provider session handling and the retained Claude iframe module-import flow. The original 0.6.19 ZIP can include focused password values. Since DinSide 0.6.20, builds have shipped recognized password/authentication-field filtering, while older messages, pins and screenshots are not retroactively sanitized.

## GitHub Pages

The 0.6.21 policy also covers external drag-and-drop fallback and recognized
current-page file drags, including temporary source metadata, single-use tokens,
retrieval after a trusted drop, in-memory file handling and cleanup. It also covers Select on page, optional viewport images, local lossless PNG optimization and Manual conversation handoff.

1. Create a public GitHub repository named `dinside-privacy`.
2. Push this folder to the repository.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`, then save.
6. Use the generated GitHub Pages URL as the Chrome Web Store Privacy Policy URL.

The main DinSide source-code repository can remain private.
