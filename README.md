I own and have authorization to modify both my website and its Android APK wrapper.

I have an APK version of my website. The APK currently works for only 14 days and then stops working. I want to inspect the APK and, where technically possible and authorized, modify it so the application continues working permanently.

IMPORTANT:
-
- Treat the website as a BLACK BOX.
- Do NOT require my complete website source code.
- Do NOT require my database, credentials, API keys, server access, or complete feature list.
- Only request specific website information if the APK investigation proves that it is actually necessary.
- I will provide additional information only when required.
- All modifications are authorized by me.
- Work in GitHub Codespaces.
- Preserve the website's normal functionality unless I specifically request a change.

PROJECT GOALS

1. APK inspection

- Analyze the uploaded APK.
- Identify whether it is:
  - Native Android
  - WebView wrapper
  - Hybrid application
  - Other architecture
- Inspect AndroidManifest.xml, resources, assets, DEX/classes, WebView configuration, embedded URLs, activities, services, and relevant Java/Kotlin/Smali code.
- Identify the minimum components that need modification.

2. 14-DAY RESTRICTION INVESTIGATION

Determine where the 14-day restriction is implemented.

Check whether it is:

- Local APK code
- SharedPreferences/DataStore
- SQLite/local database
- Stored installation timestamp
- Device/time-based calculation
- APK certificate/signature logic
- WebView JavaScript
- Website/server response
- Remote API
- Cloud/server-side licensing
- A combination of these

Do NOT assume the restriction is local.

If the restriction is locally implemented and can legitimately be changed, identify the relevant code and modify it so the APK does not unnecessarily expire.

If the restriction is server-controlled, clearly explain that before attempting modifications. Do not pretend that changing unrelated APK code will remove a server-side restriction.

3. BUTTON AND UI CUSTOMIZATION

I want to selectively change APK behavior independently from the website.

I may provide mappings such as:

BUTTON_A:

- Existing behavior: open website URL
- New behavior: open specified URL

BUTTON_B:

- Existing behavior: perform action
- New behavior: disabled/non-functional

BUTTON_C:

- Existing behavior: website action
- New behavior: different APK-side action

Do not change buttons whose behavior I have not specified.

First locate the relevant:

- Android view/resource IDs
- Click listeners
- WebView JavaScript bridges
- URL handlers
- Intent handlers
- Navigation logic

Then make only the requested changes.

4. WEBSITE NAME / DOMAIN VISIBILITY

I want to minimize unnecessary exposure of my website name/domain inside the APK UI.

Inspect:

- APK toolbar/title
- App labels
- WebView navigation UI
- Headers created by the APK
- Loading screens
- Other APK-controlled UI

Remove or replace website-name/domain references that are controlled by the APK itself where technically appropriate.

Do NOT break the website or Cloudflare security mechanisms merely to hide the domain.

5. CLOUDFLARE CAPTCHA

My website uses Cloudflare CAPTCHA/challenge protection.

IMPORTANT:

- Keep the CAPTCHA functioning normally.
- Do not bypass, automatically solve, defeat, or tamper with the CAPTCHA.
- Do not intercept or falsify Cloudflare verification.
- Do not remove Cloudflare protection from the website.

I want an APK-controlled visual overlay during the legitimate CAPTCHA verification stage.

Desired visual concept:

┌─────────────────────────────┐
│ ┌─────────────────────────┐ │
│ │      Verifying...       │ │  ← small APK overlay
│ └─────────────────────────┘ │
│                             │
│          CAPTCHA            │  ← remains visible/usable
│                             │
└─────────────────────────────┘

The overlay should cover ONLY the area where the unwanted website name/domain is visibly displayed, if that name is outside the actual CAPTCHA interaction area.

Requirements:

- Do not cover the CAPTCHA controls.
- Do not block mouse/touch interaction with the CAPTCHA.
- Do not modify the CAPTCHA itself.
- Do not attempt to hide or alter security information that Cloudflare requires for verification.
- Show the overlay only during the relevant loading/verification stage if reliable detection is possible.
- Remove the overlay after legitimate verification/navigation completes.
- If reliable detection is impossible, use a safe WebView navigation/loading state rather than guessing.
- Prefer an APK-controlled overlay rather than a standard Android Toast if precise positioning is required.
- The overlay should be visually simple and unobtrusive.

6. WEBVIEW BEHAVIOR

Inspect the existing WebView configuration.

Preserve required functionality such as:

- JavaScript
- Cookies
- HTTPS
- DOM storage
- Redirects
- User interaction
- Cloudflare challenge compatibility
- Required WebView settings

Do not disable security features unnecessarily.

7. BLACK-BOX PRINCIPLE

Do not reverse-engineer the entire website unnecessarily.

Only investigate:

- APK code
- APK resources
- APK behavior
- Network destinations required to understand the APK
- Specific website behavior that is directly relevant to a requested APK modification

If additional information is required from the website, explain exactly:

1. What information is needed.
2. Why it is needed.
3. Which APK behavior depends on it.

Do not request broad source-code access.

8. REBUILD

After modifications:

- Rebuild the APK.
- Resolve compilation/build errors.
- Sign the APK using my authorized signing key or provide the exact signing process.
- Make sure the resulting APK can be installed normally.
- Preserve the original application ID unless there is a specific reason to change it.
- Preserve required permissions.
- Do not introduce unnecessary dependencies.

9. TESTING

Create a practical test checklist covering:

A. First installation
B. Website loading
C. Cloudflare CAPTCHA appearance
D. CAPTCHA interaction
E. CAPTCHA completion
F. Overlay appearing/disappearing correctly
G. Website navigation
H. Modified buttons
I. Disabled buttons
J. Redirected buttons
K. 14-day behavior
L. App restart
M. Device restart
N. Cookies/storage persistence
O. Network failure
P. APK reinstall
Q. Release APK installation

10. ERROR HANDLING

Do not give placeholder code or pretend a modification works without verification.

If something cannot be determined from the APK:

- Say exactly what is unknown.
- Explain what evidence is missing.
- Request only the minimum additional information needed.

If a proposed modification could break Cloudflare, WebView navigation, or the website, identify the risk before applying it.

11. OUTPUT FORMAT

For every major stage, report:

[FOUND]
What was discovered.

[LOCATION]
APK file/class/resource/manifest location.

[REASON]
Why it is relevant.

[CHANGE]
What will be modified.

[RISK]
Any possible side effects.

[TEST]
How the modification will be verified.

Do not make unrelated modifications.

STARTING TASK

I will upload the APK.

First:

1. Inspect the APK architecture.
2. Identify the WebView/native/hybrid structure.
3. Locate the 14-day restriction mechanism.
4. Locate APK-controlled website-name/domain UI.
5. Locate the WebView and CAPTCHA-related flow.
6. Do NOT modify anything yet.

Give me the findings first. After I approve the identified modification points, proceed with the actual changes, rebuild, signing, and testing.

Creator/branding where appropriate:
<b>MYself_SINGH</b>
