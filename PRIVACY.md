# DinSide Privacy Policy

_Last updated: October 10, 2026 — DinSide 0.6.16_

DinSide brings relevant browser context and user-selected files into supported AI chat services in Chrome's side panel, allowing users to ask questions, summarize, explain, translate, and work with the pages and documents they are browsing.

## Information DinSide processes

DinSide may process the following information only to provide its core functionality:

- **Web history data:** page URLs, page titles, favicons, and information about browser tabs that the user chooses to include as context, including whether a pinned source tab remains open or has navigated to another page.
- **Website content:** visible page text, selected text, page content, screenshots, and other webpage content that the user chooses to include as context.
- **Prompt text and personal communications:** Prompt text entered in a supported AI chat composer is read and prepared when the user sends a message or invokes an extension action, so it can be combined with enabled browser context. User-selected page content and files can include personal communications, such as chat messages or emails.
- **User activity and viewport state:** When viewport context is enabled or requested, DinSide may process the source page's scroll position, selected text, viewport dimensions, visible media playback state and metadata, text or available values from the focused element. These details help the selected AI service understand which part of the page the user is referring to.
- **Clipboard selection data:** Supported Google Docs and document-viewer selection workflows may temporarily read the previous clipboard contents and copy user-selected text when direct selection access is unavailable. Previous clipboard contents are used only to attempt restoration, not as AI context.
- **User-selected file attachments:** file links, filenames, file type metadata and contents selected from webpages, file viewers, Google Drive or supported document applications. These can include documents, code, structured data, images, audio, video and archives. DinSide retrieves originals or prepares supported exports, then passes the selected file to the current AI provider's upload interface. Visiting a page does not automatically upload files.
- **Extension settings:** preferences such as selected AI provider, provider/model preferences, context settings, pinned context, Quick Ask actions, theme preferences, Skills, Favorites and other DinSide configuration. For supported Claude integrations, model, effort and thinking preferences may be stored locally so the selection persists across browser sessions.
- **Chat tab metadata:** when Multiple chat tabs is enabled, DinSide remembers the open tab list, selected providers, custom tab names, provider numbers, tab order, active tab and supported saved conversation URLs locally to reopen them after a panel or extension reload or browser restart.
- **Provider session information (authentication information):** for Xiaomi MiMo Studio, DinSide may read and mirror the non-HttpOnly `xiaomichatbot_ph` cookie for `aistudio.xiaomimimo.com` into the Chrome partition used by the embedded MiMo page. This lets the side-panel iframe recognize the same provider session as a normal MiMo tab. For Z.ai, DinSide may detect when the provider's local sign-in token changes so it can refresh the embedded provider after sign-in; DinSide does not copy, persist or transmit that Z.ai token. The MiMo session helper does not intentionally read or copy HttpOnly cookies, passwords or unrelated authentication cookies; the separate viewport workflow is described below.

## How information is used

DinSide uses this information only to provide browser context to the AI service selected by the user, support user-requested page, viewport, selection, screenshot, pinned-page, open-tab, Smart Context and Quick Ask workflows, retrieve and attach selected files, maintain supported provider sessions inside the side panel, and remember extension preferences.

DinSide does **not** use this information for advertising, profiling, creditworthiness, or unrelated purposes.

## Prompt and viewport context

DinSide combines the user's prompt with the context enabled or selected for that action and delivers the resulting prompt to the selected AI service. Prompt text and selected communications are subject to that service's policies. DinSide does not operate its own server for storing this content.

Focused form-field values can contain sensitive information. In DinSide 0.6.16, viewport capture does not filter focused input values by input type, so a focused password field's value may be included in viewport context and delivered to the selected AI service when that context is sent. Users can turn off page context when working with sensitive forms.

## Clipboard selection workflows

When Selected text context is enabled, supported Google Docs and document viewers may use a selection-copy workflow to obtain text selected by the user. DinSide may temporarily snapshot the previous clipboard contents and attempts to restore them after the copy operation. It does not continuously monitor the clipboard or use the previous clipboard contents as AI context. Restoration may be incomplete or fail because of browser permissions or source-application behavior. Explicit copy actions, such as copying support information, also write to the clipboard.

## Selected files and document exports

Retrieval starts after a file is selected and reaches its turn in the attachment queue. Source requests use the access already available in the user's browser and may include the browser's existing source-site credentials. DinSide does not request new Drive OAuth access for these exports. Where needed, it invokes the selected website's Download/Export control and captures the resulting file URL or data temporarily. That website may also perform its normal download or export actions.

Supported Google files may be exported as Word, Excel, PowerPoint, PDF, MP4, JPEG, project JSON or KML. Colab notebooks and saved AI Studio prompts retain their source data, including notebook outputs or saved prompt settings and inputs; DinSide does not execute cells or run prompts. Downloadable Gem, Conversation and layout data may be converted to JSON retaining readable text, settings and unknown configuration fields, or retained as HTML when provided as an explicit download.

Forms and Sites PDF exports may open temporary inactive browser tabs and retrieve images or backgrounds referenced by the selected document. Forms exports include printed questions, sections, options and images, clear answer controls and do not fetch form responses. Sites exports include the selected site's editor page tree, including pages hidden from navigation. Embedded videos and documents become references rather than separately downloaded files. Rendering libraries and fonts are packaged with the extension; no remote PDF rendering service is used. Source websites can record these requests, and temporary tabs may leave ordinary browser history entries.

PDF viewport context is separate from a whole-file attachment. It reads visible text exposed by an accessible viewer and does not attach screenshots, perform OCR or download the whole PDF through that viewport workflow. An original PDF selected for attachment retains its full file contents, including scanned page images.

## Embedded AI services

DinSide displays the selected AI provider's remote web application in webpage iframes. Those services load their own remotely hosted scripts and handle provider sign-in, conversations and responses under their own terms. For Claude, a packaged MAIN-world helper imports module resources already referenced by the Claude page inside its iframe to restore the provider's native sidebar and layout. These modules run in the provider webpage rather than extension documents or the service worker, without direct access to Chrome extension APIs. Packaged provider bridges communicate with the side panel through validated message boundaries.

## Data sharing

DinSide does not sell user data.

When the user chooses to send context to an AI provider, the selected context may be transmitted to or inserted into the AI service selected by the user. Those services process information according to their own privacy policies and terms.

Selecting a file starts upload to the current AI provider as soon as its queued transfer runs. The provider can receive and process the file before a chat message is sent. DinSide does not automatically submit a chat message. Removing an attachment or cancelling a transfer cannot undo data the provider has already received, and retention is governed by that provider.

For supported embedded provider experiences, DinSide may interact directly with that provider's website in the user's browser. DinSide does not transfer the MiMo session identifier described above to DinSide-operated servers; it is mirrored only within Chrome's cookie storage for the same MiMo domain and the extension's embedded partition.

DinSide does not transfer user data to third parties except as necessary to provide the functionality explicitly requested by the user.

## Data storage

DinSide stores extension settings, preferences and pinned context in the browser's local extension storage. Saved pins can include captured text, page titles, URLs, favicon URLs and pin metadata, including a pinned viewport's scroll position. Keep chat on reopen may separately save a supported conversation URL.

Clipboard snapshots used for selection restoration are held temporarily in memory. Previous clipboard contents are not saved to extension storage or added to AI context.

Chat tab metadata is stored in the browser's local extension storage. Restoring a tab opens its provider's normal web page; the active tab loads first and other restored pages load when selected. DinSide does not include message contents, unsent prompt drafts, attachment bytes or temporary chat context in this saved tab list. Recovery of saved conversations depends on the provider; temporary chats and unsent work are not recovered by tab metadata. The last saved tab set is shared across DinSide panels in the browser profile.

Attachment bytes, generated PDFs and temporary download-capture data are processed in memory rather than saved to extension storage. DinSide releases its temporary capture hooks and closes owned export tabs after completion, failure or cancellation. Normal browser caching, source-site download behavior and the selected AI provider's storage still apply.

DinSide does not operate its own remote server for storing webpage content, selected text, screenshots, file attachments, provider session cookies or other browser context users send through the extension.

## User control

Users control what context is included. Depending on the feature used, users can choose whether to include full-page or Smart Context content, viewport content, selected text, screenshots, pinned context, open browser tabs or file attachments. Users can remove, clear or change context before sending a message and use the AI provider's own controls to remove attachments.

Closing a chat tab removes its entry from the locally saved tab list. Disabling Multiple chat tabs clears the saved list and keeps only the active live frame. This tab restoration is separate from Keep chat on reopen, which controls the existing single-chat workflow.

Users can finish file selection while already selected files continue attaching, or cancel active and queued transfers using the attachment notification. DinSide stops its transfer and attempts to remove the newly handed-off attachment when the provider exposes a remove control. Cancellation does not reverse completed provider uploads or stop arbitrary export work already started by the source website. Owned export tabs are closed, but browser history and external retention are not erased by cancellation.

## Permissions

DinSide requests Chrome permissions only to provide its browser-context, side-panel and supported AI-provider integration features. These permissions may include access to the active tab, browser tabs and favicons, local storage, scripting, the clipboard, browsing data (limited to Perplexity service-worker cleanup), cookies, the side panel, supported AI-provider hosts, and network/declarative rules required for supported provider integrations.

DinSide uses activeTab for temporary access following user interaction, scripting for packaged context, selection, export and provider-integration helpers, and tabs to identify source pages, show open-tab information and manage owned temporary export tabs. The favicon permission provides Chrome's favicon endpoint for source-page icons. Favicon URLs may be retained locally with pins. The storage permission saves settings, pinned context and supported chat metadata.

DinSide uses host access to read context from webpages the user chooses to work with, retrieve selected files and exports, and enable supported AI services inside the side panel. Broad webpage access is required because users may request context or files from websites they browse rather than from a fixed list of sites.

Clipboard access supports the selection-copy and explicit copy workflows described above. Browsing-data access is used for targeted removal of Perplexity service-worker registrations for `perplexity.ai` and `www.perplexity.ai` while preparing its embedded side-panel view. This does not clear general browsing history, cookies or unrelated sites' data. The cookies permission is used only for the MiMo session behavior described above; Z.ai sign-in completion detection does not use the Chrome cookies permission. Packaged network/declarative rules support embedded AI-provider integrations. DinSide does not use these permissions for unrelated monitoring, advertising or collection of browsing activity.

## Security and Limited Use

DinSide limits access to user data to what is necessary for its disclosed user-facing features and uses secure HTTPS provider origins for transmitted content. DinSide's use and transfer of information received from Chrome extension APIs and supported provider pages adheres to the Chrome Web Store User Data Policy, including the Limited Use requirements.

## Children's privacy

DinSide is not specifically directed to children under 13 and does not knowingly collect personal information from children.

## Changes to this policy

This Privacy Policy may be updated when DinSide's features or data practices change. The latest version will always be published at this page.

## Contact

For privacy-related questions, please use the support contact provided on DinSide's Chrome Web Store listing.
