# Websites Incompatible with Libre Browsers (WILB)

Welcome to the **WILB** issue tracker repository!

This registry tracks websites whose developers or operators have introduced **site-side barriers** that discriminate against libre (free software) browsers. Following the principle that a system is not fully free if it contains even a fraction of non-free code, a website is not considered compatible with libre browsers unless it is **100% compatible**. 

WILB documents and triages websites that include, require, or enforce non-free web practices—rejecting artificial User-Agent blocks, non-free JavaScript requirements, non-free DRM/binary blobs, vendor lock-in, and proprietary API dependencies.

---

## 🎯 Scope & Purpose

While users routinely open site breakage reports on official libre browser issue trackers, most libre browser maintainers close or reject site-side barrier reports because they fall outside the scope of fixing browser engine code. 

**WILB fills this gap.** We focus **exclusively on site-side compatibility barriers**, creating a public record of website discrimination and offering a platform where site administrators and developers can collaborate with the free software community.

### Core Targets
- **Firefox/Gecko-based Libre Browsers:** Abrowser, GNU IceCat, Iceweasel (Parabola), Fennec F-Droid, etc.
- **Chromium-based Libre Browsers:** Iridium Browser, Ungoogled Chromium, etc.

### What We Track (In Scope)
- 🟢 **User-Agent Discrimination & Sniffing:** Sites that block or throw warnings at libre browser User-Agents (even when the underlying engine supports the page).
- 🔒 **Proprietary & DRM Requirements:** Sites that refuse to function without non-free components (e.g., Widevine DRM) or non-free proprietary client-side scripts.
- 🏢 **Vendor Lock-In & Hardcoded Assumptions:** Sites relying on non-standard, proprietary web APIs or hardcoded infrastructure tied exclusively to Google or Mozilla services.

> 💡 **Single-Barrier Rule:** **Any site-side barrier is grounds for logging.** Just as software is not free if even 0.1% of it is non-free, a website is not considered compatible with libre browsers unless it is **100% compatible**. A website does not need to be entirely unusable to qualify for WILB—whether an issue is large (e.g., a total domain block, broken login flow, or non-functional video player) or small (e.g., an artificial User-Agent warning banner, broken navigation button, or site-side layout glitch), any single site-side barrier makes the site fully eligible for reporting.

### What We Do NOT Track (Out of Scope)
- 🚫 **Browser Engine Bugs:** C++/JS code bugs, rendering regressions, or crashes inside the libre browser itself (please report these directly to the respective browser maintainers).
- 🚫 **Upstream Engine Bugs:** Issues present in official upstream Firefox or Chromium releases.
- 🚫 **User-Installed Add-ons / WebExtensions:** Script-blocking or extension-specific issues from user-added extensions (e.g., uBlock Origin, NoScript).

---

## 🧩 User-Installed Add-ons Are Excluded

While extensions (such as **uBlock Origin**, **NoScript**, or user-configured script blockers) can frequently cause websites to break or alter functionality, **WILB does not track site barriers caused by user-installed add-ons**.

We exclude user-installed extensions for two primary reasons:

1. **Extension Barriers Belong in Extension Trackers:**  
   When a website breaks due to a user-added extension (for example, uBlock Origin filtering a required asset or custom NoScript rules), the root cause lies in the extension's ruleset, not the browser engine.
   * **Where fixes occur:** Extension maintainers resolve site breakages by updating global blocklists or adjusting default whitelist rules.
   * **Official reporting channels:** Extension projects maintain dedicated infrastructure for site breakage (e.g., [uBlock Origin's uAssets tracker](https://github.com/uBlockOrigin/uAssets)). 

2. **Actionability & Triage Quality:**  
   Logging user-installed extension breakage in a browser-focused repository creates noise that cannot be resolved at the browser level.

---

### ⚠️ The One Exception: Pre-installed Default Functional Add-ons

An add-on-related issue **MAY** be reported to WILB **only if**:
- The extension/add-on is **bundled and enabled by default** in the clean, stock installation of the libre browser (e.g., **GNU LibreJS in GNU IceCat**).
- The add-on actively interacts with web page content or network traffic (e.g., script blockers, header modifiers). *Visual themes, language packs, and search engines are strictly excluded.*
- The site barrier occurs on a **fresh user profile using both the browser's and the WebExtension's default configuration**, without any modified settings, custom rules/filters, or added third-party extensions.

> **Note on Reporting:** When filing an issue caused by a pre-installed add-on, please specify if the site functions when that default add-on is temporarily disabled. This helps isolate whether the barrier is caused by site-side script requirements or browser-level User-Agent/engine policies.

---

## 🌐 Invitation to Site Administrators

This tracker invites **site administrators, web developers, and organization engineering teams** to review reported issues on their web properties. 

If your website appears in this repository:
1. **Review the Issue:** Examine the minimal steps to reproduce and environment details submitted by users.
2. **Remove Artificial Blocks:** Adjust User-Agent sniffing rules, fallback dependencies, or non-standard API requirements to enable standards-compliant libre browsers.
3. **Engage with Contributors:** Feel free to comment directly on issue reports to clarify site requirements, share updates, or announce resolutions.

---

## 🔍 Verification Requirement

To ensure an issue is truly a **site-side barrier** and not an upstream browser engine bug, every report must be verified against the upstream base browser:

1. **Firefox-based issue?** Compare the site on the libre browser against the exact same version of **Mozilla Firefox**.
2. **Chromium-based issue?** Compare the site on the libre browser against the exact same version of **Google Chromium**.

> **Valid WILB Issue:** The website fails due to site design/blocking on the libre browser, but works on the exact same version of the upstream base browser (or fails due to missing proprietary binaries like DRM).

---

## 📋 Reporting an Issue

When opening a report, please use our **[Issue Form](../../issues/new/choose)** and complete all required fields in the template.

Before submitting, ensure you have verified the barrier on a clean profile against the corresponding upstream base browser (Mozilla Firefox or Google Chromium).

---

## 🔗 External References

WILB / WILBE has been referenced in:

- **FSF Directory:** [Free Software Directory: IceCat extensions (proposed)/Resources](https://directory.fsf.org/wiki/Free_Software_Directory:IceCat_extensions_\(proposed\)/Resources)
- **IRC:** `#icecat` channel on `irc.libera.chat`

---

## 🤝 Contributing

Help us document the state of the web for free software users! Please verify your issue against an upstream base browser on a clean profile before opening a report.
